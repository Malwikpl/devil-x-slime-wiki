# Looks, cutscenes and effects

Everything that makes the gears look and sound like the anime, and the client settings that tune it for you. The client
settings live in `config/dxdtensura-client.toml`, or in game under Mods → Devil x Slime → Config.

## Model style

Every remodelled piece comes in two looks:

| `modelStyle` | Look |
|---|---|
| `NEW` (default) | Smooth, outlined models with cel-shaded textures |
| `CLASSIC` | The blocky models from the first versions |

<div class="grid" markdown>

<figure markdown="span">
  ![Smooth look](../assets/images/scale-mail-smooth.jpg){ loading=lazy }
  <figcaption>NEW: smooth</figcaption>
</figure>

<figure markdown="span">
  ![Classic look](../assets/images/scale-mail-classic.jpg){ loading=lazy }
  <figcaption>CLASSIC: blocky</figcaption>
</figure>

</div>

It covers the gauntlet's three forms, the Scale Mail, Juggernaut Drive's dragon, and Ascalon's blade on the gauntlet and
the Scale Mail. The sword itself, its relic and the skull keep their one look. The change applies at once.

The first time you hold the Boosted Gear, a screen asks which look you want (**Smooth** or **Blocky**), with a picture
of each. Any way out of it keeps the current look. To be asked again, set `modelStyleAsked` back to `false`.

Divine Dividing's wings and the white Scale Mail have the new look only.

<figure markdown="span">
  ![The model style screen](../assets/images/model-style-screen.jpg){ loading=lazy }
  <figcaption>The screen that asks the first time.</figcaption>
</figure>

## Cutscenes

**Balance Breaker** and **Juggernaut Drive** play a cutscene as they form.

