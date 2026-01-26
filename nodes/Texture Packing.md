---
context:
  - "[[Computer Graphics]]"
  - "[[Software Optimization]]"
---

# Texture Packing

Packing multiple [[Texture|Textures]] into one atlas to optimize rendering performance.

---

Combine many small textures into a single large texture called an _atlas_.

Reference individual textures using UV coordinates to specify sub-regions.

Benefits:

- Fewer draw calls.
- Reduced texture swaps.
- Better cache coherency.
- Simplified asset management.
