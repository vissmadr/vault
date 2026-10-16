---
context:
  - "[[Game Design]]"
  - "[[Disjoint]]"
---

# The Singleplayer Disjoint Solution

Throw a quick target-based Dagger towards an enemy, and while the Dagger is still flying, the enemy teleports.
What happens to the Dagger?

Most multiplayer games solve this with the [[Disjoint]] mechanic.
When the enemy teleports, the Dagger just disappears.
But that's ugly!

Developing a singleplayer game, I came up with a nice cheat for it.
When the Dagger is thrown, a hidden flag called "`shouldNotTeleport`" is activated on the targeted enemy.
The flag remains active while the Dagger is still flying through the air.
The enemy AI would just not teleport, solving the issue.

> "Just don't do that right now please."

You can't make people in multiplayer games hold their teleport, but you can make singleplayer NPCs hold theirs.
