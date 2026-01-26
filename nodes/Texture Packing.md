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

Can be a massive performance gain (especially for sprite-heavy 2D games), at the cost of some extra complexity.

## Benefits

**Fewer Draw Calls**: Batch multiple sprites in one draw call.

**Reduced Texture Swaps**: GPU state changes can be expensive.

**Better Cache Coherency**: Related textures are stored together in VRAM.

**Simplified Asset Management**: Assets stored in one file can be easier to manage.

## Considerations

### Atlas Sizing

**Commion sizes**: `2048x2048`, `4096x4096`, `8192x8192`.

**Power-of-two Dimensions**: For optimal [[Mipmap]] generation, among other things.

**Texture Size Limit**: Must fit within the GPU's max texture size limit (`GL_MAX_TEXTURE_SIZE`).

### Packing Strategies

**Rectangle Packing**: Algorithms such as _Shelf_, _Guillotine_, _MaxRects_.

**Padding**: Border padding (1-2px) that prevents texture bleeding with filtering.

**Rotation**: Packers can rotate sprites for a tighter fit.

**Grouping**: Packing by usage pattern (UI, characters, environment).

### Platform Considerations

Different GPU hardware may have different capabilities.

It can be a good idea to ship multiple resolution tiers for different hardware.

Older GPUs may only support `2048x2048` for example.
