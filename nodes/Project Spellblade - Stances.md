---
tags:
  - "original"
context:
  - "[[Project Spellblade]]"
---

# Project Spellblade - Stances

Game design concerning the stances in the game.

---

## Fire

**Resource**: Heat

- Analog resource.
- Gained passively (continuous) while in other stances. Also gained when near Burning things.
- Spent passively in Fire stance, and also manually through casting Ignite.

**Cast**: Ignite

_Aesthetic: Continuous flames out of the caster._

- Medium range in a cone.
- Channeling in the facing direction of the caster.
- Rapidly spend Heat to inflict damage and apply/refresh Burn.

### Problems

**Immolation**

_Engulfing yourself in fire to continuously damage nearby enemies._

I like the Immolation aesthetic/mechanic, but how can it be implemented? Main ideas:

- A: Permanent (weaker) immolation while in Fire stance, explaining why the Heat gets drained constantly.
- B: Immolation activates for a short duration as a result after using Ignite.

---

## Storm

**Resource**: Charge

- Discrete resource.
- Gained by movement actions in all stances, such as moving, dashing, and attacking.
- Spent manually in Storm stance by using Discharge.

**Cast**: Discharge

_Aesthetic: Chain lightning._

- Close range attack ability.
- Instant cast and hit.

### Problems

**After Discharge**:

Due to the instant nature of the cast, figure out what to do after Discharge.

Otherwise it will be: `Enter Storm → Discharge → Leave Storm`, all happening in less than a second.

One idea is to activate a buff (Overload) after Discharge, with strength depending on how much Charge was Discharged.

---

## Earth

**Resource**: Wisps

_Aesthetic: Small lights that orbit around you._

- Discrete resource.
- Gained passively (ticks) while in Earth stance, up to a maximum.
- Each Wisp provides health regen and protection.
- Wisps intercept incoming damage, acting as a shield.

**Cast**: Release

### Problems

**Undecided Release**:

Figure out what the Release mechanic is.

- A: Offensive approach where wisps are detonated.
- B: Wisps are placed on the ground, where they remain giving bonuses to the caster, and act as traps/mines when touched by an enemy.

---

## Chaos

**Resource**: Order & Entropy

- Analog resource and based on current state.
- Gained passively (continuous) while in other stances.
- Drained automatically while in Chaos stance.
- Entropy level depends on how much Order is left.

**Cast**: Unleash

_Aesthetic: Swarm of seeker missile projectiles. Similar to the visuals of Icathian Rain (LoL) and Prismatic Bolt (Torchlight 2)._

- Long range but random.
- Channeling to release bolts at random directions/targets.
- Power based on current Entropy level.
