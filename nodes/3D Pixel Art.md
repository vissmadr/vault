---
context:
  - "[[Digital Art]]"
  - "[[Computer Graphics]]"
---

#empty

# 3D Pixel Art

Digital art style that attempts to combine the qualities of [[Pixel Art]] and [[3D Graphics]] together.

---

_Heavily inspired by the art of t3ssel8r._

#wip "Flexible Toon Shader"

## Debug Views

**Normals**: Displays the directions of [[Normal Map|normals]] by encoding them as colors.
Each axis is mapped to RGB color.

**Depth**: Grayscale distance map. Shows how far each visible pixel is from the camera.
Darker usually means closer, lighter usually means farther.

## Stepped Lighting

Pixel art often defines color palettes with multiple shades per color.

The idea is to take the initial lighting and define threshold values.
The lighting then clamps to the nearest threshold, giving it a step-like appearance.

## Edge Highlights

**Outer Highlights**: The shader looks for the depth information for a particular pixel on the screen and compares it to its surrounding points.
If the difference in depth between the original and each of its neighbors hits a certain threshold, it sets that pixel as an edge, mixing the original pixel color of that pixel with your highlight color.

**Inner Highlights**: For each pixel, the shader checks the surface direction (otherwise known as the 'normal'), again comparing it to surrounding points. This time however, it's looking for changes in the angle between normals, like you would see at an edge or a corner.
Calculating the dot product of the original point and each of its neighbors tells us about their alignment relative to eachother.
This is then checked against a threshold to determine if the pixel qualifies as an edge or not.

**Bonus**: To elevate this even further, we can use the attenuation of the light shader to lighten or darken edges based on their lighting information.

## Models

#wip
