# FAQ

## Getting a gear

??? question "How do I get a Sacred Gear?"
    Reincarnate as a **human**: the Boosted Gear, Divine Dividing, Twilight Healing, Sword Birth and Forbidden Balor View are in Tensura's reincarnation
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
    `addDivineDividingToReincarnationPool`, `addTwilightHealingToReincarnationPool`, `addSwordBirthToReincarnationPool` and
    `addBalorViewToReincarnationPool` in
    `config/dxdtensura-server.toml`. The roll is random, with the same odds as every other Unique Skill in it.

??? question "My gear left me, and I didn't pick a new race."
    A Sacred Gear lives only in a human. Since 0.2.35 a gear that reached a non-human another way, such as a reroll mod, leaves at login or within a second, and you get a new Unique
    Skill. Evil Pieces, Brave Saint cards, evolution and falling keep it. See [Only in humans](getting-started/first-gear.md#only-in-humans).

??? question "Alt + my slot key opens a wheel. How do I switch modes?"
    That's the [mode wheel](getting-started/mode-wheel.md), new in 0.2.67: move the mouse toward a mode and let go of Alt. A quick tap
    without moving the mouse flips back to the mode before. To have Tensura's one-step switching back, turn off **New ability controls**
    under Mods → Devil x Slime → Config.

??? question "The Scale Mail moved my key to Boost."
    With the new ability controls on, going into the Scale Mail puts the key you pressed on Boost, and the True Queen puts the Evil Piece's
    key on Crimson Blaster, so the next press doesn't end the form. The key goes back when the form ends. Turn off **New ability controls**
    to keep your keys where you put them. See [The forms move your key](getting-started/mode-wheel.md#the-forms-move-your-key).

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

??? question "Tapping Boost in the Scale Mail stops short of ×64."
    A press only reaches as far as your max EP does: all six stacks at 100,000 EP, and one fewer per halving. The Boost keeps climbing by itself, a stack every 10 seconds. See
    [The Boost inside](boosted-gear/balance-breaker.md#the-boost-inside).

??? question "How do I get the Knight, Rook, Bishop and True Queen armours?"
    Be a Pawn in a peerage, with the Scale Mail on, and press the Evil Piece's Promotion modes. The True Queen opens after 3 minutes in each of the other three, with all 8 Pawns awake.
    See [Promotion's armour forms](boosted-gear/promotion-forms.md).

??? question "My Rook or Queen Promotion says my body can't take it."
    A Longinus holder wakes their Pawns with EP: the Rook at 10,000 base max EP and the Queen at 40,000. See
    [Growing into your Pawns](races/peerage.md#growing-into-your-pawns).

??? question "I lost my off-hand slot!"
    You accepted Ddraig's Bargain. The off-hand is his, for good.

??? question "How do I start Juggernaut Drive?"
    The first time, it happens to you: in the Scale Mail, let the rage meter fill while you're under 20% health. After
    that, Ddraig teaches you the incantation to chant yourself. See [Juggernaut Drive](boosted-gear/juggernaut-drive.md).

??? question "My max health keeps going down."
    Each Juggernaut Drive takes 10% of your max health for good (down to half), and each Divide in the Boosted Gear takes
    2% (that part grows back). Becoming a dragon race (Dragonewt and up) clears it. See
    [The price](boosted-gear/juggernaut-drive.md#the-price).

??? question "The dragon wrecks everything it walks into. Can I stop that?"
    It breaks what would stop it, with no drops, as both dragons do. Set `juggernautWalkBreaksBlocks` to false to turn it off. It
    also stops with `dragonShotBreaksBlocks`, `mobGriefing` or Tensura's `skillGriefing` off, in the Labyrinth and on claimed land. See
    [The dragon](boosted-gear/juggernaut-drive.md#the-dragon).

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

??? question "How do I get the white Scale Mail?"
    It isn't guaranteed. From 40% mastery, with your wings out, Divide an enemy that's a player, a boss or at least half your EP, and let
    its hit leave you alive under 30% health. Albion then rolls: 10% the first time, 10% more after each miss. See the
    [checklist](divine-dividing/balance-breaker.md#awakening).

??? question "The White Dragon Emperor's Divide keeps landing."
    Since 0.2.67 a white ring closes on you a second before it lands. Get a wall or a pillar between you and him, and it misses. Each Divide
    he lands makes him stronger, so dodging them keeps the fight short. See [His Divide](world/white-dragon-emperor.md#his-divide).

## Twilight Healing

??? question "My heals cost a lot of magicules."
    A whole health bar costs 20% of your max magicules, 10% once mastered, for anyone you heal. You pay only for the
    health that comes back. See [The price](twilight-healing/index.md#the-price).

??? question "The Healing Field heals my enemies."
    Until you master the gear, it heals everyone inside. Fully mastered, only you and your allies. Healing Arrows already
    fade on enemies.

## Sword Birth

??? question "Why can't I pick this sword?"
    A sword opens when your max EP reaches its own, and the rare ones also need you to have held a real one. The line at the
    foot of the menu says which. Holy swords never open. See [Which swords](sword-birth/index.md#which-swords).

??? question "How do I hold two copies?"
    Press Birth while sneaking: it tries your off hand first. Two copies is the most you can have; a third makes the oldest
    fade.

??? question "My copy vanished."
    A copy lasts 60 seconds, up to 3 minutes with mastery. It also ends at zero magicules, on death, when dropped and in any
    container. Press **Q** to dismiss one. See [A copy](sword-birth/index.md#a-copy).

## Forbidden Balor View

??? question "I pressed it and nothing happened."
    Read the action bar. "Nothing in your sight." means nothing was caught, "shrugs off your gaze" means the target has 5 times your
    EP or more, and "Time hasn't caught up with it yet." means it's [resting](balor-view/index.md#the-rest) from its last stop. None of
    them costs anything or starts the cooldown.

??? question "It stopped my friends and pets!"
    That's a [misfire](balor-view/index.md#misfires). Until 40% mastery, a hit that drops you below 30% health can open the eye by
    itself. A press of your own always spares them.

??? question "Why don't I have bats?"
    They're for a holder of Tensura's [Vampire line](balor-view/index.md#the-vampire-line), as Gasper's come from his vampire half.
    Everyone else has Stop the World with no bats, at 20 blocks instead of 30.

??? question "Can I stop a boss?"
    Yes, unless it has 5 times your EP or more. There's no list of bosses: the stronger it is, the shorter it stops. See
    [How long a stop lasts](balor-view/index.md#how-long-a-stop-lasts).

## Durandal and the Holy Factor

??? question "Durandal jolts me and leaves my hand."
    Only a holy wielder can hold it: someone with the Holy Factor, an Angel, one of Tensura's Saint or Divine races, or a True
    Hero. Carrying it in your inventory is fine. See [Who can wield it](durandal/index.md#who-can-wield-it).

??? question "How do I get the Holy Factor?"
    Picking Human or Enlightened Human gives a 5% chance, once, and each Skill or Character Reset Scroll gives one more roll.
    Otherwise look for a **Holy Factor Crystal**, in one church chest in ten. See
    [The Holy Factor](durandal/index.md#the-holy-factor).

??? question "Where is Durandal?"
    In the crypt under one ruined church in three: `/locate structure dxdtensura:ascalon_church_crypt`. The first reliquary
    opened in a world gives the true sword, and later ones a replica. See [The reliquary](durandal/index.md#the-reliquary).

??? question "This church's skull has no Ascalon."
    That's a crypt church, which holds only Durandal. Look for the stair in the nave, or another church for Ascalon.

??? question "Can a Boosted Gear holder wield Durandal?"
    No. A Heavenly Dragon's holder is never a holy wielder, and the Holy Factor never goes with their gear. Other Sacred Gears
    are fine.

??? question "Durandal's waves hurt me."
    Its aura is wild until you tame it: use it, and its skill's mastery calms it on the way to 1,000. See
    [Taming it](durandal/index.md#taming-it).

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

??? question "What's a Mutation Piece?"
    A piece that takes anyone worth up to 9 as one piece, with a servant a quarter stronger. A King has a 1 in 10 chance of one when they
    become a King and again each time their base max EP doubles. Use the case in the air to choose its kind. See
    [Mutation Pieces](races/peerage.md#mutation-pieces).

??? question "My wings won't open."
    Use Tensura's **Race/Mount Ability** key, not a skill slot. While you wear a Scale Mail or have Divine Dividing's
    wings out, the gear's wings show instead.

## House powers

??? question "How do I get a House?"
    Pick a Devil race in Tensura's race menu, and you're born of one by a roll. Devils already in a world roll at their next login. See
    [The roll](races/houses.md#the-roll).

??? question "Can I pick my House?"
    No. It's Phenex 30%, Sitri 30%, Bael 20%, Gremory 10% and Leviathan 10%. Death, evolution and a Race Reset Scroll keep it, and a
    Character Reset Scroll rolls again.

??? question "I took an Evil Piece and have no House."
    A Devil reborn by a piece has none, and neither does a hybrid. Only a pure-blooded Devil has one, and a pure Devil who takes a
    piece keeps theirs. See [Who has one](races/houses.md#who-has-one).

??? question "Why is my top power still locked?"
    Mastery isn't always enough. Extinguished Star, Firestorm, Celsius Cross Trigger and the Sea Dragon also need Ultimate-class, and
    Ruin the Extinct needs Satan-class.

??? question "My wings of fire went out and I fell."
    A holy hit, Tensura's Frost, or a cold or water hit of at least 10% of your max health puts them out for 5 seconds. Wings that were
    open come back by themselves. See [House Phenex](races/houses.md#house-phenex).

??? question "I died for real as a Phenex."
    Rebirth needs the magicules, and its price climbs from 30% to 80% with each rebirth within 5 minutes. A holy hit in the last 10
    seconds, a foe with 10 times your max EP, `/kill` and the void also kill for real.

??? question "Where do I get a Phoenix Tear?"
    Only a House Phenex Devil makes one, from a water bottle, at 50% mastery. There's no recipe, loot or trade. Anyone can drink it.

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
    or a Fallen Angel (Holy Lightning). A Fallen Angel reborn as a hybrid has one more try at Holy Lightning. See
    [Birth skills](races/angels.md#birth-skills).

??? question "How do I get a Light Sword or a Light Bow?"
    They're modes on Heaven's Light and Fallen Light. The sword is there from the start, and the bow opens at 40% mastery. See [Light weapons](races/light-weapons.md).

??? question "My Light Spear stays in my hand."
    You kept the key down. Right-click or tap the key to throw it, and tap it next time to throw it straight away. See
    [The Light Spear in your hand](races/light-weapons.md#the-light-spear-in-your-hand).

??? question "How do I open the Thunderlight Blast and the Storm?"
    The Blast opens at Holy Lightning's full mastery, 500 points. The Storm needs High-class, and then you learn it by trying.
    See [Holy Lightning](races/holy-lightning.md).

??? question "How do I get the Brave Saints?"
    Reach **Ultimate-class** as an Angel (or become a Seraph): the Brave Saints skill comes with it. Its first press picks
    your suit. See [Brave Saints](races/brave-saints.md).

??? question "Why won't my friend take my card?"
    Only a human or a pure Angel can take one. Devils, hybrids, Fallen Angels, other races, a King's servants and
    anyone as strong as you refuse, and a Longinus holder needs the Queen or the Ace. See
    [Offering a card](races/brave-saints.md#offering-a-card).

??? question "What does the Joker do?"
    Since 0.2.67 every deck has a 13th card, the Joker: a quarter stronger than the Ace, and wild in hands, any card from 2 to Ace in poker
    (never the King) and any count in Blackjack. See [The Joker](races/brave-saints.md#the-joker).

## The Castle Town

??? question "How do I get to the Castle Town?"
    Ask [Rias](races/rias.md#the-way-to-the-underworld) for "The way to the Underworld", take the map through any Hell Gate, and hold it in your hand: the action bar says how far and which
    way. See [Finding it](world/castle-town.md#finding-it).

??? question "Why are the guards attacking me?"
    You're Wanted: you hurt someone in the square, or you carry a Stray Devil's mark. Pay the Clerk 1 gold or stay out of the square for a full in-game day. A mark has no fine, so
    stay out of the square. See [Wanted](world/castle-town.md#wanted).

??? question "Why can't I break blocks or open chests there?"
    The town is protected in survival. Doors, gates and bells work. Server owners can turn it off with `protect`. See [The rules](world/castle-town.md#the-rules).

??? question "How do I respawn in the town?"
    Rent a room from the innkeeper, then choose "Set your respawn here". See [The inn](world/castle-town.md#the-inn).

??? question "How do bounties work?"
    Right-click the board at the Hunters' Office for three posters a day, and take one. You're paid in coins, EP and renown where you make the kill. See [Bounties](world/castle-town.md#bounties).

??? question "Dark winged hunters keep coming for me."
    You carry the Stray Devil mark. They come every 3 to 5 in-game days, leave after 5 minutes, and stay out of the town. See [Hunters and the mark](world/castle-town.md#hunters-and-the-mark).

??? question "How do I get a title, or the treasury's keys?"
    Earn renown with bounties and Rias's jobs, and take it to Zeoticus in the great hall. A Champion's gift is three Treasury Keys. See [Titles and renown](world/castle-town.md#titles-and-renown).

## Lore mode

??? question "How do I turn on Lore mode?"
    Set Lore Mode in the game rules on the Create World screen, or as an operator use `/gamerule dxdLoreMode true`. It's for
    one world. See [Lore mode](lore-mode.md).

??? question "Can I turn it off again?"
    Yes, at any time. It acts at once: extra stacks drop, an armour worn past its normal limit ends, and copies with no timer
    fade.

## Structures

??? question "A church in my world stands in a lake or half in a hill."
    Buildings generated before 0.1.92 stay where they are. New land follows the new rules. See
    [Where they stand](world/structures.md#where-they-stand).

??? question "`/place structure` failed."
    It follows the same ground rules, so it can fail on bad land. `/place template dxdtensura:<name>` drops the building
    anywhere.

## Nekomata and Nekoshou

??? question "How do I become a Nekoshou?"
    You can't choose it. One player in ten who becomes a Nekomata is born one, on a single roll that stays through death and a Race
    Reset Scroll. A Character Reset Scroll starts it over. See [Becoming one](races/nekomata.md#becoming-one).

??? question "How do I change my coat?"
    Use a Race Reset Scroll and pick the race again. If you closed the coat screen without picking, it asks again at your next login.

??? question "I lost my speed and Touki stopped."
    Your ears and tails are hidden, or a Scale Mail is hiding them. The race key brings them out, or Sneak + race key on a hybrid.
    See [Ears and tails](races/nekomata.md#ears-and-tails).

??? question "My tails flicker dark, and I attacked my friend."
    That's Malice. Senjutsu gathers it, it flickers from 50, and at 100 you go berserk for 15 seconds, so give it time to fade between
    fights. It fades faster by day, and never in Hell. See [Malice](races/nekomata.md#malice).

??? question "How do I open Mud Bind, Veil and Mirage?"
    Use Youjutsu on something: each use that poisons, holds or fools it earns mastery. They open at 25%, 50% and 75%, with a line
    in chat. An armour stand or a Training Dummy earns none. See [Youjutsu](races/nekomata.md#youjutsu).

??? question "Can a Nekomata have a Sacred Gear?"
    No. A cat never rolls a Sacred Gear, the Holy Factor or a Brave Saint card.

??? question "What happens if I take an Evil Piece?"
    You become a Devil with your blood: you keep Senjutsu, the coat, the ears and tails, and lose Youjutsu. See
    [Evil Pieces and hybrids](races/nekomata.md#evil-pieces-and-hybrids).

## Valkyries

??? question "How do I become a genius of Norse magic?"
    You can't choose it. One player in ten who becomes a Valkyrie is born one, on a single roll kept through death, a Race Reset Scroll
    and rebirth as a Devil. See [The genius](races/valkyrie.md#the-genius).

??? question "I'm a Valkyrie and have no Seiðr."
    A genius has none, as Rossweisse has none. Everyone else on the line has it. See [Seiðr](races/valkyrie.md#seidr).

??? question "No Chosen Soul appeared."
    Souls come only from a boss or a foe with at least half your EP, dying within 16 blocks of you (a boss within 64, or anywhere for its
    killer). Pets, summons, friends and spared players leave none. See [Chosen Souls](races/valkyrie.md#chosen-souls).

??? question "Full Burst blew a hole in my base."
    Its blasts break blocks as TNT does, when the `mobGriefing` and `skillGriefing` rules are on. A server owner can turn it off with
    `fullBurstBreaksBlocks = false`. See [Full Burst](races/valkyrie.md#full-burst).

## Kitsune and the Nine-Tailed Fox

??? question "How do I become a Nine-Tailed Fox?"
    You can't choose it. One player in ten who becomes a Kitsune is born one, on a single roll kept through death and a Race Reset Scroll.
    See [Becoming one](races/kitsune.md#becoming-one).

??? question "The Great Fox won't come out."
    It's a Nine-Tailed Fox's, from High-class. It needs room to stand ten blocks tall: not in a cave or under a low roof. After it, it
    cools down for 10 minutes. See [The Great Fox](races/kitsune.md#the-great-fox).

??? question "I can't use items as a fox."
    The fox body bites with whatever you hold and can't use items, though doors and buttons still work. Press Fox Transformation again
    to stand. See [The fox body](races/kitsune.md#the-fox-body).

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

??? question "Can I turn the wings' motion off?"
    Yes: turn off **Living wings** (`wingMotion`) in the client settings, and they keep the old slow beat. It covers the Scale Mails too. See
    [Living wings](reference/looks.md#living-wings).

??? question "The True Queen's song is too loud, or I don't want it."
    It's on the Jukebox slider in Minecraft's music and sound options. The client setting `trueQueenMusic` turns it off.

??? question "A pose or sound went missing after I died or went through a portal."
    Update to 0.2.13. Each player's looks were kept by an id that a respawn or a new dimension reuses, so a pose could fail to start, the
    wings could twitch once after a death, and Twilight Healing's Touch could go silent after a portal.

??? question "I crashed on joining a world: `Value missing: dxdtensura:twilight_healing`."
    Update to 0.2.13. When several addons registered their skills at the same moment during startup, one could go missing with no error.
    The fix protects every addon in the pack.

??? question "I fly upside down with TR: Nightmare."
    Fixed in 0.1.77. To use Nightmare's own flight pose instead of ours, turn the client setting `flightLean` off.

## Other

??? question "Are there secrets?"
    There are two hidden easter eggs from the anime, for multiplayer only. We're not telling.
