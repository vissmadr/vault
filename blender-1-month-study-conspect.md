# Blender 1 Month Study Conspect

This is a project-specific study plan for learning enough Blender to produce low-poly top-down 3D game assets, simple VFX meshes, and Mixamo-style animated characters.

This is a planning note, not canonical current-code documentation.

---

## Goal

After one month at 1-2 hours per day, be able to:

- model simple low-poly characters, enemies, weapons, props, and terrain pieces
- use clean scale, origins, pivots, naming, and transforms
- create simple materials or texture-atlas-friendly assets
- prepare humanoid characters for Mixamo-style auto-rigging
- import/export FBX and GLB reliably
- test assets quickly in the Raylib prototype/game
- use AI as a tutor, critic, prompt generator, checklist maker, and pipeline assistant

Do not aim to become a general 3D artist. Aim to build a repeatable asset pipeline for this game.

---

## What To Ignore

Avoid these for the first month unless directly needed:

- realistic sculpting
- high-poly to low-poly baking
- advanced shader nodes
- cloth, hair, fluid, and physics simulation
- advanced rigging systems
- facial animation
- complex procedural geometry nodes
- realistic lighting/rendering for final offline renders

---

## Core Style Target

Use a top-down readable low-poly style:

- large silhouettes
- exaggerated weapons and shoulders
- strong color separation
- simple materials
- low material count
- readable animations over realistic animations
- asset scale consistent with the game camera

Suggested common enemy budget:

- 500-1500 triangles
- 15-40 bones if custom-rigged later
- 1 material if possible
- simple humanoid proportions if using Mixamo

---

## Daily Loop

Use this loop every day:

1. Watch or read one focused lesson for 15-30 minutes.
2. Build one small asset or one pipeline test for 45-90 minutes.
3. Export it and inspect scale/origin/materials.
4. Ask AI to critique the asset or pipeline checklist.
5. Write one short note: what worked, what broke, what to repeat.

The export/test loop matters more than making pretty portfolio assets.

---

## Week 1: Blender Refresher And Props

Focus:

- viewport navigation
- object mode vs edit mode
- selection modes
- move, rotate, scale
- apply transforms
- origins and pivots
- extrude, inset, bevel, loop cut, knife
- mirror modifier
- shade flat vs shade smooth
- simple material assignment
- GLB export basics

Deliverables:

- 5 rocks
- 5 crates/barrels/containers
- 5 trees/stumps/bushes
- 3 wall or ruin pieces
- 1 weapon silhouette test

Success criteria:

- every asset has clean origin placement
- every asset has applied scale
- every asset exports and reimports without obvious breakage
- each asset is visually readable from the intended camera angle

AI usage:

- ask AI for low-poly prop ideas in batches
- ask AI to make a per-asset export checklist
- screenshot assets and ask for silhouette/readability critique
- ask AI for ways to simplify geometry without losing identity

---

## Week 2: Terrain And Modular Environment

Focus:

- grid snapping
- modular floor pieces
- wall pieces
- cliffs/obstacles as visual meshes only
- props as reusable pieces
- material palettes
- texture atlas basics if needed
- importing/exporting multiple assets
- keeping terrain gameplay-flat even if visually 3D

Deliverables:

- 1 small arena scene in Blender
- 3 floor variants
- 3 wall variants
- 5 forest/ruin props
- 1 simple door/portal/reward pedestal mockup

Success criteria:

- terrain can be assembled from repeatable pieces
- visual obstacles match plausible 2D collision cells
- props do not require gameplay height
- material count stays low
- exported pieces are reusable in-engine

AI usage:

- ask AI for a modular kit list for one biome
- ask AI to critique whether pieces will tile/repeat well
- ask AI for naming conventions and folder layout
- ask AI to produce a CSV-to-3D visual mapping idea list

---

## Week 3: Characters And Mixamo Pipeline

Focus:

- simple humanoid modeling
- A-pose or T-pose setup
- joint topology for elbows, knees, shoulders, hips
- character forward direction
- rough proportional consistency
- FBX export to Mixamo
- Mixamo auto-rig markers
- downloading idle, walk, run, attack, hit, death
- importing Mixamo FBX back into Blender
- checking triangle count before and after rigging
- exporting GLB for Raylib

Deliverables:

- 1 player proxy model
- 1 enemy proxy model
- 1 weapon attachment or held weapon
- 3 Mixamo animation clips successfully applied
- 1 GLB with animation loaded in prototype/game

Success criteria:

