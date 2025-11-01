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

## While Loop

```zig
var i: i32 = 0;

while (i < 10) {
    bark();
    i += 1;
}
```

**Continue Expression**: Zig `while` statements can have an optional 'continue expression' which runs every time the while loop continues (either at the end of the loop or when an explicit `continue` is invoked.

- Continue expressions do NOT execute when a while loop stops because of a `break`!

```zig
while (i < 10) : (i += 1) {
    bark();
}
```

**Break**: You can force a loop to exit immediately with a "break" statement:

- Continue expressions do NOT execute when a while loop stops because of a `break`!

```zig
while (true) : (n += 1) {
    if (n >= 42) break;
}
```

## For Loop

The `for` loop provides simple syntax for iteration:

```zig
const arr = [_]u8{ 10, 20, 30, 40 };

for (arr) |item| {
    print("item: {d}\n", .{item});
}

// Output:
// item: 10
// item: 20
// item: 30
// item: 40
```

**Index**: For can use the 'index' of the iteration, a number that counts up with each iteration. To access the index of iteration, specify a second condition as well as a second capture value.

```zig
const arr = [_]u8{ 10, 20, 30, 40 };

for (arr, 0..) |item, index| {
    print("item: {d}, index: {d}\n", .{item, index});
}

// Output:
// item: 10, index: 0
// item: 20, index: 1
// item: 30, index: 2
// item: 40, index: 3
```

## Labels

Loops can be labelled:

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
