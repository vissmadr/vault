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

const worldedit = @import("./worldedit.zig");

pub fn main() void {
    worldedit.main() catch |err| {
        std.log.err("worldedit: {}", .{err});
        // Output:
        // error: worldedit: error.BufferOutOfMemory
    };
}

// worldedit.zig
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
            set.put(item, {}) catch {
                return error.BufferOutOfMemory;
            };
        }
    }
}
```
