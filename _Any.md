# Shader Guide for Raylib/Zig Games

Since you have WebGL experience, I'll focus on **what's different** in a game context vs full-canvas WebGL.

---

## The Key Difference: WebGL Canvas vs Game Rendering

In WebGL, you typically:

- Have one canvas
- Clear it, draw everything with shaders
- Everything goes through your shader pipeline

In Raylib (and most game engines):

- Raylib has a **default shader** that handles all drawing
- You **selectively override** the shader for specific draw calls
- Most things render with the default shader (fast, optimized)

---

## The Raylib Rendering Pipeline

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

**Key insight**: `beginShaderMode(shader)` replaces the default shader for all subsequent draw calls until `endShaderMode()`.

---

## How to Target Different Things

### 1. Single Sprite (Character, Projectile, etc.)

Wrap the draw call in shader mode:

```zig
fn renderEnemy(enemy: *Enemy) void {
    // Set uniforms specific to this enemy
    Raylib.setShaderValue(poisonShader, healthLoc, &enemy.health, .float);

    {
        Raylib.beginShaderMode(poisonShader);
        defer Raylib.endShaderMode();

        enemy.texture.draw(enemy.x, enemy.y, .white);
    }

    // Other enemies drawn normally after this
}
```

### 2. Group of Sprites (All Enemies, All Projectiles)

Wrap the entire render loop:

```zig
fn renderAllEnemies() void {
    Raylib.beginShaderMode(enemyShader);
    defer Raylib.endShaderMode();

    for (enemies) |enemy| {
        // All enemies use the same shader
        enemy.texture.draw(enemy.x, enemy.y, .white);
    }
}
```

### 3. UI Elements

Same pattern, but **outside** camera mode (screen space):

```zig
fn render() void {
    Raylib.beginDrawing();
    defer Raylib.endDrawing();

    // World space (affected by camera)
    {
        Camera.begin();
        defer Camera.end();

        renderWorld();
        renderEnemies();
        renderPlayer();
    }

    // Screen space (UI) - after camera ends
    {
        Raylib.beginShaderMode(uiGlowShader);
        defer Raylib.endShaderMode();

        drawHealthBar();
        drawAbilityIcons();
    }
}
```

### 4. Full Screen Post-Processing (Bloom, Color Grading, CRT Effect)

This is where **RenderTexture** comes in - similar to WebGL's framebuffer:

```zig
const Data = struct {
    var target: Raylib.RenderTexture2D = undefined;
};

fn init() void {
    Data.target = Raylib.loadRenderTexture(screenWidth, screenHeight) catch unreachable;
}

fn render() void {
    // Pass 1: Render entire scene to texture
    {
        Raylib.beginTextureMode(Data.target);
        defer Raylib.endTextureMode();

        Raylib.clearBackground(.black);

        // Render everything normally
        Camera.begin();
        renderWorld();
        renderEnemies();
        renderPlayer();
        Camera.end();
    }

    // Pass 2: Draw texture to screen with post-process shader
    {
        Raylib.beginDrawing();
        defer Raylib.endDrawing();

        Raylib.beginShaderMode(bloomShader);
        defer Raylib.endShaderMode();

        // Draw the render texture (note: Y is flipped in OpenGL)
        Raylib.drawTextureRec(
            Data.target.texture,
            .{
                .x = 0,
                .y = 0,
                .width = @floatFromInt(Data.target.texture.width),
                .height = -@floatFromInt(Data.target.texture.height), // Flip Y
            },
            .{ .x = 0, .y = 0 },
            .white,
        );

        // UI drawn AFTER post-process (not affected by bloom)
        renderUI();
    }
}
```

### 5. Multiple Render Passes (Advanced Effects)

For complex effects like blur, you need multiple passes:

```zig
// Bloom example: 3 passes
fn renderWithBloom() void {
    // Pass 1: Render scene
    Raylib.beginTextureMode(sceneTarget);
    renderScene();
    Raylib.endTextureMode();

    // Pass 2: Extract bright pixels + horizontal blur
    Raylib.beginTextureMode(blurTarget1);
    Raylib.beginShaderMode(brightExtractShader);
    drawFullscreenQuad(sceneTarget.texture);
    Raylib.endShaderMode();
    Raylib.endTextureMode();

    // Pass 3: Vertical blur
    Raylib.beginTextureMode(blurTarget2);
    Raylib.beginShaderMode(verticalBlurShader);
    drawFullscreenQuad(blurTarget1.texture);
    Raylib.endShaderMode();
    Raylib.endTextureMode();

    // Final: Composite scene + blur
    Raylib.beginDrawing();
    Raylib.beginShaderMode(compositeShader);
    // Bind both textures and blend them
    Raylib.endShaderMode();
    Raylib.endDrawing();
}
```

---

## GLSL Inputs: What Raylib Provides Automatically

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

