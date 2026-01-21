Research:

https://x.com/startracker/status/2013322805354606898

https://x.com/the77bit

---

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

# Design

## Mutations

- The WORLD can mutate, while the player remains the same.
- Cool idea: If the run has say 5 floors, each floor has its own mutation. They can be progressively more volatile. And then final boss room mutation.
- Mutations can have pros/cons, or only cons, where if you defeat the elite that 'owns' the mutation - it stops.
- Or multiple elites per floor, each contributing to the mutation, so that it's not an assassination hit-and-run gameplay from floor to floor.
- This way you can choose your own speed. The faster you are (skipping stuff) - the harder it is.
- Instead of enemies slain %, it can also be Elite NPC's that need to be defeated, like mini-bosses that change the effects.
- Global modifiers, like wet air, or something.

Short runs: Can go without in-run scaling.
Long runs: Probably good to have _something_.

## Biomes

Biomes that affect the whole run, meaning both player and enemies.

Examples:

- Cold Biome: -10% movespeed, -10% attackspeed, +10% fire resistance.

## Stance Environment Effects

Fire stance removes slows due to cold environment.

# SECTOOOOOOOOOORS

# The Art Controls

The first authority is always:

1. Make a good game.

Every decision must revolve around that.

Everything else is secondary.

# Misc

I'm playing and rating all "Hades-like" games; simple list to help you, from 1. best to N. good
Hades II
Realm of Ink
Hades
Splintered Fate
BeatSlayer
Reignbreaker
The Eternal Die
SWORN
Curse of The Dead Gods
FELLCHASER
Will update above list when played:
Cinderia
Life Core
Grim Trials
Aksun
Rise Again
Lone Soul
Lethal Honor
Heretical
Shape of Dreams
Warm Snow
If I'm missing any, please tell me! And sorry for the claim "Hades-like", but we need something for a mutual understanding.

J: at
K: da
L: sp

LJ: sp at
LK: sp da
LL: sp sp (projectile)

---

UIO
JKL

3 to activate elements, 3 for melee, dash, special.

---

Damage to both health and max health. Imagine `10` and `5`.

Permanent negative effects (or for X turns/runs).

# Uncle Fast and Slow

"You're slow, so that's why you might reach further."

Him at 21:

- Finished highschool with excellency.
- Completed millitary training.
- Read over 1000 books.
- Studying medicine at the university.
- Training and competing in martial arts.
- Working one job related to medicine.
- Working another night job as a bouncer.
- Married.
- Has a child.

Bruh.

# UI not ECS

**mel0ndev**: ECS is great; I would recommend not making any UI part of the ECS if you can help it

# Throttling

What a great performance booster wow.

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
