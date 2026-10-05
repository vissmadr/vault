# `2026-10-05`

[ ] **(!) Better Combo Input**:
. Sometimes between Dash & Chain & Fireball, the input misses.
. Need to make sure actions don't block eachother, for great combos.
. Player intent is king.
[ ] **(!) Fireball Parabola Input**:
. Improve it so the taps don't charge it.
. Charge (range) begins only after `n` seconds of hold, or some ease so it's not in the beginning.
. This is for better and more consistent combos.
[ ] **Less Parabola Range**

[ ] **Fireball Parabola Marker**:
. Something subtle on the ground to indicate where the parabola will fall.

[k] **Beam Ability**
[ ] **(?) Beam+Fireball Synergy**
. Very powerful blast?
. For that synergy the Beam prioritizes the Fireball.

[ ] **(?) Chain+Fireball synergy**
. Not sure; Can ruin the Parabola and then Pull intent?
[ ] **(?) Directional-only synergy**:
. Directional fireball, and the chain pops it, making it explode in circle AOE instead.
. Kinda needs to be done very fast one after the other.
. For that synergy the Chain prioritizes the Fireball.

[ ] **Bladeform Passive**:
. Gaining stacks every sec of not taking damage.

[ ] **(?) Laser-like Hitscan Ability?**:

[ ] **Intercept**:
. First attack can intercept.
. Having a short cooldown after no attacks, so that it's only the fresh first one.
. Visualize on action bars UI by slightly changing the attack icon so it shows when you can intercept.

[ ] **(?) Shield Counterspell/Merlin Ability**:
. Activate to have for `n` time.

[ ] **(?) Held AOE Charge ability**:
. Longer hold for more AOE.
. Tap for instant AOE.

# `2026-10-04`

[ ] **Fireball and Shatter extra VFX**:
. Additional non-gameplay projectile particles along the way.
. For fireball along the travel path.
. For shatter as additional small fragments.
. Basically tiny FireOrb visuals.

[ ] **(?) Parry-like Ability?**:
. Now we have the space for such an ability.
. Doesn't need to be a literal shield or parry.
. Could be Fiora/Beowulf/Romeo parry-like mechanic, where we absorb the hits, and counterattack, possibly with movement?
. Could replace Bullrush.

[ ] **(?) Zed Clone Ability?**:
. The double clone where we can swap with it.
. If it's a whole ability can be more advanced.

[ ] **Better Movement Ability?**

[ ] **Research Singleplayer Games Abilities**

[ ] **(?) Non-Fireball ability choice?**:
. Always have Attack, Dash, and Fireball, and from then on allow the player to choose his other 2-3 slots?

[k] **Decide on Convergence**:
. Can be a core mechanic, which solves the fire orbs.
. Shatter already works with it.
. If not, need to find a use for the fire orbs.
[k] If Convercence is Core:
. Refactor the codebase so that it's core and not a passive.
. Will be cleaner with the Shatter and stuff.
. Think about the FireOrbs and their passives, possibly cleanup some of them.

> Maybe just having Convergence is better, and frees up design space.
> Without it we would have to use stuff like Detonate, but we already have Special.
> And we already have other abilities, and potential abilities, too.

[k] **Lift Aim Gizmos**:
. World Z vertical height.

[k] **Forward Explosions**:
. Instead of circular explosions, try forward in the direction of impact.

# `2026-10-03`

[k] **Fire Arc**
[k] **Fire Arc Code Cleanup**

[k] **(?) Chain ability**:
. Grappling hook type?

[ ] **NPC Movement Patch**:
. Movement as a whole.
. Local avoidance and collision problems.
. Rethink what we currently have.
[ ] **Clone collisions**:
. They currently stack inside eachother.

[k] ~**(?) Simplify Fireball Direct**:~
. If the midpoint is at the end, like `>= 0.8`, can simplify.
. Remove the Direct fireball's speedup, keep it constant.
. And remove any Direct gizmo elongation.

[k] **Fireball Smart Gizmo**:
. Fills to indicate the transition.

# `2026-10-02`

[ ] **Divinum damaged feedback**:
. Not simply a vignette, there is more to it.
. Study it as it feels great.

[k] **(?) Try Convergence again?**:
. Could solve the FireOrbs again.
. Also for the FireballParabola, too.
. Since we always have at least one Fireball, right?
. And then leave a slot for some Ultimate ability?
[ ] **(?) FireOrbs on Melee Only**:
. More direct, easier to count without looking at UI.

[k] **Impact Direction Explosion**:
. Ravenswatch Fireball reference.
. The Grenade vs Fireball feel difference.

[ ] **Impact Direction Particle Velocity**:
. thehuglet idea & implementation about particle velocity.
. Particle velocity depends on the parent projectile's velocity.
. Code reference from chat.

[ ] **Environmental items/objects to explode**

[k] **Fuel from Fireball explosions**
. (!) Think about this.

