---
tags:
  - "original"
context:
  - "[[Project Spellblade]]"
---

# Project Spellblade - Skills

#wip

---

Stance switching:

| Approach                | Feel                 | Risk                                                      |
| ----------------------- | -------------------- | --------------------------------------------------------- |
| 0.5-1s anti-spam        | Fluid, reactive      | Might feel "twitchy", stance identity blurs               |
| 2-3s cooldown           | Deliberate, tactical | Middle ground, might still feel restrictive               |
| No cooldown BUT cost    | Fluid with weight    | Switching costs some resource (lose 10% Heat, Order, etc) |
| No cooldown BUT ramp-up | Rewards staying      | First 2s in stance = weaker effects, then full power      |

Input:

| Stance | Button | Switch Effect                           | Cast (same button while in stance) |
| ------ | ------ | --------------------------------------- | ---------------------------------- |
| Fire   | I      | Enter Fire, start Immolation?           | Fireball / Flame stream            |
| Storm  | O      | Enter Storm                             | Discharge (obvious fit)            |
| Chaos  | P      | Enter Chaos, start Entropy burn         | ??? (Force Havoc? Random burst?)   |
| Earth  | L      | Enter Earth, start Clarity regen boost? | Summon Wisp(s)                     |

(!!!) #wip: Figure out which effects are stance-only, which are not, which can be both (tripled), and so on!

---

taking Fire damage outside Fire stance: Can burn you
taking Fire damage in Fire stance: Burning is kinda fine

taking Storm damage outside Storm stance: Can also cause your Charges to Discharge
taking Storm damage in Storm stance: Can gain you Charge (like you control the Storm)

taking Chaos damage outside Chaos stance: Chaos reduces your Order
taking Chaos damage in Chaos stance: something

---

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

#wip (draft 1) Overheat: Can use fire even if no heat, but at what cost?
#wip (draft 2) Insanity: Can continue to use Fire if overheated, but at WHAT COST?

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

WIP: don't like the name as much?
**Pyromaniac**: Gain bonus movespeed for each nearby **Burning** enemy.
`scalar: 2%`

WIP: don't like the name as much?
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
`threshold: 15%`
`damage: 15%`

WIP: "Living" feels wrong here
**Living Bomb**: **Burning** enemies explode when they die.
`damage: 20`
`radius: 80`

**Attrition**: Each stack of **Burn** reduces the damage the target deals.
`scalar: 3%`
`maxStacks: 6`

WIP:
**\_\_\_**: Burning Enemies leave **Scorch** when they die.
**\_\_\_**: Moving enemies Combust/something more easily.

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
#wip: Lightning ability to Discharge? And/or Discharge on Attack?

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

## Earth/Nature

Mechanics:

- Enter Earth stance to summon **Wisps** that can will heal, protect, and synergize.
- Summoned **Wisps** last until killed, even in other stances.

Skills:

**Wisp**: While in Earth stance, constantly summons new **Wisps** every `s` seconds
up to a maximum of `n` active **Wisps** at a time. **Wisps** have health equal to a
fraction of your own health. Each **Wisp** will continuously heal you for `h` health
per second. When you take damage, **Wisps** will sacrifice themselves to intercept
the attack.
`summon (s): 1.0s`
`maxCount (n): 5`
`heal (h): 2`

---

Clarity Return: Chance to re-gain the Clarity cost of a Wisp when it dies.
Clarity Return: Or no RNG and a percent of the portion.
Clarity Return: Or both?

**Wisp Replicate**: Random chance to spawn a wisp for every current wisp.

**Tranquility**: Bonus when having max Wisps.
**(wip name Over Tranquility)**: Bonus for every Wisp after the max.

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

**Vines**: Damaging enemies with **Thorns** has a chance to root them.
`chance: 30%`

**Magma**: Stuns also apply **Burn**.

**Grounded**: Gain **Charge** when hit.

**\_\_\_**: Gain **Order** faster while in Earth stance.

---

## Chaos

_draft_

Mechanics:

- Generate **Order** over time while in other stances.
- Entering Chaos stance triggers **Entropy**, burning **Order** quickly.
- While **Entropy** is burning, Chaos abilities have increased proc chances.
- **Entropy** burns strongest at high **Order**, and weakest at low **Order**.

Gameplay:

- Generate **Order** while in other stances.
- Enter Chaos stance to unleash maximum **Entropy**.
- Switch away from Chaos stance when **Order** depletes.

Terminology:

- **Order**: Resource that accumulates over time outside of Chaos stance.
- **Entropy**: Burns **Order** while in Chaos stance, boosting Chaos procs.
- **DOOM**: Causes a massive amount of damage.

- **_"High Entropy"_**: When **Order** is burning above two-thirds.
- **_"Low Entropy"_**: When **Order** is burning below two-thirds.

Skills:

**Havoc**: Chance on melee attack to trigger a random damaging effect.
`chance: 0% - 20%`

**Chaos Theory**: Consecutive **Havoc** procs against a target increase the chance of more **Havoc** procs on the same target.
`scalar: 0% - 3%`
`maxStacks: 5`

**Recursion**: Chance to trigger another **Havoc** on ANY **Havoc** proc.
`chance: 0% - 20%`

**Inevitability**: During high **Entropy**, Every `6`-th potential **Havoc** is guaranteed.

**Doombringer**: Adds **DOOM** to the list of possible **Havoc** effects.

**Butterfly Effect**: The first hit against a new target always procs **Havoc**.

**Equilibrium**: Enemies take bonus damage when hit by an element different from the last one that hit them.
`bonus: 5%`

**Mutation**: Burning **Entropy** has a chance to grant you a random temporary buff.
`duration: 5s`

**Metamorphosis**: At least one **Mutation** will always remain active.

**Potential**: Increases critical chance.
`scalar: 0% - 10%`

**Volatility**: Increases critical damage.
`scalar: 0% - 20%`

**Nightfall**: Makes **Entropy** increase faster.
`amount: 5%`

**Darkness**: Makes **Entropy** decrease slower.
`amount: 5%`

**Eclipse**: Every `n` seconds of burning **Entropy** causes **Eclipse**, burning maximum **Entropy** without losing **Order**.
`rotation: 18s`
`duration: 2s`

**Unreasonable**: Enables **DOOM** to also proc **Havoc**.

**Unacceptable**: Enables **DOOM** to also stun.

**Unfortunate**: Enables **DOOM** to also critically hit.

**Diffusion**: Reduces all damage taken.
`amount: 0% - 20%`

**Dispersion**: Reduces the probability of critical attacks against you.
`scale: 0% - 30%`

**Blur**: Chance to completely evade any melee attack.
`chance: 0% - 20%`

**Mirage**: Chance to completely evade any ranged attack.
`chance: 0% - 20%`

**Spectre**: Chance to completely evade any attack.
`chance: 0% - 20%`

WIP: the healing part is weird. The name could be reused to be a Wisp synergy instead?
Or something else? And then Paradox to target something else?
**Anomaly**: Small chance that enemy attacks will heal you instead.
`chance: 0% - 3%`

**Paradox**: Allows **Anomaly** chance to also proc for attacks that have been evaded.

**Reflection**: Chance to reflect projectiles back to the attacker.
`chance: 0% - 10%`

**Mimic**: When a nearby enemy gains a positive effect, there is a chance to copy it.
`chance: 0% - 10%`

**Schism**: Chance on attack to convert a random positive effect of the target into a random negative one.
`chance: 0% - 5%`
