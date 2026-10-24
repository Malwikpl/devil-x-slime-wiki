# FAQ

## Getting a gear

??? question "How do I get the Boosted Gear or Divine Dividing?"
    Reincarnate: both are in Tensura's reincarnation roll for your Unique Skill. Divine Dividing can also come from
    Albion's jewel, which the [White Dragon Emperor](world/white-dragon-emperor.md) drops. See
    [Your first Sacred Gear](getting-started/first-gear.md).

??? question "Can I have both gears?"
    No. One Heavenly Dragon per player: "Albion and Ddraig can't share a host." A Boosted Gear holder can still get
    [Albion's power to Divide](boosted-gear/divide.md) from the White Dragon Emperor.

??? question "I can't roll Divine Dividing any more. Why?"
    Only one player per world can hold Divine Dividing. While someone has it, the roll skips it. An operator can free it
    with `/dxdtensura divinedividing release <player>`, which takes it from that player.

??? question "The gears never show up in my reincarnation roll."
    The server may have turned them off: check `addToReincarnationPool` and `addDivineDividingToReincarnationPool` in
    `config/dxdtensura-server.toml`. The roll is random, with the same odds as every other Unique Skill in it.

## Boosted Gear

??? question "My Explosion does nothing to my sword hits."
    The Boost multiplies your **bare fist** only. Empty your main hand. The one weapon that counts is
    [Ascalon's blade](boosted-gear/ascalon.md#the-blade) coming out of the gauntlet.

??? question "Why is my max health lower while I Boost?"
    That's body strain: each held stack takes 5% of your max health (2.5% once mastered). It comes back when you release
    the power. See [Body strain](boosted-gear/modes.md#body-strain).

??? question "How do I unlock Dragon Shot and Transfer?"
    Mastery. Dragon Shot comes with the Base form at 40% mastery, Transfer with the Boosted Gear Gift at 100%. See
    [Forms and mastery](boosted-gear/forms-and-mastery.md).

??? question "How do I get Balance Breaker?"
    In the Boosted Gear Gift, survive a crisis: while an Explosion runs, a strong enemy leaves you under 30% health.
    Each crisis has a growing chance to awaken it. Or accept [Ddraig's Bargain](boosted-gear/ddraig.md#ddraigs-bargain),
    at the price of your off-hand. See [Balance Breaker](boosted-gear/balance-breaker.md#awakening).

??? question "I lost my off-hand slot!"
    You accepted Ddraig's Bargain. The off-hand is his, for good.

??? question "How do I start Juggernaut Drive?"
    The first time, it happens to you: in the Scale Mail, let the rage meter fill while you're under 20% health. After
    that, Ddraig teaches you the incantation to chant yourself. See [Juggernaut Drive](boosted-gear/juggernaut-drive.md).

??? question "My max health keeps going down."
    Each Juggernaut Drive takes 10% of your max health for good (down to half), and each Divide in the Boosted Gear takes
    2% (that part grows back). Becoming a dragon race (Dragonewt and up) clears it. See
    [The price](boosted-gear/juggernaut-drive.md#the-price).

??? question "My gauntlet won't summon."
    After a Juggernaut Drive the gear goes silent for 10 minutes. The panel counts the minutes down.

??? question "My gauntlet doesn't show in first person."
    In first person it shows only with an empty main hand (or a map). In third person it always shows.

## Divine Dividing

??? question "Divide says \"Its power is beyond us.\""
    The target has more than ten times your max EP. In the [white Scale Mail](divine-dividing/balance-breaker.md) no
    target is too strong.

??? question "My white Scale Mail broke on its own."
    The strain gauge overloaded: you took in more power than you could hold. Watch the gauge (the ring) and let the
    wings vent. See [The strain gauge](divine-dividing/balance-breaker.md#the-strain-gauge).

## Devils

??? question "How do I become a Devil?"
    Pick **Low-class Devil** in Tensura's race menu: when you start, after the Reincarnation spell, or with a Race Reset
    Scroll on an existing character. See [Becoming a Devil](races/devil.md#becoming-a-devil).

??? question "Can a Devil use the Boosted Gear or Divine Dividing?"
    Yes, as before. The life prices are the same. See [Devils and the Sacred Gears](races/devil.md#devils-and-the-sacred-gears).

??? question "Why am I slower in the daytime?"
    That's **Under the Sun**: in the daytime sun a Devil is 10% slower and loses the class's attack bonus. Go indoors or
    wait for the night, when Demonic Power hits harder. See [Night and day](races/devil.md#night-and-day).

??? question "My wings won't open."
    Use Tensura's **Race/Mount Ability** key, not a skill slot. While you wear a Scale Mail or have Divine Dividing's
    wings out, the gear's wings show instead.

## Settings

??? question "Can I get the old blocky models back?"
    Yes: set `modelStyle` to `CLASSIC` in the client settings (Mods → Devil x Slime → Config). See
    [Model style](reference/looks.md#model-style).

??? question "Can I skip the cutscenes?"
    Sneak to skip one, or turn `cutscenes` off in the client settings to transform at once.

??? question "Ddraig talks too much."
    Set `ddraigLines` to `IMPORTANT` or `OFF` in the client settings.

## Other

??? question "Are there secrets?"
    There are two hidden easter eggs from the anime, for multiplayer only. We're not telling.