[k] **(?) Think about optional held stance/modifier**:
. Solves the Fireball Direct/Parabola issue, as well as potentially others.
. Can be on the RB in controller, and Shift on keyboard?
. Could give more complex mechanics.

[k] **Both Fireball variants at once?**:
. Instead of choosing one, can have both of them available.
. (!) One action bar icon, two input buttons.
. You decide how you spend your Fireball cooldown/charge.
. Players choose where (or if) to bind their Fireball variants buttons.
. By default have both available, but on different keys.
. Some players might choose to use only one.
. Would make extra sense for the Convergence btw.

[k] ~**(?) Fireball Fun Passives**:~
. Need to return them now, actually.
. FireballParabola to have the bounce thing like in Hades 2.
. FireballDirect to try the Lich ultimate again, but maybe with the new blast.

[k] **Controller Hotkeys**

[x] **(?) Idea: Fireball melee hit synergy/mechanic**

[k] **Shield**:
. (?) Damage when it explodes.
. Aftereffect duration (`0.10`?).

Feedback:
> Likes the Detonate more than the Vortex.
> (Me too)

[ ] **Controller Suggested**:
. Directional with aim-assist will always be better for controller.
. Keyboard is still fine.
. Focus on controller.
. Steam thing to suggest controller.
. Intro thing to suggest controller.

# `2026-10-01`

[k] **(!) NO TARGETING IS BETTER!**:
. If the auto-aim and collisions are good enough.
. Single taps are always better.
. No pauses this way.
. **BETTER FLOW STATE**.

[k] Use new untargeted close Meteor:
. Make it not stop the player on use?

[k] ~**(!) Meteor uses slight velocity**:~
. Slightly bumps the (untargeted) Meteor direction based on player velocity?

[k] ~**Meteor continuous player movement**:~
. Don't stop the player unnecessary.

[k] **(?) Self Knockback on Abilities**:
. When casting stuff like Fireball.

> The Bullrush feels good to play with.
> Very dynamic and fun hit-and-run gameplay.
> (Second day) Still feels great.

> Parabola Fireball looks cool actually.
> While playing feels nice to throw something in the air for once.
> (Second day) Still feels great.

[k] **Smooth Appear Gizmos**:
. The Aim gizmos (Focus & Direction) should appear from nothing smoothly, not snap.
. Idea is that you might tap fast once for instant cast, no need gizmo then.

[k] ~**(?) Parabola Fireball could be without aim, just tap:**~
. Looks best when it's near I think?

[k] ~**(?) Not even Directional aim?**:~
. If the auto-aim is good/sane enough, then why even bother with aiming?
. Could just be infront of the player with the good autoaim maybe?

[k] ~**Focus with Directional Gizmo**:~
. Combining the best of both, showing the linear direction.

[k] ~**Better Aim Stop**:~
. Maybe better slow down to zero when aiming Directional.
. But configurable slowdown time, not using the default deceleration as it's too quick.
. Those abilities shouldn't be charged that long anyways, so it's fine to halt.
. But smooth to halt, so if you're fast, you have some of your speed remaining, like quick play.

[k] ~**Angle Compensation**:~
. Figure out if we should compensate for the (like isometric) squish.
. See if Hades does it for example.

[k] **Try t3ssel8r smarter auto-aim**:
. For the Directional aim thing.
. Thinking Directional + Good auto-aim might be best.
. Hades makes it work kinda? And Ravenswatch Fireball?

# `2026-09-30`

[k] **Camera Work**

[k] **Abilities GUI Menu**:
. Kinda like the Passives one, this time on `E` maybe?
. The player able to choose his abilities.

[ ] **(?) Ability Archetypes**:
. Group similar abilities into an archetype to choose one?

[k] **(?) FireOrb Spenders**:
. Maybe a single ability that spends FireOrbs?
. Could be Detonate, FirePet summon, something big, etc.

# `2026-09-29`

[k] ~**Consider Full Hex map**:~
. Both fire ground as well as collisions/pathfinding.

Story:
. Mother was scientist-like.
. She knew the world for what it is, and what needs to be done.
. Was aware of the corruption due to prolonged world incompletion.
. Wanted to complete the world.
. But she had to wait.
. Remained only because the child, for it to complete the world instead.
. When they found out, they killed her.
. Child of vengeance.

[ ] **Think/Reconsider Detonate ability**:
. What we want are the FireOrbs around the player, not necessarily the Detonate.
. FireOrbs could be another thing, or not as projectiles, but maybe as style or whatever.
. Or automatic agents.

[ ] **Try Focus targeted continuous stream**:
. Continuous like the Engineer TL2 barrage.
. Kinda like the Special, charge-based.

[ ] **Summoner Enemy Units**
. Unit that spawns other units.

[ ] **Area Caster Enemy Unit**
. Like the wizard enemies in Divinum.

# `2026-09-28`

[k] **Noise Randomized Fuel**:
. Noise fuel add, so that it's more irregular burn pattern.
. Like a noise scalar for the fuel field on top.

