---
tags:
  - "original"
context:
  - "[[Project Spellblade]]"
---

# Project Spellblade - Stats

The stats system of the game.

---

## Concepts

**Attributes**: Values that describe the overall quantity/power/balance of the character.
Examples: `maxHealth`, `attackDamage`, `modelSize`, `hitboxRadius`, `dashCooldown`, `movespeed`.

**Unlocks**: Decides whether certain conditional gameplay capabilities are enabled or disabled.
Examples: `sprint`, `immolationAura`, `shockOnHit`, `secondChance`, `enrageWhenDamaged`.

**State**: Storage for runtime state that needs to be constantly updated or queried.
Examples: `currentHealth`, `position`, `isMoving`, `animatorState`, `isBurning`, `isStunned`.

**Effects**: Temporary runtime effects with duration, meant to temporarily affect the other components.
Examples: `movespeed_flat`, `movespeed_scale`, `burn_time` `burn_flat`, `immolationAura_unlock`.

**Session**: Single game run from start to finish.

**Session Entry**: All the prerequisite data the Session has started with.
Examples: `playerAttributesAccumulator`, `playerUnlocks`, `worldMods`.

**Session Data**: Stores data for the current session.
Examples: `timeElapsed`, `totalDamageTaken`, `totalKills`, `goldCollected`, `abilitiesUsed`.

**Storage**: 

**Map**: 



## Components

The game's stats concerning characters is separated into different components.

## Layers

The components can broadly be organized into three layers.

### Data Layer

Preset data coming from the game design balancing as well as persistent storage.

**Base Attributes**: The default _Attributes_ of the character.
**Storage**:
**Map**:
**Base Unlocks**:

### Session Layer

**Items**:
**Talents**:
**World Mods**:

**Session**:

### Dynamic Layer

**Attributes**:
**Session Data**:
**Unlocks**:
**State**:
**Effects**:
