---
context:
  - "[[Zig]]"
---

# Found a Zig Bug

Found a bug on Zig version `0.17`.

---

```zig
export fn is231(number: i64) bool {
  const byte: u8 = @intCast(number);
  return byte == 231;
}
```

Zig's LLVM backend miscompiles a valid cast from a larger signed integer to a smaller unsigned integer.

With input `231`, this must return `true`.
In affected optimized builds (like 'ReleastFast' and 'ReleaseSafe'), it returns `false`.

The larger code snippet that I originally used was this:

```zig
const std = @import("std");

fn is231(number: i64) bool {
  std.debug.print("log #2: {d}\n", .{number});
  const byte: u8 = @intCast(number);
  std.debug.print("log #3: {d}\n", .{byte});
  const result = byte == 231;
  std.debug.print("log #4: {}\n", .{result}); // ???
  return result;
}

pub fn main(init: std.process.Init) !void {
  const args = try init.minimal.args.toSlice(init.arena.allocator());
  const number = try std.fmt.parseInt(i64, args[1], 10);
  std.debug.print("log #1: {d}\n", .{number});

  const result = is231(number);
  std.debug.print("log #5: {}\n", .{result});
}
```

With this result on optimized builds:

```
log #1: 231
log #2: 231
log #3: 231
log #4: false
log #5: false
```