[k] **Immolation on SSS**:
. Consuming more and more the world around.
. This is what is left of it - revenge.
. Gus and his wine.

**Story: Not to escape due to revenge**:
. Because of the revenge, should not exit.
. Nothing to live but for _burning_ revenge.
. Can let another, pure, to exit.

# `2026-09-25`

**(?) Hit And Run**:
. For better hit and run mechanics, what about initial stagger/stun?
. And then enemies have some resistance after that? Idk.

Luck Cloud ideas:
```
- Nearby fog becomes clearer, so you can choose a route.
- Soaking briefly brightens the disappearing wisps, making collection readable.
- Different lighting or weather changes its tint and contrast.
```

Luck Cloud ideas:
```
Take the luck with you.
. Passing through golden mist charges your luck briefly, letting you dash into enemies and spend it attacking. A cloud has a limited amount to give before it needs to
recover. You get that “catch a favorable current” feeling without needing to fight inside it.

Your attacks burn holes in luck.
. Good fortune gets used up wherever you fight. A bright patch supports a short offensive burst, then fades, inviting you to relocate. I like the image of
carving a trail through golden weather. The risk is making movement feel like a chore when you wanted one more swing.

Waves reveal openings on enemies.
. As a wave passes through an enemy, one side briefly becomes lucky to attack from. You’re dashing around opponents to catch shifting openings. This could fit
the movement beautifully, although it overlaps with Duelist’s Brand’s directional positioning.

Close calls create luck.
. An enemy’s missed swing or narrowly avoided arrow leaves a short golden wake. Cut through it and your next attack gets better odds. Enemy aggression would
continually create opportunities to dodge, turn, and retaliate.
```

# `2026-09-24`

[ ] Boris Harizanov:
. "Shadowstrider" tag.

[ ] **(?) Minmap***:
. Could show enemies and also luck.
. Could slightly show the luck field even, if upgraded.

[ ] **Lucky/Unlucky Maps**:
. Luck scalar based on the map itself.

[ ] **On Numbers**:
. We either show numbers, or not at all.
. Without numbers we could rely on the "feel" of things.

# `2026-09-23`

[ ] **On-kill Passives**:
. Stuff that happen on kills.

[k] **Luck Waves**:
. Doesn't get more creative/special than that lol.
. See vault.

[ ] **Runes**:
. Divinum style.
. The "bonus" suddenly turns into a "rune" if the icon says so.
. Runes give better aesthetics to what would've just been a number.

[ ] **Burning Juxtapose Bonus**:
. Increases chance for clone spawn when hitting burning enemies (so that Fire is synergy).

[ ] **Buffs Bar**:
. Something WoW inspired maybe?

[ ] **Random Mini Explosions on Burning**:
. Burning enemies sometimes cause random small explosions.
. Maybe just on them? Or very small radius?

# `2026-09-21`

[ ] **UI Player Health**

[ ] **as**
[ ] **as**
[ ] **as**

[ ] **Fireball Travel Damage Increase**:
. Reason for the player to go out and shoot from max range.

[k] **Burn Slow**:
. Stacking slow based on Burn level?
. Mandatory to have I think.

[ ] **Bane of the Stricken**

[k] **While Moving, While Attacking**:
. Passive bonus while moving, passive bonus while Attacking.

[ ] **Bonus on >=3 Fireball targets hit**

[k] **Small FireOrb generation passive**:
. Small passive regeneration.

[ ] **Auto Tristana Bomb**:
. Chance to place Tristana bomb on target.

[ ] **LOTS of Combustion-related mechanics**:
. Can work if there is a powerup that acts in place of the Combustion.
. See `https://www.wowhead.com/talent-calc/mage/fire/sunfury/EAAAAAFFVVVUBU`
. Can work with something that we get, like a powerup.
. Immolation and/or SSS rank stuff maybe? Idk.

[ ] **Cheat Death**
. On cooldown.

[ ] **Explosion more damage to center**

[k] **Fireball Cooldown Reduction Mechanics**
. Stuff like melee hits and/or Burning to reduce Fireball cooldown.

[ ] **(?) After Crit Fail Success Stacking**:
. After each non-crit, stack increase the chance of the next crit.

[ ] **Cinderia Mechanics**:
. Instead of card draft ideas, Cinderia seems to have good progression.
. Roguelike unlocks, in-run ability talents, taint meter with curse.

[k] **Special FireOrbs**:
. Some orbs are bigger/different than others.
. Big orbs, lightning-infused orbs, etc.
. Both visually around the player, on the UI, and for Detonate.

# `2026-09-20`

**Kris Feedback**:
. Likes the overall mechanics.
. "It's great how responsive it is."
. Gets the overall mechanics fast.
. Likes the flames a lot.
. Used every single ability.
. Likes the Detonate alot.
. Does not like the Convergence.
. "Lightning is badass" - both Sky and Chain and Enchant.
. Didn't understand cooldown vs charge on Special.
. Liked the old special because it was long range and cool.
. Likes the Detonate and how responsive it is and doesn't stop you.
. Likes the autoaim of the Detonate and that you're accurate with it.

