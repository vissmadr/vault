---
tags:
  - "original"
context:
  - "[[Project Spellblade]]"
---

# Project Spellblade - Mechanics

The fundamental gameplay mechanics.

---


# Latest Design

## Synergies

Earth shield from earth mode

Earth shield can be used offensively in fire mode (explode or something)

Passive effects (non-persistent; only in form)

Wind attackspeed increase attackspeed persistently during and after mode

Wind consider pull/push special

## Design

```
# Action Input Design

Goals and Constraints:

- Consistency!
- Emergent gameplay.
- Physical speed & ergonomics.
- No more than `3`-`5` action keys.
- Potential to enable player flow state.

## :hammer~1: 5 Keys 5 Abilities

`J`: Attack
`K`: Dash
`L`: Special
`I`: Spell 1
`O`: Spell 2

**Pros**:
Dumb-simple.
Single tap for everything.
Fits roguelike progression.

**Cons**:
Only `5` abilities.
Literally a Hades clone.
Increased physical keys count.

## :bloodlust: 3 Keys 5 Abilities

`J`: Attack
`K`: Dash

`LJ`: Spell 1
`LK`: Spell 2
`LL`: Spell 3

**Pros**:
Simple.
Least amount of keys.
Fits roguelike progression.

**Cons**:
Only `5` abilities.
Requires frequent double-taps.
Almost not worth compared to just `5` keys.

## :starfall: 4 Keys 7 Abilities

`J`: Attack
`K`: Dash
`L`: Special

`IJ`: Spell 1
`IK`: Spell 2
`IL`: Spell 3
`II`: Spell 4

**Pros**:
Unique.
More abilities.
Spammable special.
Fits roguelike progression.
Matches joystick key count.

**Cons**:
Requires frequent double-taps.

## :immolation: 4 Keys 4 Modes

`J`: Attack
`K`: Dash
`L`: Special

`IJ`: Mode 1
`IK`: Mode 2
`IL`: Mode 3
`II`: Mode 4

Modes augment the _Attack_, _Dash_, and _Special_ abilities while active.

Abilities sum up to `4 (modes) x 3 (abilities) = 12` possible augmentations.

Modes enable passive buffs and effects while active.

Augmented abilities can activate persistent effects (self-buffs and offensive-debuffs) for a duration or until consumption, even after the mode has been changed.

Persistent effects enable synergies between mode abilities.

**Pros**:
Unique.
Consistent.
Spammable abilities.
Matches joystick key count.

**Cons**:
Requires frequent double-taps.
Dependent on good art direction.
Doesn not fit roguelike progression.

## :stun: Consumption

`J`: Attack
`K`: Dash
`L`: Consume

Consumes magic from enemies/environment.

**Pros**:
Game-maker.
Unique mechanic.

**Cons**:
Replaces all other design.
Relies mainly on external factors.
Can become a nightmare for the artists.

## :arcane: Invoker Permutations

**Cons**:
Too slow.
Too complex.
Difficult to learn.
Requires triple taps.
```

---

## Actions

**`Q`: Attack**: Melee swing. Instant hit at `0`.
**`W`: Dash**: Quick dash.
**`E`: Toggle**: Special mode toggle.

While Special is toggled:

**`Q`: Special1**
**`W`: Special2**
**`E`: Special3**

## State Machine

- Free
- Dashing
- AttackSetup
- CastSetup

## Mechanics

Dash > Attack & Cast > Move

**Movement**
Instant 8-directional movement.
(Animation) Follows the movement.
Horizontal and vertical are linear.
Diagonal follows the isometric grid.

_Movement itself is instant. The animation is what makes the illusion._

**Attack**
Has a VERY small window before the hit.
(Animation) Single frame of setup, then the completed swing.

**DashAttack**
Single frame to Dash while in Attack setup.
Or Attack while Dash.

## Animations

Animations should only follow the logic.

States:

- Idling
- Running
- Dashing
- Attacking
- DashAttacking
- Casting
- Stunned

## Attack

1. Extremely short window of setup.

- During that short window, dashing will result in DashAttack.

2. Hitbox hits. Sword effect spawns around character. Animation plays the 'ending' part.
