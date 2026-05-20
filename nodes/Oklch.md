---
aliases:
  - OKLCH
context:
  - "[[Oklab]]"
---

# Oklch

Polar form of [[Oklab]] using lightness, chroma, and hue.

---

Oklch represents the same [[Color Space|color space]] as Oklab, but expresses the two color axes as chroma and hue instead of `a` and `b`.

- `L`: Perceived lightness.
- `C`: Chroma, or color intensity.
- `h`: Hue angle.

This makes Oklch more intuitive for design work than Oklab.

Useful for:

- Creating color scales.
- Keeping hue stable while changing lightness.
- Increasing or decreasing saturation-like intensity with `C`.
- Building perceptually smoother palettes.

## Oklab Relationship

Oklab stores color with rectangular coordinates:

```txt
L, a, b
```

Oklch stores color with polar coordinates:

```txt
L, C, h
```

`C` and `h` are derived from the `a` and `b` axes.

## CSS

CSS supports Oklch with the `oklch()` color function.

Example:

```css
color: oklch(70% 0.15 220);
```

The values are usually written as `L C h`.
