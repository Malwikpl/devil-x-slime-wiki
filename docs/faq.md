# FAQ

## Getting a gear

??? question "How do I get a Sacred Gear?"
    Reincarnate as a **human**: the Boosted Gear, Divine Dividing and Twilight Healing are in Tensura's reincarnation
    roll for a human's Unique Skill. Divine Dividing can also come from Albion's jewel, which the
    [White Dragon Emperor](world/white-dragon-emperor.md) drops. See
    [Your first Sacred Gear](getting-started/first-gear.md).

??? question "I picked a Devil (or an Angel) and never roll a gear."
    Since 0.1.84 a Sacred Gear is born only in a human, as in DxD. Start as a human, roll a gear, then become a Devil
    with an [Evil Piece](races/peerage.md) or an Angel with a [Brave Saint card](races/brave-saints.md): the gear stays.
    See [Only in humans](getting-started/first-gear.md#only-in-humans).

??? question "My gear left me when I used a Race Reset Scroll."
    Picking a race that isn't human in Tensura's race menu makes the gear leave you, and you roll a new Unique Skill in
    its place. The menu warns you first. Pick Human to keep it.

??? question "Can I have two gears?"
    No. One Sacred Gear per player: "Albion and Ddraig can't share a host.", or "You already carry a Sacred Gear." A
    Boosted Gear holder can still get [Albion's power to Divide](boosted-gear/divide.md) from the White Dragon Emperor.

??? question "I can't roll Divine Dividing any more. Why?"
    Only one player per world can hold Divine Dividing. While someone has it, the roll skips it. An operator can free it
    with `/dxdtensura divinedividing release <player>`, which takes it from that player.

??? question "The gears never show up in my reincarnation roll."
    Only a human's roll has them. Otherwise the server may have turned them off: check `addToReincarnationPool`,
    `addDivineDividingToReincarnationPool` and `addTwilightHealingToReincarnationPool` in
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
    wings vent. See [The strain gauge](divine-dividing/balance-breaker.md#the-strain-gauge). A Boosted Gear rival's
    Transfer can also flood it: [Transfer overload](divine-dividing/juggernaut-drive.md#transfer-overload).

??? question "How do I get Divine Dividing's Juggernaut Drive?"
    Master Divine Dividing with the white Scale Mail awakened, and Albion offers you Vali's words. Chant them in the
    armour and press the Balance Breaker key. See [Juggernaut Drive (the white dragon)](divine-dividing/juggernaut-drive.md).

## Twilight Healing

??? question "My heals cost a lot of magicules."
    A whole health bar costs 20% of your max magicules, 10% once mastered, for anyone you heal. You pay only for the
    health that comes back. See [The price](twilight-healing/index.md#the-price).

??? question "The Healing Field heals my enemies."
    Until you master the gear, it heals everyone inside. Fully mastered, only you and your allies. Healing Arrows already
    fade on enemies.

## Devils

??? question "How do I become a Devil?"
    Pick **Low-class Devil** in Tensura's race menu: when you start, after the Reincarnation spell, or with a Race Reset
    Scroll on an existing character. See [Becoming a Devil](races/devil.md#becoming-a-devil).

??? question "Can a Devil use a Sacred Gear?"
    Yes, if they got it as a human first and then took an Evil Piece. A Devil from the race menu rolls none. See
    [Devils and the Sacred Gears](races/devil.md#devils-and-the-sacred-gears).

??? question "Stray Devils keep coming for me at night."
    They rise now and then near players on dark nights in the overworld, and sink away at sunrise. A player with the
    Stray Devil mark (from leaving a peerage) is left alone until they hurt one. See [Stray Devils](world/stray-devils.md).

??? question "How do I get Rias's hunts?"
    Serve her, and every 3 in-game days she calls you at dusk, or ask "Any Stray Devils?" on her talk screen. See
    [Rias's hunts](world/stray-devils.md#riass-hunts).

??? question "Why am I slower in the daytime?"
    That's **Under the Sun**: in the daytime sun a Devil is 10% slower and loses the class's attack bonus. Go indoors or
    wait for the night, when Demonic Power hits harder. See [Night and day](races/devil.md#night-and-day).

??? question "Can I join a peerage in single player?"
    Yes: [Rias Gremory](races/rias.md) offers her Evil Pieces to everyone. Her bat brings you her flyer on your first
    night; follow its arrow to the old school building. Keep the flyer on you, and if you die she comes to offer you a
    piece.

??? question "My wings won't open."
    Use Tensura's **Race/Mount Ability** key, not a skill slot. While you wear a Scale Mail or have Divine Dividing's
    wings out, the gear's wings show instead.

## Angels and Fallen Angels

??? question "How do I become an Angel or a Fallen Angel?"
    Pick **Low-class Angel** or **Low-class Fallen Angel** in Tensura's race menu: when you start, after the
    Reincarnation spell, or with a Race Reset Scroll. An Angel who falls becomes a Fallen Angel. See
    [Becoming one](races/angels.md#becoming-one).

??? question "My Angel's wings are flickering black."
    That's sin. Killing villagers, golems, pets or players who didn't attack you, or learning a Deadly Sin skill, fills
    it; it fades every day. At 100 you fall. See [Sin and the fall](races/angels.md#sin-and-the-fall).

??? question "Can an Angel join a peerage?"
    No: Angels refuse Evil Pieces, and Rias won't take them. A Fallen Angel can, and becomes a Devil with Fallen Angel
    blood, a [hybrid](races/angels.md#hybrids).

??? question "I don't have Holy Barrier or Holy Lightning."
    They're rare birth skills: a 10% chance, rolled once per player, the first time you become an Angel (Holy Barrier)
    or a Fallen Angel (Holy Lightning). See [Birth skills](races/angels.md#birth-skills).

??? question "How do I get the Brave Saints?"
    Reach **Ultimate-class** as an Angel (or become a Seraph): the Brave Saints skill comes with it. Its first press picks
    your suit. See [Brave Saints](races/brave-saints.md).

??? question "Why won't my friend take my card?"
    Only a human or a pure Angel can take one. Devils, hybrids, Fallen Angels, other races, a King's servants and
    anyone as strong as you refuse, and a Longinus holder needs the Queen or the Ace. See
    [Offering a card](races/brave-saints.md#offering-a-card).

## Settings

??? question "Can I get the old blocky models back?"
    Yes: set `modelStyle` to `CLASSIC` in the client settings (Mods → Devil x Slime → Config). See
    [Model style](reference/looks.md#model-style).

??? question "Can I skip the cutscenes?"
    Sneak to skip one, or turn `cutscenes` off in the client settings to transform at once.

??? question "Ddraig talks too much."
    Set `ddraigLines` to `IMPORTANT` or `OFF` in the client settings.

??? question "My fps drops with wings out."
    Update to 0.1.84 or newer: the wings are drawn from the graphics card now. If they look wrong with another mod,
    turn the client setting `gpuModels` off.

??? question "I fly upside down with TR: Nightmare."
    Fixed in 0.1.77. To use Nightmare's own flight pose instead of ours, turn the client setting `flightLean` off.

## Other

??? question "Are there secrets?"
    There are two hidden easter eggs from the anime, for multiplayer only. We're not telling.
