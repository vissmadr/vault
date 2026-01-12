# Action Input Design

Goals and Constraints:

- Consistency!
- Physical speed & ergonomics.
- No more than `3`-`4` action keys.
- Potential to enable player flow state.

## 5 Keys 5 Abilities

`J`: Attack
`K`: Dash
`L`: Special
`I`: Spell 1
`O`: Spell 2

**Pros**:
Dumb-simple.
Single tap for everything.
Fits roguelike progression.

**Cons**:
Only `5` abilities.
Literally a Hades clone.
Increased physical keys count.

## 3 Keys 5 Abilities

`J`: Attack
`K`: Dash

`LJ`: Spell 1
`LK`: Spell 2
`LL`: Spell 3

**Pros**:
Simple.
Least amount of keys.
Fits roguelike progression.

**Cons**:
Only `5` abilities.
Requires frequent double-taps.
Almost not worth compared to just `5` keys.

## 4 Keys 7 Abilities

`J`: Attack
`K`: Dash
`L`: Special

`IJ`: Spell 1
`IK`: Spell 2
`IL`: Spell 3
`II`: Spell 4

**Pros**:
Unique.
More abilities.
Spammable special.
Fits roguelike progression.
Matches joystick key count.

**Cons**:
Requires frequent double-taps.

## 4 Keys 4 Modes

`J`: Attack
`K`: Dash
`L`: Special

`IJ`: Mode 1
`IK`: Mode 2
`IL`: Mode 3
`II`: Mode 4

Modes are persistent and change the Attack, Dash, and Special while active.
Modes can activate possible buffs and persistent effects upon mode entry.

**Pros**:
Unique.
Consistent.
Spammable abilities.
Matches joystick key count.

**Cons**:
Requires frequent double-taps.
Dependent on good art direction.
Doesn not fit roguelike progression.

## Spellsteal

`J`: Attack
`K`: Dash
`L`: Spellsteal

Consumes magic from enemies/environment.

**Pros**:
Game-maker.
Unique mechanic.

**Cons**:
Consumes all other design.
Relies mainly on external factors.
Can be a nightmare for the artists.

## Invoker Permutations

**Cons**:
Too slow.
Too complex.
Difficult to learn.
Requires triple taps.

---

Spell Toggle

**Modes**:
Cons:

Trying to decide between Modes vs single Spells.

I seem to like Modes more, as they are a unique mechanic and give more creative freedom.
Modes also advocate for faster pace.
Imagine timed buffs that are given once upon Mode entry, and slowly diminish/expire.
Player would be suggested to switch modes relatively frequently to keep the buffs active.
Also modes provide for situational consistent play.

Think also about Warrior stances and Druid forms.

# Ideas

## Triple

J: Attack
K: Dash
L: Shift

if(shift) {
J: Spell 1 (Frontal, close/mid range)
K: Spell 2 (any, could be dash-like to match key)
L: Spell 3 (AOE)
}

## Modes

I: Shift
J: Attack
K: Dash
L: Cast

if(shift):
I: Free (can be Mode 0 or a spell; use wisely)
J: Mode 1 (Offense) (Fire?)
K: Mode 2 (Offense/Speed/AOE)
L: Mode 3 (Defense/Utility)

## Invoker Permutations

J: Attack
K: Dash
L: Special
I: Enter Invoker Mode

while in invoker mode: - JJ: Spell 1 - KK: Spell 2 - LL: Spell 3 - JK: Spell 4 - KL: Spell 5 - JL: Spell 6

to exit invoker mode: - successful cast - pressing I again

## Spellsteal

J: Attack
K: Dash
L: Special
I: Spellsteal

Can spellsteal (melee range) from both enemies and environment, enabling buffs for a duration, changing the default abilities for a duration.

## Spell Toggle

J: Attack
K: Dash
L: Special
I: Enter spell mode

While spell mode is active:

J: Spell 1
K: Spell 2
L: Spell 3
I: Exit spell mode

## Hades-like

J: Attack
K: Dash
L: Special 1
I: Special 2

# Design

JKL actions
I spellsteal

---

JKL actions
I invoker mode

---

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
