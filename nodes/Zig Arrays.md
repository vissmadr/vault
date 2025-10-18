---
context:
  - "[[Zig]]"
  - "[[Array]]"
---

# Zig Arrays

Arrays in Zig.

---

Arrays are denoted by `[N]T`, where `N` is the number of elements in the array, and `T` is the type of those elements.

```zig
const a = [5]u8{ 'h', 'e', 'l', 'l', 'o' };
const b = [_]u8{ 'w', 'o', 'r', 'l', 'd' };
```

To get the size of the array, access the array's `len` field:

```zig
const a = [5]u8{ 'h', 'e', 'l', 'l', 'o' };
const length = a.len;
```