| Transformation | First time | After that |
|---|---|---|
| Balance Breaker (red Scale Mail) | full, about 7 s | short, 3 s |
| Juggernaut Drive | full, about 7 s | short, 3 s |
| Divine Dividing's Balance Breaker (white Scale Mail) | full | full, every time |
| Divine Dividing's Juggernaut Drive (the white dragon) | full, about 7 s | short, 3 s |
| Taking Albion's power | a short cutscene | |
| [The True Queen](../boosted-gear/promotion-forms.md#the-true-queen) | full, about 6 s | a flash, no cutscene |

- You stand still and **can't be hurt** while it plays, and your head stays level; the mouse can't turn you.
- **Sneak** skips the rest of it. You still transform.
- Players around you see your poses and effects, but keep their own camera.
- `cutscenes = false` turns them off for you: you transform at once.

## Living wings

The race wings aren't stiff. Angels', Fallen Angels', Devils', hybrids', Rias's and House Phenex's wings all move, as the Nekomata's ears
and tails do.

- **On your feet** they sweep back when you run, lag behind your turns, get thrown up when you fall, breathe when you stand still and
  stretch now and then.
- **In flight** the beat follows the flight: full strokes hovering, harder climbing, and a near-still glide flat out, with the wings
  swept back like a falcon's.
- **Every feather** moves on its own, and a bat wing's blades follow a little.
- **[Wings of fire](../races/houses.md#house-phenex)** bend along their length even when you stand still, so they read as flames. With a
  shader pack they stay straight.

**The Scale Mail** is alive too, since 0.2.35. Its wings lag, overshoot and beat heavily, the white leather ripples between rigid red bones, and the tail follows you on the ground and in the
air. The True Queen's wings never flap, and the white Scale Mail's tail moves the same way. See
[The wings and the tail](../boosted-gear/balance-breaker.md#the-wings-and-the-tail).

**Soft lines.** Angels' and Fallen Angels' wings have soft lines, as a plush toy's, in place of the hard outline. Devils' bat wings keep
theirs.

`wingMotion = false` turns the motion off for you, and the wings keep the old slow beat. The Scale Mail's leather lies flat, and its tail keeps a slow sway.

<div class="grid" markdown>

<figure markdown="span">
  ![Feathered wings at rest](../assets/images/wings-rest.jpg){ loading=lazy }
  <figcaption>At rest, with the soft lines.</figcaption>
</figure>

<figure markdown="span">
  ![Feathered wings thrown up in a fall](../assets/images/wings-falling.jpg){ loading=lazy }
  <figcaption>Thrown up in a fall.</figcaption>
</figure>

<figure markdown="span">
  ![Wings of fire with their tongues bent](../assets/images/wings-fire-bent.jpg){ loading=lazy }
  <figcaption>Wings of fire, their tongues bending.</figcaption>
</figure>

</div>

## Callouts

The gear calls out what it does in bold italic letters that float up and fade, coloured from crimson to green:

- **EXPLOSION!**, **RESET** and **DRAGON SHOT!** float beside the gauntlet, on the outside of your arm.
- Each **BOOST!** booms out on its own at a new spot around you (around the crosshair in your own view), a little tilted,
  and fades there. A rage burst's quick boosts pop one after another.
- **TRANSFER!** floats over whoever receives it.
- The big moments appear over your head in larger letters: **WELSH DRAGON BALANCE BREAKER!**, **DRAGON BOOSTER!**,
  **SECOND LIBERATION!**, **JUGGERNAUT DRIVE!**, **LONGINUS SMASHER!** and **PENETRATE!**.
- Divine Dividing's **DIVIDE!** floats beside the target, cut in two through the middle with its halves slightly out of
  line, and **VENT!** beside you. In the white Scale Mail a small
  **DIVIDE!** comes off you when the armour halves a magic hit or a projectile; **COMPRESS!**, **VANISH!**, **REDUCE!**
  and **REFLECT!** mark its other powers, and **OVERLOAD!** a Transfer that floods its strain gauge.
- A Brave Saints hand's name rises over everyone in it ("FLUSH!"), with the cards fanned out in gold.
- The [armour forms](../boosted-gear/promotion-forms.md) call **ARMOR RELEASE!**, **CHANGE STAR SONIC!**, **CHANGE SOLID IMPACT!**, **CHANGE FANG BLAST!** and **CARDINAL CRIMSON
  PROMOTION!**, and their moves **SOLID IMPACT!**, **DRAGON BLASTER!** and **CRIMSON BLASTER!**.

<div class="grid" markdown>

<figure markdown="span">
  ![JUGGERNAUT DRIVE! callout](../assets/images/juggernaut-forms.jpg){ loading=lazy }
  <figcaption>A big moment</figcaption>
</figure>

<figure markdown="span">
  ![TRANSFER! callout](../assets/images/transfer.jpg){ loading=lazy }
  <figcaption>TRANSFER! over the receiver</figcaption>
</figure>

</div>

In first person they show just above your gauntlet, and the big ones over the middle of your view.

## Effects

Every big moment has its own effect, made with Photon and seen by everyone around you:

| Moment | What you see |
|---|---|
| Summon | Red sparks drawn into your raised arm; the gauntlet appears with a green flash from the jewel, a red ring and sparks |
| Dismiss | The gauntlet breaks into crimson motes and a few falling scales as the jewel's light goes out |
| Boost | The gauntlet's gems flare bright, and a green flash and a ring of green sparks burst from the jewel; your arm stays where it is. While you hold stacks a red aura rises off you, stronger at 3 and at 5 stacks |
| Explosion! | A crimson burst with the jewel's green star at its heart, a shockwave along the ground, sparks, and flames around you until it ends. You brace and the camera shakes |
| Reset | The power sinks down your body, a ring closes in at your feet and dark red smoke puffs out |
| Transfer | A green-gold stream from your jewel into the target, which glows green and keeps green motes while the boost lasts |
| Dragon Shot | A crimson flare as you thrust your palm, a glowing orb with a trail, and a flash, shockwave, sparks, fire and smoke where it lands |
| Evolution | A column of red and green light around you that bursts as the new form appears; taller and with gold for the Gift |
| Balance Breaker | A red aura drawn in through the countdown, a ring tightening each second with a heartbeat; the armour forms in a pillar of crimson light, and shatters into crimson shards when it ends |
| Rage burst | A dark red aura pulsing with each quick boost, and the edges of your screen throb red |
| Penetrate | A crimson crack where the hit breaks through |
| Divide | A thin white line across your view through the target, a burst of light and blue-white stars |
| Demonic Power | A dark crimson orb that bursts on what it hits |
| Magic circle | A crimson circle with a sigil opens under you while it hums, in your House's colours if you have one, and you arrive at your respawn point |
| Demonic Blast | A crimson-black orb twice the size that explodes where it hits |
| The white dragon | Wings of starry blue light edged with white blades; the core blazes as the white Longinus Smasher charges, and its jewels and eyes turn violet in the berserk |
| Twilight Healing | Silver rings on both hands; green light from the hands to the one you heal; a bow and arrows of green light; the Healing Field's ring with motes rising inside |
| Stray Devils | A dark circle as they rise or hop away; a crimson Demonic Power orb from a Bishop; a lair's circle in the hall's floor |
| Power of Destruction | Rias's power holds a Stray still in a crimson ring, then erases it |
| Brave Saints | A card sinking into its new holder; gold halos on monster holders; gold circles for calls; light falling for Heaven's Judgement |
| Holy Lightning | Golden-white bolts, thinner or thicker by the mode; the Blast's jagged beam from your hand; bolts falling all around in the storm |
| Durandal | Blue-white sparks off a wild blade; the wave's fan of aura and low rumble, debris and a fading fissure of cracks and blue light; a crescent in the air; a flash for a tamed cut; a pillar of light as the seal breaks |
| Nekomata | Ears and tails that move with you; a ring under an air step; Touki's white aura; a white bolt; wheels of orange, white or black flame rolling along the ground; a dark violet mist; a patch of mud welling up; a Veil's wisps, which only you see; copies stepping out and popping in dark smoke; a dark burst for the berserk |
| Sword Birth | A violet sheen on a copy, breaking into black shards when it fades; huge blades tinted by your element rising through dust, thrown rocks and a violet haze, then crumbling |
| Forbidden Balor View | Two red lights at the holder's eyes; a red clock ring behind the head, or on the ground under an Evil Eye's target; stopped things drained to a cold grey-violet; red screen edges, and grey on a big stop; small dark bats for the Vampire line |
| House Bael and Gremory | A black ball rimmed in red, with small fast bullets; a red shell for the Guard; Extinguished Star's huge sphere and its burst; twelve spheres homing in for Ruin the Extinct |
| House Phenex | Wings of moving flame, bright even at midnight; bolts of flame, a ring of fire and a burning column under smoke; a pillar of flame for a rebirth |
| House Sitri | A hawk, a serpent, lions and a dragon of bright water; a wall of water or ice; a barbed spear of ice and crystals round who it freezes; a wave of frost, great spikes and spires for Celsius Cross Trigger |
| House Leviathan | Dark water with white foam: a pool over a target, waves and a towering flood; the long Sea Dragon and its blue-black breath |
| Light weapons | Weapons of gold or violet light, with a flare as one forms or fades and a burst on a blocked blow; straight bolts from the bow |
| Promotion's armour forms | Plates bursting off the Knight, its green flames and a thin trail at speed; an aura closing in and a ground ring for the Rook, and dust at each step; the Bishop's cannons brightening, then two red beams with rings along them; a flash and a shock ring for Solid Impact |
| The True Queen | Her jewels blazing pink in a crimson column; pink shards in a flash after the first time; pink flames and falling sparkles; wings that open into cannons for the Crimson Blaster's beams |
| The Castle Town | A purple sky with a great moon and thin clouds; crimson circles for the Town Circle and tickets; small circles bringing guards in an alarm |

### LambDynamicLights

With [LambDynamicLights](../getting-started/installation.md#optional) installed, the summoned gauntlet's gems, held
stacks, the Explosion, the Scale Mail, a rage burst and a Dragon Shot in flight light up the blocks around them, and the
big moments flash.

## The settings

| Setting | Default | What it does |
|---|---|---|
| `ddraigLines` | `ALL` | How much of Ddraig and Albion you see: `ALL`, `IMPORTANT` (teaching, warnings and story lines) or `OFF` |
| `screenShake` | `true` | Shake the camera for the Explosion, the Scale Mail forming and a Dragon Shot landing close by |
| `gearEffects` | `ALL` | `ALL`; `MOMENTS` (no lingering auras or motes); or `OFF` (no effects, no light from the gear, no rage tint). Poses and sounds always play |
| `cutscenes` | `true` | The transformation cutscenes. Off, you transform at once |
| `modelStyle` | `NEW` | `NEW` or `CLASSIC` models |
| `modelStyleAsked` | `false` | Whether the model style screen has been answered; set it to `false` to be asked again |
| `flightLean` | `true` | Lean into the flight on the mod's wings or in a Scale Mail; off, you fly upright (and TR: Nightmare's pose can take over) |
| `wingMotion` | `true` | [Living wings](#living-wings): the race wings and the Scale Mails answer your movement; off, they keep the old slow beat |
| `townSky` | `true` | The purple sky and the great moon over the [Castle Town](../world/castle-town.md); off, Hell keeps its own sky there |
| `trueQueenMusic` | `true` | [The True Queen](../boosted-gear/promotion-forms.md#the-true-queen)'s song, on the Jukebox slider |
| `gpuModels` | `true` | Draw the race wings from the graphics card, far faster; off, the old way |
