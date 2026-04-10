# AGENTS.md

This file tells AI how to work in this vault.

## Scope

- Durable notes live in `nodes/`.
- Root files prefixed with `_` are system files. See `_System.md`.
- Do not invent new folder structures, databases, or taxonomies.

## Core System

- Create nodes, link them, let structure emerge.
- Prefer atomic notes.
- Every note includes a `context:` field.
- `context:` may be empty when there is no appropriate parent concept yet.
- Multiple parent concepts in `context:` are normal.
- Improve notes over time instead of overdesigning structure up front.

## Default AI Behavior

- Search `nodes/` before creating a new note.
- If the concept already exists, update the existing note instead of creating a duplicate.
- Prefer the smallest useful edit.
- Be concise by default.
- If one sentence and a few bullets are enough, stop.
- Do not pad notes to make them feel complete.

## Required Note Template

The canonical human template is `templates/_Template.md` and should stay unchanged:

```md
---
aliases:
context:
---

#empty

# {{title}}

ad

---
```

Rules:

- Filename must exactly match the H1 title.
- `context:` is always present, but it may be empty.
- `aliases:` is always present and may be empty.
- `tags:` is optional.
- If `tags:` is used, it goes before `aliases:`.
- Use multiple `context:` parents when helpful.
- When AI creates a note, it may write the literal final title instead of relying on `{{title}}`.
- AI usually creates notes with real content, so it should usually replace `#empty` and `ad` instead of keeping them.

## Writing Style

- Write plainly, directly, and practically.
- Prefer short definitions, short paragraphs, bullets, formulas, examples, tables, and code when they compress meaning.
- Avoid generic AI tone, padded transitions, motivational filler, summaries, and conclusions.
- Do not over-explain obvious things.
- Do not turn concise notes into essays.
- Match the local style of the note when extending an existing one.

## Linking

- Links are the main structure.
- Add links to broader parent concepts and directly relevant related concepts.
- Prefer exact existing note names.
- Do not spam links on every term.

## Status Markers

- `#wip` can be placed freely anywhere something still needs work.
- `#empty` means the note exists but is not really started yet.
- Do not remove `#wip` or `#empty` unless the note state has actually changed.
- AI should only keep or add `#empty` when creating an intentional stub or placeholder.

## Tags

- Use tags sparingly.
- Tags are optional.
- Existing tag patterns include `original`, `data`, `article`, `essay`, `book`, `journal`, `code`.
- Do not invent lots of new tags.

## Creating Notes

1. Search for an existing note first.
2. Reuse or extend an existing note if the idea already belongs there.
3. Create a new note only if the idea is meaningfully distinct.
4. Use the same structure as `templates/_Template.md`.
5. Set `context:` with the closest broader parent concept or concepts when appropriate. Leave it empty if there is no good parent yet.
6. Write the shortest useful version of the note.
7. For notes with content, usually replace `#empty` and `ad` with the real opening sentence and body.
8. Very short notes do not need an extra `---` section after the opening sentence.
9. If the whole note is only the sententia or a couple short lines, stop there.
10. Add `tags:` only when they are actually useful.
11. Add `#wip` or keep `#empty` only if the note really needs them.

## Updating Notes

- Preserve the existing voice unless asked to rewrite it.
- Do not sanitize blunt phrasing into generic polished prose.
- Keep useful raw fragments in project notes if they still carry meaning.
- Do not expand a short note unless the extra detail clearly improves usefulness.
- Keep filename and H1 identical.

## Root System Files

- Files starting with `_` in the root are system files, not normal nodes.
- Use them for system-wide notes, scratch capture, planning, calendar, devlog, quotes, and similar root-level material.
- New durable concept notes should go in `nodes/`.

## Examples

These are good examples of the local note style and note shape.

They are style examples from the vault, not a replacement for the structural rules above.

Very short notes like `API`, `AI Model`, and `Game Development` show that not every note needs a body separator after the opening sentence.

### Weighted A-Star Algorithm

```md
---
context:
  - "[[A-Star Algorithm]]"
---

# Weighted A-Star Algorithm

Variation of the [[A-Star Algorithm]] that uses scalar weights in order to bias its heuristic function.

---

See [[A-Star Algorithm#Bounded Relaxation]].

Biasing the heuristic function can speed up the search process at the expense of admissibility.

`F(n) = X * G(n) + H(n)`, where `X` is an arbitrary weight value.
If `X > 1`, the algorithm becomes biased towards nodes that are closer to the goal.
```

### Vector

```md
---
context:
  - "[[Mathematics]]"
  - "[[Linear Algebra]]"
---

# Vector

Abstract multidimensional quantity.

---

Entity with both magnitude and direction.

Ordered collection of numbers used together as a single entity.

**Components**: A vector itself is defined by its components. The number of components determines its dimension.

**Equality**: Two vectors are equal only if all corresponding components are identical.

**Etymology**: A vector is what is needed to "carry" the point `A` to the point `B`. The Latin translation of 'vector' means 'carrier'.

See [[Vector Operations]]

## Interpretation

**Abstraction**: Vectors are a versatile abstraction, capable of describing various types of information, with their meaning defined by context.

**Multidimensional**: Vectors represent multidimensional quantities that cannot be fully described by a single [[Scalar]] alone.

For example the vector `<5, 60>` can be used to represent:

- Ordered pair of the numbers `5` and `60`.
- Location in space where `x: 5` and `y: 60`.
- Force with a magnitude of `5`, directed at `60` degrees.

## Representation

Graphically represented as a directed line segment (an arrow) in space.

- _Tail_: Starting point of the vector.
- _Head_: Ending point of the vector.
- _Direction_: Orientation of the arrow.
- _Magnitude_: Length of the arrow.

## Magnitude

The magnitude of a vector is a scalar quantity representing its length, independent of direction.

**Hypotenuse**: When a vector is positioned with its tail at the origin, the line segment from the origin to the vector's head forms the hypotenuse of a right triangle with legs along the coordinate axes. This hypotenuse is the magnitude (length) of the vector.

**Calculating Magnitude**: To calculate the magnitude, use the [[Pythagorean Theorem]]:

```
x² + y² = magnitude²

