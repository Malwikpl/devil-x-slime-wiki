# The Castle Town of Gremory

The Gremory family's town stands in Tensura's **Hell**, added in **0.2.35**: a walled town on its own base of rock, with a market, an inn, a
bounty board, people in its streets and a castle with Rias's parents on their thrones, under a purple sky and a great artificial moon. There's one
per world.

<div class="grid" markdown>

<figure markdown="span">
  ![The town from above](../assets/images/town-from-above.jpg){ loading=lazy }
  <figcaption>The town from above, in Hell's sand.</figcaption>
</figure>

<figure markdown="span">
  ![The south gate under the moon](../assets/images/town-gate.jpg){ loading=lazy }
  <figcaption>The south gate, the way in on foot.</figcaption>
</figure>

</div>

## Finding it

It's about a thousand blocks from the middle of Hell. Tensura's **Hell Gates** keep your X and Z, so any gate will do, and a map tells you
where to walk.

**Getting a map:**

- **Ask Rias.** Her talk screen has **The way to the Underworld**. She gives anyone a map once an in-game day, servant or not.
- **A wandering trader** sometimes offers one for 12 emeralds.
- **The Curio Seller** in the town's market sells them for 3 silver, to pass on to a friend.

**Using it:** it's a map of Hell with a red X, and its tooltip gives the coordinates. Hold it in either hand in Hell, and the action bar says
how far and which way, once a second: "Castle Town: 2,340 blocks north-east".

**The sky** tells you you're close: it starts to turn purple about 450 blocks out, and it's fully purple at 150.

<figure markdown="span">
  ![The town under a purple sky, from far off](../assets/images/town-sky.jpg){ loading=lazy }
  <figcaption>About 300 blocks out, with the sky already turning.</figcaption>
</figure>

Operators can find it with these:

```
/locate structure dxdtensura:castle_town
/dxdtensura town where
```

!!! note "A world that already explored Hell"
    If Hell's land is already generated where the town would stand, it picks unexplored land further along and comes up as you get close, chunk
    by chunk. `/locate` can't find a town that moved, but the map and `/dxdtensura town where` can.

## Coming and going

**On foot.** The town stands level on its own base, over the pits if it has to, with a paved terrace all the way round. Walk round to the **south
gate**. Flyers can land anywhere.

**By ticket.** A **Ticket to the Castle Town** costs 5 silver at the Curio Seller. Use it and stand still for 5 seconds: a circle opens under you and
you arrive on the Town Circle, from any dimension. A step or a hit breaks the circle and you keep the ticket. It doesn't work inside the town, in a
boss area or in the Labyrinth.

**By Devil's circle.** A [Devil](../races/devil.md#the-magic-circle) from Middle-class who has been inside the walls once gets a new Demonic Power mode,
**Circle to the Castle Town**. It costs and cools down as the circle home does, and arrives on the Town Circle.

**The way out: the Town Circle.** It's in the plaza inside the south gate. Right-click it, and 3 seconds later you're back where you last left the
overworld, for free, whoever you are. A step or a hit breaks it. With no spot saved, you land at the world spawn.

<figure markdown="span">
  ![The Town Circle in the plaza](../assets/images/town-circle.jpg){ loading=lazy }
  <figcaption>The Town Circle, in the plaza inside the south gate.</figcaption>
</figure>

**The first time** you step inside the walls, a title reads "Castle Town of Gremory" and a bell rings. If you serve Rias, she has a word for you too.

## The town

