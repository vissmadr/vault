---
context:
  - "[[Zig]]"
---

# Zig Defer

The `defer` statement in Zig.

---

Allows to postpone the execution of a statement until the end of the current scope.

Designed to ensure that resource cleanup or other final actions happen reliably, no matter how the scope is exited (normally, via a return, or even if an error occurs).

```zig
defer some_expression;
```

**LIFO**: Multiple `defer` statements follow the LIFO (Last In First Out) principle, executing from bottom to top, with the last `defer` statement executing first.

```zig
fn multiple() void {
    print(1);
    print(2);
    defer print(6);
    defer print(5);
    print(3);
    defer print(4);
}

// Output: 1, 2, 3, 4, 5, 6
```

**Error Defer**: An `errdefer` is a defer that only runs if the block exits with an error.

```zig
{
    errdefer cleanup();
    try canFail();
}
```
