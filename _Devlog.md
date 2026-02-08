# Big Study

Spent months of prerequisite learning to get ready for this project.

Technically years, if one considers the whole gaming & software & design experience before that.

# Sprite Drawing

`2025 10`

Learned how to draw sprites and use a drawing tablet.

Choosing isometric 2D art for now.

Looks like even simple art can look very very good when polished well in the end.

Too many great examples prove this right.

# Account

`2025 10 14`

Accounts setup.

# Tech

`2025 10 17`

_Lots of research._

Figuring ot what technologies I should use for the project.

Lots of YouTube, lots of DeepSeek.

Technologies in mind: `C`, `C++`, `OpenGL`, `Raylib`, `SDL3`, `ImGui`, `SQLite`, `GLFW`, `SFML`...

Trying to prototype in different ones to see how they work.

Struggling with the fact that C doesn't have namespacing.

Really struggling with C/C++ build systems.

Learning how the build process actually works.

`2025 10 18`

_Lots of research._

Probably watched a hundred different videos on YouTube about various game development projects and technologies.

Randomly stumbled upon the Zig programming language.

Will check it out...

HOLY SHIT!

This is it.

It's funny how it's easier to setup and build a C/C++ library with Zig than it is with C/C++ build tools, lol.

Turns out you can very easily import Raylib into a Zig project and use it directly. This way I even have it enclosed in a namespace. And there are also custom Zig bindings for it. Magic!

Technologies in mind: `Zig`, `Raylib`

# Zig

`2025 10 19`

_Practice, practice, practice..._

Went through the full Raylib wiki.

Going through the `zig-raylib` package examples one by one to build a fundamental understanding before I dive in myself.

# Data Oriented Design

`2025 10 28`

Researching data oriented design, ECS, and software architecture.

It's good and I learned a ton.

Found out that it's not necessarily an all-in architecture. Things can be refactored into data oriented form later for better performance. So focus on building first.

# Raylib-Zig Examples

`2025 11 02`

Going back and completing the `zig-raylib` examples.

# Creation

`2025 11 04`

Created the project repository around this time.

# Isometric Tilemap

`2025 11 06`

Figuring out how to do the isometric tilemap.

Should probably use Tiled, and then convert the data for the game.

# Tilemap Grid

`2025 11 07`

Learned how to use Tiled.

Playing around with exporting tilemap data and loading it in Zig.

Got a debug grid working, both rectangular and isometric.

# Perspective

`2025 11 08`

But what if I try 3D?

Imported a 3D model.

# Camera

`2025 11 09`

Got a 3D camera working.

Created a GUI for the camera control.

# 3D Files

`2025 11 09`

Researching how 3D works in terms of files and stuff.

Managed to import a 3D model.

Struggling with character animations.

# Graphics Decision

`2025 11 13`

Played around with graphics, 3D models, animations, Blender, talked to developers...

I needed a decision between 2D vs 3D, as both have their own reasonable pros & cons.

I've decided on 2D.

Now, time to decide between standard and isometric.

2D can really look good and sharp. Especially for top-down.

Experimenting with 3D was a good experience nonetheless.

# Player Spritesheets

`2025 11 15`

Loaded spritesheets and setup the player render.

Switching from `.png` to `.dds` format drastically improved load times.

Need to remember that `.dds`, although extremely unlikely, may not be supported on all platforms. Need to test targets.

About the graphics: Looking at other games, it seems like it's all about polish. Even low-quality assets can look really good in a complete game.

For advanced character spritesheets (probably only the player and bosses, if at all), there is a technique to go from 3D to 2D. Use Blender or something to model and animate 3D characters, and with an orthographic camera record in 4, 8, or 16 directions by rotating the model. Figure out how to capture images. Assemble to a spritesheet. Now it's 2D. It can also have a consistent light source in Blender.

Improved the asset loader structure.

# Grid

`2025 11 15`

Going back to playing around with an isometric grid.

Did a huge fucking refactor of everything btw lmao.

Still need to figure out isometric, normal, or hybrid.

