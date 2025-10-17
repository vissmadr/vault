---
context:
  - "[[Game Development]]"
  - "[[Software Architecture]]"
---

# Game Loop

The central coordinating cycle that drives a game's execution process.

---

```c
while (gameIsRunning)
{
   // Poll events
   // Update application/game state
   // Render contents into a framebuffer
   // Swap/Present framebuffer to the screen
   // Wait some time (e.g. 1/60 of a second)
}
```
