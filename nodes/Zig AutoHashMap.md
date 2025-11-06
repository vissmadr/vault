---
context:
  - "[[Zig]]"
---

# Zig AutoHashMap

The `AutoHashMap` data structure in Zig.

---

Simulating a [[Set (Abstract Data Type)|Set]]:

```zig
const std = @import("std");
const log = @import("std").debug.print;

const dungeon = @import("./assets/tilemaps/dungeon.zig");

pub fn main() !void {
    var buffer: [1024]u8 = undefined;
    var fba = std.heap.FixedBufferAllocator.init(&buffer);
    const allocator = fba.allocator();

    var set = std.AutoHashMap(u16, void).init(allocator);
    defer set.deinit();

    for (dungeon.m1_floor) |row| {
        for (row) |item| {
            set.put(item, {}) catch {
                return error.BufferOutOfMemory;
            };
        }
    }

    var iterator = set.iterator();
    while (iterator.next()) |entry| {
        log("{}\n", .{entry});
    }

    log("\n", .{});

    iterator.index = 2;
    while (iterator.next()) |entry| {
        log("{}\n", .{entry});
    }
}
```

```bash
[program]$ zig build run
.{ .key_ptr = u16@7ffe49ab4082, .value_ptr = void@7ffe49ab40a0 }
.{ .key_ptr = u16@7ffe49ab4084, .value_ptr = void@7ffe49ab40a0 }
.{ .key_ptr = u16@7ffe49ab4086, .value_ptr = void@7ffe49ab40a0 }
.{ .key_ptr = u16@7ffe49ab4088, .value_ptr = void@7ffe49ab40a0 }
.{ .key_ptr = u16@7ffe49ab408a, .value_ptr = void@7ffe49ab40a0 }
.{ .key_ptr = u16@7ffe49ab4090, .value_ptr = void@7ffe49ab40a0 }
.{ .key_ptr = u16@7ffe49ab409a, .value_ptr = void@7ffe49ab40a0 }

.{ .key_ptr = u16@7ffe49ab4088, .value_ptr = void@7ffe49ab40a0 }
.{ .key_ptr = u16@7ffe49ab408a, .value_ptr = void@7ffe49ab40a0 }
.{ .key_ptr = u16@7ffe49ab4090, .value_ptr = void@7ffe49ab40a0 }
.{ .key_ptr = u16@7ffe49ab409a, .value_ptr = void@7ffe49ab40a0 }
```
