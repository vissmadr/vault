---
tags:
  - "original"
context:
  - "[[Project Spellblade]]"
---

# Project Spellblade - Stats

The architecture for player Attributes, Skills, State, and Effects.

---

## Overview

The system uses a **layered accumulator pattern** where modifiers from multiple sources are collected, merged, and applied in a mathematically correct order (flats before scales).

```
Pre-Run Layer (persistent, predefined)
    |
Run Layer (immutable during run)
    |
Runtime Layer (computed each frame)
```

---

## Core Concepts

### Attributes

Numeric parameters that define character capabilities.

Examples: `maxHealth`, `movespeed`, `attackDamage`, `dashCooldown`.

### Skills

Boolean capability flags that enable behaviors or grant passive bonuses.

Examples: `sprint`, `vitality`, `fury`, `immolationAura`.

### State

Runtime mutable data/cache that needs to be remembered or queried.

- **Stored**: `position`, `health`, `comboStep`, `isSprinting`
- **Derived**: `isStunned`, `isBurning` (derived from Effects accumulator)

### Effects

Temporary timed modifiers with duration. Auto-expire when their clock reaches zero.

Examples: `stun (4s)`, `burn (3s)`, `speed potion (10s)`, `enrage buff (5s)`.

### Accumulators

Each source has its own Accumulator type containing only the fields it can modify. This makes it explicit what each source can affect.

```zig
// RunEntry.Accumulator - from Items, Talents, Map
const Accumulator = struct {
    maxHealth_flat: f32 = 0,
    maxHealth_scale: f32 = 0,
    // ... only fields Items/Talents/Map can modify
};

// Effects.Accumulator - from timed effects
const Accumulator = struct {
    moveSpeed_flat: f32 = 0,
    moveSpeed_scale: f32 = 0,
    stun_time: f32 = 0,
    burn_time: f32 = 0,
    // ... only fields Effects can modify
};

// Skills.Accumulator - from active skills
const Accumulator = struct {
    maxHealth_flat: f32 = 0,
    moveSpeed_scale: f32 = 0,
    attackDamage_scale: f32 = 0,
    // ... only fields Skills can modify
};

// RunState.Accumulator - from run state (kills, time, etc.)
const Accumulator = struct {
    attackDamage_scale: f32 = 0,
    // ... only fields RunState can modify
};
```

To find what can modify a specific attribute, check the `Attributes.apply` function.

### SkillsModifier

Collects skill grants and revokes from a source. Revokes take priority over grants.

```zig
const SkillsModifier = struct {
    granted: ActiveSet,
    revoked: ActiveSet,
};
```

---

## Data Layers

### Pre-Run (Persistent)

Data that exists before any run begins:

| Data            | Description                           |
| --------------- | ------------------------------------- |
| Base Attributes | Default attributes per character type |
| Base Skills     | Default skills per character type     |
| Items           | Unlocked items (player progression)   |
| Talents         | Unlocked talents (player progression) |
| Map             | Selected map and its modifiers        |

### Run Start (Immutable During Run)

Calculated once when a run begins:

```
Run Entry = accumulate(Items, Talents, Map)
    -> attributesAccumulator
    -> skillsModifier { granted, revoked }

Run Attributes = Attributes.apply(BaseAttributes, RunEntry.attributesAccumulator)
Run Skills = (BaseSkills | RunEntry.granted) & ~RunEntry.revoked
```

These remain constant for the entire run.

### Runtime (Each Frame)

Computed every frame during gameplay:

| Data              | Description                                |
| ----------------- | ------------------------------------------ |
| Effects           | Ticked, expired removed, accumulated       |
| Run State         | Updated (kills, time elapsed, items found) |
| Player Skills     | Computed from Run + Effects + RunState     |
| Player Attributes | Computed from all accumulators             |
| State             | Flags derived from Effects accumulator     |

---

## Runtime Calculation Order

Each frame, the following steps execute in order:

```
1. Effects.updateClocks()
   -> Tick all effect timers
   -> Remove expired effects

2. effectsAccumulator = Effects.accumulate()
   -> Collect all effect modifiers into Effects.Accumulator

3. State.deriveFlags(effectsAccumulator)
   -> isStunned = (effectsAccumulator.stun_time > 0)
   -> isBurning = (effectsAccumulator.burn_time > 0)

4. Compute Player Skills:
   allGranted = Effects.skillsModifier.granted | RunState.skillsModifier.granted
   allRevoked = Effects.skillsModifier.revoked | RunState.skillsModifier.revoked
   PlayerSkills = (RunSkills | allGranted) & ~allRevoked

5. Gather Accumulators (each source has its own type):
   - runEntryAccumulator: RunEntry.Accumulator (stored at run start)
   - effectsAccumulator: Effects.Accumulator (from step 2)
   - skillsAccumulator: Skills.accumulateAttributes(playerSkills, state)
   - runStateAccumulator: RunState.getAccumulator()

6. PlayerAttributes = Attributes.apply(
       RunAttributes,
       runEntryAccumulator,
       effectsAccumulator,
       skillsAccumulator,
       runStateAccumulator
   )
```

---

## Math Order

The accumulator pattern enforces **flats before scales**. The `apply` function takes all source accumulators directly for performance and explicitness:

