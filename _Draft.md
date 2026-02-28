## The problem

Your game runs on monitors of different sizes (720p, 1080p, 1440p, 4K) and different aspect ratios (16:9, 4:3, 21:9). You need every player to have a consistent gameplay experience, sharp visuals, and you want to apply screen-wide shader effects (bloom, vignette, etc.).

## The solution in one sentence

Render the game scene into a texture the same size as the screen, then draw that texture onto the screen (applying shader effects in the process), then draw the GUI on top.

## Why a texture in between?

Without the texture, your game draws directly to the screen. That works fine for the game world, but if you want a screen-wide shader effect like bloom or vignette, the shader needs to read the entire finished scene as input. It can't do that if the scene is being drawn directly to the screen piece by piece. The RenderTexture captures the finished scene as an image, which the shader can then process as a whole.

## How different monitors see the game

You pick one fixed number: **how many game units are visible vertically**. That's your current `gameHeight = 540`. This never changes regardless of monitor.

The camera zoom is:

```
zoom = screenHeight / 540
```

On a 1080p monitor: zoom = 2.0. Each game unit = 2 screen pixels.
On a 4K monitor: zoom = 4.0. Each game unit = 4 screen pixels. Sharper, same gameplay view.

Horizontally, the visible width adapts to the monitor's aspect ratio:

```
visibleWidth = screenWidth / zoom
```

On 16:9 (1920x1080): 1920 / 2.0 = 960 game units wide.
On 4:3 (1024x768): 1024 / 1.42 = 720 game units wide. Narrower, but no black bars.
On 21:9 (3440x1440): 3440 / 2.67 = 1290 game units wide. Wider, sees more.

Everyone sees the same amount vertically. Wider monitors see more horizontally. The player is always centered, so this is natural and fair.

## What happens each frame

Three phases:

**Phase 1 - Render game world into the texture**

Create a RenderTexture that's the same size as the screen. All game drawing (tiles, enemies, player, projectiles, damage numbers) goes here, using the Camera2D with the zoom described above. This is your complete game scene as an image.

**Phase 2 - Draw the texture to the screen**

Draw that texture fullscreen. Since it's the same size as the screen, this is a 1:1 copy. But here's where you can wrap it with a post-processing shader. The shader receives the entire scene as a texture and can apply bloom, vignette, color grading, screen shake (offset the draw position), chromatic aberration, or whatever you want. Without a shader, it's just a straight copy.

**Phase 3 - Draw GUI to the screen**

GUI draws directly to the screen in screen pixels, on top of everything. It doesn't go through the camera or the texture. To make GUI elements the same proportional size on every monitor, you multiply all sizes by a scale factor:

```
uiScale = screenHeight / 540
```

A 32-unit icon becomes 64px on 1080p, 128px on 4K. Same proportional size on screen.

## What changes in your code

**`config.zig`** - Remove `gameWidth` (it's now computed from the aspect ratio, not fixed). Keep `gameHeight = 540`.

**`window.zig`** - Manages the RenderTexture. Creates it at screen size, recreates it when the window resizes. Exposes the zoom, uiScale, and adaptive gameWidth as getters.

**`camera.zig`** - Zoom becomes `screenHeight / 540` instead of `@min(displayW/gameW, displayH/gameH)`. Functionally similar, just cleaner and always height-anchored.

**`main.zig`** - The render function wraps game drawing in RT begin/end, then draws the RT to screen, then draws GUI.

**`gui.zig`** - All hardcoded pixel sizes (icon size 64, text size 18, padding values) multiply by `uiScale`.

**`input.zig`** - No changes. The F1-F5 window resize keys work the same, RT recreation happens internally in window.zig.

## What doesn't change

All game logic, physics, collision, entity rendering, TOML data, asset loading, shaders you already have. The game world rendering code inside the camera block is identical - it still draws in game units and the camera handles the mapping. The only structural change is *where* those draws end up (a texture instead of directly to the screen).
