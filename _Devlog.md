# Big Study

Spent months of prerequisite learning to get ready for this project.

Technically years, considering the whole road before that.

# Sprite Drawing

`2025 10`

Learned how to draw sprites and use a drawing tablet.

Chose isometric 2.5D art for now.

Looks like even simple art can look very good when polished well.

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

# State Machine
