---
context:
  - "[[TUI Application]]"
  - "[[Artificial Intelligence]]"
---

# OpenCode

OpenCode is an [[Open Source]] [[Artificial Intelligence|AI]] coding agent.

[Opencode Website](https://opencode.ai/)
[Opencode Github](https://github.com/anomalyco/opencode/)

---

## Modes

- **Plan**: Use for reasoning and asking questions.
- **Build**: Use for code generation.

## Planning and Action

The currently recommended way to divide the process into two steps:

1. **Plan**: Use `Plan mode` to first think about a plan. Describe what you want it to do. Give it enough context and clear goals. Iterate over the plan.
2. When the plan is good enough, switch to `Build mode` and ask it to execute said plan.

For simpler changes, you can ask OpenCode to directly build without having to review the plan first.

## Undo

Use the `/undo` command to undo previous changes, and OpenCode will revert them.

You can `/undo` multiple times to undo multiple changes.

Use `/redo` to redo the changes back.

## Share

Use `/share` to get a URL of the session copied to your clipboard.
Use `/unshare` to invalidate the link.
