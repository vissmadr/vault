---
context:
  - "[[Algorithm]]"
---

#wip

# Swap-Remove

---

Allows to use an [[Array]] as if it had dynamic size.

Tracks the last _active_ element of the array.

```
----------------v-
[A][B][C][D][E][F]


----------------v-
[A][B][C][D][E][F]
       *        *

----------------v-
[A][B][F][D][E][F]


-------------v----
[A][B][F][D][E][F]
```
