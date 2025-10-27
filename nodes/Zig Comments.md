---
context:
  - "[[Zig]]"
  - "[[Comment (Programming)]]"
---

# Zig Comments

Comments in Zig.

---

Zig supports 3 types of comments:

- **Normal comments (`//`)**
- **Doc comments (`///`)**
- **Top-level doc comments (`//!`)**

```zig
//! Main module

const std = @import("std");
const p = @import("player.zig");

/// Documentation of main() function
pub fn main() void {
    const constantInteger: i32 = 42;
    var mutableInteger: i32 = 42;

    // This is a normal comment
}
```

**Package Documentation**: Normal comments are ignored, but doc comments and top-level doc comments are used by the compiler to generate the package documentation.

**Single Line**: There are no multiline comments in Zig. This allows Zig to have the property that each line of code can be tokenized out of context.

## Doc Comments

Doc comments begin with exactly three slashes (i.e. `///` but not `////`); multiple doc comments in a row are merged together to form a multiline doc comment. The doc comment documents whatever immediately follows it.

Doc comments are only allowed in certain places; it is a compile error to have a doc comment in an unexpected place, such as in the middle of an expression, or just before a non-doc comment.

## Top-level Doc Comments

The top-level doc comment begins with two slashes and an exclamation point: `//!`; It documents the current module.
