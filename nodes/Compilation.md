---
context:
  - "[[Computing]]"
---

# Compilation

The process of translating [[Source Code]] into [[Machine Code]].

---

This process is executed done by a [[Compiler]].

## Process

In general, the compilation process follows these steps:

1. Preprocessing
2. Compilation
3. Assembly
4. Linking

### Preprocessing

Prepares the source code by doing things like:

- **Removing Comments**
- **Expanding Macros**
- **Resolving Conditional Compilation**
- **Resolving Includes**: Replaces the `include` lines with the contents of the header file, and all the headers it includes. Basically inserts the code into the file before the compilation begins.

**Output**: Single large file

### Compilation

**Assembly**: Translates source code into an intermediate [[Assembly]] source code.

### Assembly

**Machine Code**: Translates the human-readable assembly into [[Machine Code]].

### Linking

**Static**: Puts any needed machine code into the final [[Binary File]].

Dynamic files ending in `.dll` on [[Windows]] or `.so` on [[Linux]] and [[MacOS]].
