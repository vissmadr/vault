---
context:
  - "[[Zig]]"
  - "[[Control Flow]]"
---

# Zig Control Flow

Control flow in Zig.

---

## Conditional Logic

Zig's conditional statements accept only boolean values: `true` or `false`.

**No Coercion**: Unlike other languages, there are no values that implicitly coerce to boolean values.

**No Ternary**: The ternary conditional operator (`cond ? a : b`) does not exist in Zig.

**If Expressions**: If statements are also valid expressions: `x += if (a) 1 else 2;`

## Loops

```zig
var i: i32 = 0;

while (i < 10) {
    bark();
    i += 1;
}
```

Zig `while` statements can have an optional 'continue expression' which runs every time the while loop continues (either at the end of the loop or when an explicit `continue` is invoked.

```zig
var i: i32 = 0;

while (i < 10) : (i += 1) {
    bark();
}
```

**Labels**: Loops can be labelled:

```zig
fn labels() void {
    var i: u16 = 0;
    outer: while (i < 10) : (i += 1) {
        print(i);

        var j: u16 = 100;
        while (j < 110) : (j += 1) {
            print(j);
            if(j >= 105) break :outer;
        }
    }
}

// Output: 0, 100, 101, 102, 103, 104, 105
```

## Defer

See [[Zig Defer]]
