---
context:
  - "[[Development Software]]"
---

# TexturePacker

Sprite sheet packer.

---

## Features

Core Packing Features:

- **Multiple Packing Algorithms**: Grid, Basic, MaxRects (gap-filling), and Polygon (removes transparent areas).
- **Automatic Trimming**: Removes transparent areas around sprites to reduce memory usage.
- **Duplicate Detection**: Identifies identical sprites and includes them only once.
- **Multipack Support**: Automatically creates the minimum number of sprite sheets needed for all sprites.

Optimization Features:

- **Multi-resolution Support**: Automatically scale sprites for different screen sizes and devices.
- **PNG Optimization**: Includes PngQuant and Zopfli compression to reduce file sizes.
- **Hardware Compression**: Supports ETC1/2, PVRTC1/2, DXT1/5, ASTC, Basis Universal formats.
- **Artifact Prevention**: Eliminates flickering lines, jagged edges, halos, and color bleeding.

Artist-Friendly Tools:

- **9-patch/9-scale editor**: For UI elements like buttons and dialog boxes.
- **Pivot point editor**: Visual editor with real-time animation preview.
- **Animation preview**: See sprite animations while editing.
- **Sprite sheet splitter**: Extract sprites from existing sprite sheets.

Workflow Integration:

- **Drag & drop UI**: Simple interface for quick setup.
- **Smart folders**: Auto-detects changes and rebuilds sprite sheets automatically.
- **Command line interface**: For build automation and scripting.
- **Docker/CI support**: For continuous integration pipelines.
- **48+ game engines supported**: Unity, Cocos2d-x, Phaser, Godot, Unreal, and many more.
