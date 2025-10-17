---
context:
  - "[[Computing]]"
---

# Compilation

The process of translating [[Source Code]] into executable [[Machine Code]].

---

Transforms human-readable source code into a runnable [[Computer Program]] through several stages.

## Overview

Compilation typically includes these stages:

1. **Preprocessing**
2. **Compilation**
3. **Assembly**
4. **Linking**

### Preprocessing

Prepares the source code for compilation by:

- **Removing Comments**
- **Expanding Macros**
- **Handling Conditional Compilation**
- **Resolving Includes**: Inserts the contents of header files before compilation begins.

**Output**: Single expanded and cleaned-up source file.

### Compilation

Translates the preprocessed source code into an intermediate [[Assembly]] representation, often performing syntax and semantic analysis and applying optimization.

See [[Compiler]]

**Output**: Assembly code.

### Assembly

Converts the assembly code into [[Object Code]] containing [[Machine Code]] instructions.

See [[Assembler]]

**Output**: [[Object File]] (`.o` or `.obj`).

### Linking

Combines one or more object files and required libraries into a single [[Executable File]].

See [[Linker]]

- **Static Linking**: Includes all necessary code directly in the final binary.
- **Dynamic Linking**: References shared libraries (`.so` on [[Linux]] and [[MacOS]], `.dll` on [[Windows]]).

**Output**: Executable binary or library file.
