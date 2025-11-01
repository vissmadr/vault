---
context:
  - "[[Zig]]"
  - "[[Enumeration]]"
---

# Zig Enum

Enums in Zig.

---

```zig
const Fruit = enum{ apple, pear, orange };
```

Enums are really just a set of numbers. You can leave the numbering up to the compiler, or you can assign them explicitly. You can even specify the numeric type used.

```zig
const Stuff = enum(u8){ foo = 16 };
```

You can get the integer out with the built-in function `@intFromEnum()`:

```zig
const Animal = enum {
    dog,
    cat,
    raven,
    snake,
    turtle,
    pigeon,
    lizard,
    fox,
    wolf,
    sheep,
    bull,
};

print("enum value: {}\n", .{@intFromEnum(Animal.wolf)});

// Output:
// enum value: 8
```