- Mixamo does not materially change the visual triangle count
- deformation is acceptable from top-down camera
- animation is readable when small on screen
- root motion is avoided or stripped unless deliberately supported
- scale/orientation are consistent across exports

AI usage:

- ask AI for humanoid topology checklist for Mixamo
- ask AI to debug export/import symptoms
- ask AI to compare animation clip choices for gameplay readability
- ask AI to generate a per-character QA checklist

---

## Week 4: Game Asset Pipeline And VFX Meshes

Focus:

- repeatable Blender-to-game export process
- GLB material sanity
- simple VFX meshes
- ground decals as planes/rings
- slash arcs as curved strips or simple mesh cards
- projectile meshes and billboards
- attachment points using empties or named bones if needed
- asset naming and versioning
- quick in-engine validation

Deliverables:

- 1 complete enemy with idle/walk/attack/death
- 1 complete player proxy with idle/walk/attack
- 1 small terrain kit
- 5 gameplay VFX meshes/cards
- 1 written export checklist

Success criteria:

- assets load in Raylib without manual rescue work
- material count is controlled
- scale is predictable
- animation clips are identifiable
- models remain readable in the game camera
- the pipeline is repeatable enough to produce the next 10 assets faster

AI usage:

- ask AI to turn mistakes into a permanent checklist
- ask AI to generate asset QA prompts
- ask AI to review screenshots for readability and style consistency
- ask AI to draft small Blender Python helpers only after the manual workflow is understood

---

## Minimum Tutorial Set

Use tutorials as targeted input, not as endless passive watching.

Recommended sources:

- Blender Studio: Blender Fundamentals 4.5 LTS for official refresher material
- Grant Abbitt for beginner low-poly and stylized assets
- Imphenzia for fast ultra-low-poly game asset workflow
- Polygon Runway for stylized scene language and composition ideas
- Royal Skies for short practical rigging, animation, and retargeting explanations
- Blender Manual for reference on glTF, FBX, modifiers, armatures, UVs, and export settings

Suggested order:

1. Blender UI and navigation refresher.
2. Mesh modeling basics.
3. Modifiers, especially mirror and bevel.
4. Materials and simple color palettes.
5. UV basics only if texture atlas workflow is needed.
6. Import/export basics.
7. Basic armature and weight concepts.
8. Mixamo pipeline.
9. Simple VFX mesh/card creation.

---

## AI Power User Workflow

Use AI aggressively, but make the final judgment in-engine.

Good AI tasks:

- make daily assignments
- generate asset lists for a biome or class
- critique screenshots for silhouette and readability
- explain Blender errors and export settings
- produce checklists for rigging, Mixamo, GLB export, and Raylib import
- suggest low-poly simplifications
- generate Blender Python snippets for repetitive cleanup
- convert vague art direction into concrete modeling constraints

Bad AI tasks:

- deciding final asset quality without game-camera screenshots
- overcomplicating the rigging setup
- pushing advanced shaders before the basic pipeline works
- creating huge study plans that delay asset production
- replacing practical export/import testing with theory

Useful prompt patterns:

```txt
Critique this low-poly top-down game asset for silhouette, material clarity, and triangle waste. Assume it will be small on screen.
```

```txt
Give me a Blender checklist before exporting this humanoid to Mixamo. Focus on pose, transforms, topology, scale, and common failure modes.
```

```txt
I imported this Mixamo FBX back into Blender and want to export GLB for Raylib. Give me a minimal troubleshooting checklist.
```

```txt
Design a low-poly forest biome modular kit with 20 reusable assets for a top-down action RPG. Keep material count low.
```

---

## Export Checklist

Before export:

- apply scale and rotation where appropriate
- set origin intentionally
- remove hidden junk objects
- use clear object names
- keep material slots minimal
- check triangle count
- check forward direction
- check real size against game scale
- ensure normals look correct
- ensure character is in clean A-pose or T-pose for Mixamo
- ensure limbs have enough separation for auto-rigging

After export/import:

- reimport into a clean Blender scene
- verify scale
- verify orientation
- verify materials
- verify animation clips
- verify triangle count did not unexpectedly explode
- test in Raylib as soon as possible

---

## Final Month Outcome

The month is successful if you can produce this without major help:

- one low-poly enemy model
- one auto-rigged animation set
- one GLB that loads and animates in Raylib
- one small terrain kit
- several simple props
- several simple VFX meshes/cards
- one personal Blender-to-game export checklist

If this loop works, production art becomes iteration rather than research.
