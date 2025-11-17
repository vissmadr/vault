---
context:
  - "[[Computer Graphics]]"
---

# Culling

Technique that ignores the rendering things that shouldn't be visible anyways.

---

Culling removes whole things before rasterization to reduce workload.

See [[Clipping]]

## Types

**Back-face culling**: Discard triangles facing away from the camera.

**Frustum culling**: Discards objects completely outside of the camera's view volume.

**Occlusion culling**: Discard objects hidden entirely behind other objects.
