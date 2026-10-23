# Your first Sacred Gear

Devil x Slime's Sacred Gears are Tensura **Unique Skills**. There are two, the rival Heavenly Dragons:

| Sacred Gear | Dragon | What it is |
|---|---|---|
| [Boosted Gear](../boosted-gear/index.md) | Ddraig, the Red Dragon Emperor | A crimson gauntlet that doubles your power again and again |
| [Divine Dividing](../divine-dividing/index.md) | Albion, the White Dragon Emperor | Wings of light that halve your enemy's power and take it for you |

## Getting one

**Reincarnate.** When Tensura rolls your Unique Skill, the Boosted Gear and Divine Dividing are in the roll, with the
same odds as every other skill in it.

- **One Heavenly Dragon per player.** You can never hold both. If you have one, the other can't be given to you in
  any way: "Albion and Ddraig can't share a host."
- **One Divine Dividing per world.** While a player holds Divine Dividing, the roll skips it. Its other way in is the
  [White Dragon Emperor](../world/white-dragon-emperor.md)'s jewel.
- Tensura's plundering skills can't steal either gear.

!!! note "Operators and testing"
    With cheats on (or operator level 2), you can grant a gear straight away:

    ```
    /tensura edit ability grant @s dxdtensura:boosted_gear
    /tensura edit ability grant @s dxdtensura:divine_dividing
    ```

## Putting it on a key

1. Open Tensura's **Status Menu** (default **B**) and put the skill on one of your ability slots.
2. Press that slot's key. Tensura's defaults are **Z**, **X** and **C** for slots 1 to 3.
3. The first press **summons** the gear ("Boosted Gear!" or "Divine Dividing!"). It costs nothing. Once it is out, each
   press uses the slot's mode.

**Switching modes.** Hold **Left Alt** (Tensura's "Next Ability Mode" key) and press the slot key to step to the next
mode. "Previous Ability Mode" has no key by default; you can set one under Controls → Key Binds, in the
**Tensura:Reincarnated** category. You can also put a different mode of the same gear on each slot, so Boost is on Z
and Dragon Shot on X, for example.

You can also set a slot with a command: `/ability set <skill> <mode> <slot>`. For example,
`/ability set dxdtensura:boosted_gear 0 1` puts Boost on slot 1.

**Modes you haven't unlocked yet** are skipped when you switch. A slot still set to one just tells you when it unlocks.

## Mastery

Using your gear earns Tensura **mastery** for it, the bar in Tensura's skill screen. Mastery is how the gears grow:

- The Boosted Gear's gauntlet **evolves** at 40% and at 100%, unlocking new modes. See
  [Forms and mastery](../boosted-gear/forms-and-mastery.md).
- Divine Dividing can **Divide deeper** and **fly faster** as its mastery grows, and its Balance Breaker can awaken
  from 40%. See [Divine Dividing](../divine-dividing/index.md).

## The Sacred Gear panel

While your gear is out, a panel to the right of your hotbar shows its state: a ring around the gear's jewel with a
countdown, the gear's name, your power, your form and mastery, and the key of your first slot with its mode. Only you
see it, and **F1** hides it. Each gear's page explains what its panel shows.

## Your partner

The dragon sealed in your gear talks to you. Ddraig (Boosted Gear) and Albion (Divine Dividing) teach you each power the
first time you use it, warn you when you're running low, and react to what you do, in a small speech box above the
panel. The client setting `ddraigLines` sets how much of them you see. See [Ddraig and his Bargain](../boosted-gear/ddraig.md).

## Server owners: the reincarnation roll

Tensura picks the reincarnation Unique Skill from a list in its own config file,
`config/tensura/reincarnation_config.toml`, under `[Skills] startingSkills`. To join that roll, **Devil x Slime writes
its gears into that list** every time a world or server starts:

- `"dxdtensura:boosted_gear"`, switched by `addToReincarnationPool` in `config/dxdtensura-server.toml`;
- `"dxdtensura:divine_dividing"`, switched by `addDivineDividingToReincarnationPool`.

It adds each entry once and leaves the rest of the file alone. Set a switch to `false` and the next start **removes**
that entry, even one you added by hand. If you uninstall Devil x Slime, a leftover entry is harmless: Tensura skips
skill ids it doesn't know.
