---
context:
  - "[[Zig]]"
---

# Zig Error Handling

Error handling in Zig.

---

```zig
// main.zig
const std = @import("std");

const somefile = @import("./somefile.zig");

pub fn main() void {
    somefile.main() catch |err| {
        std.log.err("somefile: {}", .{err});
    };
}

// somefile.zig
const std = @import("std");
const log = @import("std").debug.print;

const dungeon = @import("./assets/tilemaps/dungeon.zig");

pub fn main() !void {
    var buffer: [24]u8 = undefined;
    var fba = std.heap.FixedBufferAllocator.init(&buffer);
    const allocator = fba.allocator();

    var set = std.AutoHashMap(i16, void).init(allocator);
    defer set.deinit();

    for (dungeon.m1_floor) |row| {
        for (row) |item| {
            set.put(item, {}) catch |err| {
                return err;
            };
        }
    }
}
```
