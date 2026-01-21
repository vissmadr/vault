---
context:
  - "[[Zig]]"
---

# Zig Slices

Slices in Zig.

---

Slices contain two pieces of information:

1. **Pointer**: A pointer to the start of a contiguous sequence of elements.
2. **Length**: The number of elements.

**Syntax**: `[]T` or `[]const T`

| Type             | Syntax  | Size Known         | Length Stored | Bounds Checked |
| ---------------- | ------- | ------------------ | ------------- | -------------- |
| Array            | `[n]T`  | Compile-time (`n`) | No (implicit) | Yes            |
| Pointer to Array | `*[n]T` | Compile-time (`n`) | No (implicit) | Yes            |
| Slice            | `[]T`   | Runtime            | Yes (`.len`)  | Yes            |
