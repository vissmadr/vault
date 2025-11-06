# Architecture

Start simple, then evolve.

**Early stage**:

- Focus on gameplay logic and iteration speed.
- Use clear, object-style structs and references.
- Don’t over-optimize data layout before you have working systems.

**Mid stage**:

- Profile real gameplay.
- Identify hot loops (thousands of bullets, AI ticks, physics updates).
- Convert those specific systems to data-oriented or ECS layouts.

**Late stage**:

- Keep the high-level game logic (spawning, quests, UI) object-style.
- Keep the performance-critical subsystems (movement, collision, rendering) SoA or ECS.

**You can mix both**:

- Entities at the design level (spells, enemies, etc.) can own IDs pointing into data-oriented subsystems.
- Each subsystem manages its own arrays efficiently.

**Summary**:

- Build for clarity first.
- Profile.
- Refactor the 5–10% of code that runs 90% of the time into data-oriented form.

That yields maintainable code and strong performance without premature complexity.

# Art

Isometric 2D

Will 100% suffice for my first one.

It's more about design than the art itself.

**Color Palettes**: https://lospec.com/palette-list

Great examples online.

The angle is not a problem - even ellipses are very slight.

3D ones of the genre don't often look that good.

Polish is what makes it great.

Figure out controls.

Carrion seems low res. Also Celeste, etc.

# Technology

Zig: Low level, full control, clean.

Raylib: Effectively native performance for 2D.

- Can rebuild own parts from it in the future by looking at the source.

_Raylib is good as fuck._

# Engine Tasklist

- [x] Get a window running.
- [ ] Print user input.
- [x] Display an image.
- [ ] Display a shader.
- [ ] Open a debug GUI.
- [ ] Read/write to file.
- [ ] Make a sound.
- [ ] Database query.
- [ ] Profiler setup.
- [ ] Cross-platform builds.

# Prorotype Tasklist

- [ ] Isometric Tilemap.
- [x] Player movement.
- [x] Player controls.
- [ ] Camera follow.
- [ ] Terrain collision.
- [ ] Save/Load file.
- [ ] Basic GUI.
- [ ] Random enemies.
- [ ] Enemy behavior.
- [ ] Debug hitboxes.
- [ ] Terrain generation.
