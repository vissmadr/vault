---
context:
  - "[[Raylib]]"
  - "[[Software Architecture]]"
---

# Raylib Architecture

The architecture of Raylib.

[Raylib Architecture Wiki](https://github.com/raysan5/raylib/wiki/raylib-architecture)

---

**Modular**: Raylib follows [[Modular Design]] principles. Everything is contained within a small number of well-defined, specific, and self-contained modules.

Raylib has seven main modules:

- **`rcore`**: Window / Graphic Context / Input management.
- **`rlgl`**: Graphic API (OpenGL) wrapper and pseudo-OpenGL 1.1 translation layer.
- **`rtextures`**: Textures / Image loading and management.
- **`rtext`**: Font data loading and text drawing.
- **`rshapes`**: Basic 2D shapes drawing functions.
- **`rmodels`**: 3D models loading and drawing.
- **`raudio`**: Audio device management and sounds / music loading and playing.

**Common Header**: Those seven modules share a common header, named `raylib.h`. All API functions are defined in that header, despite being internally divided into seven modules, so the user only needs to include `raylib.h` to access all of the raylib functionality.

Beyond the seven main modules that are described above, there is a small collection of additional modules that implement extra features:

- **`raymath`**: Vector2, Vector3, Matrix and Quaternion math related functions.
- **`rcamera`**: 3D Camera system (free, 1st person, 3rd person, custom).
- **`rgestures`**: Touch gesture detection and processing (Tap, Swipe, Drag, Pinch).
- **`raygui`**: Simple IMGUI system with several controls for tools development.
- **`rres`**: Resource packaging file-format with some tools provided.

**Decoupled Extra Modules**: Raylib extra modules are designed to be as decoupled as possible from the other modules. In fact, some modules can be used as standalone libraries, independently of raylib.