### Available Shader Locations (built-in uniforms)

Raylib has predefined uniform locations you can use:

```zig
const ShaderLocationIndex = enum {
    vertex_position,
    vertex_texcoord01,
    vertex_texcoord02,
    vertex_normal,
    vertex_tangent,
    vertex_color,
    matrix_mvp,
    matrix_view,
    matrix_projection,
    matrix_model,
    matrix_normal,
    vector_view,
    color_diffuse,
    color_specular,
    color_ambient,
    map_albedo,      // texture0
    map_metalness,
    map_normal,
    map_roughness,
    map_occlusion,
    map_emission,
    map_height,
    map_cubemap,
    map_irradiance,
    map_prefilter,
    map_brdf,
    // ...
};
```

---

## Custom Uniforms: Passing Data to Shaders

### Types You Can Pass

| GLSL Type   | Zig Type    | Enum                          |
| ----------- | ----------- | ----------------------------- |
| `float`     | `f32`       | `.float`                      |
| `vec2`      | `[2]f32`    | `.vec2`                       |
| `vec3`      | `[3]f32`    | `.vec3`                       |
| `vec4`      | `[4]f32`    | `.vec4`                       |
| `int`       | `i32`       | `.int`                        |
| `ivec2`     | `[2]i32`    | `.ivec2`                      |
| `sampler2D` | `Texture2D` | (use `setShaderValueTexture`) |

### Example: Time-based Animation

```glsl
// In shader
uniform float time;

void main() {
    float pulse = sin(time * 3.0) * 0.5 + 0.5;
    vec4 texel = texture(texture0, fragTexCoord);
    finalColor = texel * vec4(1.0, pulse, pulse, 1.0);
}
```

```zig
// In Zig
const timeLoc = Raylib.getShaderLocation(shader, "time");

// In update/render loop
var time: f32 = @floatCast(Raylib.getTime());
Raylib.setShaderValue(shader, timeLoc, &time, .float);
```

### Example: Multiple Textures

```glsl
uniform sampler2D texture0;  // Main texture (automatic)
uniform sampler2D noiseMap;  // Custom texture

void main() {
    vec4 texel = texture(texture0, fragTexCoord);
    float noise = texture(noiseMap, fragTexCoord).r;
    finalColor = texel * noise;
}
```

```zig
const noiseMapLoc = Raylib.getShaderLocation(shader, "noiseMap");
Raylib.setShaderValueTexture(shader, noiseMapLoc, noiseTexture);
```

---

## Performance Optimization

### 1. Minimize Shader Switches

**Bad** - switching shader per entity:

```zig
for (enemies) |enemy| {
    Raylib.beginShaderMode(shader);  // Switch
    enemy.draw();
    Raylib.endShaderMode();          // Switch back
}
// Result: 200 enemies = 400 shader switches
```

**Good** - batch by shader:

```zig
Raylib.beginShaderMode(shader);  // Switch once
for (enemies) |enemy| {
    enemy.draw();
}
Raylib.endShaderMode();          // Switch back once
// Result: 200 enemies = 2 shader switches
```

### 2. Minimize Uniform Updates

**Bad** - setting constant uniforms every frame:

```zig
fn render() void {
    // These never change!
    Raylib.setShaderValue(shader, texSizeLoc, &texSize, .vec2);
    Raylib.setShaderValue(shader, glowColorLoc, &glowColor, .vec4);
    // ...
}
```

**Good** - set constants once at load time:

```zig
fn load() void {
    shader = loadShader(...);

    // Set once
    Raylib.setShaderValue(shader, texSizeLoc, &texSize, .vec2);
    Raylib.setShaderValue(shader, glowColorLoc, &glowColor, .vec4);
}

fn render() void {
    // Only set dynamic uniforms
    Raylib.setShaderValue(shader, timeLoc, &time, .float);
}
```

### 3. Reduce Texture Samples

Each `texture()` call in GLSL is expensive. Your glow shader does 5 samples:

```glsl
// 5 samples = ~5x cost
texel = texture(texture0, fragTexCoord);      // 1
glow += texture(texture0, offset1).a;          // 2
glow += texture(texture0, offset2).a;          // 3
glow += texture(texture0, offset3).a;          // 4
glow += texture(texture0, offset4).a;          // 5
```

For a single sprite: fine. For 500 sprites: consider alternatives.

### 4. Lower Resolution for Expensive Effects

Post-process at half resolution, then upscale:

```zig
// Full resolution: 1920x1080 = 2M fragments
// Half resolution: 960x540 = 500K fragments (4x faster!)

const halfTarget = Raylib.loadRenderTexture(width / 2, height / 2);

// Render effect at half res
Raylib.beginTextureMode(halfTarget);
applyExpensiveEffect();
Raylib.endTextureMode();

// Upscale to full screen (cheap)
Raylib.drawTexturePro(halfTarget.texture, srcRect, fullScreenRect, ...);
```

