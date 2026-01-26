---
context:
  - "[[Development Software]]"
  - "[[Texture Packing]]"
---

# TexturePacker

Spritesheet packer.

[Website](https://www.codeandweb.com/texturepacker)

---

**License**: Proprietary

## Features

Core Packing Features:

- **Multiple Packing Algorithms**: Grid, Basic, MaxRects (gap-filling), and Polygon (removes transparent areas).
- **Automatic Trimming**: Removes transparent areas around sprites to reduce memory usage.
- **Duplicate Detection**: Identifies identical sprites and includes them only once.
- **Multipack Support**: Automatically creates the minimum number of spritesheets needed for all sprites.

Optimization Features:

- **Multi-resolution Support**: Automatically scale sprites for different screen sizes and devices.
- **PNG Optimization**: Includes PngQuant and Zopfli compression to reduce file sizes.
- **Hardware Compression**: Supports ETC1/2, PVRTC1/2, DXT1/5, ASTC, Basis Universal formats.
- **Artifact Prevention**: Eliminates flickering lines, jagged edges, halos, and color bleeding.

Artist-Friendly Tools:

- **9-patch/9-scale Editor**: For UI elements like buttons and dialog boxes.
- **Pivot Point Editor**: Visual editor with real-time animation preview.
- **Animation Preview**: See sprite animations while editing.
- **Spritesheet Splitter**: Extract sprites from existing spritesheets.

Workflow Integration:

- **Drag & Drop UI**: Simple interface for quick setup.
- **Smart Folders**: Auto-detects changes and rebuilds spritesheets automatically.
- **Command Line Interface**: For build automation and scripting.
- **Docker/CI Support**: For continuous integration pipelines.
- **48+ Game Engines Supported**: Unity, Cocos2d-x, Phaser, Godot, Unreal, and many more.
