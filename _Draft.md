# Design

_WoL-inspired_

**Attack Lock**: Attacks lock the character for the duration of the swing.

**Cast Lock**: Casts lock the character for the duration of the cast.

**Attack Step**: The attack lock can step in a direction just like the Dash.

**Pushback**: Attacks/Casts push the target away.

**Ministun**: Attacks/Casts ministun the target.

**Health**: Limited and expensive resource.

ACTUALLY: https://wiki.leagueoflegends.com/en-us/Udyr

## Cast-first

**Pros**:
Single tap to cast any spell.
Solves the stance switch spam problem.

**Cons**:
Cannot stance switch while spell is in cooldown.
Dilemma between casting a spell versus remaining in a stance.

**Timed Stance Idea**: The cast-first approach makes it possible for stances to remain for a duration only.

# Research X

# Stats

Generate `Persistent Stats` first.

Then before gameplay generate `Game Stats`.

All part of the entity store:

- `Dynamic Stats`
- `Dynamic State`
- `Dynamic Modifiers`
- `Logic Cache`

`Dynamic Stats`: What the entity can currently do and how well it does it.
`Dynamic State`: The current state of the entity.
`Dynamic Modifiers`: Any timed effects affecting the entity. Can change both `Dynamic Stats` and `Dynamic State`.
`Logic Cache`: Systems-related cache for the entity that isn't used otherwise.

**State to State Problem**: Imagine that in the `State` there is a `health` field, but also a `burnDamage` field. Simply set the state first, and somewhere after that have functionality and logic that actually applies the state, like `applyBurns(state)`.

It's probably best to use a `Dynamic Modifiers` array in order for it to keep track of all effects and their timers. Otherwise, both `Stats` and `State` will receive a fuckton of bloat. The linear search is extremely performant, so that's not an issue, ever. Common useful flags like `isBurning` can still be written to the `State` for ease of query.

Otherwise bigger problems emerge. Without `Dynamic Modifiers`, instead keeping both effects and timers in the state:

1. The state gets bloated heavily.
2. Not only the state, but the stats also get bloated.
3. Is probably actually worse for performance. Linear array iteration is not bad compared to every unnecessary state there is.

Examples:

- Health: state
- MaxHealth: STAT
- isBurning: state
- isStunned: state
- burnDps: state
- playerStance: state
- isStanceSwitchPending: logic cache
- chargeCooldown: state
- maxCharges: stats
- animatorStuff: logic cache

---

| Concept               | Mutability | Components                    | Lifetime   | Purpose                        |
| --------------------- | ---------- | ----------------------------- | ---------- | ------------------------------ |
| **`baseStats`**       | immutable  | `stats` + `variety`           | per entity | design baseline                |
| **`persistentStats`** | immutable  | `baseStats` + `modifiers`     | per run    | talents, items, environment    |
| **`dynamicStats`**    | mutable    | `persistentStats` + `effects` | per update | effects, stuns, buffs, debuffs |

# Terminal

Ctrl+T

# Overhaul

## Abilities

`3` buttons for `2` + `3`, or `2` + `9` total abilities.

## Classes

**Base**: Attack, Dash, 3 abilities

**Invoker**: Attack, Dash, 9 abilities

**Modes**: Attach, Dash, 3 modes

- Could be "weapons arsenal"
- Could be "shapeshift forms"
- Could be "warrior stances"

# Ability Design

TODO: https://www.method.gg/fellowship/heroes/meiko/playstyle-and-rotation

# Performance

**Raylib Performance**: https://youtu.be/aRTi7D4V0Yg

# Development

3D to 2.5D: https://www.youtube.com/watch?v=l1Io7fLYV4o

Learn from Galactic Assault Squad [GAS](https://gasgame.net/)
Learn from ISOCORE
Learn from 9kings
Learn from Stoneshard
Learn from Death Must Die (!)
Learn from Hyper Light Drifter
Check out Drova: Forsaken Kin

Amit Patel RPG probability

**rTexPacker**: https://raylibtech.itch.io/rtexpacker

**3D Animation Pack**: https://quaternius.itch.io/universal-animation-library

# Formatting

Consistent and popular formatters are optimal.

Think about what the LLM has mostly been trained on.

# Flat Control Flow

Deep nesting harms reasoning.
