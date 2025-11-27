---
tags:
  - "original"
context:
  - "[[Project Spellblade]]"
---

# Project Spellblade - Spells

Player spells and abilities.

---

## Test

| Keys | Active       | CP Effect    | CP Gain            | Details                               |
| ---- | ------------ | ------------ | ------------------ | ------------------------------------- |
| JJ   | Melee1       | +power +stun | .                  | .                                     |
| JK   | Melee2       | +power +area | (?) per target hit | .                                     |
| JL   | Melee3       | +power +area | (?) per target hit | .                                     |
| KJ   | AOE          | +duration    | .                  | Attacks can extend duration slightly. |
| KK   | Block        | .            | per hit blocked    | .                                     |
| KL   | Regeneration | +duration    | .                  | Getting hit punishes this.            |
| LJ   | Bolt         | .            | .                  | .                                     |
| LK   | .            | .            | .                  | .                                     |
| LL   | Dash         | .            | .                  | .                                     |

## Design

(?) Consider blood as mana.

(?) Actually, should there be CP or Mana? Is there a difference?

(?) Consider no cooldown and no resource, just synergies and freedom.

| Keys | Active       | CP Effect    | CP Gain            | Details                               |
| ---- | ------------ | ------------ | ------------------ | ------------------------------------- |
| JJ   | Bash         | +power +stun | .                  | .                                     |
| JK   | Stomp        | +power +area | (?) per target hit | .                                     |
| JL   | Bolt         | +power +area | (?) per target hit | .                                     |
| KJ   | Enchant      | +duration    | .                  | Attacks can extend duration slightly. |
| KK   | Block        | .            | per hit blocked    | .                                     |
| KL   | Regeneration | +duration    | .                  | Getting hit punishes this.            |
| LJ   | .            | .            | .                  | .                                     |
| LK   | .            | .            | .                  | .                                     |
| LL   | Dash         | .            | .                  | .                                     |

Spells have no cooldown.

(?) There is no mana.

**Combo Points (CP)**: The player can stack up to `x` (modifiable) combo points. Some spells can spend the combo points to increase potency.

**Synergies**: Spells can have synergies between eachother:

- Bolt & MeleeStun: Hitting the Bolt with MeleeStun causes effect.
- Dash & Bolt: Casting Bolt quickly after Dash makes it fly faster.
- Block & Regeneration: Successful blocks increase Regeneration duration.
- Block & Enchant: Successful blocks increase Enchant duration.

## Spells

### Bash

Single target melee spell.

**CP**: +power, +stun

### Stomp

AOE spell around the player.

**CP**: +power, +area

- Gains CP per target hit.

### Bolt

Projectile spell.

**CP**: +power, +area

- Gains CP per target hit.

### Enchant

Attack buff.

**CP**: +duration

- Attacks can extend duration slightly.

### Block

Quick damage block.

- Gains CP on successful block.

### Regeneration

Heal over time.

**CP**: +duration

- Getting hit reduces duration!

### Dash

Short dash.

- (?) Decaying sprint after dash.

### Orbs

Creates `x` orbs around the player.
The player's melee attacks now shoot the orbs instead.

**Design Pros**: Gameplay variety & possible synergies.

**Design Cons**: Forces the player into a melee-only vs ranged-only state at a time.
If he chooses to play ranged-only, then this becomes just another aura bot.

### Mana Burn/Steal

Melee attack that burns/steals CP from the target.

### Life Tap

Sacrifices health to gain CP.
