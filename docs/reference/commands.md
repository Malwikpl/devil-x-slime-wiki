# Commands

## Devil x Slime's commands

All of them need operator permission (level 2), except `/dxdtensura incantation` for yourself.

| Command | What it does |
|---|---|
| `/dxdtensura lifespan clear [players]` | Wipes the life debt from [Juggernaut Drive](../boosted-gear/juggernaut-drive.md#the-price) and [Divide](../boosted-gear/divide.md#the-price): the Shortened Lifespan effect and the lowered max health, at once |
| `/dxdtensura albion give [players]` | Gives a Boosted Gear holder [Albion's power](../boosted-gear/divide.md), as the White Dragon Emperor's jewel does |
| `/dxdtensura albion take [players]` | Takes it away again |
| `/dxdtensura divinedividing holder` | Names the players who hold Divine Dividing in this world |
| `/dxdtensura divinedividing release <player>` | **Takes Divine Dividing from that player** (at once if they're online, otherwise at their next login) and frees it, so the reincarnation roll and the jewel can give it again |
| `/dxdtensura max [players]` | Puts every gear they hold at its top, for testing. Boosted Gear: the Gift, Balance Breaker awakened and trained, Juggernaut Drive's words learned. Divine Dividing: mastered, with Reduce and Compression Divider, the white Scale Mail awakened and trained, and the [white dragon's](../divine-dividing/juggernaut-drive.md) words learned. Twilight Healing: mastered, Healing Arrows and the Field open. Sword Birth: mastered, with every relic known, both blade moves and the elements open |
| `/dxdtensura sin <player>` | Shows an [Angel](../races/angels.md#sin-and-the-fall)'s hidden sin, 0 to 100 |
| `/dxdtensura sin <player> set <0-100>` | Sets it, with what that level brings: the warning and the flicker from 50, the fall at 100 |
| `/dxdtensura eastereggs` | Says which of the hidden easter eggs are still waiting in this world |
| `/dxdtensura eastereggs reset` | Makes both easter eggs happen again |
| `/dxdtensura incantation [players]` | Gives a fresh copy of Ddraig's [incantation](../boosted-gear/juggernaut-drive.md#the-incantation) book, or Albion's [words of the white dragon](../divine-dividing/juggernaut-drive.md#learning-the-words), for a lost one. Only works once the words are learned. **Anyone can use it for themselves**; giving it to other players needs operator permission |

`[players]` is optional; without it, the command applies to you.

### Rias Gremory

For [Rias Gremory](../races/rias.md). All need operator permission.

| Command | What it does |
|---|---|
| `/dxdtensura rias where` | Where her home is, and the old school building's state: not placed yet, standing, or waiting further out for its land to be explored |
| `/dxdtensura rias home` | Brings her back to her desk |
| `/dxdtensura rias flyer <player>` | Gives that player one of her flyers (at their feet if their inventory is full) |
| `/dxdtensura rias release <player>` | Releases that player from her peerage (she never does it herself) |
| `/dxdtensura rias rejoin <player>` | Ends that player's wait to rejoin her after leaving |

### Stray Devils

For [Stray Devils](../world/stray-devils.md). All need operator permission.

| Command | What it does |
|---|---|
| `/dxdtensura stray spawn <class> <piece> [mutations]` | A Stray 3 blocks in front of you. The class is `low`, `middle` or `high`, the piece `pawn`, `knight`, `bishop` or `rook`, and the mutations a number from 0 to 255 |
| `/dxdtensura stray boss` | A lair boss 4 blocks in front of you, with the world's next name (Viser first) |
| `/dxdtensura stray lair` | The nearest Stray mansion and its lair's state |
| `/dxdtensura stray job <player> start` | Sends one of Rias's servants after a Stray now |
| `/dxdtensura stray job <player> end` | Ends their job, as if the Stray got away |
| `/dxdtensura stray job <player> reset` | Clears their wait for the next job |

### Brave Saints

For the [Brave Saints](../races/brave-saints.md). All need operator permission.

| Command | What it does |
|---|---|
| `/dxdtensura bravesaints info <player>` | A Seraph's deck, or a holder's card |
| `/dxdtensura bravesaints suit <player> <suit>` | Sets a Seraph's suit (`spades`, `hearts`, `diamonds` or `clubs`), which only an operator can change |
| `/dxdtensura bravesaints release <player>` | Releases a holder from their Seraph's deck; the card goes back |

### Durandal and the Holy Factor

For [Durandal and the Holy Factor](../durandal/index.md). All need operator permission.

| Command | What it does |
|---|---|
| `/dxdtensura holyfactor give <targets> born` | Gives them the Holy Factor |
| `/dxdtensura holyfactor give <targets> artificial` | Gives them the Artificial Holy Factor |
| `/dxdtensura holyfactor take <targets>` | Takes either factor away |
| `/dxdtensura holyfactor reroll <targets>` | One more birth roll; a Human or Enlightened Human rolls now |
| `/dxdtensura holyfactor durandal reset` | The true Durandal can be found again in this world |

### Nekomata and Nekoshou

For the [Nekomata and Nekoshou](../races/nekomata.md). All need operator permission.

| Command | What it does |
|---|---|
| `/dxdtensura nekoshou give <targets>` | Makes them a Nekoshou |
| `/dxdtensura nekoshou take <targets>` | Makes them a plain Nekomata, with the roll spent |
| `/dxdtensura nekoshou reroll <targets>` | Rolls again |
| `/dxdtensura coat <player> <coat>` | Sets their coat: `ginger`, `grey`, `brown_tabby`, `calico`, `tuxedo`, `cream`, or a Nekoshou's `white` or `black` |
| `/dxdtensura malice <player>` | Shows their [Malice](../races/nekomata.md#malice), 0 to 100 |
| `/dxdtensura malice <player> set <0-100>` | Sets it |

### Lore mode

[Lore mode](../lore-mode.md) is a game rule, so it's vanilla's command, with operator permission:

```
/gamerule dxdLoreMode true
```

## Useful Tensura commands

Tensura's own commands work on Devil x Slime's skills too.

| Command | What it does |
|---|---|
| `/tensura edit ability grant @s dxdtensura:boosted_gear` | Gives you the Boosted Gear |
| `/tensura edit ability grant @s dxdtensura:divine_dividing` | Gives you Divine Dividing |
| `/tensura edit ability grant @s dxdtensura:twilight_healing` | Gives you Twilight Healing |
| `/tensura edit ability grant @s dxdtensura:sword_birth` | Gives you Sword Birth |
| `/tensura edit race set @s dxdtensura:seraph` | Makes you a Seraph, to try the [Brave Saints](../races/brave-saints.md) |
| `/tensura edit ability mastery @s dxdtensura:boosted_gear 400` | Sets the mastery: 400 is the Base form, `max` the Boosted Gear Gift, `0` back to Initial |
| `/ability set dxdtensura:boosted_gear <mode> <slot>` | Puts a mode on an ability slot (1 to 3). See the mode numbers on the [Boosted Gear](../boosted-gear/index.md#modes) and [Divine Dividing](../divine-dividing/index.md#modes) pages |

## Finding structures

```
/locate structure dxdtensura:ascalon_church
/locate structure dxdtensura:ascalon_church_crypt
/locate structure dxdtensura:white_dragon_colosseum
/locate structure dxdtensura:old_school_building
/locate structure dxdtensura:stray_mansion
```
