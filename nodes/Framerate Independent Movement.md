---
context:
  - "[[Game Development]]"
  - "[[Delta Time]]"
---

# Framerate Independent Movement

Creating velocity-based movement that depends on time instead of framerate.

---

Example data:

```zig
const Movement = struct {
    velocity: Vector2,
    maxVelocity: f32,
    acceleration: f32,
    deceleration: f32,
};
```

## Pure Numbers

These represent real physical speeds.

They stay constant regardless of framerate.

They do not scale with `deltaTime`.

**`velocity`**: This is the actual current movement speed. Meaured in _units per second_.

**`maxVelocity`**: This is the maximum allowed speed. Measured in _units per second_.

## Per-second Quantities

These define how velocity changes over time.

**`acceleration`**: Velocity increases by this amount each second. Measured in _units per second²_.

**`deceleration`**: Velocity decreases by this amount each second. Measured in _units per second²_.

Both of these must be multiplied by `deltaTime` to convert them into per-frame changes.

## Position

Velocity is _units per second_.

Position is _units_

To update position, you integrate velocity over time: `position += velocity * deltaTime`

Fundamental rules:

- `velocity` uses `deltaTime` only when applied to `position`.
- `acceleration`/`deceleration` uses `deltaTime` only when applied to `velocity`.
- `maxVelocity` is never multiplied by `deltaTime`.
