---
aliases:
  - Quantized Lighting
context:
  - "[[Lighting (Computer Graphics)]]"
  - "[[Shader]]"
---

# Stepped Lighting

Lighting technique that clamps smooth light values into a small set of discrete bands.

---

Common in toon shaders, cel shading, and [[3D Pixel Art]].

Instead of smooth (continuous/analog) gradient from dark to bright, the light value is quantized into discrete steps.

```txt
smooth lighting:  dark -> mid -> bright
stepped lighting: shadow | midtone | highlight
```

The usual process:

1. Calculate normal lighting.
2. Compare the light value against thresholds.
3. Output the nearest shade band.

Useful when the goal is a stylized look with clear graphic shapes instead of realistic gradients.

Example:

```
Realistic lighting:

0.12 -> very dark
0.23 -> less dark
0.34 -> medium dark
0.45 -> medium
0.56 -> medium bright
0.67 -> bright

Toon lighting:

0.12 -> dark
0.23 -> dark
0.34 -> mid
0.45 -> mid
0.56 -> bright
0.67 -> bright
```
