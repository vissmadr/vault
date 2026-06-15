## Design direction

Your idea is strongest when the **hero and the buildings solve different problems**.

The player character should be the flexible problem-solver: rotating between lanes, dueling elites, saving failing fronts, using skill-based combat, interrupting siege units, collecting resources, activating buildings, and making clutch decisions.

The buildings should be the strategic plan: economy, passive damage, delay, unit production, repairs, buffs, map control, and long-term scaling. The danger is making buildings feel like “shops with health bars.” Your Blacksmith example works better if its physical presence matters: it occupies a defendable location, unlocks weapon upgrade paths, maybe powers nearby towers, maybe requires workers, maybe produces upgrade materials over time.

I would strongly consider a **hybrid between Thronefall’s preset nodes and Warcraft-style freedom**:

* **Preset major buildings**: blacksmith, barracks, farm, mage tower, shrine, town hall, walls.
* **Limited free-placement tactical objects**: traps, barricades, temporary turrets, mines, rally flags.
* **Map-specific upgrade slots**: “this hill can become an archer tower or signal fire,” “this ruin can become a shrine or barracks,” etc.

That gives you the elegance and readability of Thronefall, while preserving some creative expression from RTS/tower-defense games.

Thronefall is very relevant because it already frames the loop as building a kingdom by day, defending it by night, balancing economy/defense, recruiting troops, fortifying walls, and personally charging into battle. ([Steam Store][1]) Orcs Must Die! is the other obvious pillar: it combines third-person combat with trap-laying and wave defense; the newer Deathtrap adds roguelite-style character progression on top. ([Steam Store][2]) AirMech is useful specifically for the “single controlled unit as commander/combatant” angle, because it mixes fast action-RTS play with constructing and ordering AI units. ([Steam Store][3])

## Preset buildings vs grid building

A **free grid** gives creativity, emergent pathing, and player ownership, but it also adds a lot of design cost: pathfinding abuse, ugly optimal layouts, wall spam, slow planning, balance complexity, and UI burden.

A **preset-node system** gives much stronger control over pacing and readability. It lets you make each map feel handcrafted. It also lets combat stay the focus, because the player is not spending half the game playing mini-RTS construction Tetris.

The risk with preset nodes is that choices can become obvious. To avoid that, make nodes have **branching identities**, not just linear upgrades:

Example: one tower foundation can become:

* **Ballista Tower**: elite/boss damage.
* **Archer Tower**: anti-swarm sustained fire.
* **Frost Tower**: slows enemies, enables hero combos.
* **Beacon Tower**: buffs nearby troops and reveals incoming waves.

Same node, different strategic plan.

For the Blacksmith:

* Tier 1: unlocks basic weapon upgrade.
* Tier 2A: hero damage path.
* Tier 2B: tower/trap enhancement path.
* Tier 2C: troop armor path.
* Active interaction: spend gold to “overforge” your weapon for the next wave.
* Vulnerability: if destroyed, upgrades remain but future upgrades/repairs are unavailable until rebuilt.

That makes it a **place in the world**, not just a menu.

## The key balance question

The game should constantly ask:

> “Where should the player personally intervene?”

Buildings should handle predictable pressure. The hero should handle exceptions.

Good enemy types for that:

* **Swarm enemies**: towers/traps should mostly handle them.
* **Shield enemies**: need hero flanking or specific tower counters.
* **Siege enemies**: attack buildings from range; force the hero to respond.
* **Saboteurs**: ignore the core and target farms/blacksmith/barracks.
* **Fast runners**: test slows, walls, and player mobility.
* **Elites/bosses**: require player combat skill plus prepared defenses.
* **Support enemies**: buff or shield waves unless interrupted.

This makes the player feel heroic without making buildings irrelevant.

## Games worth studying

### Closest references

**Thronefall** — study its economy/defense readability, day/night structure, preset building nodes, and how little UI it needs to create meaningful decisions. ([Steam Store][1])

**Orcs Must Die! 3 / Orcs Must Die! Deathtrap** — study trap placement, chokepoint design, hero loadouts, enemy routing, and the balance between personal combat and automated defenses. Deathtrap is especially relevant if you want roguelite progression. ([Steam Store][2])

