---
tags:
  - "original"
context:
  - "[[Project Spellblade]]"
---

# Project Spellblade - Skills

---

taking Fire damage outside Fire stance: Can burn you
taking Fire damage in Fire stance: Burning is kinda fine

taking Storm damage outside Storm stance: Can also cause your Charges to Discharge
taking Storm damage in Storm stance: Can gain you Charge (like you control the Storm)

taking Chaos damage outside Chaos stance: Chaos reduces your Order
taking Chaos damage in Chaos stance: something

| Aspect           | Draft 1                      | Draft 2                         |
| ---------------- | ---------------------------- | ------------------------------- |
| Feel             | Empowering (more = better)   | Risky (manage your limits)      |
| Positioning      | Encouraged (stay near fires) | Neutral                         |
| Stance switching | Return to reapply burns      | Forced by Overheat management   |
| Skill ceiling    | Optimizing Heat uptime       | Pushing limits before switching |

## Fire

#wip Draft 1: Gain Heat and use it to cast Fire spells.
#wip Draft 2: Cast Fire spells, but don't Overheat.

Resource:

- (draft 1) **Heat**: Gain Heat constantly. Use Heat to cast Fire abilities. Gain more Heat when nearby burning enemies & environment.
- (draft 2) **Overheat**: Casting Fire spells gains Heat. Heat can Overheat, causing negative effects (like burning the player, weaker Fire spells, etc).

(draft 1) **Heat** Gameplay:

- Apply as much **Burn** as possible to as many targets as possible.
- Entering Fire stance activates **Immolation**, using **Heat** and constantly **Burning** nearby enemies.
- Position yourself near burning enemies/environment to gain more **Heat**.
- Return to Fire stance to reapply **Burn** durations.

(draft 2) **Overheat** Gameplay:

- Apply as much **Burn** as possible to as many targets as possible.
- Entering Fire stance activates **Immolation**, gaining **Heat** and constantly **Burning** nearby enemies.
- When close to **Overheating**, switch to another stance to cool down.
- Return to Fire stance to reapply **Burn** durations.

Skills:

- **Burn**: Debuff that causes Fire damage over time.
- **Scorch**: Continuous Fire AOE on the ground.
- **Explosion**: Instant Fire AOE damage blast.

#wip If (draft 1) Heat: Immolation can be something that follows a spell/stance switch automatically? Like casting Fireball also immolates for 2 seconds?

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

## Storm

Resource:

- **Charge**: Gained mostly from moving/dashing/attacking.

Gameplay:

- Move, dash, and attack to gain **Charge**, even in other stances.
- Enter Storm stance to **Discharge** any gained **Charges**.

Skills:

- **Charge**: Stacks of **Charge** can be gathered by the player to be released on Storm attacks and abilities.
- **Discharge**: Discharge current **Charge** stacks to release a chain lightning that jumps from target to target.

---

#wip: Heavy redesign to follow the new move/dash/attack Charge gain gameplay.
#wip: Maybe max charges per Discharge, to not dump everything into one Discharge?

**Tailwind**: Bonus movespeed.
`movespeed: 10%`

**Zephyr**: Not taking damage for `x` seconds increases movespeed.
`minDuration: 5s`
`movespeed: 10%`

**Stormbringer**: Moving for `x` seconds gains **Charge**.
`minDuration: 2s`

**Gathering Storm**: Gains **Charge** every `n` seconds.
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

**Eye Of The Storm**: Chance to re-gain **Charge** when **Discharging**.
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

Gameplay:

- wip

Skills:

- wip

---

**Bash**: Chance to stun on melee attack.
`chance: 10%`
`duration: 1s`

**Earth Shield**: Shield.
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

Resource:

- **Order**: Gained constantly, but randomly (noise function).

Gameplay:

- Generate **Order** over time while in other stances.
- Entering Chaos stance triggers **Entropy**, which burns **Order**.
- While **Entropy** is burning, Chaos proc chances are increased.
- When **Order** is depleted, **Entropy** ends.

Abilities:

- **Attack**:

Skills:

- **Order**: Resource that accumulates over time outside of Chaos stance.
- **Entropy**: Burns **Order** while in Chaos stance, boosting Chaos procs.
- **DOOM**: Causes a massive amount of damage.

---

#wip: Adapt for the new Entropy & Order mechanics.
#wip: Almost every (or every) Chaos effect should be Entropy-based.
#wip: All proc chances should be min & max.
#wip: Add skills that affect Entropy itself, causing it to burn faster/slower.
#wip: Renames, renames, renames... Potential for good stuff.

**@ WIP @** (Schism? Singularity?): Overflowing **Order** in causes effect in other stances?

---

**Havoc**: Chance on melee attack to trigger a random effect.
`chance: 10%`

**Butterfly Effect**: Consecutive **Havoc** procs on a target increase the chance of more **Havoc** procs on the same target.
`scalar: 2%`
`maxStacks: 5`

**Recursion**: Chance to trigger another **Havoc** on any **Havoc** procs.
`chance: 20%`

**Inevitability**: Every `n`-th potential **Havoc** is guaranteed.

**Omen**: Adds **DOOM** to the list of possible **Havoc** effects.

**Chaos Theory**: The first two hits on a new target always proc **Havoc**.

**Mutation**: Chance to gain a random temporary buff.
`chancePerSecond: 20%`
`duration: 5s`

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

**Unforseen Consequences**: Chance to proc **Havoc** on the attacker when taking damage.
`chance: 20%`