```zig
pub fn apply(
    base: Attributes,
    runEntry: RunEntry.Accumulator,
    effects: Effects.Accumulator,
    skills: Skills.Accumulator,
    runState: RunState.Accumulator,
) Attributes {
    var result = base;

    // --- 1. All flats first ---
    result.maxHealth += runEntry.maxHealth_flat + skills.maxHealth_flat;
    result.movespeed += runEntry.moveSpeed_flat + effects.moveSpeed_flat;
    result.movespeed -= effects.moveSlow_flat;

    // --- 2. Then all scales (additive stacking) ---
    result.maxHealth *= (1.0 + runEntry.maxHealth_scale);
    result.movespeed *= (1.0 + runEntry.moveSpeed_scale + effects.moveSpeed_scale + skills.moveSpeed_scale);
    result.movespeed *= (1.0 - effects.moveSlow_scale);
    result.attackDamage *= (1.0 + skills.attackDamage_scale + runState.attackDamage_scale);

    return result;
}
```

This function is the single source of truth for what each source can modify. No intermediate merging required.

---

## Effects

Effects are temporary modifiers with a clock that auto-expires.

### Structure

```zig
const Effect = struct {
    type: EffectType,
    clock: f32,       // remaining duration
    magnitude: f32,   // effect strength
};
```

### Outputs

Effects produce two outputs when accumulated:

1. **Accumulator** - Attribute modifiers + state-derivable values (`stun_time`, `burn_time`)
2. **SkillsModifier** - Skills temporarily granted or revoked

### Removal

- **99% case**: Automatic expiry when `clock <= 0`
- **1% case**: Manual removal via cleanse/dispel abilities

---

## Skills

Skills are boolean flags that enable capabilities or grant bonuses.

### Types

1. **Passive bonuses** - Always apply when skill is active
   - Example: Vitality grants +25 max health

2. **Capability flags** - Enable behaviors
   - Example: Sprint enables the ability to sprint

3. **Conditional bonuses** - Apply when skill is active AND state condition is met
   - Example: Sprint grants +30% speed when `state.isSprinting`

### Accumulation

Skills contribute to attributes via `accumulateAttributes`, returning a `Skills.Accumulator`:

```zig
fn accumulateAttributes(skills: ActiveSet, state: State) Skills.Accumulator {
    var accumulator: Skills.Accumulator = .{};

    if (skills.vitality) {
        accumulator.maxHealth_flat += 25.0;
    }

    if (skills.sprint and state.isSprinting) {
        accumulator.moveSpeed_scale += 0.30;
    }

    return accumulator;
}
```

Conditional checks against State happen here to ensure modifiers participate in correct math order.

---

## Skills Grant/Revoke

Skills can be granted or revoked by multiple sources:

```
Final Skills = (RunSkills | allGranted) & ~allRevoked
```

Revoke takes priority. If a skill is both granted and revoked, it is revoked.

### Sources

| Source                          | Can Grant | Can Revoke |
| ------------------------------- | --------- | ---------- |
| Run Entry (Items, Talents, Map) | Yes       | Yes        |
| Effects                         | Yes       | Yes        |
| Run State                       | Yes       | Yes        |

---

## Run State

Runtime data for the current run that can influence Attributes and Skills.

### Examples

- `timeElapsed` - "Damage increases every minute"
- `totalKills` - "Enrage: +1% damage per kill"
- `itemsFound` - "Finding 5 relics unlocks X skill"

### Outputs

```zig
fn getAccumulator() RunState.Accumulator {
    return .{
        .attackDamage_scale = @as(f32, Data.totalKills) * 0.01,
    };
}

fn getSkillsModifier() SkillsModifier {
    return .{
        .granted = .{ .secretAbility = (Data.relicsFound >= 5) },
        .revoked = .{},
    };
}
```

---

## Entity Scope

| Component           | Player | Enemies               |
| ------------------- | ------ | --------------------- |
| Base Attributes     | Yes    | Yes (separate struct) |
| Base Skills         | Yes    | Yes (separate struct) |
| Run Entry           | Yes    | No                    |
| Map Modifiers       | Yes    | Yes                   |
| Effects             | Yes    | Yes                   |
| State               | Yes    | Yes (separate struct) |
| Run State influence | Yes    | Yes                   |

Enemies use a similar but separate system. No code sharing required between player and enemy Attribute/Skill structs.

---

## Diagram

```
+---------------------------------------------------------------------+
|                        PRE-RUN (Persistent)                         |
+---------------------------------------------------------------------+
|  Base Attributes    Base Skills    Items    Talents    Map          |
+---------------------------------------------------------------------+
                                |
                  +-------------v-------------+
                  |   Run Entry Calculation   |
                  |   (Items + Talents + Map) |
                  +-------------+-------------+
                                |
                                v
+---------------------------------------------------------------------+
|                   RUN START (Immutable during run)                  |
+---------------------------------------------------------------------+
|  Run Attributes = Base + RunEntry.attributesAccumulator             |
|  Run Skills     = (Base | RunEntry.granted) & ~RunEntry.revoked     |
+---------------------------------------------------------------------+
                                |
                                v
+---------------------------------------------------------------------+
|                       RUNTIME (Each frame)                          |
+---------------------------------------------------------------------+
|  1. Tick Effects (decrement timers, remove expired)                 |
|  2. Accumulate Effects -> Effects.Accumulator                       |
|  3. Derive State flags from Effects.Accumulator                     |
|  4. Compute Player Skills (Run | Effects | RunState, minus revoked) |
|  5. Gather Accumulators (each source has its own type):             |
|     - RunEntry.Accumulator                                          |
|     - Effects.Accumulator                                           |
|     - Skills.Accumulator                                            |
|     - RunState.Accumulator                                          |
|  6. Attributes.apply(base, runEntry, effects, skills, runState)     |
|     -> Player Attributes                                            |
+---------------------------------------------------------------------+
```