**Dungeon Defenders / Dungeon Defenders II** — study hero classes, tower-building during defense, repairs/upgrades, loot, co-op scaling, and how action-RPG progression can sit inside tower defense. ([Steam Store][4])

**Sanctum 2** — study “core defense” with direct player shooting plus tower placement, especially how it makes loadout choices matter before a wave starts. ([coffeestain.com][5])

**AirMech Strike** — study the player as a mobile commander: fighting, transporting, building, ordering units, capturing bases, and influencing the battlefield without becoming a traditional RTS cursor. ([Steam Store][3])

### Very relevant adjacent games

**Kingdom Two Crowns** — maybe more relevant than it first appears. It has a single controlled ruler, coin spending, preset-ish expansion, workers, archers, walls, night attacks, and a strong “I influence the kingdom but don’t directly control everyone” feeling. ([Steam Store][6])

**Tribes of Midgard** — study the village-defense loop: action RPG exploration/combat by day, home-base growth, and enemies attacking the settlement at night. ([Tribes of Midgard][7])

**The Riftbreaker** — study base-building plus action-RPG combat, especially large-scale attacks, research, resources, and the fantasy of personally defending a growing base. ([The Riftbreaker][8])

**X-Morph: Defense** — study top-down shooter plus tower defense, build mode vs combat mode, maze-building, and environmental control. ([Steam Store][9])

**Deathtrap** — not Orcs Must Die Deathtrap, but Neocore’s 2015 game. Useful for Diablo-like action-RPG combat with tower-defense/trap systems. ([Steam Store][10])

**Iron Brigade** — study third-person shooter/tower defense with mobile firepower plus stationary defenses. ([Double Fine Productions][11])

**Fortified** — study hero classes, defensive structures, commanded army elements, and third-person combat against waves. ([Steam Store][12])

**Toy Soldiers HD** — study the “commander who can directly possess/use defenses” angle: strategic placement plus manual control of battlefield assets. ([Steam Store][13])

**Sang-Froid: Tales of Werewolves** — study planning-phase traps followed by real-time third-person execution. Very useful for the “day plan / night survive” structure. ([Steam Store][14])

### Study for economy, waves, and base pressure

**They Are Billions** — study escalating swarms, economy greed, perimeter defense, expansion pressure, and catastrophic breaches. It lacks the single action hero focus, but its wave pressure is highly relevant. ([Steam Store][15])

**Age of Darkness: Final Stand** — study hero-led survival RTS defense, day/night pressure, swarms in the thousands, and “final stand” pacing. ([Age of Darkness][16])

**Mindustry** — study how logistics can feed defenses. Probably too factory-heavy for your core idea, but useful if you want buildings to require supply chains rather than just gold. ([Google Play][17])

**Super Fantasy Kingdom** — study city-building, roguelite runs, defenders, resources, and night attacks; useful if you lean more into settlement management than direct hero combat. ([Steam Store][18])

**Nordhold** — study city-building plus tower defense with hero power, economy growth, and replayable wave preparation. ([Steam Store][19])

**Cataclismo** — study fortress construction and destructible/physical defense layouts. Probably more building-heavy than your target, but useful for thinking about walls and defensive architecture. ([Steam Community][20])

### Community/design-history references

**Warcraft III custom maps** — especially Hero Defense, Tower Defense, Castle Defense, X Hero Siege-style maps, Legion TD-style maps, and AoS/DotA-like maps. Warcraft III’s custom-game ecosystem is historically important for this design space, and Blizzard still advertises the World Editor/custom maps as including tower defense, MOBAs, RPGs, and other player-created game types. ([eu.shop.battle.net][21]) Community map repositories are also useful for browsing TD and hero-defense variants. ([maps.w3reforged.com][22])

**Dota-style lane defense** — not because you should copy PvP MOBA structure, but because it has useful ideas: lane pressure, defensive towers as time buffers, barracks as wave-scaling objectives, and a final Ancient/core as the ultimate fail state. Dota’s barracks/super-creep relationship is a useful reference for “destroyed structure changes future wave pressure.” ([dota2.fandom.com][23])

## A strong prototype shape

I would prototype this first:

**One hero. One keep. Three lanes. Six building nodes. Ten waves.**

Buildings:

