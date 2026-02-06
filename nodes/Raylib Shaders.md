---
context:
  - "[[Raylib]]"
  - "[[Shader]]"
---

# Raylib Shaders

Shaders in Raylib, and how to work with them.

---

```
┌─────────────────────────────────────────────────────────────┐
│                      beginDrawing()                         │
│                                                             │
│   ┌─────────────────────────────────────────────────────┐   │
│   │                 beginMode2D(camera)                 │   │
│   │                                                     │   │
│   │   ┌─────────────────────────────────────────────┐   │   │
│   │   │          beginShaderMode(shader)            │   │   │
│   │   │                                             │   │   │
│   │   │   drawTexture(...)  ← uses YOUR shader      │   │   │
│   │   │   drawRectangle(...) ← uses YOUR shader     │   │   │
│   │   │                                             │   │   │
│   │   │          endShaderMode()                    │   │   │
│   │   └─────────────────────────────────────────────┘   │   │
│   │                                                     │   │
│   │   drawTexture(...)  ← uses DEFAULT shader           │   │
│   │                                                     │   │
│   │                 endMode2D()                         │   │
│   └─────────────────────────────────────────────────────┘   │
│                                                             │
│   drawText(...)  ← uses DEFAULT shader (screen space)       │
│                                                             │
│                       endDrawing()                          │
└─────────────────────────────────────────────────────────────┘
```

## Predefined Uniforms

Raylib has predefined uniform locations you can use.

Some useful uniforms provided by Raylib for 2D fragment shaders:

```glsl
// Automatically bound textures
uniform sampler2D texture0;     // The texture being drawn

// Automatically set colors
uniform vec4 colDiffuse;        // Tint color from draw call

// Inputs from vertex shader
in vec2 fragTexCoord;           // UV coordinates (0-1) for current fragment
in vec4 fragColor;              // Per-vertex color attribute
```

## Data Types

The data types you can pass:

| GLSL Type   | Zig Type    | Enum                          |
| ----------- | ----------- | ----------------------------- |
| `float`     | `f32`       | `.float`                      |
| `vec2`      | `[2]f32`    | `.vec2`                       |
| `vec3`      | `[3]f32`    | `.vec3`                       |
| `vec4`      | `[4]f32`    | `.vec4`                       |
| `int`       | `i32`       | `.int`                        |
| `ivec2`     | `[2]i32`    | `.ivec2`                      |
| `sampler2D` | `Texture2D` | (use `setShaderValueTexture`) |
