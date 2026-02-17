
Summary
New Files Created
src/player/skills/
    set.zig       # Boolean flags (what's enabled)
    state.zig     # Skill runtime state (stacks, cooldowns)
    contexts.zig  # Context structs (OnAttack, OnDamaged, OnKill)
    flags.zig     # Frame-local flags (handler→game communication)
    handlers.zig  # Skill logic implementations
    triggers.zig  # Trigger functions + getAttributeModifiers()
Key Changes
1. Skills.Set - Pure boolean table, removed vitality
2. Vitality - Now a direct attribute bonus in Talents.getAttributesAccumulator()
3. Triggers.onAttack() - Centralized trigger called from combat code
4. Triggers.getAttributeModifiers() - Computes conditional bonuses (sprint, fury)
5. Handlers - Skill logic moved from actions.zig to dedicated handlers
Example Skills After Refactor
| Skill | Type | Implementation |
|-------|------|----------------|
| vitality | Pure Attribute | Talents.getAttributesAccumulator() adds +25 health |
| chaosStanceProjectiles | Pure Behavior | Handlers.chaosStanceProjectiles() spawns projectiles |
| sprint | Hybrid | Set flag + getAttributeModifiers() for speed bonus |
| fury | Hybrid | Set flag + getAttributeModifiers() for damage bonus |
Architecture
Game Event (attack, kill, etc.)
    │
    ▼
Skills.Triggers.onX(skills, context)
    │
    ▼
Skills.Handlers (do stuff, update Skills.State)
    │
    ▼
Skills.Triggers.getAttributeModifiers(skills, state)
    │
    ▼
Attributes.apply(..., skillModifiers, ...)
# Skills architecture design
▣  Build · claude-opus-4-5 · 6m 41s

---

Modifiers Skills patch.

Not using flags and stuff, instead getting them from one place.

---

**Attributes**: 

```
┌─────────────────────────────────────────────────────────┐
│ SPAWN (once)                                            │
│                                                         │
│   sessionAccumulator = Items + Talents + World          │
│   (cached, immutable)                                   │
└─────────────────────────────────────────────────────────┘
┌─────────────────────────────────────────────────────────┐
│ RUNTIME (per-frame)                                     │
│                                                         │
│   dynamicAccumulator = Effects + Skills                 │
│                                                         │
│   frameAttributes = apply(                              │
│       presetAttributes,                                 │
│       sessionAccumulator,                               │
│       dynamicAccumulator                                │
│   )                                                     │
└─────────────────────────────────────────────────────────┘
```

# Design

Think about roguelike progression still, with the skills just as in-run stuff.

---

**Stances**:

- Cooldown: On entry effect
- Free:

# Wisp Rendering

Yes, this is absolutely doable in 2D isometric! The key is understanding the isometric depth/draw order.
How Isometric Depth Works
In your isometric setup, objects are drawn back-to-front based on their world position. Looking at your transform:

```zig
// From grid/transform.zig
fn toIsometric_v2(vector: Vector2) Vector2 {
    return .init(
            (vector.x - vector.y),          // screen X
            ((vector.x + vector.y) / 2.0),  // screen Y
        );
}
```

The screen Y `((x + y) / 2)` determines depth - higher values are "in front" and should be drawn later.
Wisp Orbit Solution
For wisps orbiting the player:

1. Calculate wisp world positions - orbit around player in world-space (not screen-space)
2. Compare depth - a wisp is "behind" the player when its world `(x + y)` is less than the player's `(x + y)`
3. Draw in two passes:
   - First pass: draw wisps that are behind the player
   - Draw player
   - Second pass: draw wisps that are in front of the player

# Torchlight 2 Ideas

ITEM ENCHANCEMENTS!

FIREBOMBS!
