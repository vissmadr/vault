---
context:
  - "[[Zig]]"
  - "[[Vector]]"
---

# Zig Vectors

Vectors in Zig.

---

The vector in Zig is a group of booleans, integers, floats, or pointers

Vectors are operated on in parallel using [[SIMD]] instructions if possible.

Created with the built-in `@Vector` function:

```zig
const vec = @Vector(4, u8){ 10, 20, 30, 40 };
```

## Splat

Use the built-in `@splat` function to convert a scalar into a vector:

```zig
const vec: @Vector(4, i32) = @splat(42);
```

- The vector type and length are inferred.

## Reduce

Use the built-in `@reduce` function to reduce a vector into a scalar:

```zig
const vA = @Vector(3, i32){ 10, 20, 30 };

print("Mul: {}\n", .{@reduce(.Mul, vA)});
print("Min: {}\n", .{@reduce(.Min, vA)});
print("Max: {}\n", .{@reduce(.Max, vA)});
print("Add: {}\n", .{@reduce(.Add, vA)});
print("And: {}\n", .{@reduce(.And, vA)});
print("Xor: {}\n", .{@reduce(.Xor, vA)});
print("Or: {}\n", .{@reduce(.Or, vA)});

// Output:
// Mul: 6000
// Min: 10
// Max: 30
// Add: 60
// And: 0
// Xor: 0
// Or: 30
```

## Operators

Vectors generally support the same built-in operators as their underlying base types.

- The exception to this are the keywords `and` and `or` on vectors of booleans, since these operators affect control flow, which is not allowed for vectors.

All operations are performed element-wise, and return a vector of the same length as the input vectors.

This includes:

- **Arithmetic** `+`, `-`, `/`, `\*`, `@divFloor`, `@sqrt`, `@ceil`, `@log`, etc.
- **Bitwise operators** `>>`, `<<`, `&`, `|`, `~`, etc.
- **Comparison operators**: `<`, `>`, `==`, etc.
- **Boolean not**: `!`
