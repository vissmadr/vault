---
context:
  - "[[Color Space]]"
  - "[[Computer Graphics]]"
---

# RGB

Additive [[Color Space|color model]] with red, green, and blue as primary colors.

---

The primary colors can be mixed together to produce a broad array of colors.

- `R`: Red component.
- `G`: Green component.
- `B`: Blue component.

Each component describes how much of that primary color is emitted.

While not perfect, the RGB model is sufficient enough for humans.

Heavily used to represent color with [[Hardware]] devices due to its simplicity.

## Additive Color

RGB is additive: more light means a brighter color.

- No light produces black.
- Full red, green, and blue together produce white.
- Red and green produce yellow.
- Green and blue produce cyan.
- Blue and red produce magenta.

## Digital Representation

RGB values are commonly stored as integers from `0` to `255` per channel.

```txt
rgb(255, 0, 0) = red
rgb(0, 255, 0) = green
rgb(0, 0, 255) = blue
rgb(255, 255, 255) = white
rgb(0, 0, 0) = black
```

Normalized graphics APIs often use values from `0.0` to `1.0` instead.

## Limitations

RGB is device-oriented, not perceptually uniform.

Changing RGB values by the same numerical amount does not always produce the same perceived color change.

See [[Oklab]] and [[Oklch]] for more perceptual color spaces.
