---
context:
  - "[[Zig]]"
  - "[[Variable (Programming)]]"
---

# Zig Variables

Variables in Zig.

[Documentation](https://ziglang.org/documentation/master/#Variables)

---

A variable is a unit of Memory storage.

It is generally preferable to use `const` rather than `var` when declaring a variable. This increases clarity and creates more optimization opportunities.

The `extern` keyword or `@extern` builtin function can be used to link against a variable that is exported from another object. The `export` keyword or `@export` builtin function can be used to make a variable available to other objects at link time. In both cases, the type of the variable must be C ABI compatible.

## Identifiers

Variable identifiers are never allowed to [[Variable Shadowing|shadow]] identifiers from an outer scope.

Identifiers must start with an alphabetic character or underscore and may be followed by any number of alphanumeric characters or underscores. They must not overlap with any keywords. See Keyword Reference.

If a name that does not fit these requirements is needed, such as for linking with external libraries, the `@""` syntax may be used.

## Local Variables

Local variables occur inside functions, `comptime` blocks, and `@cImport` blocks.

When a local variable is `const`, it means that after initialization, the variable's value will not change.

## Comptime

If the initialization value of a `const` variable is `comptime`-known, then the variable is also `comptime`-known.

A local variable may be qualified with the `comptime` keyword. This causes the variable's value to be `comptime`-known, and all loads and stores of the variable to happen during semantic analysis of the program, rather than at runtime.

All variables declared in a `comptime` expression are implicitly `comptime` variables.