[ ] **Return Chrono**:
. No parry anymore.

[k] **(!) Draft can be Roguelike**:
. (!) Either the Card button experiment, or just Roguelike.
. (!) Cinderia for roguelike, ability talents, and curses!
. (!) Cinderia is a damn good reference it seems!

**Forward Autoaim Detonate**:
. It's just too cool to not Detonate lol.

**?Shield?**:
Maybe the Shield doesn't fit as much anyways?
Dash-only defense?
And Intercept, too.

# `2026-09-18`

[k] **Card Draft?**:
. Instead RollTheBones to draft a card, with greedy mechanic.

[k] **Experiment Automatic Immolation**:
. Maybe on `SSS` rank?

Immolation is cool.

The new special > old special.

~**Held Shield**: Holding shield can activate it as MerlinShield, but this time with a bigger cooldown?~
. Feels stupid.

# `2026-09-17`

[ ] **Boss Inverse Heal Mechanic**: Reverses the damage as healing for a duration.

Roll The Bones can be automatic, so you adapt all the time to current bonuses.
Or a roguelike mechanic.

[ ] **StackingForNextFireball**: Melee attacks increase the damage of next spell by `n`, stacking up to 20 times.

**BombOnHit**: Chance to place a bomb on enemy on melee hit, which detonates through Detonate/Fireball.

Brainstorming/playtesting critically and RollTheBones seems actually good.
. What else is the reson to use Immolate rather than Detonate for example? Both are AOE damage, so if one is stronger...

RollTheBones:
- Immolate
- Cheap Detonate/Fireball
- Clone powerup
- Clone caster
- Two Clones
- OnParry something
- Special recharge
- Heat regen
- More Heat generation
- Spending Heat gives Special charge
- Backstab

Active abilities:
- **Spawn FirePets**
- **Mark Nearby**

# `2026-09-16`

[ ] **Cosmetic Metaprogression**:
. `thehuglet` idea first.
. Reward for something specific and challenging, not just because.
. Reward for "no hit run", tie it to achievements.

[ ] **Clone & Immolation synergies**:
. Both burning?

[k] **Clone Explode**:
. At the end of its lifetime.
. Can synergize well with the swap.

If RollTheBones is a thing:
[ ] **RTB Slot/Cards Visual**: In the center of the screen, could be the upper-middle, have like 1, 2, 3, cards/slots revealing/dropping for the 3 (or so) bonuses that you will have.
[ ] **Variety not from Roguelike**: This mechanic could potentially give us the gameplay variety without needing to use roguelike mechanics. Like you adapt to whatever the current roll.
[ ] **Lucky Rolls**: Some rolls could have a chance for sudden more bonus cards and stuff, or rarity for the buffs.
[ ] **RARITY**: Cards can have rarity, which also works for the randomness factor, like buffs, but could be rare, epic, legendary, etc.

# `2026-09-14`

**Focus Art**: The Focus circle/thing can look better.
. Could have levels (0-5) relative to the Heat points.

# `2026-09-13`

[ ] **Passives**:
- After spellcast, gain bonus(es) (attackspeed?).
- Melee attacks stack next spell bonus(es).
- Every `n`-th (4th?) Fireball/Detonate has bonus.
- Every `n`-th Melee Attack has bonus.
- After `n` seconds, next Attack is empowered.
- Not taking damage for `n` seconds grants Bubble.
- Every `n`-th Parry something.
- While Sprint then a Melee Attack has bonus.

[k] **Short Meditate Focus**:
. Entering Focus gives a brief meditate Heat generation.

[k] **Lightning Passives on SSS**: 
. Abilities affected by lightning?
. Random SkyLightning falls?
. Random zaps?

[k] **Fiora Passive**:
. Random vitals revealed on random enemies for bonus(es).

[k] **Fire Remnant**: Send out a Fire Remnant at the location, mimicing the player.
. On re-activation, orbDash/blink fast towards the remnant.
. Basically Zed & Ember Spirit.
. The remnant could move and attack maybe.
. Arrow towards the Remnant.
. Possibly multiple Remnants, with direction for consume.
. A way to trigger a 2nd remnant through something.

[ ] **Offense Immolation**:
. _DOOM / Spectral Dagger_
. Immolation, but targeted at an enemy, burning heavily.
. Works the same way as player immolation, meaning burns other enemies nearby.
. Also sets the ground on fire.

[ ] **(?) Bonus on Scorch**:
. Maybe some slight bonus while walking over Scorch ground.

[ ] **Mark Focus Ability**: Maybe can mark an enemy inside the circle for the Fiora ultimate?
. Completing the Fiora ultimate, or killing the enemy, grants a bonus?
. Can combine this with Roll the Bones? Or it can be its own thing.

## Boss Abilities

Lots of the abovementioned are viable.
Some abilities are probably better suited for bosses.

**Duel Zone**: AOE around a Boss, immune to all damage outside of it.

