---
context:
  - "[[Zig]]]"
---

# Zig Safety

Safety mechanisms in Zig.

---

**No Shadowing**: Variable identifiers are never allowed to shadow identifiers from an outer scope.

```zig
const something: i32 = 42;

pub fn main() void {
    const something: bool = false; // ERROR
}
```