# Isometric Grid

`2025 11 18`

Decided to stick to 2D isometric.

Grid looks good.

Had a design problem around the movement. The grid is squashed 2:1 width:height, so the `y`-axis movement should technically be halved to achieve 'correct' movement on the grid. But it feels kinda shit and slow when you move like this. Sticking to the same speed in all directions feels better, even if it's not technically the 'correct' isometric behavior. Have to test this further.

# Player

`2025 11 20`

Worked on the player state machine.

Decoupled animations.

Decoupled movement.

# Player Movement

`2025 11 22`

Went heavy on the player movement.

Made a clean and configurable movement component.

Struggled with the classic 'drag' approach, where one would scale the velocity by a scalar number each frame. It's harder to get this working properly without being framerate dependent. Another problem is that I would like to have exact movement passed through config. The way it works now is with a flag that marks whether the velocity is currently being accelerated or not. If it is, it applies a constant scalar `acceleration` velocity. If not, it applies a constant scalar `deceleration` velocity.

Also split the movement into different pieces for each type of movement. Currently there are:

- `selfMovement`: the manual movement of the player.
- `pushMovement`: external movement applied to the player.
- `attackStepMovement`: movement applied when the player uses an attack.

# Spells

`2025 11 24`

Created the spell combination keys.

There are the 3 spell keys, as well as the attack key.

The combinations are 9 spells and 3 attackSpells in total.

Spent some time refactoring code and also thinking carefully about the input. It's important to catch the correct keys when players get really fast.

# Spell Design

`2025 11 25`

Bruh.

# Spell Design

`2025 11 27`

Finally `3` buttons for: Attack, Dash, SpecialMode

# Overhaul

`2025 11 28`

Simpler and sharper movement.

No velocity, no acceleration.

If it needs to look smooth - animations only.

# Overhaul complete

`2025 12 02`

Split the player into `logic`, `render`, and `stats` files.

Mechanics:

```
Attack
  Instant action.
  Attack `duration` and `cooldown` are the same.
  Slows player movement while in attack state.
  Can be overwritten by dash.

Dash
  Instant action.
  Player is locked while dashing.
  Both facing and movement directions remain locked while dashing.
  New directions are set after the dash is completed.

Cast
  Instant action.
  Slows player movement while in cast state.
  Can be overwriten by dash.
```

The dash now has charges.

Fixed the player debug renderer.

# GUI

`2025 12 05`

Created ability icons.

Created player stats debug.

# Collisions

`2025 12 06`

Created collisions with walls in rectangular space.

# Isometric

`2025 12 07`

Separated the rectangle logic from the isometric render.

**Direction**: Had to rotate the movement direction `45°` counterclockwise so that WASD matches the movement in the isometric render.

**Anti Stuck System**: Created an AntiStuckSystem that checks if the player is colliding with anything or is outside of the map once in a while, and if so teleports him back to a safe position.

**Isometric Shift**: Implemented switching between rectangle (logical) space and isometric (render) space.

# Collision Architecture

`2025 12 10`

Trying to figure out how to design some data-oriented-ish system for projectiles, collisions, targets, and so on.

For example, if I have a bunch of enemies in the object pool, most of them inactive, how should I design the logic to have a collider check against the active enemies?

There were 3 main options:

1. **Linear Search**: Just iterate the array of `enemies` and `if(!enemy.isActive) continue;`. Basically a linear search.
2. **ArrayList Swapping**: Have separate data structures, one for active and one for inactive enemies, swapping the enemies between those structures.
3. **Spatial Partitioning**: Store enemies in some form of spatial partitioning, which indirectly solves the problem of 'active/inactive' enemies, since inactive ones wouldn't be in the space.

Think I'll go for the spatial partitioning approach, as in the other cases I would still need to implement spatial partitioning anyways.

The only downside, even though I cannot really call a solid argument against it, is that it feels weird that I rely on some system, like spatial partitioning, to kiiinda indirectly solve a problem. Since I don't explicitly have an awareness of `active` or `inactive` enemies.

# Sectors

