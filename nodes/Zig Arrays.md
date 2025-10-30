---
context:
  - "[[Zig]]"
  - "[[Array]]"
---

# Zig Arrays

Arrays in Zig.

---

Array elements are stored contiguously in memory with no implicit padding inbetween.

Arrays are denoted by `[N]T`, where `N` is the number of elements in the array, and `T` is the type of those elements. `N` can also be `_` to infer the array size.

```zig
const arr = [5]u8{ 10, 20, 30, 40, 50 };
const arrInfer = [_]u8{ 10, 20, 30, 40, 50 };
const arrExplicit: [5]u8 = [5]u8{ 10, 20, 30, 40, 50 };
```

Use the built-in `@splat` function to convert a scalar into a vector:

## Length

To get the size of the array, access the array's `len` field:

```zig
const arr = [5]u8{1, 2, 3, 4, 5};
const length = arr.len; // 5
```

## Splat

Use the built-in `@splat` function to convert number into an array where each element is the number:

```zig
const arr: [4]i32 = @splat(42);
```

- The array type and length are inferred.

## Multidimensional Arrays

Multidimensional arrays can be created by nesting arrays:

```zig
const eightColors = [8][3]u8{
    [3]u8{ 100, 100, 100 },
    [3]u8{ 100, 100, 100 },
    [3]u8{ 100, 100, 100 },
    [3]u8{ 100, 100, 100 },
    [3]u8{ 100, 100, 100 },
    [3]u8{ 100, 100, 100 },
    [3]u8{ 100, 100, 100 },
    [3]u8{ 100, 100, 100 },
};

print("Sixth Color Red Value: {d}\n", .{eightColors[5][0]});
```

## Copy

Arrays are first-class elements.

The syntax `const arrB = arrA` performs a deep copy of all elements.

```zig
var arrA = [5]u8{ 100, 100, 100, 100, 100 };

var arrB = arrA;

arrA[0] += 5;
arrB[2] += 1;
arrB[3] += 1;
arrB[4] += 1;

print("arrA: {s}\n", .{arrA});
print("arrB: {s}\n", .{arrB});

// Output:
// arrA: idddd
// arrB: ddeee
```

## Destructuring

Arrays can be destructured:

```zig
const color = [3]u8{ 101, 102, 103 };

const R, const G, const B = color;

print("RGB({d}, {d}, {d})\n", .{ R, G, B });

const eightColors = [8][3]u8{
    [3]u8{ 100, 101, 110 },
    [3]u8{ 100, 102, 120 },
    [3]u8{ 100, 103, 130 },
    [3]u8{ 100, 104, 140 },
    [3]u8{ 100, 105, 150 },
    [3]u8{ 100, 106, 160 },
    [3]u8{ 100, 107, 170 },
    [3]u8{ 100, 108, 180 },
};

const thirdRed, const thirdGreen, const thirdBlue = eightColors[2];

print("RGB({d}, {d}, {d})\n", .{ thirdRed, thirdGreen, thirdBlue });

// Output:
// RGB(101, 102, 103)
// RGB(100, 103, 130)
```
