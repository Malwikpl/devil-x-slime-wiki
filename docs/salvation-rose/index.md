# Salvation Rose

A Sacred Gear of our own, added in **0.2.107**: the mod's first gear that isn't from the story. A gold ring with a pink gem sits on your main
hand's finger, and the gem is your soul's light. When you shoot, a bow of rose wood and light grows out of it. It is a Tensura **Unique
Skill** (`dxdtensura:salvation_rose`) with no summoned state: the bow shows while you draw and fades a little after your last shot.

Its Balance Breaker is [Cycle of Salvation](#cycle-of-salvation), a winged goddess form. A gem that goes dark can also choose the other
way, [the witch](#the-witch).

## Getting it

- **Only the reincarnation roll**, at the same odds as the other gears, and only for a
  [human](../getting-started/first-gear.md#only-in-humans).
- Learning it costs 30,000 magicules. Any number of players can hold it.
- **One Sacred Gear per player.** A holder reborn as another race in Tensura's race menu loses it: "The ring slips from your finger, and
  its pink light goes out."
- No dragon lives in it, and it isn't a Longinus. It goes with the [Holy Factor](../durandal/index.md#the-holy-factor).
- [Rias](../races/rias.md) offers a holder of worth up to 3 her **Bishop**.

## Modes

| # | Mode | Opens at | Price | Gem | Cooldown where it opens / mastered |
|---|---|---|---|---|---|
| 0 | **Rose Arrow** | the start | 0.5% at a full draw | −1 from half a draw | none |
| 1 | **Arrow Rain** | 40% mastery | 10% | −8 | 30 s / 15 s |
| 2 | **Purify** | 70% mastery | 8% | −6 | 30 s / 15 s |
| 3 | **Wish Arrow** | full mastery | 30% | −25 | 120 s |
| 4 | **Cycle of Salvation** | once awakened | the Scale Mails' upkeep | | the Scale Mails' |
| 5 | **Witch** | once awakened, while the gem is dark | | | 15 minutes of silence |

Prices are a share of your max magicules. The mode key and the [mode wheel](../getting-started/mode-wheel.md) skip what isn't open yet,
and each new power is announced once as it opens.

## Rose Arrow

Hold the key to draw and let go to shoot. A press let go at once does nothing and costs nothing. While you draw you slow to a walk and
can't swing, use items or open things.

- **A full draw** (a second) shoots an arrow that splits 6 blocks out into **3 arrows**, 4 from 50% mastery and **5** mastered. They seek
  enemies up to **48 blocks ahead** along your aim, hostile mobs first, each its own where it can.
- **A shorter draw** shoots one arrow that hits weaker and curves toward the enemy nearest your crosshair.
- Each arrow also bursts on what stands within 2 blocks of its hit, for half.
- Your pets and allies are never aimed at, and arrows pass through them. An arrow stops at the first wall and breaks nothing.
- Short of magicules, a full draw shoots a weaker single arrow with what's left. With none, the draw doesn't start.

**The poses.** The bow is in your off hand and the ring's hand draws the string to your cheek, side-on, with real bent elbows. The hand
flicks back past your ear on the release, Arrow Rain is aimed high and swept, and the Wish Arrow is a wide stance, a long draw and a heavy
recoil. In first person the bow comes to the middle and kicks on a release. The client setting `bentArms` plays the same poses with
straight arms, if another mod's player model clashes with bending.

## Arrow Rain

From **40% mastery**. Look at the ground up to 48 blocks away and press: a pink sigil opens over the spot, and after a second the circle
under it is struck **8 times over 4 s** by falling arrows. Your pets in it are untouched and no block is hurt. Looking at empty sky does
nothing and costs nothing ("No ground for the rain.").

## Purify

From **70% mastery**. A ring of light runs out **8 blocks** round you. It clears poison, curses and fire from you and your allies (a Scale
Mail's marker, a Divide's weakness and Tensura's incurable curses stay), and it strikes the lost souls it reaches. It costs the same with
nothing around. Another holder it reaches gets some light back.

## Wish Arrow

At **full mastery**. Hold the key for **3 s** and let go: a great arrow flies along a **96-block line**, through walls and breaking
nothing, and every enemy within 2 blocks of the line takes **200**, once. Let go early and nothing is shot or paid.

## The gem's light

The gem holds your light, **0 to 100**, and starts full. The panel by your hotbar shows it.

| Dims it | Brightens it |
|---|---|
| Each power (see the [modes](#modes)) | Killing a hostile mob: +2 |
| A single hit of a quarter of your max health or more: −5 | Killing a lost soul: +4 |
| An ally's death within 32 blocks, your pets too: −15 | Helping kill a boss, or saving a Stray Devil: +15 |
| | Quiet time: +1 every 30 s, up to 50 |
| | A night's sleep: back to 100 |

- A kill by your pet counts as yours. Animals, Tensura's Training Dummy and armour stands give nothing.
- **Under 50 the gear hits weaker**, down to half near dark. "Your gem is clouding." shows when it crosses 50, and "Your gem is almost
  dark." at 20.
- **At 0 the gem goes dark**: for **60 s** every press is refused, and kills or sleep change nothing. Then "A faint light returns to your
  gem." and it comes back at 20. Going dark drops a draw and stops a rain.
- From 70% mastery the moment it would go dark is also [the contract](#the-contract).

## Lost souls

**Stray Devils, the undead and Tensura's daemons** are lost souls: every hit of the gear on one is **half again as strong**.

A [Stray Devil](../world/stray-devils.md) your hit would kill isn't killed: it stops, fades away over a second and a half, saved, and drops
its loot. You get +15 light and "You gave it an ending.", a hunt for it from Rias counts as done, and nothing can hurt it while it fades.

## The small white creature

A small white creature with red eyes sits beside you at the gem's turning points (the first time it clouds, nears dark and goes dark, the
first Stray you save, full mastery) and has a word for you. Only Salvation Rose holders see him, and he can't be touched. He has more to
say once you're near [the contract](#the-contract).

## Cycle of Salvation

The Balance Breaker. A white gown with a galaxy inside its long skirt, big white wings with pink tips, four see-through straps flowing
from two white bows, golden eyes, your gem as a pink drop at the neckline, and a long bow with a rose at its tip, all over your own skin.
Worn armour isn't drawn under it, but it still protects. The client setting `goddessEyes` leaves the golden eyes out, for a skin whose
eyes are painted elsewhere.

### The contract

From **70% mastery**, the moment anything would take your gem to 0, it stops at 1 and the creature appears with an offer: a contract and
one wish. **"Make the contract"** or **"Not yet"**.

- While the offer is open nothing hurts you but `/kill` and the void (on a server only for its first 10 s). In single player the game
  pauses; on a server it closes by itself after 15 s.
- Any close without a choice (the time running out, Esc, logging out, dying, a new dimension) counts as "Not yet": the gem goes dark,
  and he won't ask again for **10 minutes**.
- Creative players, players in a cutscene and players with another offer open are held at 1 instead.

**Making it** awakens the gear for good: your wish in your own voice, then a **48-second cutscene** with its own song, played once, and the
state starts at its climax, free. Its time starts counting only when the cutscene gives you control back. The awakening is kept through
death and relogging, and lost with the gear. `/dxdtensura max` awakens it with no contract.

### Mode 4

Once awakened, **mode 4** starts the form whenever you like: a press counts down (shorter the longer you've worn it, as the Scale Mails'),
a second press cancels, and in the state a press ends it. A dark gem doesn't refuse it. Every later start plays a short cutscene of 3 s.
Sneak skips either cutscene, and the `cutscenes` client setting turns them off.

### The state

- The gem fills to 100 and **nothing dims it**.
- You **fly**, at the white Scale Mail's speed.
- **Every hit of the gear is half again as strong**, 2.5 times on a lost soul.
- A full draw takes **half a second** and always splits into **5**.
- **Arrow Rain** is twice as wide on half the cooldown, and opens a rose of light over the rain.
- **The Wish Arrow** is far bigger, and where it first meets the ground it bursts in a blast **30 blocks across**: the whole hit at its
  middle, half at its edge. The blast is light only and breaks nothing.
- **Its song** plays through the state, on the Jukebox volume slider in place of the game's music (client settings `roseMusic`, and
  `gearSongs` for other players').
- It costs the Scale Mails' upkeep a second, for up to **3 minutes**, with their cooldowns, and running dry exhausts you. In
  [Lore mode](../lore-mode.md) there's no time limit.

The panel names the form from the countdown on and shows the time left.

### Salvation

Once each state, **you and every ally within 24 blocks** (your pets and summons, players on your team) who takes a killing blow is caught
instead by a pair of wings of light, which close round them and break into falling feathers. They're left at **20% health**, purified:
"A gentle light caught you." Never from `/kill` or the void, and never where Tensura's Instant Regeneration would stop the death anyway.

## The witch

Hope isn't the only choice. Once Cycle of Salvation is awakened, **mode 5, Witch**, shows on the mode key and the wheel. It works only
while your gem rests dark, the 60 s after it goes out: then the choice is **mode 4 for hope, or mode 5 for despair**. The first time your
gem goes dark after the awakening, the creature tells you what a dark gem becomes.

Mode 5 is refused while the gem still holds light, while the gear is silent, in Cycle of Salvation, in a cutscene and with the contract's
offer open.

### The form

It lasts **2 minutes 10 seconds**: 40 s in your control, then a minute and a half of rage.

- You're **healed to full** and fly on black wings, in the goddess form turned black and blood red.
- Around you stands **the witch**, about **14 blocks tall**: a bell of black legs to the ground and a starved figure on it with a spiked
  crown and long bony arms. She follows you, walking or flying, staying on the ground under you. **Everyone sees her.**
- In the form every mode is one of her moves, with her own names and icons on the key and the wheel. Any cooldowns you came in with are
  cleared.

| # | Her move | What it does | Cooldown |
|---|---|---|---|
| 0 | **Her legs** | Her legs come down like spears on the enemies ahead along your aim, up to 32 blocks out, one leg each and the spare legs on the first, for 24 each | 1 s |
| 1 | **Her pull** (hold) | Black strands drag every enemy within 16 blocks toward you and drain 6 a second from each; you heal half of it. Bosses are pulled slower | none |
| 2 | **Rain of Legs** | For 3 s her legs rain over a circle 8 blocks round where you aim, half of them seeking the enemies in it, 18 each | 8 s |
| 3 | **Her Embrace** | Her arms sweep down round in front of you: everything within 14 blocks in front takes 48 and is flung away | 10 s |
| 4 | **Mire of Despair** | A black pool 9 blocks round where you aim, for 8 s: what's in it is slowed, weakened and drained 6 a second | 20 s |

She starts with **3 legs** and grows one every **6 seconds**, 13 by the end.

### Her rage

5 s before it, the creature warns you and the panel flashes. For the last **1:30 she rages**: no key ends her, and a leg comes down every
half second on **everything near in turn, your pets, villagers and allies too**. Other players only where you could hurt them anyway (PvP
and teams). Every 8 s she also rains, embraces or spreads her mire on her own at whatever is nearest.

She ends when her time runs out, at a press of mode 5 while you're still in control, or if you die, log out or change dimension.

### The price

- **The whole gear is silent for 15 minutes.** Every mode is refused, mode 4 too, the gem stays dark and cracked, and the panel counts the
  silence down. Then the light comes back at 20. Death doesn't end the silence, and its clock runs while you're away.
- **Weakness II and Slowness II** for a minute.
- No life price.

### Her cutscene, songs and sky

- The first time you unleash her she has her own cutscene, about 50 s; every later time a short one of 3 s. Her time counts from its
  end. Sneak skips either.
- **Her songs**: one while she's in your control, another the moment she rages. Both follow the `roseMusic` and `gearSongs` client
  settings.
- **Her sky**: within about 50 blocks of her the sky turns to blood dusk, a red vortex turns overhead (faster while she rages), the fog
  closes in and ash falls. Everyone near sees it. The client setting `witchSky` turns it off.

### In Lore mode

Her legs strike 5 times as hard and reach twice as far, the pull reaches 48 blocks and drains three times as hard, and her raging strikes
come twice as often.

## Mastery

A point for an arrow that hits (once every 4 s at most), 3 for an Arrow Rain that struck, 3 for a Purify that worked and 2 for a Stray
Devil saved, out of 1,000. Tensura's Training Dummy and armour stands earn nothing.
`/tensura edit ability mastery @s dxdtensura:salvation_rose <amount>` sets it: 400 for Arrow Rain, 700 for Purify and the contract, `max`
for everything.

## Commands and settings

- `/dxdtensura max` masters the gear, fills the gem and awakens Cycle of Salvation.
- `/dxdtensura rose light <0-100> [players]` (operators) sets the gem as a real change would: 0 at 70% mastery or more brings the offer.
- `/dxdtensura cutscene play cycle_of_salvation full|short` and `/dxdtensura cutscene play witch full|short` replay the cutscenes with
  nothing gained or lost.
- Every number is in [`[salvation_rose]`](../reference/configuration.md#salvation_rose), and the client settings are under
  [Client settings](../reference/configuration.md#client-settings).
