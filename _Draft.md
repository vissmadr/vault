**mel0ndev**: ECS is great; I would recommend not making any UI part of the ECS if you can help it

# Throttling

What a great performance booster wow.

# Terminal

Ctrl+T

# Overhaul

## Abilities

`3` buttons for `2` + `3`, or `2` + `9` total abilities.

## Classes

**Base**: Attack, Dash, 3 abilities

**Invoker**: Attack, Dash, 9 abilities

**Modes**: Attach, Dash, 3 modes

- Could be "weapons arsenal"
- Could be "shapeshift forms"
- Could be "warrior stances"

# 3D to 2D Characters

Core Pipeline

1. Base humanoid model

One male base and one female base (or a single unisex base).

Keep proportions simple and readable at your final sprite size (e.g., 64–128 px tall).

Rig it with a standard humanoid skeleton.

2. Camera setup for isometric angles

Pick your directional set:

8-direction:

N, NE, E, SE, S, SW, W, NW
16-direction:

Same as above plus half-angles for smoother turns.

In Blender:

Create an orthographic camera.

Set it to your isometric angle (commonly 30–35° tilt, 45° rotation).

Duplicate the camera 8 or 16 times, each rotated around the character.

This ensures perfectly aligned sprite directions.

3. Animation set

For an ARPG, animate these once:

Core movement

Idle (loop)

Walk (loop)

Run (loop)

Combat

Basic melee attack

Basic ranged attack

Spellcast animations (1–2 variants)

Dodge/roll (optional)

Other

Hit-stun

Death

Special pose animations (optional)

Every animation will be rendered by all cameras automatically.

4. Modular gear system (attachment approach)

Model each gear piece as a separate mesh, skinned to the same skeleton:

Helmets

Chest armor

Pants/skirts

Boots

Gloves

Shoulders

Capes / back items

Weapons (melee, ranged)

Off-hand (shields, orbs)

Direct attachment to bones:

Weapons → hand bones

Armors → follow rig weights

Back items → spine or shoulder bone

Capes → separate bone chain or physics sim baked to keyframes before rendering

Because everything shares the same skeleton, every animation automatically works with every item.

5. Rendering pass

For each animation clip:

Play the animation.

For each frame, render from all cameras.

Output transparent PNGs.

Batch-assemble spritesheets.

Rendering passes should be consistent:

Same lighting

Same shadows

Same materials

Same camera FOV/ortho size

This makes all sprites consistent across characters.

6. Optional: Layered rendering (if you want runtime equipment changes)

Instead of baking a full combined character, you can render separate layers:

Body

Head

Hair

Armor

Weapons
Then, stack them at runtime.

This is heavier on your engine but allows dynamic item-swapping without regenerating sprites.

Production Tips
Keep the sprite readable

For Diablo-style readability:

Emphasize silhouette.

Keep armor shapes strong and uncluttered.

Avoid tiny details; use broad shading.

Keep the number of frames modest

Isometric games usually use:

6–8 frames per walk cycle

4–6 for attack

6–10 for run

More frames = smoother but larger spritesheets.

Use consistent lighting

ARPGs often use:

Single directional light

Optional subtle rim light

Neutral ambient

This creates readable silhouettes from all angles.

---

TODO: https://www.method.gg/fellowship/heroes/meiko/playstyle-and-rotation

Fuck Y/D and distractions!

---

Spellblade - Movement WHILE attacking.

TODO: `Ctrl a` in insert?

**Raylib Performance**: https://youtu.be/aRTi7D4V0Yg

**Mixamo - Blender - Raylib - GLTF**: https://www.youtube.com/watch?v=MYaIodlxHrk

Learn from Galactic Assault Squad [GAS](https://gasgame.net/)
Learn from ISOCORE
Learn from 9kings
Learn from Stoneshard
Learn from Death Must Die (!)
Check out Drova: Forsaken Kin

Amit Patel RPG probability

**rTexPacker**: https://raylibtech.itch.io/rtexpacker

**3D Animation Pack**: https://quaternius.itch.io/universal-animation-library
