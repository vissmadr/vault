---
context:
  - "[[Zig]]"
---

# Zig Assignment

Assignment in [[Zig]].

---

`(const|var) identifier: type = value`

- `const`: indicates that `identifier` is a constant that stores an immutable value.
- `var`: indicates that `identifier` is a variable that stores a mutable value.
- `: type`: is a type annotation for `identifier`, and can be omitted if the data type of `value` can be inferred.

```zig
const constantInteger: i32 = 42;
var mutableInteger: i32 = 42;
```

Where possible, `const` values are prefered over `var` values.

**Undefined**: Constants and variables must have a value. If no known value can be given, the `undefined` value, which coerces to any type, may be used as long as a type annotation is provided.

```zig
const a: i32 = undefined;
var b: u32 = undefined;
```
