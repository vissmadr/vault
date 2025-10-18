---
context:
  - "[[Raylib]]"
---

# Raylib Camera

The camera system in Raylib is an abstraction for controlling how a 2D or 3D world is viewed.

---

The camera defines a transformation from world space to screen space.

- **`target`**: The focus point in the world.
- **`offset`**: How the `target` maps to the screen.
- **`rotation`**: Rotates the entire view around `target`.
- **`zoom`**: Scales the view.

Main functions:

- **`BeginMode2D`**: Activates the transformation. All drawing commands afterward are transformed.
- **`EndMode2D`**: Restores normal (screen-space) drawing.

```zig
pub const Camera2D = extern struct {
    offset: Vector2,
    target: Vector2,
    rotation: f32,
    zoom: f32,

    /// Begin 2D mode with camera
    pub fn begin(self: Camera2D) void {
        rl.beginMode2D(self);
    }

    /// Get camera 2d transform matrix
    pub fn getMatrix(self: Camera2D) Matrix {
        return rl.getCameraMatrix2D(self);
    }

    /// Ends 2D mode with camera
    pub fn end(_: Camera2D) void {
        rl.endMode2D();
    }
};
```
