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

**Attributes**: Values that describe the overall parameters of the character.
Examples: `maxHealth`, `attackDamage`, `modelSize`, `hitboxRadius`, `dashCooldown`, `movespeed`.

**Base Attributes**: Default preset _Attributes_ for each character.

**Unlocks**: Gated conditional gameplay capabilities flags.
Examples: `sprint`, `immolationAura`, `shockOnHit`, `secondChance`, `enrageWhenDamaged`.

**Base Unlocks**: Default preset _Unlocks_ for each character.

**State**: Storage for runtime state that needs to be constantly updated or queried.
Examples: `currentHealth`, `position`, `isMoving`, `animatorState`, `isBurning`, `isStunned`.

**Effects**: Temporary runtime effects with duration, meant to temporarily affect the other components.
Examples: `movespeed_flat`, `movespeed_scale`, `burn_time` `burn_flat`, `immolationAura_unlock`.

**Run**: Single game run from start to finish.

**Run Entry**: The prerequisite data the current _Run_ has started with.
Examples: `playerAttributesAccumulator`, `playerUnlocks`, `worldMods`.

**Run State**: Stores runtime state data for the current _Run_.
Examples: `timeElapsed`, `totalDamageTaken`, `totalKills`, `goldCollected`, `abilitiesUsed`.

**Storage**: Persistent storage for off-_Run_ data and player progression, such as _Items_ and _Talents_.

**Items**: Table of items unlocked by the player.

**Talents**: Table of talents unlocked by the player.

**Map**: Stores the data of different maps.

## Connections

Values that are already set before the _Session_ has even started:

- The player's _Base Attributes_ and _Base Unlocks_.
- The _Session Entry_, consisting of the _Map_ data, as well as the player's equipped _Items_ and unlocked _Talents_, both coming from the _Storage_.

When the session begins, the _Session Entry_ needs to be calculated. It accumulates all of the stats coming from _Items_, _Talents_, _Map_, #wip

The _Session Entry_ accumulates all of its player _Attributes_ into an accumulator, as well as all of the _Unlocks_.
