---
tags:
  - "original"
context:
  - "[[Project Spellblade]]"
---

# Project Spellblade - Spells

Active player abilities.

---

## Design 3

Spells have no cooldown.

**CP**: Spells can use combo points (CP) to increase potency.

**Max CP**: The player can stack up to `5` combo points.

| Orbs | Active               | CP Dump | CP Effect | Details             |
| ---- | -------------------- | ------- | --------- | ------------------- |
| JJ   | FlameSlash & Enchant | all     | +duration | .                   |
| JK   | OffenseAOE           | all     | +power    | +CP per target hit  |
| JL   | OffenseBolt          | all     | +power    | +CP per target hit  |
| KJ   | Stun                 | .       | .         | .                   |
| KK   | Block & Shield       | .       | .         | +CP per hit blocked |
| KL   | Heal & Regen         | all     | +duration | .                   |
| LJ   | Shukuchi             | .       | .         | .                   |
| LK   | SlowAura             | .       | .         | .                   |
| LL   | Dash & Sprint        | .       | .         | .                   |

## Design 2

`JJ`: OffenseFront → null
`JK`: OffenseAOE → null
`JL`: OffenseBolt → null

`KJ`: Stun → null
`KK`: **Block** → **Shield**
`KL`: BuffDefense → null

`LJ`: SummonOffense → null
`LK`: SummonBuff → null
`LL`: **Dash** → **Sprint**

## Design 1

**OffenseBolt**: Projectile forward.
**OffenseAOE**: Damage in AOE around the player.
**OffenseGround**: Damage that remains on the ground.
**OffenseMeleeBuff**: Special slash attack that enchants the blade afterwards.

**BuffOffense**: Immolation aura maybe.
**Shield**: Instant deflection.
**BuffDefense**: Defensive armor aura.
**Stun**: Melee stun attack.

**SummonOffense**: Serpent ward.
**SummonBuff**: Totem buff.
**Dash**: Dash with a sprint afterwards.
**Push**: Push maybe?
