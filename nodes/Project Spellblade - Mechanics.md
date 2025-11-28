---
tags:
  - "original"
context:
  - "[[Project Spellblade]]"
---

# Project Spellblade - Mechanics

The fundamental gameplay mechanics.

---

## Actions

**`Q`: Attack**: Melee swing. Instant hit at `0`.
**`W`: Dash**: Quick dash.
**`E`: Toggle**: Special mode toggle.

While Special is toggled:

**`Q`: Special1**
**`W`: Special2**
**`E`: Special3**

States:

- Free
- Dashing
- Stunned

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
