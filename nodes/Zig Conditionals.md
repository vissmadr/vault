---
context:
  - "[[Zig]]"
---

# Zig Conditionals

Conditional logic in Zig.

---

Zig's if statements accept boolean values: `true` or `false`.

**No Coercion**: Unlike other languages, there are no values that implicitly coerce to boolean values.

**No Ternary**: The ternary conditional operator (`cond ? a : b`) does not exist in Zig.

**If Expressions**: If statements also work as expressions: `x += if (a) 1 else 2;`
