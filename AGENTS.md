# AGENTS.md

This file tells AI how to work in this vault.

## Scope

- Durable notes live in `nodes/`.
- Root files prefixed with `_` are system files. See `_System.md`.
- Do not invent new folder structures, databases, or taxonomies.

## Core System

- Create nodes, link them, let structure emerge.
- Prefer atomic notes.
- Every note must have context.
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
8. Add `tags:` only when they are actually useful.
9. Add `#wip` or keep `#empty` only if the note really needs them.

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