- **The Avenue** runs north from the south gate, through the square, to the castle steps.
- **Fountain Square** has its fountain and two marble statues facing each other across it: the Scale Mail and Rias.
- **Market Row** has the [five stalls](#the-market). The [inn](#the-inn) and the **Hunters' Office** are nearby.
- **About 60 houses,** noble gardens and lanes fill the rest, inside the town wall.
- **The stadium** is closed for now.
- **[The castle](#the-castle)** has the rooms the story names: the great hall with its thrones, a theatre, a dining room, a library, Rias's room, and a
  treasury under the hall.

<div class="grid" markdown>

<figure markdown="span">
  ![Fountain Square](../assets/images/town-square.jpg){ loading=lazy }
  <figcaption>Fountain Square.</figcaption>
</figure>

<figure markdown="span">
  ![The two marble statues](../assets/images/town-statues.jpg){ loading=lazy }
  <figcaption>The Scale Mail and Rias, in marble.</figcaption>
</figure>

<figure markdown="span">
  ![The Avenue](../assets/images/town-avenue.jpg){ loading=lazy }
  <figcaption>The Avenue, with the castle at its end.</figcaption>
</figure>

<figure markdown="span">
  ![The castle's gate and wall](../assets/images/town-castle.jpg){ loading=lazy }
  <figcaption>The castle.</figcaption>
</figure>

</div>

The purple sky and the moon are a client setting. Turn `townSky` off and Hell keeps its own sky there.

## The rules

In survival, inside the town's square and on its terrace:

- **No breaking or building.** Blocks don't break or place, buckets and flint do nothing, axes don't strip, and explosions and skills leave the town
  whole. Juggernaut Drive's dragon can't break it either. Creative players and operators can.
- **What you can click:** doors, gates and bells work. Chests and barrels stay shut. A bed says "Talk to the innkeeper".
- **No monsters.** Nothing spawns in the square. Outside, Hell is as it always is.
- **No poison inside the walls.** Hell's Magicule Poison stops at them, and starts again on the terrace.

## The people

While a player is near, the town has **24 citizens** and **10 guards**. They arrive before you're inside, and leave when you've gone.

- **Citizens** walk the streets, stop in pairs to talk, sit on the square's benches and run from danger.
- **Guards** carry swords. They stand at the gates, walk the south wall and patrol the Avenue.
- **The Hunters' Clerk** stands behind the counter of the Hunters' Office. Nobody can hurt the Clerk, the stallkeepers, the innkeeper or the lords in the castle,
  and trying makes you Wanted.
- **Right-click** a citizen or a guard for a line. It depends on who you are: a Devil, an Angel, a Fallen Angel, a stranger, Rias's servant, or Wanted.
- **The dead stay dead for a day.** Each citizen or guard killed leaves one fewer until the next in-game day.
- They can't take an Evil Piece, a Brave Saint card or a name. [Forbidden Balor View](../balor-view/index.md) stops a citizen, but not the Clerk.

<div class="grid" markdown>

<figure markdown="span">
  ![Citizens talking in the street](../assets/images/town-people.jpg){ loading=lazy }
  <figcaption>Citizens in the street.</figcaption>
</figure>

<figure markdown="span">
  ![Guards at the gate](../assets/images/town-guards.jpg){ loading=lazy }
  <figcaption>Guards at the gate.</figcaption>
</figure>

</div>

### Wanted

Hurt anyone inside the square, or send a pet or an arrow to do it, and "The town has marked you Wanted. Its guards will attack on sight." Creative players
are let off.

- **Guards** open their wings and fly at you, hit you close up and throw Demonic Power orbs from further off. They give up about 30 blocks past the walls.
- **The alarm.** While a guard can see you, 2 more come through a circle about every 20 seconds, up to 12 in a day. It stops after you've been out of
  sight for 30 seconds.
- **Citizens** run with a cry.
- **Stalls, the inn and the bounty board** refuse you, and Zeoticus has nothing for you.

**It ends** either way:

- after a **full in-game day outside the square**, and coming back early starts the count again;
- for **1 gold coin** paid to the Clerk.

**A [Stray Devil mark](stray-devils.md#the-stray-devil-mark)** makes you Wanted whenever you're in the square, and there's no fine to pay for it. Outside the
square, [hunters](#hunters-and-the-mark) may come for you.

<div class="grid" markdown>

<figure markdown="span">
  ![Winged guards over the square](../assets/images/town-guards-wings.jpg){ loading=lazy }
  <figcaption>Guards with their wings open, in a chase.</figcaption>
</figure>

<figure markdown="span">
  ![The Clerk asking for the fine](../assets/images/town-clerk.jpg){ loading=lazy }
  <figcaption>The Clerk takes the fine.</figcaption>
</figure>

</div>

## The market

Five stalls on Market Row, each with a keeper. Right-click a keeper, then **Trade** for the normal trade screen, paid in Tensura's coins.

| Stall | Sells from Tensura's lists for |
|---|---|
| **Apothecary** | Clerics |
| **Smith** | Weaponsmiths, armourers and toolsmiths |
| **Tome Seller** | Magic trainers and librarians |
| **Grocer** | Butchers and farmers |
| **Curio Seller** | Merchants, and the coin exchange, always, both ways |

- **The stock changes every in-game day,** and it's the same for everyone.
- **Use limits are per player,** and come back the next day.
- **A Devil pays 10% less,** and so does a [Valkyrie](../races/valkyrie.md#in-the-world), pure or hybrid; the cuts add up, to 25% at most. What a stall pays you and the
  coin exchange never change.
- **No stall buys what a stall sells,** so there's no money from nothing.
- The screen closes by itself if you walk more than 8 blocks away or become Wanted, and any coins in its slots come back to you.

<div class="grid" markdown>

<figure markdown="span">
  ![The stalls on Market Row](../assets/images/town-market.jpg){ loading=lazy }
  <figcaption>Market Row.</figcaption>
</figure>

<figure markdown="span">
  ![Talking to the Curio Seller](../assets/images/town-stall.jpg){ loading=lazy }
  <figcaption>A keeper's panel.</figcaption>
</figure>

<figure markdown="span">
  ![The Curio Seller's trades](../assets/images/town-trade.jpg){ loading=lazy }
  <figcaption>The Curio Seller's trades.</figcaption>
</figure>

</div>

### The town's own goods

These are always on the stall, on top of the day's stock.

| Goods | Stall | Price | A day |
|---|---|---|---|
| **Bael Apple** | Grocer | 3 silver | 8 |
| **Dragon Apple** | Grocer | 8 silver | 8 |
| **Map to the Castle Town** | Curio Seller | 3 silver | 2 |
| **Ticket to the Castle Town** | Curio Seller | 5 silver | 4 |
| **Gremory Banner**, a crimson banner with the crest | Curio Seller | 2 silver | 4 |
| **[Phoenix Tear](../races/houses.md#house-phenex)**, for a Friend of House Gremory and up | Apothecary | 16 gold | 1 |

### The apples

- **Bael Apple:** eaten fast, always edible. Food 4, 4 health and **5% of your max magicules** back.
- **Dragon Apple:** for a dragon, meaning a dragon race or a Boosted Gear or Divine Dividing holder, it's food 8 and **a quarter of your max magicules and
  aura** back. For anyone else, it's food 4 and 30 seconds of Fire Resistance.

## The inn

The innkeeper stands behind the inn's counter.

- **Rent a room** once, for 1 gold. It's free for a Devil, and it's yours for good.
- **Set your respawn here** and you wake at the inn when you die. **Give up your room** puts your respawn back. Setting it again costs nothing.
- **Wanted,** the inn won't have you: you wake at the world spawn instead, and the room is still yours afterwards.
- **Buy Sake,** a bottle for 1 gold. A genius [Valkyrie](../races/valkyrie.md#sake) should go easy on it.

<figure markdown="span">
  ![The innkeeper](../assets/images/town-inn.jpg){ loading=lazy }
  <figcaption>The innkeeper.</figcaption>
</figure>

## Bounties

The **bounty board** stands on the wall of the Hunters' Office. Right-click it for three posters a day of your own, and take one.

| Poster | Target |
|---|---|
| 1 | A Stray of your class |
| 2 | A Stray one class up |
| 3 | A lair boss, if one is in range of where you last stood above, or else another Stray |

- **It runs like [Rias's jobs](stray-devils.md#riass-hunts).** A marker points the way, the target comes up when you get within 64 blocks, and you have two in-game days. Anything above your EP is
  stamped.
- **One hunt at a time,** shared with Rias's jobs. If you serve her, her call waits.
- **Anyone can hunt,** though not while Wanted or with the Stray Devil mark. On Peaceful, the board says the land is quiet.
- **It pays where you make the kill:** coins through a small circle at your feet, a little EP, and renown. Rias doesn't come. If someone else kills it, or it's killed with you more than 64 blocks
  away, there's no pay.

| Target | Coins | EP | Renown |
|---|---|---|---|
| Low-class Stray | 8 to 12 silver | 5% of the target's | 10 |
| Middle-class Stray | 24 to 36 silver | 5% | 20 |
| High-class Stray | 2 to 3 gold | 5% | 40 |
| Lair boss | 5 to 8 gold | 5% | 100 |

The posters change every in-game day.

<div class="grid" markdown>

<figure markdown="span">
  ![The bounty board on the Hunters' Office wall](../assets/images/town-board-wall.jpg){ loading=lazy }
  <figcaption>The board, on the Hunters' Office.</figcaption>
</figure>

<figure markdown="span">
  ![The bounty board's three posters](../assets/images/town-board.jpg){ loading=lazy }
  <figcaption>Three posters a day.</figcaption>
</figure>

</div>

### Hunters and the mark

Carry the [Stray Devil mark](stray-devils.md#the-stray-devil-mark) and the Hunters' Office comes for you too.

- **Hunter parties** come every 3 to 5 in-game days, in the overworld at night or in Hell at any time, never inside the town. Their line comes first, and 3 seconds later they arrive through small dark
  circles 24 to 32 blocks away, flying at you, and only you.
- **Two come at first,** and one more for each party you beat, up to five. Each has half your EP, from 20,000 to 400,000, and drops 2 to 5 silver.
- **They leave** after 5 minutes, when you die or when you leave the dimension.

**With PvP on,** the player marked longest also has a poster on everyone else's board, in darker paper. It's a hunt of its own, for two days, alongside a Stray job. A kill by your own hand pays **5 gold
and 50 renown**, and the poster stays off your board for 3 days.

<figure markdown="span">
  ![A hunter party flying in](../assets/images/town-hunters.jpg){ loading=lazy }
  <figcaption>A hunter party.</figcaption>
</figure>

## The castle

At the north end of the Avenue, and anyone may walk in. **Zeoticus and Venelana Gremory**, Rias's parents, sit on their thrones in the great hall. Nobody can hurt them, and trying makes you Wanted.

- **Zeoticus** is who you take your renown to. **My renown** gives the number, and how far the next title is.
- **Venelana** has something stern to say, and nothing to give.
- **As Rias's servant,** each has a line of their own for you.

<div class="grid" markdown>

<figure markdown="span">
  ![The great hall](../assets/images/town-hall.jpg){ loading=lazy }
  <figcaption>The great hall.</figcaption>
</figure>

<figure markdown="span">
  ![Zeoticus and Venelana on their thrones](../assets/images/town-thrones.jpg){ loading=lazy }
  <figcaption>Zeoticus and Venelana on their thrones.</figcaption>
</figure>

<figure markdown="span">
  ![The theatre](../assets/images/town-theatre.jpg){ loading=lazy }
  <figcaption>The theatre.</figcaption>
</figure>

<figure markdown="span">
  ![The library](../assets/images/town-library.jpg){ loading=lazy }
  <figcaption>The library.</figcaption>
</figure>

</div>

### Titles and renown

**Renown** counts what the town thinks of you, and `/dxdtensura town renown` shows yours. [Bounties](#bounties) and Rias's jobs raise it. It falls by 10 when you become Wanted and by 50 when you kill.

**Titles.** When your renown is high enough, Zeoticus offers you the next title, and you accept it on his panel. Each brings a gift, opens more of each stall's lists and takes a cut off prices. The cut adds
to a Devil's 10%, and never comes to more than 25%.

| Title | Renown | Stall lists it opens | Cut | His gift |
|---|---|---|---|---|
| Visitor | 0 | Levels 1 and 2 | none | |
| Guest of House Gremory | 100 | Up to level 3 | none | 5 gold, 2 Gremory Banners |
| Friend of House Gremory | 300 | Up to level 4, and the Phoenix Tear | 5% | 10 gold |
| Honoured by House Gremory | 700 | All 5 | 10% | A Stellar Gold Coin |
| Champion of House Gremory | 1,500 | All 5 | 15% | 3 Treasury Keys |

- **One at a time,** each with its own Accept.
- **A title is never taken back.** Renown can fall, and the next title waits until it's back.
- **Wanted or with the mark,** Zeoticus won't deal with you.
- With a full inventory, the gift drops at your feet.

<figure markdown="span">
  ![Zeoticus on his throne, with his panel open](../assets/images/town-zeoticus.jpg){ loading=lazy }
  <figcaption>Zeoticus Gremory.</figcaption>
</figure>

### The treasury

A Champion's three **Treasury Keys** open the vaults under the hall, down the long stair behind the thrones. Hold a key near a vault and it lights up. Right-click, and it takes the key and gives you a
reward: **one reward from each vault, ever**. In survival, nothing else in the room works.

| Vault | What it may give |
|---|---|
| Coins | 8 to 16 gold, or 1 or 2 Stellar Gold Coins |
| Arms | A Hihiirokane or Adamantite weapon or chestplate, or ingots |
| Tomes | A magic tome or a battlewill manual |

<figure markdown="span">
  ![The treasury, with three vaults at its far end](../assets/images/town-treasury.jpg){ loading=lazy }
  <figcaption>The treasury, with its three vaults at the far end.</figcaption>
</figure>

## For server owners

- The numbers are in the [`[town]`](../reference/configuration.md#town) config section. `enabled = false` takes away the town's rules, people, circle, tickets and
  Rias's map, and no new town generates. `protect = false` lets anyone break blocks. `phoenixTearsInMarket = false` leaves Phoenix Tears to Phenex players.
- Operators have the [`/dxdtensura town`](../reference/commands.md#the-castle-town) commands.
- **People, stalls, the board and the lords need no new world:** a town already generated gets them. The buildings themselves don't change once generated.
