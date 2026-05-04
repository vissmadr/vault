---
context:
  - "[[Computer Graphics]]"
  - "[[3D Graphics]]"
---

# Shadow Map

[[Texture]] that stores scene depth from a light's point of view.

---

Used to approximate dynamic shadows.

1. Pretend the sun is a camera.
2. Render the scene from that sun camera.
3. Store only depth: “how far is the closest caster from the sun at this pixel?”
4. During the normal color pass, each surface asks: “from the sun’s view, am I behind something closer?”
5. If yes, that surface is in shadow.
