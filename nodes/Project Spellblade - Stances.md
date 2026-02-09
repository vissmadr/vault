---
tags:
  - "original"
context:
  - "[[Project Spellblade]]"
---

# Project Spellblade - Stances

Game design concerning the stances in the game, and their overall gameplay.

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

**Undecided Cast**:

Figure out what the Earth Cast is.

- A (Detonate Stun): Offensive approach where wisps are detonated for a short AOE stun. This way you can use Wisps aggressively to extend a combo, or defensively to stun attackes while you escape.
- B (Detonate Heal): Defensive approach where wisps are detonated for an instant heal. This way you can save yourself from a clutch situation, but lose the passive regeneration of the wisp.
- C (Place on Ground): Wisps are placed on the ground, where they remain giving bonuses to the caster, and act as traps/mines when touched by an enemy.

Idea: Placing wisps on the ground, changing their element with an attack.

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
