---
context:
  - "[[Game Design]]"
---

# Lessons from Hades

Lessons learned from Hades.

---

## Mechanics

**Movement**
Instant 8-directional movement.
Horizontal and vertical are linear.
Diagonal follows the isometric grid.
Doesn't have any speedup or slowdown.

(Animation) Follows the movement.

(Animation) Rotating 180° plays a single frame of normal (idle?) direction between the two.
For example 180° from West to East plays a frame of South facing, and then East stopping animation.

_Movement itself is instant. The *stopping* animation is what makes the illusion._

**Attack**
Has an extremely small (1 frame) window of setup before the hit.
(Animation) Single frame of setup, then the completed swing.

_The hit swing happens almost instantly, and the *post-swing* animation follows afterwards._

**DashAttack**
Single frame to Dash while in Attack setup.
Or Attack while Dash.

**Cast**
Can dash while casting at any time, not preventing the cast.
Very early attack overwrites the cast.
Late attack waits for the cast to complete.

_Protip: This means that a DashAttack is better when casting because it always works instantly without the delay of the cast._
