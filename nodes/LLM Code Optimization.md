---
context:
  - "[[Software Development]]"
  - "[[Large Language Model (LLM)]]"
---

# LLM Code Optimization

Tips and guidelines to optimize AI LLM for software development purposes.

---

_Optimizing code for AI is largely the same as optimizing code for humans - except the penalties for ambiguity are higher._

**Optimal Style**: Idiomatic, conventional, explicit, boring, and internally consistent.

See: [[Cognitive Load Article]]

## Context

Provide desire and intent explicitly.

Prefer explicit code over implicit code.

## Consistency

_Conventions and idioms matter more than originality._

It's better to have a consistent way of doing things than having multiple different ways of doing thins, even if they seem better in theory.

_LLMs are trained on conventional code, not clever code._

Strongly preferred:

- Standard library patterns
- Idiomatic language constructs
- Widely used frameworks in canonical form

## Comments

_Comments help when they explain why, not what._

LLMs already know what code does syntactically.
