---
context:
  - "[[Color Space]]"
  - "[[Computer Graphics]]"
---

# HSL

[[Color Space|Color model]] that represents colors with hue, saturation, and lightness.

---

HSL is a cylindrical representation of [[RGB]] designed to be easier for humans to adjust directly.

- `H`: Hue angle, usually measured in degrees.
- `S`: Saturation, or how colorful the color is.
- `L`: Lightness, from black through the color to white.

Example:

```css
color: hsl(220 80% 55%);
```

## Components

**Hue**: Selects the base color around a color wheel.

**Saturation**: Controls how gray or vivid the color is. `0%` saturation is grayscale.

**Lightness**: Controls how dark or bright the color is. `0%` is black, `50%` is the normal color, and `100%` is white.

## Use

HSL is useful for quick manual color edits, especially in CSS.

It is less useful for perceptual color work because equal HSL changes do not produce equal perceived color changes.

See [[Oklch]] for a more perceptual lightness, chroma, and hue model.
