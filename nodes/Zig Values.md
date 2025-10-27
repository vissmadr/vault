---
tags:
  - "data"
context:
  - "[[Zig]]"
  - "[[Data Type (Computer Science)]]"
---

# Zig Values

Values in Zig.

[Documentation](https://ziglang.org/documentation/master/#Values)

---

## Primitive Types

| Type             | C Equivalent        | Description                                                                     |
| ---------------- | ------------------- | ------------------------------------------------------------------------------- |
| `i8`             | `int8_t`            | signed 8-bit integer                                                            |
| `u8`             | `uint8_t`           | unsigned 8-bit integer                                                          |
| `i16`            | `int16_t`           | signed 16-bit integer                                                           |
| `u16`            | `uint16_t`          | unsigned 16-bit integer                                                         |
| `i32`            | `int32_t`           | signed 32-bit integer                                                           |
| `u32`            | `uint32_t`          | unsigned 32-bit integer                                                         |
| `i64`            | `int64_t`           | signed 64-bit integer                                                           |
| `u64`            | `uint64_t`          | unsigned 64-bit integer                                                         |
| `i128`           | `__int128`          | signed 128-bit integer                                                          |
| `u128`           | `unsigned __int128` | unsigned 128-bit integer                                                        |
| `isize`          | `intptr_t`          | signed pointer sized integer                                                    |
| `usize`          | `uintptr_t, size_t` | unsigned pointer sized integer.                                                 |
| `c_char`         | `char`              | for ABI compatibility with C                                                    |
| `c_short`        | `short`             | for ABI compatibility with C                                                    |
| `c_ushort`       | `unsigned short `   | for ABI compatibility with C                                                    |
| `c_int`          | `int`               | for ABI compatibility with C                                                    |
| `c_uint`         | `unsigned int `     | for ABI compatibility with C                                                    |
| `c_long`         | `long`              | for ABI compatibility with C                                                    |
| `c_ulong`        | `unsigned long `    | for ABI compatibility with C                                                    |
| `c_longlong`     | `long`              | long for ABI compatibility with C                                               |
| `c_ulonglong`    | `unsigned long `    | long for ABI compatibility with C                                               |
| `c_longdouble`   | `long double `      | for ABI compatibility with C                                                    |
| `f16`            | `_Float16`          | 16-bit floating point (10-bit mantissa) IEEE-754-2008 binary16                  |
| `f32`            | `float`             | 32-bit floating point (23-bit mantissa) IEEE-754-2008 binary32                  |
| `f64`            | `double`            | 64-bit floating point (52-bit mantissa) IEEE-754-2008 binary64                  |
| `f80`            | `long double `      | 80-bit floating point (64-bit mantissa) IEEE-754-2008 80-bit extended precision |
| `f128`           | `_Float128`         | 128-bit floating point (112-bit mantissa) IEEE-754-2008 binary128               |
| `bool`           | `bool`              | `true` or `false`                                                               |
| `anyopaque`      | `void`              | Used for type-erased pointers.                                                  |
| `void`           | (none)              | Always the value `void{}`                                                       |
| `noreturn`       | (none)              | the type of `break`, `continue`, `return`, `unreachable`, and `while (true) {}` |
| `type`           | (none)              | the type of types                                                               |
| `anyerror`       | (none)              | an error code                                                                   |
| `comptime_int`   | (none)              | Only allowed for comptime-known values. The type of integer literals.           |
| `comptime_float` | (none)              | Only allowed for comptime-known values. The type of float literals.             |

**Arbitrary Bit-Width Integers**: In addition to the integer types above, arbitrary bit-width integers can be referenced by using an identifier of `i` or `u` followed by digits. For example, the identifier `i7` refers to a signed `7`-bit integer. The maximum allowed bit-width of an integer type is `65535`.

## Primitive Values

| Name               | Description                            |
| ------------------ | -------------------------------------- |
| `true` and `false` | boolean values                         |
| `null`             | used to set an optional type to `null` |
| `undefined`        | used to leave a value unspecified      |

## Strings

_**String Literals and Unicode Code Point Literals**_

String literals are constant single-item pointers to null-terminated byte arrays.

Dereferencing string literals convertd them to arrays.

### Escape Sequences

| Escape Sequence | Name                                                              |
| --------------- | ----------------------------------------------------------------- |
| `\n`            | Newline                                                           |
| `\r`            | Carriage Return                                                   |
| `\t`            | Tab                                                               |
| `\\`            | Backslash                                                         |
| `\'`            | Single Quote                                                      |
| `\"`            | Double Quote                                                      |
| `\xNN`          | hexadecimal 8-bit byte value (2 digits)                           |
| `\u{NNNNNN}`    | hexadecimal Unicode scalar value UTF-8 encoded (1 or more digits) |

### Multiline String Literals

Multiline string literals have no escapes and can span across multiple lines. To start a multiline string literal, use the `\\` token. Just like a comment, the string literal goes until the end of the line. The end of the line is not included in the string literal. However, if the next line begins with `\\` then a newline is appended and the string literal continues.

```zig
const helloWorldInC =
    \\#include <stdio.h>
    \\
    \\int main(int argc, char **argv) {
    \\    printf("hello world\n");
    \\    return 0;
    \\}
;
```

## Assignment

Use the `const` keyword to assign a constant value to an identifier.

Use the `var` keyword to assign a mutable value to an identifier.

```zig
pub fn main() void {
    const solid: i32 = 42;

    var fluid: i32 = 1234;
    fluid = 5678;
}
```

### Undefined

Use `undefined` to leave variables uninitialized:

```zig
pub fn main() void {
    var value: i32 = undefined;

    value = 42;
    print("{}\n", .{value}); // 42
}
```

The `undefined` variable can be coerced to any type. Once this happens, it is no longer possible to detect that the value is `undefined`.

The meaning of `undefined` is that a value could be anything, even something that is nonsense according to the type.

### Destructure

The destructuring assignment can separate elements of indexable aggregate types:

```zig
fn destructure() void {
    var x: i32 = undefined;
    var y: i32 = undefined;
    var z: i32 = undefined;

    const tuple = .{ 10, 20, 30 };

    x, y, z = tuple;

    print("{d}\n", .{x}); // 10
    print("{d}\n", .{y}); // 20
    print("{d}\n", .{z}); // 30

    const array = [_]i32{100, 200, 300};

    x, y, z = array;

    print("{d}\n", .{x}); // 100
    print("{d}\n", .{y}); // 200
    print("{d}\n", .{z}); // 300

    const vector: @Vector(3, i32) = .{1000, 2000, 3000};

    x, y, z = vector;

    print("{d}\n", .{x}); // 1000
    print("{d}\n", .{y}); // 2000
    print("{d}\n", .{z}); // 3000

    comptime const vx, _, const vz: i32 = vector;

    print("{d}\n", .{vx}); // 1000
    print("{d}\n", .{vz}); // 3000
}
```

A destructuring expression may only appear within a block.

The left hand side of the assignment must consist of a comma separated list, each element of which may be either an lvalue (for instance, an existing `var`) or a variable declaration.

A destructure may be prefixed with the `comptime` keyword, in which case the entire destructure expression is evaluated at comptime. All vars declared would be comptime vars and all expressions (both result locations and the assignee expression) are evaluated at comptime.
