---
context:
  - "[[Zig]]"
  - "[[Computer Memory]]"
---

# Zig Memory

Memory in Zig.

---

Memory management in Zig is done manually by the programmer.

**No Default Allocator**: There is no default memory allocator. Instead, functions which need to allocate accept an `Allocator` parameter. Likewise, some data structures accept an `Allocator` parameter in their initialization functions.

## Choosing an Allocator

What allocator to use depends on a number of factors. Here is a flow chart to help you decide:

1. **Library**: If you are building a library, it is best to accept an `Allocator` as a parameter and allow the users of the library to decide what allocator to use.
2. **libc**: If you are linking `libc`, the `std.heap.c_allocator` is likely the right choice, at least for your main allocator.
3. **Comptime**: If you know the maximum number of bytes that you will need in comptime, use `std.heap.FixedBufferAllocator`.
