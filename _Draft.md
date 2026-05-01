good fix

---

Performance is good enough. No optimization pass needed right now.
Rough frame time:

- 1 grass instance: ~530 FPS = ~1.9 ms/frame
- 8000 instances: ~325 FPS = ~3.1 ms/frame
- Grass cost at 8000: about +1.2 ms/frame
  That is fine, especially because grass is currently drawn into color, normal, and depth passes. Raylib’s DrawMeshInstanced() does upload instance transforms each draw, but at these numbers it is not a bottleneck worth solving yet.
  Recommended next step: visual tuning, not performance.
  I’d do this next:

1. Add a small grass tuning UI page.
2. Expose density, blade width/height, wind speed, wind strength, wind framerate, and maybe root height.
3. Tune until the field looks good in final view.
4. Then add matching floor color patches so the grass feels integrated with the ground.
5. Only after that consider accent grass or character displacement.
   Persistent GPU instance buffers / chunking can wait until FPS becomes an actual problem.
