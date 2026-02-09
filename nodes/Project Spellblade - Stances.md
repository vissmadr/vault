---
tags:
  - "original"
context:
  - "[[Project Spellblade]]"
---

# Project Spellblade - Stances

Game design concerning the stances in the game.

---

| Stance | Resource | Type     | Use              | Feel      |
| ------ | -------- | -------- | ---------------- | --------- |
| Fire   | Heat     | analog   | passive & manual | ignite    |
| Storm  | Charge   | discrete | manual           | discharge |
| Earth  | Wisps    | discrete | passive & manual | release   |
| Chaos  | Entropy  | analog   | passive          | unleash   |

## Cast

### Chaos

"Distortion"

Upon stance activation:

- **Entry**: Ability that gets activated upon stance entry.
- **Effects**: Duration-based buffs that begin on stance entry and can expire.
- **Passives**: Persistent buffs that are active while the stance is active.

There can be slots that you put abilities/effects/passives in for each stance, or it can all be unlocked by talents/items. Or both?

---

---

---

---

---

## Fire

**Resource**: Heat

- Analog resource.
- Gained passively (continuous) while in other stances. Also gained when near Burning things.
- Spent passively in Fire stance, and also manually through casting Ignite.

**Cast**: Ignite

- Medium range in a cone.
- Channeling in the facing direction of the caster.
- Rapidly spend Heat to inflict damage and apply/refresh Burn.

### Problems

**Immolation**:

I like the Immolation aesthetic, but how does it work? Main ideas:

- A: Constant immolation while in Fire stance, explaining why the Heat gets drained constantly.
- B: Immolate yourself for a short duration as a result after using Ignite.

---

## Storm

**Resource**: Charge

- Discrete resource.
- Gained by movement actions in all stances, such as moving, dashing, and attacking.
- Spent manually in Storm stance by using Discharge.

**Cast**: Discharge

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

- Discrete resource.
- Gained passively (ticks) while in Earth stance, up to a maximum.
- Each Wisp provides health regen and protection.
- Wisps intercept incoming damage, acting as a shield.

**Cast**: Release

### Problems

**Release**:

Figure out what the Release mechanic is.

- A: Offensive approach where wisps are detonated.
- B: Wisps are placed on the ground, where they remain giving bonuses to the caster, and act as traps/mines when touched by an enemy.

---

## Chaos

**Resource**: Order & Entropy

- Analog resource and based on current state.

**Cast**: Unleash

### Problems
