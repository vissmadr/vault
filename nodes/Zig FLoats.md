---
context:
  - "[[Zig]]"
---

# Zig FLoats

Floats in Zig.

---

Zig has the following floating point types:

| Type           | Description                                |
| -------------- | ------------------------------------------ |
| `f16`          | IEEE-754-2008 binary16                     |
| `f32`          | IEEE-754-2008 binary32                     |
| `f64`          | IEEE-754-2008 binary64                     |
| `f80`          | IEEE-754-2008 80-bit extended precision    |
| `f128`         | IEEE-754-2008 binary128                    |
| `c_longdouble` | matches `long double` for the target C ABI |

## Float Literals

Float literals have type `comptime_float` which is guaranteed to have the same precision and operations of the largest other floating point type, which is `f128`.

Float literals coerce to any floating point type, and to any integer type when there is no fractional component.

```zig
const floating_point = 123.0E+77;
const another_float = 123.0;
const yet_another = 123.0e+77;

const hex_floating_point = 0x103.70p-5;
const another_hex_float = 0x103.70;
const yet_another_hex_float = 0x103.70P-5;

// underscores may be placed between two digits as a visual separator
const lightspeed = 299_792_458.000_000;
const nanosecond = 0.000_000_001;
const more_hex = 0x1234_5678.9ABC_CDEFp-10;
```
