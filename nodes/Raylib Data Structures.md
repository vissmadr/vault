---
tags:
  - "data"
context:
  - "[[Raylib]]"
  - "[[Data Structure]]"
---

# Raylib Data Structures

Data structures in Raylib.

---

## Basic Data Structures

| Name               | 32bit size   | 64bit change | Description                                    |
| ------------------ | ------------ | ------------ | ---------------------------------------------- |
| struct Color;      | `[ 4 bytes]` | -            | // RGBA values, 4 char, 32bit color            |
| struct Rectangle;  | `[16 bytes]` | -            | // 4 float values                              |
| struct Vector2;    | `[ 8 bytes]` | -            | // 2 float values                              |
| struct Vector3;    | `[12 bytes]` | -            | // 3 float values                              |
| struct Vector4;    | `[16 bytes]` | -            | // 4 float values                              |
| struct Matrix;     | `[64 bytes]` | -            | // 16 float values, right handed, column major |
| struct Quaternion; | `[16 bytes]` | -            | // Vector4 alias                               |

## 2D Data Structures

| Name                    | 32bit size   | 64bit change | Description                                         |
| ----------------------- | ------------ | ------------ | --------------------------------------------------- |
| struct Image;           | `[20 bytes]` | `[+4 bytes]` | // Image data pointer (RAM) and 4 data parameters   |
| struct Texture;         | `[20 bytes]` | -            | // OpenGL texture id (VRAM) and basic info          |
| struct Texture2D;       | `[20 bytes]` | -            | // Texture alias                                    |
| struct TextureCubemap;  | `[20 bytes]` | -            | // OpenGL cubemap, texture alias                    |
| struct RenderTexture;   | `[44 bytes]` | -            | // OpenGL framebuffer id and color + depth textures |
| struct RenderTexture2D; | `[44 bytes]` | -            | // RenderTexture alias                              |

| Name              | 32bit size   | 64bit change  | Description                                         |
| ----------------- | ------------ | ------------- | --------------------------------------------------- |
| struct NPatchInfo | `[36 bytes]` |               | // Source rectangle and border offsets              |
| struct GlyphInfo; | `[32 bytes]` | `[+4 bytes]`  | // One glyph character metrics and image            |
| struct Font;      | `[40 bytes]` | `[+12 bytes]` | // Texture atlas and recs+chars data array pointers |

## Screen View Structures

| Name                   | 32bit size    | 64bit change | Description                                              |
| ---------------------- | ------------- | ------------ | -------------------------------------------------------- |
| struct Camera2D;       | `[24 bytes]`  | -            | // 2D camera offset, target, rotation and zoom           |
| struct Camera3D;       | `[44 bytes]`  | -            | // 3D camera position, target, up vectors and parameters |
| struct Camera;         | `[44 bytes]`  | -            | // Camera3D alias                                        |
| struct VrDeviceInfo;   | `[64 bytes]`  | -            | // Head-Mounted-Display device configuration parameters  |
| struct VrStereoConfig; | `[304 bytes]` | -            | // VR stereo rendering configuration for simulator       |

## 3D Data Structures

> [!NOTE]
> These structures are more complex so they use some internal pointers to data.

| Name                   | 32bit size   | 64bit change  | Description                                                                  |
| ---------------------- | ------------ | ------------- | ---------------------------------------------------------------------------- |
| struct Mesh;           | `[60 bytes]` | `[+52 bytes]` | // Vertex data, OpenGL buffers ids, animation data (skeleton bones and pose) |
| struct Shader;         | `[ 8 bytes]` | `[+8 bytes]`  | // OpenGL program id, locations array pointer                                |
| struct Material;       | `[16 bytes]` | `[+16 bytes]` | // Shader and maps array pointer                                             |
| struct MaterialMap;    | `[28 bytes]` | -             | // Texture, color and value                                                  |
| struct Model;          | `[96 bytes]` | `[+24 bytes]` | // Meshes+materials array pointers, transform matrix (64 bytes)              |
| struct ModelAnimation; | `[48 bytes]` | `[+8 bytes]`  | // Skeletal bones data and frames transformation                             |
| struct BoneInfo;       | `[36 bytes]` | -             | // Bone name (32 bytes) and parent id                                        |
| struct Transform;      | `[40 bytes]` | -             | // Vertex transformation: translation, rotation, scale                       |

| Name                 | 32bit size   | 64bit change | Description                               |
| -------------------- | ------------ | ------------ | ----------------------------------------- |
| struct Ray;          | `[24 bytes]` | -            | // Ray-casting position+direction vectors |
| struct RayCollision; | `[32 bytes]` | -            | // Ray collision information              |
| struct BoundingBox;  | `[12 bytes]` | -            | // Defined by min and max vertex          |

## Audio Related Data

| Name                | 32bit size   | 64bit change  | Description                                          |
| ------------------- | ------------ | ------------- | ---------------------------------------------------- |
| struct Wave;        | `[20 bytes]` | `[+4 bytes]`  | // Wave data pointer (RAM) and data parameters       |
| struct AudioStream; | `[20 bytes]` | `[+12 bytes]` | // Audio buffer pointer (private) and parameters     |
| struct Sound;       | `[24 bytes]` | `[+16 bytes]` | // Audio stream and samples count                    |
| struct Music;       | `[36 bytes]` | `[+20 bytes]` | // Audio stream and music data pointer for streaming |
