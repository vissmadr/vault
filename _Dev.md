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

# Examples

Study all the examples in the `raylib-zig` directory:

- [x] core/2d_camera.zig
- [x] core/2d_camera_mouse_zoom.zig
- [x] core/2d_camera_platformer.zig
- [x] core/3d_camera_first_person.zig
- [x] core/3d_camera_free.zig
- [x] core/3d_picking.zig
- [x] core/basic_screen_manager.zig
- [x] core/basic_window.zig
- [x] core/basic_window_web.zig
- [x] core/drop_files.zig
- [x] core/input_keys.zig
- [x] core/input_mouse.zig
- [x] core/input_mouse_wheel.zig
- [x] core/input_multitouch.zig
- [x] core/window_flags.zig

- [x] audio/module_playing.zig
- [x] audio/music_stream.zig
- [x] audio/raw_stream.zig
- [x] audio/sound_loading.zig

- [x] gui/message_box.zig

- [x] models/models_bone_socket.zig
- [x] models/models_box_collisions.zig
- [x] models/models_heightmap.zig

- [x] shaders/raymarching.zig
- [x] shaders/shaders_basic_pbr.zig
- [x] shaders/shaders_hybrid_render.zig
- [x] shaders/texture_outline.zig

- [x] shapes/basic_shapes.zig
- [x] shapes/bouncing_ball.zig
- [x] shapes/collision_area.zig
- [x] shapes/colors_palette.zig
- [x] shapes/draw_circle_sector.zig
- [x] shapes/draw_rectangle_rounded.zig
- [x] shapes/draw_ring.zig
- [x] shapes/easings_ball_anim.zig
- [x] shapes/easings_box_anim.zig
- [x] shapes/easings_rectangle_array.zig
- [x] shapes/following_eyes.zig
- [x] shapes/lines_bezier.zig
- [x] shapes/logo_raylib.zig
- [x] shapes/logo_raylib_anim.zig
- [x] shapes/reasings.zig
- [x] shapes/rectangle_scaling.zig
- [x] shapes/splines_drawing.zig
- [x] shapes/top_down_lights.zig

- [x] text/codepoints_loading.zig
- [x] text/draw_3d.zig
- [x] text/font_filters.zig
- [x] text/font_loading.zig
- [x] text/font_sdf.zig
- [x] text/font_spritefont.zig
- [x] text/format_text.zig
- [x] text/input_box.zig
- [x] text/raylib_fonts.zig
- [x] text/rectangle_bounds.zig
- [x] text/unicode.zig
- [x] text/writing_anim.zig

- [x] textures/sprite_anim.zig
- [x] textures/textures_background_scrolling.zig
- [x] textures/textures_image_loading.zig

# Art

Isometric 2D

Will 100% suffice for my first one.

It's more about design than the art itself.

**Color Palettes**: https://lospec.com/palette-list

Great examples online.

The angle is not a problem - even ellipses are very slight.

3D ones of the genre don't really look that good.

Polish is what makes it great.

Figure out controls.

# Technology

Zig: Low level, full control, clean.

Raylib: Effectively native performance for 2D.

- Can rebuild own parts from it in the future by looking at the source.

_Raylib is good as fuck._

# Engine Tasklist

- [ ] Get a window running.
- [ ] Print user input.
- [ ] Display an image.
- [ ] Display a shader.
- [ ] Open a debug GUI.
- [ ] Read/write to file.
- [ ] Make a sound.
- [ ] Database query.
- [ ] Profiler setup.
- [ ] Cross-platform builds.

# Prorotype Tasklist

- [ ] Isometric tilemap.
- [ ] Player movement.
- [ ] Player controls.
- [ ] Camera follow.
- [ ] Terrain collision.
- [ ] Save/Load file.
- [ ] Basic GUI.
- [ ] Random enemies.
- [ ] Enemy behavior.
- [ ] Debug hitboxes.
- [ ] Terrain generation.
