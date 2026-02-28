# Resolution & Scale


| Monitor | Scale | Result    |
| ------- | ----- | --------- |
| 720p    | x2    | 1280×720  |
| 1080p   | x3    | 1920×1080 |
| 1440p   | x4    | 2560×1440 |
| 4K      | x6    | 3840×2160 |

| 720p | 1280×720 |
| 1080p | 1920×1080 |
| 1440p | 2560×1440 |
| 4K | 3840×2160 |

# 3D to 2D Pipeline

## Context

This is a 2D isometric action RPG. Characters are viewed from an isometric camera angle with a 2:1 ratio. Because the game is 2D, characters need pre-rendered sprites for every direction they can face. The game uses 16 directions (22.5° increments) with approximately 16 frames per animation.
Rendering every direction and frame by hand for every character and equipment combination is not feasible. Instead, characters are modeled and animated once in 3D (Blender), then an automated render script outputs 2D spritesheets from all 16 directions.

## Equipment Slots

Characters are composed of layered sprite pieces, one per equipment slot:

- **Boots**: rigged to foot/ankle bones
- **Legs**: rigged to leg bones
- **Torso**: rigged to spine/arm bones
- **Helmet**: rigged to head bone
- **Weapon**: rigged to hand bone

Each slot can have multiple item variants (e.g. 5 different helmets). All variants for a slot are rigged to the same shared armature, so they animate identically.

A base body mesh is always present underneath, providing the humanoid silhouette when not fully covered by equipment.

## Blender Setup

1. One shared humanoid armature (skeleton) with all bones. All animations (idle, run, attack, dash, die, etc.) are defined on this armature.
2. Equipment meshes are separate objects, each rigged to the shared armature. Modeled to avoid clipping between slots.
3. Orthographic camera at ~30° elevation for the 2:1 isometric ratio, fixed distance from the model.

## Render Script

A Blender Python script automates spritesheet generation:
For each equipment mesh, for each animation:

- Hide all other meshes, enable only the target piece
- Set transparent background
- Rotate the camera around the model in 16 steps (22.5° each)
- At each direction, render every frame of the animation
- Pack into a spritesheet: rows = 16 directions, columns = N frames
- Output one image per piece per animation

All pieces are rendered from the same armature, same camera, same origin — so they align perfectly when stacked.

## Runtime

At runtime, the game draws 6 layers per character (body + 5 equipment slots) at the same screen position using the current animation frame and direction. Since all layers were rendered from the same 3D setup, they overlap correctly.
The weapon layer needs direction-dependent draw ordering: drawn in front of the body when the character faces the camera (south half), drawn behind when facing away (north half). This is a simple 16-entry lookup.
Equipment swapping is just changing which spritesheet is active for a given slot.

## Migration Steps

1. Set up Blender armature + one animation + one piece. Render and load in-game to validate end-to-end.
2. Implement multi-layer draw with body + weapon. Verify direction-dependent ordering.
3. Add remaining slots. Connect equipment selection to spritesheet indices.
4. Animate all animations, batch-render all spritesheets.
5. Remove old monolithic spritesheets.

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