magnitude = √(x² + y²)
```

- For example, the vector `<4, 3>` has a magnitude of `5`.

**Always Positive**: The formula does not produce negative values. This is a good feature as a negative magnitude wouldn't make much sense.

## Mathematical Foundation

_The vector space defines the rules, while the coordinate system provides the framework._

**Vector Space**: Vectors exist within the axiomatic framework of a [[Vector Space]], which defines the rules for vector operations and ensures consistency across different vector implementations.

**Coordinate Systems**: Vectors are typically represented and manipulated using a [[Coordinate System]] which provides a geometric interpretation of vector components.

**Basis Vectors**: Any vector can be represented by a linear combination of [[Basis Vectors]] that define the coordinate system's axes.
```

### Ubuntu

```md
---
context:
  - "[[Linux Distribution]]"
---

# Ubuntu

Popular, user-friendly [[Linux Distribution]] based on [[Debian]].

---

**Packages**: Uses the [[APT (Package Manager)|APT package manager]] and `.deb` packages.

**Desktop**: Uses GNOME as its default desktop environment.

**Preconfigured**: Wide range of pre-installed software and tools.

**Updates**: Regular releases every 6 months, with LTS versions every 2 years.
```

### Arch

```md
---
context:
  - "[[Linux Distribution]]"
---

# Arch

Lightweight linux distribution known for its simplicity and minimalism.

---

**Wiki**: The [Arch Wiki](https://archlinux.org) is an extensive community-built documentation.

**Control**: Aimed at advanced users wanting to reach full control and extreme performance.

**Customization**: The minimalistic DIY approach enables the user to configure from the ground up, customizing everything along the way.

**Packages**: Follows a rolling-release model, providing up-to-date software. Uses [[Pacman (Package Manager)|pacman]] as the core package manager.
```

### Triangle Mesh

```md
---
context:
  - "[[Computer Graphics]]"
---

# Triangle Mesh

Set of [[Triangle|Triangles]] connected by their common edges or vertices.

---

Essential to [[Computer Graphics]], where complex shapes and models are commonly represented by a set of connected triangles.

## Components

**Vertices**: Points in 3D space. Each triangle has exactly three vertices. Each vertex may be shared by multiple triangles. The _valence_ of a vertex refers to how many faces are connected to the vertex.

**Edges**: An edge connects two vertices. Each triangle has three edges.

**Faces**: The surfaces of the triangles themselves.

## Storage

One standard data storage format is the _indexed triangle mesh_.

Consists of two lists:

- **Vertices List**: Stores the position coordinates of vertices.
- **Triangles List**: Stores triangles by three integers for each, where the integers index into the vertices list.

Additional data per vertex is also commonly stored.
```

### Sway

```md
---
context:
  - "[[Window Manager]]"
---

# Sway

Tiling [[Window Manager]] and [[Wayland]] compositor.

---

Lightweight, keyboard-driven, and highly customizable.

**i3**: Designed as a modern [[i3]] replacement.
```

### Skewer (Chess Tactic)

```md
---
aliases:
  - Skewer
context:
  - "[[Chess Tactic]]"
---

# Skewer (Chess Tactic)

When an attacked piece has to move and expose a less-valuable piece to the same attack.

---

**Absolute Skewer**: An absolute skewer is when the attacked piece is a King, and is legally forced to move, exposing the piece behind it.
```

### Service

```md
---
context:
  - "[[Software Architecture]]"
---

# Service

Managed background process that provides specific functionality to the system or users.

---

**Persistency**: Services run persistently, often starting at boot.

**Autonomous**: Operates in the background without direct user interaction. No controlling terminal.

**Lifecycle**: Services follow a lifecycle, for example `start`, `stop`, `restart`, `reload`.

**OS Supervision**: Services are supervised and managed by different service managers, depending on the [[Operating System|OS]].

**Daemon**: Service are usually used to wrap and manage [[Daemon]] programs.
```

### AI Model

```md
---
context:
  - "[[Artificial Intelligence]]"
  - "[[Software]]"
---

# AI Model

Software system trained on data in order to gain knowledge and change behavior.
```

### API

```md
---
aliases:
  - Application Programming Interface
context:
  - "[[Software]]"
---

# API

(Application Programming Interface)

Responsible for the communication between software.

Allows two or more computer programs to communicate with each other.

See: [[Interface]]
```

### Game Development

```md
---
context:
  - "[[Software Development]]"
  - "[[Game]]"
---

# Game Development

The multidisciplinary process of designing and creating a [[Game]].
```
