---
tags:
  - "original"
context:
  - "[[Project Spellblade]]"
---

# Project Spellblade - Skills

---

## Fire

Gameplay:

- Attrition damage that builds up.
- Apply as much **Burn** as possible to as many targets as possible.
- Entering Fire stance activates **Immolation** for a duration.

Skills:

- **Burn**: Debuff that causes Fire damage over time.
- **Scorch**: Continuous Fire AOE on the ground.
- **Explosion**: Instant Fire AOE damage blast.

---

**Immolation**: Engulfed in flames, you constantly damage nearby enemies.
`duration: 3s`
`damage: 5`
`range: 3`

**Ignite**: **Immolation** damage has a chance to apply **Burn**.
`chance: 10%`

**Inner Fire**: Increases the duration of **Immolation**.
`duration: 1s`

**Phoenix**: Regenerate health while **Immolation** is active.
`amount: 5`

**Burning Blade**: Chance to apply **Burn** on melee attacks.
`chance: 20%`

**Searing Blade**: Triple **Burn Blade** proc chance on critical attacks.

**Shadowburn**: **Burn** ticks have a chance to trigger **Havoc**.

**Firestarter**: The first Fire attack on a target always applies **Burn**.

**Dragon Skin**: Gain passive resistance to Fire damage, tripled while in Fire stance.
`scalar: 10% (or 30%)`

**Dragon Heart**: Taking Fire damage extends **Immolation** duration.
`duration: 0.2s`

**Crucible**: While in Fire stance, half of all damage taken is taken as Fire damage.

**Pyromaniac**: Gain bonus movespeed for each nearby **Burning** enemy.
`scalar: 2%`

**Arsony**: Gain bonus damage for each nearby **Burning** enemy.
`scalar: 2%`

**Combust**: **Burn** ticks have a chance to trigger an **Explosion**.
`chance: 2%`

**Incinerate**: **Burn** damage can now crit.

**Eruption**: **Burn** damage has a chance to stun.
`chance: 5%`
`duration: 0.5s`

**Pyre**: Bonus **Burn** damage vs stationary targets.
`scalar: 15%`

**Macropyre**: Spawns a **Scorch** below **Burning** targets that have stood still for a duration.
`spawnAfter: 1.5s`

**Ember Lock**: Bonus stun duration for each **Burn** on the target.
`scalar: 3%`
`maxStacks: 6`

**Molten Fury**: Bonus Fire damage vs Stunned targets.
`scalar: 20%`

**Kindle**: Fire damage increases the longer the target remains **Burning**.
`increasePerSecond: 2%`
`durationLimit: 6s`

**Wildfire**: **Burn** has a chance to spread to nearby enemies.
`chance: 10%`
`range: 2`

**Conflagrate**: **Explosion** applies **Burn** to all targets.

**To Ashes**: Increases **Burn** damage against low health targets.
`threshold: 20%`
`damage: 20%`

**Living Bomb**: **Burning** enemies explode when they die.
`damage: 20`
`radius: 80`

**Attrition**: Each stack of **Burn** reduces the damage the target deals.
`scalar: 3%`
`maxStacks: 6`

---

## Storm

> Gameplay: Gather

> Skills:
> **Charge**: Stacks of **Charge** can be gathered by the player to be released on Storm attacks and abilities.
> **Discharge**: Discharge current **Charge** stacks to release a chain lightning that jumps from target to target.

---

**Tailwind**: Bonus movespeed.
`movespeed: 10%`

**Zephyr**: Not taking damage for `x` seconds increases movespeed.
`minDuration: 5s`
`movespeed: 10%`

**Stormbringer**: Moving for `x` seconds gains **Charge**.
`minDuration: 2s`

**GatheringStorm**: Gains **Charge** every `n` seconds.
`time: 6s`

**Spark**: Chance to gain **Charge** on melee attack.
`chance: 20%`

**Thunderfury**: Chance to use **ChainLightning** on melee attack.
`chance: 10%`

**Feedback**: If there are no new targets in range, **Discharge** jumps to the same target again.

**Shock**: The first Storm damage on an enemy always crits.

**Stormcloak**: Damage reduction per **Charge** stack.
`scalar: 5%`

**Shatter**: Bonus Storm damage to stunned enemies.
`scalar: 10%`

**Aftershock**: Stunned enemies take damage when the stun expires.
`damage: 15`

**Firestorm**: Storm abilities have a chance to apply **Burn**.
`chance: 30%`

**Emberspark**: **Burn** enemies have a chance to gain you **Charge**.
`chance: 4%`

**Detonate**: Storm ability consumes **Burn** stacks to deal massive damage.
`damagePerStack: 40`

**Capacitor**: Store more max charges.
`count: 2`

**EyeOfTheStorm**: Chance to re-gain **Charge** when discharged.
`chance: 10%`

**Alacritty**: Each **Charge** stack increases attackspeed.
`scalar: 1%`

**Overcharge**: Each new **Charge** beyond the maximum causes a storm explosion around you.

**Tempest**: Each **Discharge** increases attackspeed for a duration.
`scalar: 2%`

**Surge**: Each **Discharge** increases movespeed for a duration.
`scalar: 2%`

**Unleash**: Each **Discharge** increases damage for a duration.
`scalar: 2%`

---

## Earth

**Bash**: Chance to stun on melee attack.
`chance: 10%`
`duration: 1s`

**EarthShield**: Shield.
`amount: 20`

**Barkskin**: Damage reduction.
`damageReduction: 10%`

**Earthquake**: Slow nearby enemies when moving.
`scalar: 10%`

**Thorns**: Getting hit in melee range inflicts damage to the attacker.
`damage: 5`

**Magma**: Stuns also apply **Burn**.

**Grounded**: Gain **Charge** when hit.

---

## Chaos

> **DOOM**: Causes a massive amount of damage.

**Havoc**: Chance on melee attack to trigger a random effect.
`chance: 10%`

**ButterflyEffect**: Consecutive **Havoc** procs on a target increase the chance of more **Havoc** procs on the same target.
`scalar: 2%`
`maxStacks: 5`

**Recursion**: Chance to trigger another **Havoc** on any **Havoc** procs.
`chance: 20%`

**Inevitability**: Every `n`-th potential **Havoc** is guaranteed.

**Omen**: Adds **DOOM** to the list of possible **Havoc** effects.

**ChaosTheory**: The first two hits on a new target always proc **Havoc**.

**Mutation**: Chance to gain a random temporary buff.
`chancePerSecond: 20%`
`duration: 4s`

**Metamorphosis**: At least one **Mutation** will always remain active.

**Volatility**: Increases critical damage.
`increase: 10%`

**Disorder**: Small chance to trigger **DOOM** on any chaos crit.
`chance: 2%`

**Ruin**: **DOOM** also stuns.
`duration: 1s`

**Blur**: Chance to completely evade any attack when moving.
`chance: 10%`

**Spectre**: Chance to completely evade any attack.
`chance: 10%`

**Diffusion**: Reduces any damage taken by a random amount.
`min: 0%`
`max: 20%`

**Midnight**: Reduces the probability of critical hits against you.
`scale: 30%`

**Eclipse**: Completely evade every `n`-th attack.

**Anomaly**: Chance that incoming damage will heal you instead.
`chance: 10%`

**Paradox**: **Anomaly** can also proc on attacks that have been evaded.

**UnforseenConsequences**: Chance to proc **Havoc** on the attacker when taking damage.
`chance: 20%`
