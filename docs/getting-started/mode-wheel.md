# The mode wheel

Added in **0.2.67**. The gears and race skills have many modes: the Boosted Gear has seven, the Evil Piece's True Queen two moves and a way
out. Instead of stepping through them one at a time, **hold Left Alt and press the slot key**, and a wheel of the skill's modes opens round
the crosshair.

It's part of the **New ability controls**, on by default. You can [turn them off](#turning-it-off) and keep Tensura's one-step switching.

## Picking a mode

1. **Hold Left Alt** (Tensura's "Next Ability Mode" key) and **press the slot key** (Z, X or C by default).
2. **Move the mouse toward a mode.** It lights up.
3. **Let go of Alt.** The key is now on that mode, and pressing it uses that mode.

- **A left click** picks the lit mode at once. **A right click** closes the wheel with nothing changed, and so does Escape.
- While it's open **the camera holds still**, and you keep walking.
- Only the modes you've **unlocked** are on the wheel. A mode cooling down shows its seconds left.
- A pick only aims the key: nothing fires until you press it.

It works for **every skill from this addon**: the gears, the race skills, the Evil Piece and the House powers. Tensura's own skills and other
mods' skills keep Tensura's one-step switching.

## A quick tap flips back

Tap Alt + the slot key **without moving the mouse**, and the key flips back to the mode it had before. Two modes you use together, like
Boost and Dragon Shot, are one tap apart.

With nothing to flip back to, a tap steps one mode forward, as Tensura does.

## Your other skills round the edge

Your other skills from this addon sit round the wheel's edge as icons. **Move the mouse further out** to one, and its modes come inside;
pick one, and the key now holds **that skill** on that mode.

- Two race skills can share one key this way, a Kitsune's Fox Fire and Youjutsu, say.
- **Alt + an empty key** opens the edge alone, so you can put a skill on it.
- The client setting `abilityWheelSkills` ("Mode wheel: other skills") hides the edge.

## The forms move your key

With the new controls on, going into a form puts the key you pressed onto the form's first move, so your next press doesn't end it:

- going into the **Scale Mail** puts the key on **Boost**;
- going into the [True Queen](../boosted-gear/promotion-forms.md#the-true-queen) puts the Evil Piece's key on **Crimson Blaster**. Her
  wheel shows "Leave True Queen" in place of the Queen, and greys out the Knight, which does nothing in her.

When the form ends, the key goes back, unless you moved it yourself meanwhile. Priming a
[Juggernaut Drive](../boosted-gear/juggernaut-drive.md) in the Scale Mail puts the key back on Balance Breaker, which releases it.

## Turning it off

The client setting **New ability controls** (`abilityWheel` in `config/dxdtensura-client.toml`, on by default), under Mods → Devil x Slime →
Config. Off, since **0.2.67** it turns off everything above:

- Alt + the slot key steps **one mode** forward, as Tensura does;
- the forms **leave your keys** where you put them.

Each player chooses for themselves; a server can't force it either way.

!!! tip "Other ways to set a key"
    "Previous Ability Mode" steps back. It has no key by default; set one under Controls → Key Binds, in the **Tensura:Reincarnated**
    category. `/ability set <skill> <mode> <slot>` sets a slot by command.
