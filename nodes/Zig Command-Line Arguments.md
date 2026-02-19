---
context:
  - "[[Zig]]"
---

# Zig Vectors

Command-line arguments in Zig allow input to be passed to the program.

---

```zig
const std = @import("std");

pub fn main() !void {
    var argumentsIterator = std.process.args();

    var i: usize = 0;
    while (argumentsIterator.next()) |argument| {
        std.debug.print("{d}: {s}\n", .{ i, argument });
        i += 1;
    }
}
```
