# Divine Dividing

The White Dragon Emperor's Sacred Gear, with **Albion** sealed inside. Its wings of light are the whole gear: they fly,
and they **Divide**, halving an enemy's power and taking it for you. It is a Tensura **Unique Skill**
(`dxdtensura:divine_dividing`), the Boosted Gear's rival.

<div class="grid" markdown>

<figure markdown="span">
  ![The wings of light](../assets/images/wings-open.jpg){ loading=lazy }
  <figcaption>The wings of light</figcaption>
</figure>

<figure markdown="span">
  ![The wings flaring with a Divide](../assets/images/wings-divide-flare.jpg){ loading=lazy }
  <figcaption>Flaring with a Divide</figcaption>
</figure>

</div>

## Getting it

- **Reincarnation** can roll it, at the same odds as the Boosted Gear.
- **Albion's jewel**, dropped by the [White Dragon Emperor](../world/white-dragon-emperor.md), gives it to a player with
  no gear.
- **One Heavenly Dragon per player.** A Boosted Gear holder can't learn Divine Dividing, and the other way round.
- **One Divine Dividing per world.** While someone holds it, the reincarnation roll skips it and nothing else gives it.
  Players who already held it keep it.

## Modes

| # | Mode | Unlocks | What it does |
|---|---|---|---|
| 0 | **[Divide](#divide)** | from the start | Slash at a target and keep halving its power |
| 1 | **Wings** | from the start | Summon or put away the wings |
| 2 | **[Balance Breaker](balance-breaker.md)** | awakening, from 40% mastery | Put on the white Scale Mail |
| 3 | **[Half Dimension](balance-breaker.md#half-dimension)** | awakening; in the armour only | Divide everything around you |
| 4 | **[Compression Divider](balance-breaker.md#compression-divider)** | awakening; in the armour only | Land Divides at once |

While the wings are away, any press only summons them ("Divine Dividing!"). The Wings mode puts them away.

## Flight

With the wings out you can fly, creative-style (double-tap jump).

- Flying costs **0.5% of your max magicules a second** in the air. Standing is free.
- When your magicules can't pay, you fall, and the flight comes back once you have a second's worth again. Albion warns
  you once a flight when you drop below 20%.
- Flying forward you lean into it; flying backwards you lean back, and you bank into turns. Sprint-flying you go flat
  out, arms and legs still.
- **Sprint-flying gets faster with mastery**, up to twice as fast once mastered.

## Divide

Press it and you **slash your hand** at what you're looking at, up to **8 blocks** away. Blocks stop it; players in
creative or spectator and armour stands don't count.

A thin white line cuts across your view through the target, light bursts on it, **DIVIDE!** floats beside it and
blue-white stars scatter. Then, **every 10 seconds**, it is divided again by itself, as long as it stays within
32 blocks and your wings are out. Each Divide:

- **takes half its magicules and aura** and pours them into you, up to your own maximum. What you can't hold, your wings
  vent away as light. Tensura's energy-drain immunity and Energy Protection stop this part.
- **halves everything it deals**: melee, skills, magic and its projectiles, every hit (not its speed). It shows as the
  **Divided** effect, I to III, lasting 30 seconds after the last Divide. Its summons and pets aren't Divided with it.
- **turns the attack it lost into Absorbed Power**, a flat attack bonus for you, never more than 7× your own attack
  (8× in all). The stronger the enemy, the stronger you get.
- **takes a Boosted Gear holder's stack**: they drop one held Boost stack (×2ⁿ to ×2ⁿ⁻¹, exactly half).

**Too strong.** A target with more than **ten times your max EP** (max magicules plus max aura) is beyond you: "Its
power is beyond us.", and the press costs nothing.

### How deep you can Divide

| Your mastery | Divides on one target | Its hits deal |
|---|---|---|
| new host | 1 | ½ |
| 40% | 2 | ¼ |
| mastered | 3 | ⅛ |

Bosses never take more than 2. A target that refuses effects (like Tensura's bosses) still stops at the cap and still
gives you the attack it would have lost; it only loses energy. Each Divide earns mastery.

### One target at a time

A press on a new target moves Divide to it and goes on a **10 second cooldown**; the old target stays weakened until its
effect runs out. A press on a target already at the cap says "It can't be divided further."

## Albion

Albion speaks to you in his own white and blue box, like Ddraig: teaching once each, the low-magicule warning, and the
rivals' meeting. When a Boosted Gear holder comes within 64 blocks: "The Red One is near." (and Ddraig to them: "I smell
the White One, partner."). The client setting `ddraigLines` covers him too.

## The panel

While the wings are out, the panel right of the hotbar is white and blue:

- the ring counts down to the next Divide around a blue jewel (dimmed while the Divide mode cools down);
- DIVINE DIVIDING;
- one pip per Divide your mastery allows, with the target's lit, and what's left of it (÷2, ÷4, ÷8);
- the target's name (or "No target"), with your mastery over the bar;
- the key for Divide.

A target divided to the cap stays on the panel for 30 seconds. Outside the armour the panel also shows your strength
(×3.5) and what's left of the target ("Pig ÷4").

## The wings

The wings unfold when summoned, sway at rest, beat while you fly, flare with each Divide and fold away when dismissed.
Your cape and elytra hide under them.

!!! note "Operators and testing"
    ```
    /tensura edit ability grant @s dxdtensura:divine_dividing
    /dxdtensura divinedividing holder             # who holds it in this world
    /dxdtensura divinedividing release <player>   # take it from them and free it
    ```