`2025 12 12`

# Pathfinding

`2025 12 13`

Implemented A\* pathfinding from enemy to player.

Was waaay more difficult with Zig.

Now I'm thinking to remove A\* and instead use a single BFS flood-fill from the player which every enemy can re-use.

Chris gave me the idea to pre-bake the entire map this way.

# Sense

`2025 12 22`

# Precompute Flow Field

`2025-12-27`

Will try to precompute the whole flow field.

Turns out it's not a good solution for this case, as precomputing the grid is at least `O(n⁴)` in terms of memory.

The data structure is something like `pathResults[yFrom][xFrom][yTo][xTo]`.

Depending on the grid size, it can easily cost over `100MB` for every single map.

Computing throttled pathfinding at runtime is way faster than having to access and cache huge 4D arrays. Plus it costs no build memory.

Throttled to `0.1` - `0.2` seconds makes its cost trivial.

# Profiling

`2025-12-29`

Ran a profiler for the first time to see the actual bottlenecks.

Long story short it's all rendering basically.

The game logic (for now) is optimized well enough that it's about `5%` of the total CPU work.

Turns out that throttling the pathfinding was an extreme performance booster.

# Enemy Movement

`2025-12-29`

Merged both sense and pathfinding movement into a single system.

Now it's sense-based, where the pathfinding direction is just another weight for the sense.

Looks surprisingly good out of the box.

Added directional smoothing by lerping from the previous direction to the desired new one.

Now I must test it with many enemies at once.

# Debug Rendering

`2025-12-29`

Pleasently surprised to find that I could code debug stuff relatively easily due to systems already being built and working.

Created some otherwise difficult to make debug visuals in minutes.

Code reuse can be great.

# Going Strong

`2025-12-30`

These 3-4 days have been an insane progress.

Made tons of improvementds, especially for the movement logic:

- sense system
- movement inertia
- analog axis speed
- facing direction
- smooth move rotation
- smooth face rotation
- debug rendering
- performance boosts

Will try to make a good video just before new year.

# Data-oriented Refactor

`2025-12-31`

Making a huge refactor into ECS-ish architecture.

Data-oriented has many benefits it seems. The more I use it the more I like it.

- The performance gain is absolutely insane. Without rendering, my game logic currently runs at about `7000` FPS lol.
- Surprisingly using DOD actually made the code better and more readable. Separating state from logic is good.

Found a guy for the 3D to 2D idea. Will see what he does, of if he does anything at all.

# Multiple Enemies

`2026-01-01`

Multiple enemies after the DOD refactor.

Code is so much nicer now.

But the enemies stack together in a single point...

# Neighbor Avoidance

`2026-01-02`

Created neighbor avoidance logic as part of the sense system with the help of my AI friend.

It turned out great.

Had some problems with the performance, but did the good'ol throttle and suddenly the sense evaluation dissapeared from the profiler charts.

# Enemy Restructure

`2026-01-03`

Completely restructured the enemies architecture:

- **Stats**: Authorative, persistent, and immutable.
- **Variety**: Slight variations to the stats.
- **Presets**: Preset stats and variations per enemy type.
- **Components**: Mutable state data.
- **Modifiers**: Mutable modifiers to be applied to the components.
- **Logic**: Pure logic that operates on enemy data.
- **Store**: Data-oriented storage for all enemy data.

Enables clean and performant code.

Component values can be derived on each update, where:

```
component = (stats + variety) + modifiers
```

# 3D to 2D

`2026-01-03`

Luben managed to create a basic 3D to 2D workflow.

He exports images for a total of `16` angles with `16` frames per animation each.

This could be it.

Now I need to work and find out what to do about the shadows before I invest him further.

# Lighting

`2026-01-04`

Researching shadows and light.

Wanted to see if I can make dynamic shadows. Technically I can, but it seems too much of a hassle without that great of a result.

Consistency is better than realism.

Thinking I'll do static shadows, which can look good, and also have quite a few engineering benefits:

- Can be pre-rendered.
- No additional logic; just draw them before the sprites.