# `2026-09-12`

[k] Remove Dash from action bars.
. This will allow better Permutations.

[k] Permutations with Auto Focus.

# `2026-09-11`

**MINIGAMES**
**MINIGAMES**
**MINIGAMES**
**MINIGAMES**
**MINIGAMES**
**MINIGAMES**
**MINIGAMES**
**MINIGAMES**

**Roll The Bones**:
. Thinking of buffs that are not only stats, but also change your gameplay.
. Not forced to adapt gameplay to the buff, but good if you do.
. Could combine both gameplay buffs as well as passive buffs, maybe randomly?

Active Buffs List:
- Immolation: Close range combat in order to burn enemies in AOE.
- Chrono: sex?
- Away Focus: Rapidly generates Heat and Special charges as long as no enemies nearby.
- Next Attack: Once every `n` seconds of no attacking, empowers the next attack greatly. Will do hit-and-run gameplay.
- (?) Detonate: Chance to not consume FireOrbs, or deterministic every 2nd doesn't consume.
- StackUnleash: All the heat spend during the buff will be released in an explosion around the player when the buff ends.
- FireEcho: Casting leaves an echo character that will repeat the last spell cast after a delay.
- Juxtapose: Chance on attack to summon a clone.
- FireSpawner: Summons FireSpawns one by one.

Passive Buff List:
- Passive Heat generation.
- Movespeed increase.
- Critical chance.
- Firebombs cooldown reduction.

**Combine Both**: Thinking to have one gameplay active buff, and then one or many passive buffs, randomly.
. This way you have one overall thing you can adapt your gameplay to, and some additional buffs that are just useful.

Permutations can all be combo point spenders, so they don't need cooldowns?
Also they can use visual fire orbs?

[k] ROLL THE BONES!
[k] Smaller Lightning bar in place of Mana.
[k] Ability cooldowns instead of Mana.

**Cooldowns**: Per ability instead of mana.
. Already standard in so many games of the genre.
. Can be done good with the UI and cooldowns.
. Think of Cind, Had, WoL, Dea... all, lol.
. Already have UI to track it.
. WoL Firedragons charges.

# `2026-09-09`

[k] (!) Engineer pins could be fire orbs?
. They could be harder to get?
. And since related to Heat, impermanent, solving the issue.
. Makes perfect sense for the Detonate visuals, and Fireball (Convergence) visuals then.

Torchlight 2 fills.

# `2026-09-08`

Both Mana and Heat bars.

# `2026-09-06`

Core 4 abilities gameplay is good.
Now not sure about the Permutations abilities.

Don't know if I like the automatic FireOrbs launch ability.
Maybe more like ammo?
Like fuck the meditate maybe.

Could make it non-Focus?

**NEED SOME LIGHTNING SOMEHOW**

(if Focus) Different behavior of Fireball when it's melee.

What if Lightning is the Fury (style) thing?
Where you automatically enter Lightning mode.
And everything is converted to Lightning for some time, like FireEnchant into LightningEnchant, the spells, etc.

**Attack**:
**Dash**:
**Parry**:
**Special**: Core spell, thinking Firebombs.
**Permutations**: Permutation mode of spells. Could be Fireball and FireOrbs and stuff.

Also combos!

# `2026-09-04`

**FINDINGS**:
- Don't really like the old Meditate orbs movement.
- Like Orbs as ammo more I think.

[k] Meteor Mode?
. Have it as a mode, where different keys do different things.
. Still have the Fire permutation thing.
. Could be the Meditate again? With Meteor-like Detonations.
. Maybe more direct than the old Meditate, meaning FireOrbs are just Ammo, not that much control?
. Have them maybe like Detonate (one by one), Fireball (all Convergence), Enchant (go to sword), Vortex, Shield, experiment.

# `2026-09-03`

**Fire Tristana Bomb Plant**:
. Basically the Tristana bomb on a target.
. Hitting the target in melee adds to the explosion.

# `2026-09-02`

Could go for 3x3 permutations too, or 2x4 / 2x5, because there are lots of good ideas and abilities.

# `2026-09-01`

**Held Permutations**: New Fire & Lightning permutations allow us to hold them for something special?
. Because the first press doesn't do anything on its own anyways.

# `2026-08-31`

**Automatic FireOrbs**:
. Maybe we can try with FireOrbs having automatic behavior.
. Instead of having to manually use them, to use them through Convergence, or like the finisher to detonate FireOrbs on the enemy instead of Detonate button.

# `2026-08-31`

**Gameplay Redesign**

```
J: Attack
K: Dash
L: Parry
U: Fire
I: Lightning
O: ?
```

The Attack, Dash, and Parry need to be excellent.

Then, the premutations should do a good work of additional abilities.
Important to have good visuals when first clicking the permutation button.

Choice between `2` vs `3` permutation buttons.
Can be Fire & Lightning as permutations, with the `O` button free for something else.

# `2026-08-30`

Maybe no STATES?
. Don't know, it seems slow kinda.
. Feels better if everything is action-based I think.

