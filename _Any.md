| scale | width | height |
| ----- | ----- | ------ |
| x1    | 640   | 360    |
| x2    | 1280  | 720    |
| x3    | 1920  | 1080   |
| x4    | 2560  | 1440   |
| x5    | 3200  | 1800   |
| x6    | 3840  | 2160   |

| Monitor | Scale | Result    |
| ------- | ----- | --------- |
| 720p    | x2    | 1280×720  |
| 1080p   | x3    | 1920×1080 |
| 1440p   | x4    | 2560×1440 |
| 4K      | x6    | 3840×2160 |

---

11:30 - 12:00 camera

# Auto Aim

Idea: `onPress` start the cast and WASD are for rotation in place. `onRelease` the projectile is released towards the facing direction.

---

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