### 5. Avoid Branching in Shaders

**Bad** - GPU threads diverge:

```glsl
if (fragTexCoord.x > 0.5) {
    // Half the threads do this
    finalColor = expensiveCalculation1();
} else {
    // Half do this
    finalColor = expensiveCalculation2();
}
// GPU runs BOTH paths, discards results
```

**Good** - branchless:

```glsl
float t = step(0.5, fragTexCoord.x);
finalColor = mix(result1, result2, t);
```

### 6. Use Appropriate Precision

For mobile/WebGL (GLSL ES), precision hints matter:

```glsl
precision mediump float;  // Faster than highp on mobile
```

For desktop GLSL 330, this doesn't apply (always highp).

---

## Common Shader Patterns

### Pattern 1: Outline/Glow (what you have)

- Sample surrounding pixels
- Check alpha discontinuity
- Add color where edges detected

### Pattern 2: Flash/Hit Effect

```glsl
uniform float flashAmount;  // 0-1

void main() {
    vec4 texel = texture(texture0, fragTexCoord);
    vec3 flashColor = vec3(1.0, 1.0, 1.0);
    finalColor = vec4(mix(texel.rgb, flashColor, flashAmount), texel.a);
}
```

### Pattern 3: Dissolve

```glsl
uniform float dissolveAmount;  // 0-1
uniform sampler2D noiseMap;

void main() {
    vec4 texel = texture(texture0, fragTexCoord);
    float noise = texture(noiseMap, fragTexCoord).r;

    if (noise < dissolveAmount) discard;

    // Edge glow
    float edge = smoothstep(dissolveAmount, dissolveAmount + 0.1, noise);
    vec3 edgeColor = vec3(1.0, 0.5, 0.0);

    finalColor = vec4(mix(edgeColor, texel.rgb, edge), texel.a);
}
```

### Pattern 4: Screen-Space Distortion

```glsl
uniform float time;
uniform float intensity;

void main() {
    vec2 uv = fragTexCoord;
    uv.x += sin(uv.y * 20.0 + time) * intensity;
    uv.y += cos(uv.x * 20.0 + time) * intensity;

    finalColor = texture(texture0, uv);
}
```

### Pattern 5: Color Grading (Post-Process)

```glsl
uniform sampler2D lutTexture;  // 3D LUT as 2D strip

void main() {
    vec4 texel = texture(texture0, fragTexCoord);

    // Look up color in LUT
    float blueIndex = texel.b * 15.0;
    vec2 lutCoord = vec2(
        (texel.r + floor(blueIndex)) / 16.0,
        texel.g
    );

    finalColor = texture(lutTexture, lutCoord);
}
```

---

## Architecture Recommendation for Your Project

Based on your codebase patterns, here's how I'd structure shaders:

```
src/
  assets/
    shaders.zig          # Load/unload all shaders

resources/
  shaders/
    glsl330/
      # Per-sprite effects
      glow.glsl
      hit_flash.glsl
      dissolve.glsl

      # Post-processing
      bloom_extract.glsl
      blur_horizontal.glsl
      blur_vertical.glsl
      composite.glsl
      color_grade.glsl
```

```zig
// src/assets/shaders.zig
pub const Out = struct {
    pub const load = Shaders.load;
    pub const unload = Shaders.unload;

    // Per-sprite shaders
    pub const Sprite = struct {
        pub const glow = Shaders.getGlow;
        pub const hitFlash = Shaders.getHitFlash;
        pub const dissolve = Shaders.getDissolve;
    };

    // Post-process shaders
    pub const Post = struct {
        pub const bloom = Shaders.getBloom;
        pub const colorGrade = Shaders.getColorGrade;
    };

    // Uniform setters
    pub const Set = struct {
        pub const time = Shaders.setTime;
        pub const flashAmount = Shaders.setFlashAmount;
        // ...
    };
};
```

---

## Summary: Mental Model

| What you want           | Technique                                  |
| ----------------------- | ------------------------------------------ |
| Affect ONE sprite       | Wrap single draw call in `beginShaderMode` |
| Affect GROUP of sprites | Wrap render loop in `beginShaderMode`      |
| Affect UI               | Same, but outside camera mode              |
| Affect ENTIRE screen    | RenderTexture + post-process               |
| Multi-pass effects      | Multiple RenderTextures, chain shaders     |

| Performance concern       | Solution                       |
| ------------------------- | ------------------------------ |
| Many shader switches      | Batch draws by shader          |
| Expensive fragment shader | Lower resolution RenderTexture |
| Many texture samples      | Reduce samples, use LOD        |
| Constant uniforms         | Set once at load time          |

---

Any specific effect you want to dive deeper into, or shall I help you set up a more robust shader architecture for the project?