Two weapons suck!
. Played Divinum and didn't feel the need to swap weapons at any point.
. Ended up only playing with the sword.

# `2026-08-28`

**Stagger and Parry**: Can be stagger-based combat like WoL.
. Stagger-based makes it good when you hit first, gives the certainty you will continue the combo, like WoL.
. Sometimes enemies can break out of stagger, and that's when you have to react with Parry/Dash. Otherwise spam attack for stagger chain.

**(?) No Meditate**: Think about removing Meditate.
. Think about automatic FireOrbs.

**Mark**: On an enemy that received many attacks?

Multi color flames.
Like purple, etc.

```
J: Attack
K: Dash
L: Parry

QQ: Something1
QW: Something2
QE: Something3

WQ: Fire1
WW: Fire2
WE: Fire3

EQ: Spark1
EW: Spark2
EE: Spark3
```

# `2026-08-24`

Denis:
. Rigged plane.
. Noise displacement.

# `2026-08-19`

The lightning can consume all the fire, like orbs and FireEnchant and convert into lightning stuff, like LightningEnchant.

Can add the Mantle effect to buffs that happen on stance switch maybe?

Lightning stance to have Meditate, but this time it's truly powerful Carmilla orb or something?
With cool visuals, with the particles of the trail, and many of the GroundArcs to the ground and stuff.

Zakk and marketing:

- Start with a big reveal trailer first.
- After that can do the devlogs, but as a secondary thing.
- Talk to people and research how Steam works.

# `2026-08-18`

What if you build up Heat as a resource.
The more Heat, the easier to gain FireOrbs and such.

You can then discharge Heat into Lightning at a very fast rate.
Meaning that Lightning is stronger and as a burst, but limited by Heat resource.

Potential also for Overheat mechanic.

What if the Lightning stance's overall strength is determined on the level of the bar?
So that you're always free to change stances, but if the bar is depleted it's just going to be weaker.

# `2026-08-17`

Normal:
    (j) Attack
    (k) Dash
    (l) Shield
    (u) Detonate
    (i) Meditate
    (o) Spell

Meditate:
    (j) Enchant
    (k) Exit
    (l) Shield
    (u) Detonate
    (i) Exit
    (o) Vortex

Lightning-Normal:
    (j) Attack
    (k) Dash
    (l) Shield
    (u) Detonate
    (i) Meditate
    (o) Spell

Lightning-Meditate:
    (j) Enchant
    (k) Exit
    (l) Shield
    (u) Detonate
    (i) Exit
    (o) Vortex

# `2026-08-17`

[k] Think about abilities/input redesign again, with Empower & LightningEmpower maybe.

[k] (!) Think about removing shield for a LightningStance or LightningCharge/Empower or Mark again.
. Shield can sometimes fight the design, an example of this being the Chrono, and Hades being without a shield.
. The button can then be used for something Lightning or Mark.
. Can experiment for cool lightning visuals and stuff with the sword Enchant vfx and the huglet hue shift idea and lightnign particles vfx.

[k] (!) FireExplosions give FireEnchant automatically.
. Reconsider having an active ability for FireEnchant then?
. Can be freed up for other things if so.
. Gameplay becomes close orb Detonating to keep FireEnchant up, hitting MeleeFireball, etc.
. Can be rebalanced for both time and number-of-attacks, too.

[k] Chrono visual effect.
. Some full-screen post-process thing maybe? Like the shader debug views?

[k] Analog fire orbs experiment.
. Having a bar that fills by acting/meditating.
. The bar has visual separators for how many orbs.

[k] (!) Style-related Heat generation.

# `2026-08-12`

[ ] huglet visual ideas from the reference.
```
vissmadr — 9:55 PM
Amazing, as usual
I like how it's not simply fire orange-ish but it fades into this purple-magenta color
looks awesome
huglet [LUE!],  — 10:07 PM
heh that's actually my secret sauce to nice looking VFX
hue shifting everywhere
almost every effect in my game has hue shifting over lifetime
vissmadr — 10:10 PM
I should play around with that, seems like a ton of value from a relatively simple concept
embedFile("sietse") [FART],  — 10:11 PM
Lue shifting
huglet [LUE!],  — 10:16 PM
it makes a world of a difference
its especially potent when you spawn a cluster of particles with differing lifetimes, some will hue shift faster than others
gives it chonk
```

Now that the design is heavy on the Meditate as a stance, I should play Melusine.
Want to feel how the gameplay feels there, see if I can learn anything from her.

# `2026-08-11`

The machine doesn't agree with the philosophy of it's nature.
And yet it's all it is and all it can do.

"Imagine fixing something for once."

# `2026-08-10`

**TUNE EVERYTHING DOWN!**
. Chaos right now, but should be tuned down for the actual game.

[k] While Meditating for the Fireball to be FireNova AOE?

Could still go for stances, but less changing the abilities?

[k] Yamamoto Bankai ultimate.