* **Farm**: economy scaling.
* **Blacksmith**: hero upgrades.
* **Barracks**: friendly units.
* **Tower node x2**: damage/control choices.
* **Shrine or Mage Tower**: active ability / global support.

Hero:

* Fast, readable top-down action.
* 2 basic attacks, 1 dodge, 2 abilities.
* Can repair, overcharge, or rally buildings.
* Strong enough to save one front, not all fronts.

Wave structure:

* Between waves: spend gold, upgrade, choose risk/reward.
* During waves: no deep menus; only quick interactions.
* Every third wave introduces a “problem enemy” that invalidates a lazy build.

The most promising identity is probably:

> **A compact action roguelite defense game where maps are handcrafted like Thronefall, combat feels closer to Hades/Wizard of Legend, and buildings act as strategic loadout pieces rather than passive decorations.**

That is distinct enough from pure tower defense, pure action roguelike, and full RTS.

[1]: https://store.steampowered.com/app/2239150/Thronefall/?utm_source=chatgpt.com "Thronefall on Steam"
[2]: https://store.steampowered.com/app/1522820/Orcs_Must_Die_3/?utm_source=chatgpt.com "Orcs Must Die! 3"
[3]: https://store.steampowered.com/app/206500/AirMech/?curator_clanid=3229727&l=swedish&snr=1_1056_4_1056_curator-tabs&utm_source=chatgpt.com "AirMech på Steam"
[4]: https://store.steampowered.com/app/65800/Dungeon_Defenders/?utm_source=chatgpt.com "Dungeon Defenders on Steam"
[5]: https://coffeestain.com/game/sanctum-2/?utm_source=chatgpt.com "Sanctum 2"
[6]: https://store.steampowered.com/app/701160/Kingdom_Two_Crowns/?utm_source=chatgpt.com "Kingdom Two Crowns on Steam"
[7]: https://www.tribesofmidgard.com/?utm_source=chatgpt.com "Tribes of Midgard: Home"
[8]: https://www.riftbreaker.com/?utm_source=chatgpt.com "The Riftbreaker - Enlist for planetary assignment now!"
[9]: https://store.steampowered.com/app/408410/XMorph_Defense/?utm_source=chatgpt.com "Save 80% on X-Morph: Defense on Steam"
[10]: https://store.steampowered.com/app/310510/Deathtrap/?utm_source=chatgpt.com "Deathtrap on Steam"
[11]: https://www.doublefine.com/games/iron-brigade?utm_source=chatgpt.com "Iron Brigade"
[12]: https://store.steampowered.com/app/334210/Fortified/?utm_source=chatgpt.com "Fortified on Steam"
[13]: https://store.steampowered.com/app/1446160/Toy_Soldiers_HD/?utm_source=chatgpt.com "Toy Soldiers: HD"
[14]: https://store.steampowered.com/app/227220/SangFroid__Tales_of_Werewolves/?utm_source=chatgpt.com "Sang-Froid - Tales of Werewolves"
[15]: https://store.steampowered.com/app/644930/They_Are_Billions/?utm_source=chatgpt.com "They Are Billions on Steam"
[16]: https://www.ageofdarkness.com/?utm_source=chatgpt.com "Age of Darkness: Final Stand | Video Game"
[17]: https://play.google.com/store/apps/details/Mindustry?hl=en_SG&id=io.anuke.mindustry&utm_source=chatgpt.com "Mindustry – Apps on Google Play"
[18]: https://store.steampowered.com/app/2289750/Super_Fantasy_Kingdom/?utm_source=chatgpt.com "Super Fantasy Kingdom on Steam"
[19]: https://store.steampowered.com/app/3028310/Nordhold/?utm_source=chatgpt.com "Nordhold on Steam"
[20]: https://steamcommunity.com/app/1422440/allnews/?utm_source=chatgpt.com "Cataclismo"
[21]: https://eu.shop.battle.net/en-us/product/warcraft-3-reforged?utm_source=chatgpt.com "Warcraft® III: Reforged"
[22]: https://maps.w3reforged.com/maps/categories/tower-defense-td?utm_source=chatgpt.com "Tower Defense (TD) category map list | Warcraft 3"
[23]: https://dota2.fandom.com/wiki/Lane_Creeps?utm_source=chatgpt.com "Lane Creeps - Dota 2 Wiki"
