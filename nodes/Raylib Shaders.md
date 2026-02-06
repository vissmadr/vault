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

When you write a fragment shader, Raylib's default vertex shader provides:

```glsl
#version 330

// These come from Raylib's vertex shader (always available)
in vec2 fragTexCoord;   // UV coordinates (0-1)
in vec4 fragColor;      // Vertex color (usually white)

// These are set by Raylib automatically
uniform sampler2D texture0;  // The texture being drawn
uniform vec4 colDiffuse;     // Tint color passed to draw function

// Your output
out vec4 finalColor;

void main() {
    vec4 texel = texture(texture0, fragTexCoord);
    finalColor = texel * colDiffuse * fragColor;  // Default behavior
}
```

Raylib has predefined uniform locations you can use:

```zig
pub const ShaderLocationIndex = enum(c_int) {
    vertex_position = 0,
    vertex_texcoord01 = 1,
    vertex_texcoord02 = 2,
    vertex_normal = 3,
    vertex_tangent = 4,
    vertex_color = 5,
    matrix_mvp = 6,
    matrix_view = 7,
    matrix_projection = 8,
    matrix_model = 9,
    matrix_normal = 10,
    vector_view = 11,
    color_diffuse = 12,
    color_specular = 13,
    color_ambient = 14,
    map_albedo = 15,
    map_metalness = 16,
    map_normal = 17,
    map_roughness = 18,
    map_occlusion = 19,
    map_emission = 20,
    map_height = 21,
    map_cubemap = 22,
    map_irradiance = 23,
    map_prefilter = 24,
    map_brdf = 25,
    vertex_boneids = 26,
    vertex_boneweights = 27,
    bone_matrices = 28,
    shader_loc_vertex_instance_tx = 29,
    //
};
```

Types You Can Pass:

| GLSL Type   | Zig Type    | Enum                          |
| ----------- | ----------- | ----------------------------- |
| `float`     | `f32`       | `.float`                      |
| `vec2`      | `[2]f32`    | `.vec2`                       |
| `vec3`      | `[3]f32`    | `.vec3`                       |
| `vec4`      | `[4]f32`    | `.vec4`                       |
| `int`       | `i32`       | `.int`                        |
| `ivec2`     | `[2]i32`    | `.ivec2`                      |
| `sampler2D` | `Texture2D` | (use `setShaderValueTexture`) |
