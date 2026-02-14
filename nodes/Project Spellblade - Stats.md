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

**Base Attributes**: Default preset _Attributes_ for each character.

**Unlocks**: Decides whether certain conditional gameplay capabilities are enabled or disabled.
Examples: `sprint`, `immolationAura`, `shockOnHit`, `secondChance`, `enrageWhenDamaged`.

**Base Unlocks**: Default preset _Unlocks_ for each character.

**State**: Storage for runtime state that needs to be constantly updated or queried.
Examples: `currentHealth`, `position`, `isMoving`, `animatorState`, `isBurning`, `isStunned`.

**Effects**: Temporary runtime effects with duration, meant to temporarily affect the other components.
Examples: `movespeed_flat`, `movespeed_scale`, `burn_time` `burn_flat`, `immolationAura_unlock`.

**Session**: Single game run from start to finish.

**Session Entry**: The prerequisite data the current _Session_ has started with.
Examples: `playerAttributesAccumulator`, `playerUnlocks`, `worldMods`.

**Session Data**: Stores runtime data for the current session.
Examples: `timeElapsed`, `totalDamageTaken`, `totalKills`, `goldCollected`, `abilitiesUsed`.

**Storage**: Persistent storage for off-session data and player progression, such as _Items_ and _Talents_.

**Items**: Table of items unlocked by the player.

**Talents**: Table of talents unlocked by the player.

**Map**: Stores the data of different maps.

## Connections

Values that are already set before the _Session_ has even started:

- The player's _Base Attributes_ and _Base Unlocks_.
- The _Session Entry_, consisting of the _Map_ data, as well as the player's equipped _Items_ and unlocked _Talents_, both coming from the _Storage_.
