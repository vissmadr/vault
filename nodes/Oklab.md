---
aliases:
  - OKLab
context:
  - "[[Computer Graphics]]"
---

# Oklab

Perceptual [[Color Space]] designed so numerical color changes better match human color perception.

---

Oklab separates color into lightness and two opponent color axes.

- `L`: Perceived lightness.
- `a`: Green-red axis.
- `b`: Blue-yellow axis.

Unlike raw RGB values, similar distances in Oklab tend to produce similar perceived color differences.

Useful for:

- Smooth color interpolation.
- Generating palettes.
- Adjusting lightness without shifting hue as much.
- Working with colors in a more perceptually uniform way.

See [[Oklch]].

## CSS

CSS supports Oklab with the `oklab()` color function.

Example:

```css
color: oklab(70% 0.1 0.05);
```

The values are usually written as `L a b`.
