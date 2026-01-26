---
context:
  - "[[Software Optimization]]"
---

# Software Optimization Tips

Ideas, guidelines, and techniques for software optimization.

---

**Data Oriented Design**: Think about [[Data Oriented Design]].

**Simple Data**: Prefer using simple data types and data structures. Booleans, integers, floats, arrays, and structs.

**Create Once**: Create all the data once in the beginning, and then only reuse it. See [[Object Pooling]].

**Local Cache**: Store frequently used data in cache instead of fetching it repeatedly.

**Culling**: Render only what is visible.

**Pack Resources Together**: See [[Texture Packing]] for example.
