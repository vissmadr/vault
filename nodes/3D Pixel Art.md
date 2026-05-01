---
context:
  - "[[Digital Art]]"
  - "[[Computer Graphics]]"
---

# 3D Pixel Art

Digital art style that blends [[Pixel Art]] aesthetics and [[3D Graphics]] together.

---

_Heavily inspired by the art of t3ssel8r._

## Pixel Effect

The pixel effect mostly comes from rendering the 3D scene into a small internal resolution, and then scaling that image up without smoothing.
The key part is using [[Nearest-neighbor Interpolation|nearest-neighbor]] texture filtering. This is to prevent blurry upscaling.
Example: scaling up a `640x360` render texture `3.0` times using `TEXTURE_FILTER_POINT` for a `1920x1080` output.

## Debug Views

**Normals**: Displays the directions of [[Normal Map|normals]] by encoding them as colors.
Each axis is mapped to RGB color.

**Depth**: Grayscale distance map. Shows how far each visible pixel is from the camera.
Darker usually means closer, lighter usually means farther.
See [[Depth Shader]]

## Stepped Lighting

Pixel art often defines color palettes with multiple shades per color.

The idea is to take the initial lighting and define threshold values.
The lighting then clamps to the nearest threshold, giving it a step-like appearance.

See [[Stepped Lighting]].

## Edge Highlights

Edge pixels are visualized by mixing the original pixel color with an edge highlight color.

**Outer Highlights**: Visualizes differences in depth, where each pixel is compared against its surrounding neighbors.
The pixel is considered an edge if the difference in depth between it and its neighbors passes a certain threshold.

**Inner Highlights**: Visualizes differences in surface normal direction, where each pixel is compared against its surrounding neighbors.
Surface normal vector angles are compared by dot product. The dot product tells us about their alignment relative to eachother.
This alignment is then checked against a threshold to determine if the pixel qualifies as an edge or not.

#wip **Bonus**: To elevate this even further, we can use the attenuation of the light shader to lighten or darken edges based on their lighting information.

## Models

#wip small bevels break stuff - prefer no bevels

#wip Probably stones NOT triangulated?

