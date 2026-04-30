---
context:
  - "[[Computer Graphics]]"
  - "[[3D Graphics]]"
---

# Normal Map

[[Texture]] that stores surface normal directions.

---

Often used for used for lighting.

Can be used to fake small surface detail without changing the actual [[Triangle Mesh|mesh]] geometry.

Each texel stores a normal [[Vector]] direction, usually encoded as RGB color data.
During shading, this sampled normal replaces or perturbs the interpolated surface normal used by the [[Lighting (Computer Graphics)|lighting]] calculation.

**Tangent Space**: Most normal maps are tangent-space maps. They store normals relative to the surface, making them reusable on moving and deforming models.

**Encoding**: Normal components range from `-1` to `1`, but texture color channels range from `0` to `1`, so values are remapped.

```
encoded = normal * 0.5 + 0.5
normal = encoded * 2.0 - 1.0
```

**Blue Bias**: A flat tangent-space normal points mostly outward as `(0, 0, 1)`, which encodes to roughly `(0.5, 0.5, 1.0)`. This is why normal maps are usually bluish.

Sampled normals should be [[Vector Normalization|normalized]] before use.