Need to decide one light angle and stick to it.

**Torches**: Local lights wont create new shadows. They affect color only. Can change color, brightness, and add glow.

# Windows Build

`2026-01-04`

Horror.

- Problems with high-DPI.
- Problems with Alt+Tab.
- Problems with resolution.
- Problems with VSync.
- Problems with provider trust.

Fuck Windows.

# Social

`2026-01-06`

Doing some social work, such as setting up Discord and also getting other people to join on the project.

# Sectors

`2026-01-08`

Begin Reworking the sectors logic again to follow data-oriented principles.

# Time

`2026-01-09`

Trying to prevent `deltaTime` errors when switching windows and in general.

Need to do:

- Global clamped `deltaTime`.
- Pause updates when unfocused.
- Create a timestep accumulator.

Actually decided not to pause anything when unfocused. The pause should come manually from the game, not from OS-level systems.

# Mechanics Overhaul

`2026-01-11`

Complete mechanics/actions overhaul.

# Desi

`2026-01-12`

Found an artist.

Self-taught, free time, and is serious about the craft.

Fingers crossed, she seems like the perfect fit right now.

Hope this works out. If it does - thank the Scramble King™.

`2026-01-14`

Agreed to work together.

Hoping for the best.

She seems great.

# Stats

`2026-01-15`

Something like this:

`all`: Authoritative owner of all lifecycles and state.

`stats-baseline`: Immutable Enemy baseline data.
`stats-variety`: Unique spawn-time per-entity random mutation.
`stats-presets`: Pre-designed `baseline  variety` combinations.

`mods-persistent`: Immutable static pre-game modifiers.
`mods-dynamic`: Mutable dynamic in-game modifiers.

`derived`: Combines all data for a final derived sum.

`components`: Runtime state modules specific to systems.
`systems`: Pure stateless logic.

Needs to scale well.

Figuring it out.

Also, thinking about a YouTube idea.

Researching the different types of scaling:

- Flat Additive
- Percent Additive
- Percent Multiplicative

# People

`2026-01-16`

Talked to Veselin, who would like to join as a designer.

He's great for deep brainstorm sessions, especially about game design.

Talked to Nikola, who came up with some great design ideas.

I came up with a new game loop mechanic that solves the 'speedrun' problem.

Talked to Stela about art, game development, and stuff.

She would also like to join the team as an artist.

This is going great so far.

Hope that continues.

# Stats

`2026-01-17`

Continuing with the `stats`, `variety`, `presets`, `modifiers`, `statEffects`, `statusEffects`, `components`, `derived`, `all`...

This is getting longer than I want, or maybe I'm just slower due to the burnout.

Either way gotta complete that and move on.

Hopefully the time spent on this will be worth in terms of quality.

`2026-01-19`

This shit is difficult.

# Story & Marketing

`2026-01-19`

Continued the old story.

Redesigned it in order to fit the current (imaginary) gameplay and aesthetic.

Talked to Viki - marketing.

She seems interested and up for it.

Hope this works out.

# Stats & OpenCode

`2026-01-22`

Finally finishing the stats and attributes.

This took a while.

Setup some great stuff with OpenCode, which can really help for some things.

# Design

`2026-01-24`

Long sessions with Vesko to brainstorm design.

# Meetup

`2026-01-25`

Had a board games meeting with Luben and Vesko. Good times.

Live brainstorm session with Vesko which progressed both the gameplay mechanics and story.

# Design & Story Issues

`2026-01-27`

We're lost with the overall story and design.

Figured out we should make a playable game loop first, and only then think about design, story, and aesthetics.

# Huge Refactor

`2026-01-29`

Huge fucking refactor.

Code seems to be cleaner than ever. Hope so at least.

Now it's time to rush a few features because I am behind from all the social stuff, community building, and game design.

# #wip

Missing a whole week.
Not that I didn't work, just didn't write here.

# Skills Design

`2026-02-07`

Brainstormed all day.

Came up with many skills. Especially the ones for Fire, Storm, and Chaos.
