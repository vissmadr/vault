---
context:
  - "[[Raylib]]"
  - "[[Shader]]"
  - "[[Software Optimization]]"
---

# Raylib Shader Optimization

Guidelines and tips to optimize the performance of shaders in Raylib.

---

## Minimize Shader Switches

**Bad**: Switching shader per entity

```zig
for (enemies) |enemy| {
    Raylib.beginShaderMode(shader);  // Switch
    enemy.draw();
    Raylib.endShaderMode();          // Switch back
}
// Result: 200 enemies = 400 shader switches
```

**Good**: Batch by shader

```zig
Raylib.beginShaderMode(shader);  // Switch once
for (enemies) |enemy| {
    enemy.draw();
}
Raylib.endShaderMode();          // Switch back once
// Result: 200 enemies = 2 shader switches
```

## Minimize Uniform Updates

**Bad**: Setting constant uniforms every frame

```zig
fn render() void {
    // These never change!
    Raylib.setShaderValue(shader, texSizeLoc, &texSize, .vec2);
    Raylib.setShaderValue(shader, glowColorLoc, &glowColor, .vec4);
    // ...
}
```

**Good**: Set constants once at load time

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

## Reduce Texture Samples

Each `texture()` call in GLSL is expensive.

```glsl
// 5 samples = ~5x cost
texel = texture(texture0, fragTexCoord);    // 1
glow += texture(texture0, offset1).a;       // 2
glow += texture(texture0, offset2).a;       // 3
glow += texture(texture0, offset3).a;       // 4
glow += texture(texture0, offset4).a;       // 5
```

For a single sprite: fine. For 500 sprites: consider alternatives.

## Lower Resolution for Expensive Effects

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

## Avoid Branching in Shaders

**Bad**: GPU threads diverge

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

**Good**: Branchless

```glsl
float t = step(0.5, fragTexCoord.x);
finalColor = mix(result1, result2, t);
```