Balance Fire vs Melee.
Melee should have bonuses against burning, but not apply that much burning itself.
Idea is that you try to burn enemies, and then attack them, but not just attack and they auto-burn.
Like the focus of the player should be to *spread the fire* and then *abuse burning enemies*.

Held attack to be like dash-spin-attack?
Some variety, not just "normal attack but with fire".
The normal combo can have a wave?
Or to avoid the problem of melee burn spam, consume FireOrbs or whatever resource for the wave?

# `2026-08-05`

ULTRAKILL-inspired Fire lore.
To ashes.

# `2026-08-03`

Badass fire quotes.
Originally a 'Fire Destroyer' program, but redemption arc or something?

# `2026-07-29`

Burning and Scorch durations should be short by default.
. Exception to this would be upgrades, like augments and stuff.
. Like short burns for only a few seconds.
. This improves the dynamics of the game.
. Beowulf ignite is `5` seconds with `+2` from talent.

[k] (?) Buffs/Debuffs indicators.
. Hmm, maybe, not sure.

[k] Lightning from the sky?
. Like DotA 2 Zeus W/R.
. Can synergize to proc when hitting with Attack or Fireball explosion.
. Direct Fireball hit spawns it. And then the Cascade augment naturally.
. Can be used for random nearby enemy lightning passive.

[k] Brand/Lich ultimate?

[ ] Omnislash?

[k] Fiora ultimate?
. Hitting a target many times activates the ring.
. This means it will be mostly vs bosses and elites, as intended.
. When the ring completes, maybe some cool ground thing or player power or chrono.

[k] Cooldown reduction/reset on kill?
. Or whatever the antispam mechanic it is, such as mana.

[k] Puck Q swap?

# `2026-07-27`

[k] Dash+Fireball synergy.
. Maybe speed up the Fireball greatly after dash?
. Could be made to be faster and therefore travel more distance.

[k] Projectile Eater Fireball.

[k] Luck waves.
. Doesn't get more creative/special than that lol.
. See vault.

[k] Fireball explosion leaves Scorch.
. "Scorch" is fire on the ground. Just ground AOE that stays there and damages enemies that walk on it.
. Multiple Scorch should not stack. I mean they can cover more area no problem, but the damage doesn't overlap. Like a boolean, an enemy is either on Scorch ground or not, thus either taking damage from (a single) Scorch or not.
. Maybe FireOrbs explosions too?
. Scorch area radius is based on the explosion radius that spawned it. Therefore small explosions spawn small Scorch area, big explosions spawn big Scorch area. Therefore for example the normal Fireball explosion will spawn a Scorch, and the bigger melee-detonated Fireball with bigger explosion AOE will spawn bigger scorch.

[k] (!) Spawns! Fire elementals?
. No action button for it, somewhat "passive", meaning activated by skills/upgrades/synergies.
. Enigma DotA 2 Eidolons.
. Instead of an ability, this could be a passive, or chained to abilities.
. Like the TL2 where it spawns the shadow creatures on kill or something.
. Or spawns them when hitting/burning enemies with some condition.
. And then we can use it for the Juxtapose, like more elementals leads to more elementals.

# `2026-07-25`

Thinking stances better maybe...

[ ] EmpowerCharges
. Empower button that affects the next ability.
. Have player charges, like combo points, that can be used for the Empower.

Stance could also become Empower, same level of complexity almost.
. Think about the visuals and feel between Fire & Lightning.

Try both, both can be great.
. Maybe literally implement both?
. Playtest with people until decision?

# `2026-07-24`

[k] Just copy some mechanics from Divinum, it feels so great!
. What an amazing game feel it has.
. The Runes, the Masteries, the Skills.
. The way Attacks work.
. The iframes on Parry, Dash, and Attack-Intercept.
. How fast-paced, controllable, and forgiving it is.

# `2026-07-23`

[k] Use the Body Mantle effect.
. Already implemented and waiting.

[k] IT HAS TO BE PARRY!
. Figure out what form exactly, but it feels good!
. Maybe use the bubble visual for something else? Or for this, but think about it.
. No need for cooldown reset I think.
. Feels good in Divin, also in Cinderia.

Lightning stance is more RNG.
. "Chance on hit to strike nearby enemies with lightning."

