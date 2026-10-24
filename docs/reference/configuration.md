# Configuration

Devil x Slime has a **server** config with every rule and number, and a **client** config for how things look to you.

## The server config

- **File:** `config/dxdtensura-server.toml`, in the game folder (singleplayer) or the server folder. It is created the
  first time a world or server starts.
- **Per world:** put a copy at `<world>/serverconfig/dxdtensura-server.toml` (in singleplayer,
  `saves/<world>/serverconfig/`) to override it for one world.
- **Changes apply live.** NeoForge watches the file, so saving it applies the new values within a moment. No restart is
  needed. (`/reload` reloads data packs, not this file.)
- **On a server only the server's values count.** NeoForge sends them to every player who joins, and every rule is
  applied on the server.
- **Updating the mod keeps your values.** When a new version changes a default, files that still hold the old default
  get the new one; values you changed yourself are kept.

!!! tip
    Most options say what they are in their name. Ticks are 1/20 of a second: 200 ticks = 10 s. Percentages are written
    as whole numbers (50 = 50%).

## `[boosted_gear]`

The Boosted Gear: Boost, Transfer, Dragon Shot, mastery and body strain.

| Option | Default | Range | Meaning |
|---|---|---|---|
| `boostIntervalTicks` | 200 | 20–72000 | Ticks between Boost stacks while charging (200 = 10 s) |
| `maxStacks` | 6 | 1–10 | The most stacks anyone can hold, over the form caps (2, 5, 6); lowering it caps stacks already held |
| `baseStackCost` | 100.0 | 0–1e9 | Magicule cost of the first stack; each next stack costs double |
| `transferRange` | 8.0 | 1–32 | Transfer reach in blocks |
| `transferDurationTicks` | 600 | 20–72000 | Transferred Boost duration (600 = 30 s) |
| `dragonShotBaseDamage` | 5.0 | 0–1e6 | Dragon Shot damage at 0 stacks (× 2ⁿ when fired) (it was 20 in older versions) |
| `dragonShotCost` | 500.0 | 0–1e9 | Magicules per Dragon Shot |
| `dragonShotCooldownSeconds` | 5 | 0–3600 | Dragon Shot cooldown |
| `dragonShotBreaksBlocks` | true | — | Also break blocks on impact, in a blast of 1.5 blocks plus 0.5 a stack, at most 6 (about TNT's at 5 stacks); respects `mobGriefing` |
| `dragonShotBlastDamagePercent` | 50 | 0–100 | Share of the shot's damage the blast deals to everything else in it (not you): all of it at the centre, half at the edge, less behind cover; whether or not blocks break; 0 turns it off |
| `addToReincarnationPool` | true | — | Add Boosted Gear to (true) or remove it from (false) Tensura's `startingSkills` at start-up |
| `explosionDurationTicks` | 300 | 20–6000 | How long "Explosion!" multiplies melee (300 = 15 s) |
| `resetCooldownSeconds` | 30 | 0–3600 | Boost cooldown after the stored power is released |
| `baseFormMasteryPercent` | 40 | 1–99 | How far along the mastery bar the gauntlet evolves into its Base form |
| `masteryGainMultiplier` | 2.0 | 0–100 | Multiplies the mastery each use earns (0 turns mastery gain off) |
| `explosionMasteryHitCap` | 10 | 0–1000 | How many melee hits of one Explosion earn mastery |
| `strainPercentPerStack` | 5.0 | 0–25 | Max health each held stack takes at mastery 0 (0 turns strain off) |
| `masteredStrainPercentPerStack` | 2.5 | 0–25 | The same at full mastery |

## `[balance_breaker]`

Balance Breaker (both Scale Mails), Ddraig's Bargain and Ascalon.

| Option | Default | Range | Meaning |
|---|---|---|---|
| `breakerCrisisHealthPercent` | 30 | 1–99 | A crisis leaves you under this % of max health |
| `breakerWorthyEpPercent` | 50 | 0–1000 | A worthy enemy has at least this % of your max EP (players and `c:bosses` always count) |
| `breakerCrisisBaseChance` / `breakerCrisisChanceStep` | 10 / 10 | 0–100 | % chance of the first crisis, and % added per miss |
| `breakerCountdownSeconds` / `breakerTrainedCountdownSeconds` | 10 / 1 | 0–600 | The countdown untrained and fully trained |
| `breakerTrainingMinutes` | 10 | 1–1000 | Minutes worn, in total, to be fully trained |
| `breakerUpkeepPercent` | 0.6 | 0–100 | % of max magicules paid per second |
| `breakerMaxSeconds` | 180 | 1–3600 | The longest it lasts |
| `breakerArmor` / `breakerToughness` | 20 / 8 | 0–100 | Armour and toughness added |
| `breakerKnockbackResistance` | 0.5 | 0–1 | Knockback resistance added |
| `breakerSpeed` | 0.02 | 0–0.5 | Movement speed added (walking is 0.1) |
| `breakerFlight` | true | — | Flight while it lasts |
| `breakerEndCooldownSeconds` | 60 | 0–3600 | Cooldown after a short end: letting go within `breakerShortEndSeconds`, death, interference |
| `breakerLongCooldownSeconds` | 300 | 0–3600 | Cooldown after the time runs out, or letting go later than `breakerShortEndSeconds` |
| `breakerShortEndSeconds` | 90 | 0–3600 | How long after forming letting go gives only the short cooldown |
| `breakerExhaustedCooldownSeconds` / `breakerExhaustionSeconds` | 300 / 60 | 0–3600 | Cooldown, and Weakness and Slowness, after running dry |
| `rageFromDamage` | 0.35 | 0–100 | Rage from a hit before armour (0.35: a hit for your whole health bar gives 35%) |
| `ragePerHit` / `rageDrainPerSecond` | 2.0 / 2.0 | 0–100 | Rage per bare-handed hit, and drained per second when calm |
| `rageCalmSeconds` | 10 | 0–600 | Seconds without a hit before rage drains |
| `rageBurstIntervalTicks` | 10 | 1–200 | Ticks between a burst's quick boosts |
| `bargainEnabled` | true | — | Ddraig offers his Bargain in a crisis before the awakening |
| `bargainOfferSeconds` | 30 | 5–300 | How long an offer stays open on a server (the game can't pause there) |
| `bargainMaxSeconds` | 30 | 1–3600 | The early Scale Mail's longest |
| `bargainBoostIntervalTicks` | 100 | 1–12000 | Ticks per stack inside the early Scale Mail (100 = 5 s) |
| `bargainCooldownSeconds` | 600 | 0–36000 | Balance Breaker cooldown after the early Scale Mail ends |
| `bargainRetrySeconds` | 120 | 0–3600 | The wait after a refused offer |
| `breakerCrisisHealPercent` | 50 | 0–100 | Health the Scale Mail restores when it forms in a crisis (the awakening, the Bargain); 0 heals nothing |
| `ascalonFusedDamage` | 2.0 | 0–1000 | Attack the blade adds to an empty hand (the Explosion multiplies it like the fist) |
| `ascalonBurnPercent` | 5 | 0–100 | % of max health a dragon holding Ascalon loses each second |
| `ascalonBurnFloorHealth` | 2.0 | 0–1000 | The burn never takes a holder below this health (2 = one heart) |
| `ascalonTransferSeconds` | 30 | 1–3600 | How long a Transfer into the blade boosts its holy strike |
| `dragonSlayerPercent` | 100 | 0–1000 | The true Ascalon's holy strike on a dragon, % of the hit |
| `dragonSlayerReplicaPercent` | 50 | 0–1000 | A replica's holy strike on a dragon, % of the hit |

!!! note "The white Scale Mail"
    The white Scale Mail shares the red one's numbers in `[balance_breaker]`: the crisis, the countdown and its
    training, the upkeep, the time limit, the stats, the endings and the cooldowns.

## `[juggernaut]`

Juggernaut Drive and the Longinus Smasher.

| Option | Default | Range | Meaning |
|---|---|---|---|
| `juggernautEnabled` | true | — | Off removes the incantation and the past hosts' first takeover |
| `juggernautFirstHealthPercent` | 20 | 1–99 | The first Drive takes over a holder whose rage meter fills under this % of max health |
| `incantationRadius` | 64 | 0–1024 | Players within this many blocks see the incantation (0: the whole server) |
| `incantationWindowSeconds` | 30 | 5–600 | Seconds the incantation waits for its next line |
| `juggernautPrimeSeconds` | 60 | 5–600 | Seconds a finished incantation stays primed |
| `juggernautScale` | 4.0 | 1–16 | The dragon's size, times the holder's |
| `juggernautExtraStacks` | 2 | 0–4 | Stacks the dragon holds over the holder's cap |
| `juggernautStackIntervalTicks` | 20 | 1–1200 | Ticks between the dragon's stacks (free) |
| `juggernautShockwaveRadius` / `juggernautShockwavePercent` | 4.0 / 50 | 0–32 / 0–100 | The shockwave around a struck target and its share of the hit |
| `juggernautStrikeTicks` / `juggernautStrikeRange` | 30 / 8.0 | 5–600 / 1–32 | The claws' pace and reach from the body |
| `juggernautSpareAllies` | true | — | The claws, the shockwave and the beam spare pets, subordinates and teammates |
| `juggernautUpkeepPercent` | 3.0 | 0–100 | % of max magicules burned a second |
| `juggernautShpBurnPercent` / `juggernautShpFloorPercent` | 3.0 / 10 | 0–100 | Then % of max spiritual health a second, down to the floor, which ends it |
| `juggernautMaxSeconds` | 0 | 0–3600 | The longest a Drive lasts (0: no limit, it runs until you are spent; creative then stops at 4 minutes) |
| `juggernautAftermathSeconds` | 120 | 0–3600 | The debuffs and halved magicules and aura afterwards |
| `juggernautLockMinutes` | 10 | 0–600 | How long the gear stays silent |
| `juggernautLifespanPercent` / `lifespanFloorPercent` | 10 / 50 | 0–100 | Max health each Drive takes for good, and the debt it never passes |
| `smasherBaseDamage` | 40.0 | 0–1e6 | Longinus Smasher's damage before the Boost (× 2ⁿ) |
| `smasherChargeTicks` | 334 | 20–1200 | The charge (the two clips back to back) |
| `smasherRange` / `smasherRadius` | 64 / 5.0 | 8–256 / 0.5–16 | The beam (it bores a tunnel 0.8 of its radius) |
| `smasherCostPercent` | 10.0 | 0–100 | % of max magicules a shot costs (the rest burns spiritual health) |
| `juggernautArmor`, `juggernautToughness`, `juggernautKnockbackResistance`, `juggernautSpeed`, `juggernautStepHeight`, `juggernautJumpStrength`, `juggernautSafeFall`, `juggernautReach` | 10, 4, 0.5, 0.06, 1.5, 0.2, 20, 6 | — | What the dragon adds |
| `incantationLine1` … `incantationLine5` | the English lines | — | The accepted ways to type each line (edit or translate them) |

## `[divine_dividing]`

Divine Dividing, its white Scale Mail, and the Boosted Gear's Divide.

| Option | Default | Range | Meaning |
|---|---|---|---|
| `addDivineDividingToReincarnationPool` | true | — | Divine Dividing in the reincarnation roll |
| `divideReach` | 8.0 | 1–64 | How far the slash reaches |
| `divideRange` | 32.0 | 4–256 | How far the target can go before the chain breaks |
| `divideIntervalSeconds` | 10 | 1–600 | Between Divides; also the Divide mode's cooldown |
| `maxDivides` | 3 | 1–8 | The most Divides one target takes, over the mastery cap |
| `divideBossMaxDivides` | 2 | 0–8 | The most any boss takes |
| `divideEnergyPercent` | 50 | 0–100 | Share of current magicules and aura each Divide takes |
| `divideWeakenPercent` | 50 | 0–100 | Attack each Divide takes (compounding) |
| `dividedSeconds` | 30 | 1–3600 | How long the weakness and your bonus last after the last Divide |
| `absorbedPowerCapPercent` | 700 | 0–1000 | Your bonus never passes this share of your own attack (700: 8× in all) |
| `divideMasteryPoints` | 1 | 0–100 | Mastery per Divide |
| `divineFlight` / `divineFlightCostPercent` | true / 0.5 | — / 0–100 | The wings fly; % of max magicules a second in the air |
| `divineSprintFlightMultiplier` | 2.0 | 1–10 | How much faster sprint-flying on the wings is once mastered (grows with mastery) |
| `divideMaxEpRatio` | 10.0 | 0–1e6 | Divide fails on a target with more than this many times your max EP; 0 turns it off |
| `breakerDivideIntervalSeconds` | 5 | 1–600 | Between Divides in the white Scale Mail |
| `halfDimensionRadius` / `halfDimensionCooldownSeconds` | 12.0 / 60 | 1–64 / 0–3600 | Half Dimension's reach and cooldown |
| `compressionCooldownSeconds` | 60 | 0–3600 | Compression Divider's cooldown, once its target has all its Divides |
| `divineBreakerLongCooldownSeconds` | 150 | 0–3600 | The white Scale Mail's cooldown after a long wear (the red one's is `breakerLongCooldownSeconds`) |
| `breakerAbsorbedPowerCapPercent` | 1500 | 0–5000 | In the white Scale Mail your bonus never passes this share of your own attack (1500: ×16 in all) |
| `strainCapacityPercent` / `strainVentPercent` / `strainWarnPercent` | 200 / 4 / 75 | — | The gauge's size (% of max EP), what the wings vent a second (% of the gauge), Albion's warning |
| `boostedDivideLifePercent` | 2.0 | 0–50 | Max health each of the Boosted Gear's Divides takes (it grows back) |
| `boostedDivideRecoveryMinutes` | 10 | 1–1440 | Minutes of play for 1% of it to grow back |
| `boostedDivideCooldownSeconds` | 5 | 0–600 | Between the Boosted Gear's Divides |
| `dragonDivideRadius` / `dragonDivideDamagePercent` | 8.0 / 50 | 1–64 / 0–100 | With Albion's power, how close shots at the dragon are divided away, and the share of other damage that lands |

## `[white_dragon_emperor]`

The White Dragon Emperor boss and Albion's jewel.

| Option | Default | Range | Meaning |
|---|---|---|---|
| `emperorMaxHealth` | 3000 | 100–10000 | His health |
| `emperorHitCapPercent` | 10 | 1–100 | The most one hit counts, as a percent of his max health |
| `emperorAttackWings` / `emperorAttackScaleMail` / `emperorAttackBroken` | 40 / 60 / 30 | 0–1000 | His punch in each phase |
| `emperorArmorWings` / `emperorArmorScaleMail` | 20 / 50 | 0–100 | His armour (broken uses the wings') |
| `emperorOrbDamage` | 20 | 0–1000 | One orb of light |
| `emperorDivideCap` | 2 | 1–8 | His Divides on one target at a time |
| `emperorDivideSecondsWings` / `emperorDivideSecondsScaleMail` | 10 / 5 | 1–120 | Between his Divides |
| `emperorHalfDimensionSeconds` / `emperorCompressionSeconds` | 30 / 60 | 5–600 | Between his powers |
| `emperorFleeSeconds` / `emperorAloneSeconds` | 60 / 30 | 5–600 | Broken before he flees; alone before he fades |
| `emperorXp` | 1000 | 0–100000 | His kill's XP |
| `jewelChannelSeconds` / `jewelLingerSeconds` | 5 / 300 | 1–60 / 10–3600 | Holding use on the jewel; how long it stays after the fight |
| `altarNeedsEnderDragon` | true | — | The altar answers only after the Ender Dragon's death |
| `oneDivineDividingPerWorld` | true | — | Only one player may gain Divine Dividing |

## `[easter_eggs]`

| Option | Default | Range | Meaning |
|---|---|---|---|
| `easterEggs` | true | — | The two multiplayer easter eggs (each once per world) |

## `[penetrate]`

[Penetrate](../boosted-gear/penetrate.md).

| Option | Default | Range | Meaning |
|---|---|---|---|
| `penetrate` | true | — | Penetrate at all |
| `penetrateCostPercent` | 0.5 | 0–100 | % of max magicules a hit that breaks through costs |
| `penetrateResistanceLevel` | 2.0 | 0–3 | Tensura's resistance bypass level: 1 ignores Resistances and makes Nullifications act as Resistances, 2 ignores both |
| `penetrateBarrierLevel` | 1.5 | 0–3 | Tensura's barrier bypass level: 1 Multilayer Barrier and Full Counter, 1.5 Guardian, 1.75 Pride and Infinite Regeneration's death save, 2 Strengthen Body and shields, 3 Anti-Skill |

## `[devil]`

The [Devil race](../races/devil.md)'s powers. The races' own stats, EP ranges and requirements are in a separate file,
`config/dxdtensura/race/devil_config.toml`, which is read when the game starts (a change there needs a restart).

| Option | Default | Range | Meaning |
|---|---|---|---|
| `devilInRaceMenu` | true | — | Low-class Devil in Tensura's race menu (its starting, random and Reincarnation lists) |
| `devilFlightSpeed` | 0.8, 1.0, 1.2, 1.5, 2.0 | 0+ | Flight speed on the wings per class (Low to Satan), times creative flight |
| `devilNightBonusPercent` | 25 | 0–1000 | % more Demonic Power damage at night and in Hell |
| `devilNightRegenPercent` | 25 | 0–1000 | % faster magicule regeneration at night and in Hell |
| `devilSunSlowPercent` | 10 | 0–100 | % slower under the daytime sun (the class's attack bonus goes too) |
| `demonicPowerDamage` | 6, 12, 24, 48, 96 | 0+ | Demonic Power's damage per class |
| `demonicPowerCost` | 100, 400, 1800, 7500, 30000 | 0+ | Its magicule cost per class |
| `demonicPowerCooldownSeconds` | 1 | 0–3600 | Between shots |
| `magicCircleSeconds` | 3 | 0–60 | The circle's channel |
| `magicCircleCostPercent` | 10 | 0–100 | % of max magicules it costs, paid on arrival |
| `magicCircleCooldownSeconds` | 60 | 0–86400 | After arriving |
| `holyWaterDamage` | 8 | 0+ | Holy Water's holy damage at the centre of its splash (half at the edge) |

## Client settings

Each player also has a **client** config, `config/dxdtensura-client.toml`. You can edit it in game: Mods → Devil x
Slime → Config.

| Option | Default | Meaning |
|---|---|---|
| `ddraigLines` | `ALL` | How much of Ddraig you see: `ALL`, `IMPORTANT` (teaching, warnings and story lines) or `OFF` |
| `screenShake` | true | Shake the camera for the Explosion, the Scale Mail forming and a Dragon Shot landing close by |
| `gearEffects` | `ALL` | `ALL`; `MOMENTS` (no lingering auras or motes); or `OFF` (no effects, no light from the gear, no rage tint). Poses and sounds always play |
| `cutscenes` | true | Film Balance Breaker (both Scale Mails) and Juggernaut Drive forming: the full cutscene the first time, a short one after (the white Scale Mail plays its full one every time). Off, they form at once |
| `modelStyle` | `NEW` | `NEW` (the remodelled, outlined models) or `CLASSIC` (the blocky models from before); changes at once. The gauntlet's three forms, the Scale Mail, Juggernaut Drive's dragon and Ascalon's blade on the gauntlet and the Scale Mail (the sword itself, its relic and the skull keep their look). The first time you hold the Boosted Gear a screen asks which look you want, with a picture of each |
| `modelStyleAsked` | `false` | Whether that screen has been answered (any way out counts, keeping the current look); set it back to `false` to be asked again |
