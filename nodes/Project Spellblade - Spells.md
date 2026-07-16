---
tags:
  - "original"
context:
  - "[[Project Spellblade]]"
---

# Project Spellblade - Spells

Player spells and abilities.

---

## Ability Ideas

**Deflect**: Parry, basically.

**Absorb**: Absorbs all damage for `x` seconds and explodes upon expiration, dealing AOE damage based on how much was absorbed.

**TimeLapse**: Snapshots the current position and health (percent) of the player. After `x` seconds, returns the player (if alive) back to the same position with the same health.

**Projectile**: Self-explanatory.

**ForwardCone**: Self-explanatory.

**RingDamage**: Rings/Orbs around the player that deal damage.

## Stance Ideas

Passive stats while in the stance.
For example damage increase in offense, armor increase in defense.

Stance activation buffs/effects/spells.
. For sure have explosions on stance switch variants.
. The first attack after a stance switch is special.

Maybe holding the stance button for another thing?
Maybe some ULTIMATE ability? Like a big cooldown or something?

Imagine `keydown`, which just activates the stance.
But you hold it down for some time, and the player progressively slows down to a halt.
Animation could be crouching, as if focusing internally.
And then the awakening. Or chrono, or something.
. Maybe to fix the problem of which stance you got the bonus from, just have it while ultimate to have both stances effects or something? Or to be able to freely switch them with low cooldown?

---
---
---

## OLD

| Keys | Stance1   | Stance2 |
| ---- | --------- | ------- |
| `QQ` | Fireballs | -       |
| `QW` | Meteors   | -       |
| `QE` | Bombs     | -       |
| `WQ` | Slash     | -       |
| `WW` | Shield    | -       |
| `WE` | -         | -       |
| `EQ` | Haunt     | -       |
| `EW` | Empower   | -       |
| `EE` | Stance2   | Stance1 |

---

| Keys | Normal             | Empowered               |
| ---- | ------------------ | ----------------------- |
| `QQ` | Spread Projectiles | Single Projectile       |
| `QW` | Forward Stun       | -                       |
| `QE` | AOE Blast          | -                       |
| `WQ` | Summon             | Consume/Explode Summons |
| `WW` | Shield             | -                       |
| `WE` | Wisp               | Consume Wisps           |
| `EQ` | -                  | -                       |
| `EW` | -                  | -                       |
| `EE` | Empower            | Un-empower              |

---

(`WQ`) **Frontal Stun**: Frontal short-range AOE that also stuns.

(`QQ`) **Direct Projectile**: Single fireball-ish projectile
. Gets better/bigger the longer it travels.
. Maybe have it stun at max range instead, or analog stun depending on travel time.
. Idea is to try and use at max range.

(`QW`) **Spread Projectiles**: Multiple smaller projectiles in a cone or lightning channel.
. Could be a short channel like 'Dragon Arc' or 'Fork Lightning'.

(`QE`) **Area Damage**: #wip damage around the player.

(`WW`) **Shield**: Damage immunity for a short period.
. Explode after duration ends.
. Negative effect cleanse.
. Reflect projectiles.
. Damage attackers.

(`WE`) **Summon**: Small untargetable allies that follow the player and attack nearby enemies.
. Skills can unlock different types of summons, like the wc3 skeleton melee vs archer vs necromancer.
. SKills can unlock additional effects for summons, such as short range auras or onDeath effects.

(`EQ`) **Wisp**: Health regeneration over time. Taking damage removes one wisp. They could also have health and act as shield.
. Increased wisps max count.
. Small initial heal on spawn.
. Heal tick rate.
. Additional wisp per spawn.
. Attribute per wisp.
. More attributes per wisp.

(`EW`) **Aura**: #wip

(`EE`) **Empower**: #wip Empowers the next spell cast for a different variation?