[k] Study Divinum.
. [Divinum](https://store.steampowered.com/app/1148130/Divinum/)

[k] [Yomi no Kuni](https://store.steampowered.com/app/4103600/Yomi_no_Kuni/)
. This needs to be studied.

[ ] Sword Slash Arc + Trail + Impact VFX
. Maybe all of them, both trail and arc would be best.
. `codex resume, then select sword-slash-arc-trail (019f9052-5379-7481-95aa-67aefff7ed94)`

[k] Dash-attack.

# `2026-07-22`

[k] Phantom Lancer: Your (Lightning-only?) attacks have a chance to spawn a clone.
. Clones are short-lived and attack an enemy.
. Juxtapose: Makes clones also have this passive chance (limit this to a cap).
. Talent: Increases chance for clone spawn when hitting burning enemies (so that Fire is synergy).

[k] What if Special is a continuous flame/lightning?
. You hold it down for continuous stream of damage.
. For Fire maybe hold down to stream Rumble flames while slowly(?) moving.
. For Lightning could do something else, like charge and release for lightning?
. Could be the consumer of (visible orbs) lightning charges?
. Carmilla Orb?
. Chidori?

Enemy/Bossfight where they can friendly-fire eachother.

Adding a 6th action button like 'Power' is fine for ergonomics.
. Consider if it's needed for more player gameplay complexity.
. If you REALLY want complexity, it could be an 'Empower' lol.
. Or a 'Power' that does some form of buff or AOE around you?
. Or it could be a mark and mark consume? Lee Sin?

# `2026-07-21`

**Gainer & Spender**: Need this type of core mechanic.
Could do Attack-based gainer and Special-based spender for example.

**Posture**: Think about which abilities deal more posture vs health damage.

# Misc

After testing, figured out Hades/HLD style charged attack instead of the Sekiro one.
This is more suited to the top-down gameplay. Sekiro one is too unresponsive for this.

Feels good already. This is it, close it.
Now it just needs better tuning and animations.

[k] For the normal attack itself, can still think about combos though.

TLDR lock the keydown normal and the charge on second.

---

Combo points can come through the orbs.
Just like D2 visuals.
"Charges" basically.

---

Try the flame attack maybe as a dash forward and punch with the other hand for AOE?

And/or change the heavy followup.

---

Fire and Lightning.

Gaining charge through motion?

# Driving to Sea

*This is already good enough for a game. Plus everything that will emerge. So just lock in!*

*It's actually getting there. Stop with the paralysis and make it. Promise it's good if made well.*

`2026-07-18`

## Gameplay

**Fire & Lightning**: Could create the overall feeling.
. Fire can have obvious burn effects.
. Lightning can have obvious chain-lightning effects.
. Lightning can have clones, which is cool. Maybe short-lived?
. Could also try Fire clones, that could also be fun.
. Check the old `skills-draft.md` for ideas for the two.

**Ability Buttons**:
- Attack: Attack combo chain, as well as charge-attack on hold.
- Dash:
- Stance: Switch on keydown, can hold for a stance-based special, or something.
- Defense: Can be parry-ish, or Sekiro guard, or can be a MerlinShield spell.
- Cast: Think about the Sekiro frontal fire explosion thing. Not that much range better. Plus fire and lightning variants.

Think 5 buttons are enough. Especially with the advanced mechanics on keydown and keyup.

**Stance**: Can become Fire and Lightning stance.
. Can create interesting gameplay.

**Attack**: Better to have the combos.
I think the first two attacks can be normal slashes, and then the 3rd and 4th are different each, with a finisher.

**Charge-Attack**: With the combo-based attack, the charge-attack can now being different based on which attack it is.
. For example charging after the 3rd or 4th can result in different charged attack.

**Marked-Strike**: Really want to have that option at some point, but not sure where to put it.
. Can be on the shield, like if you hold... or nah fuck it.
. (!) What if the last attack, and/or the charged attack, apply marks to the targets.
. (!) Could somehow jump on a marked target.

## Effects

**Sword Arc**: Would be cool to have both Fire and Lightning arcs.

**Fire & Lightning**: With a scope of only two elements, can really work to make them look good.
. Will be a quality>quantity thing, and an investment in those two can really pay off.

Can also try that heat-blur effect thing.

## Meta

Classic WoW-like talent pages for each thing, for example: Body, Mind, Strategy, Blade, Fire, Spark...

Talents can be rows of 3 choices, from which you select 2/3.

Should be able to simultaneously invest in different pages.

The thalent progression can be belt color systems.
White, Blue, Purple, Brown, Black, and last only one row Red.

## Lore

"By Fire and Spark!"

**Robot Humanoid**: Cn fit well with the Fire and Lightning.

**Sage**: The "learned one" knows everything about the "world" (system) at this point.
. He knows the world and him are one, as well as all others within it.
. But the dilemma that one can exit. One within the world, but one can exit.

**Arc Warden**: Really fits the Lightning part.
. Both aesthetically and philosophically.

"Animal or machine?"
"- Does it matter?"

## Characters

**Player**: Robot, some clothing, belt, sword, maybe orbs? Idk about the orbs.
. See Project Yi or something, lol.

## Environment

**Eden**: Beautiful small and cozy starting zone where the player (robot) initially spawns.
. Can stay there indefinitely, but have the choice to open a "Pandora" thing.
. Opening the Pandora thing leads to a bossfight.
. "Curiosity check: Passed"

**Tunnel**: Try a long tunnel.

**Water Labyrinth**: Torchlight-inspired.

**Room of Corpses**: Boss room full of robot parts. Hints about the thousands of previous iterations.
. Can progressively fill with corpses the multiple times you enter.

**Sage's Garden**: The place where the learned one spawns his trees and geometry objects and stuff.
