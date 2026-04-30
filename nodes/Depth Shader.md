---
context:
  - "[[Shader]]"
  - "[[Depth Buffer]]"
---

# Depth Shader

[[Shader]] that renders or uses scene depth information.

---

Usually samples the [[Depth Buffer]] or a depth texture to visualize distance, compare neighboring pixels, or drive screen-space effects.

Depth values are often nonlinear in perspective projection, so they may need to be linearized before use.

Useful for:

- Edge detection
- Fog
- Soft particles
- Depth of field
- Screen-space outlines
- Occlusion effects
