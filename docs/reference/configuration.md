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
| `transferEfficiency` | 0.5 | 0–1 | How much of the Boost's extra power a Transfer gives: the receiver of n stacks hits for 1 + this × (2ⁿ − 1), or their own Boost if higher (1 is the whole ×2ⁿ) |
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
| `boostSpeedPerStackPercent` | 20.0 | 0–100 | Walking speed each held stack adds, in %, while the Explosion runs or the red Scale Mail is on (not in the dragon); in the Scale Mail the higher of this and the armour's own speed counts; 0 turns it off |
| `boostSpeedMaxPercent` | 100.0 | 0–500 | The most speed the Boost adds, in % (100: twice as fast, at 5 stacks) |
| `gauntletFireCutPercent` | 50.0 | 0–100 | With the gauntlet out, fire damage (burning, lava, campfires, magma blocks, fireballs, Tensura's flame types) is cut by this % |

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
| `redScaleMailDamageCutPercent` | 30.0 | 0–100 | The red Scale Mail (the Bargain's armour and the dragon too) cuts every hit by this %, after armour and Tensura's resistances; not `/kill` or the void |
| `scaleMailFireSpellCutPercent` | 50.0 | 0–100 | In the red Scale Mail vanilla fire does nothing and never sets you alight; Tensura's flame spells and skills are cut by this % |
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
| `scaleMailBoostPress` | true | — | Each press of the Boost mode in the red Scale Mail adds a stack at once, at the usual price, with no cooldown. The 10-second growth goes on either way. A rival fight keeps its own pace, and Juggernaut Drive's dragon has its own |
| `scaleMailPressFullEp` | 100000 | 0–1e12 | The max EP at which a press reaches every stack. Each halving below it is one stack fewer by press (50,000 EP reaches 5, 25,000 reaches 4), and the 10-second growth still takes anyone to their cap. 0: a press always reaches the cap |

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
| `smasherRange` / `smasherRadius` | 64 / 10.0 | 8–256 / 0.5–16 | The beam, both dragons' (it bores a tunnel 0.8 of its radius; its blast and the flash at the chest grow with it) |
| `smasherCostPercent` | 10.0 | 0–100 | % of max magicules a shot costs (the rest burns spiritual health) |
| `juggernautArmor`, `juggernautToughness`, `juggernautKnockbackResistance`, `juggernautSpeed`, `juggernautStepHeight`, `juggernautJumpStrength`, `juggernautSafeFall`, `juggernautReach` | 10, 4, 0.5, 0.06, 1.5, 0.2, 20, 6 | — | What the dragon adds |
| `juggernautWalkBreaksBlocks` | true | — | Both dragons break what would stop them as they walk or fly, with no drops; also needs `dragonShotBreaksBlocks` and the `mobGriefing` and `skillGriefing` rules on |
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
| `absorbedPowerCapPercent` | 700 | 0–1000 | Your bonus never passes this share of your own attack (700: ×8 in all) |
| `divideStrengthFloor` | false | — | If on, every Divide doubles your strength even on a weak target (×2, ×4, ×8), under the cap; off (the default since 0.1.72), you take only the attack the target lost |
| `divideMasteryPoints` | 1 | 0–100 | Mastery per Divide |
| `divineFlight` / `divineFlightCostPercent` | true / 0.5 | — / 0–100 | The wings fly; % of max magicules a second in the air |
| `divineSprintFlightMultiplier` | 2.0 | 1–10 | How much faster sprint-flying on the wings is once mastered (grows with mastery) |
| `divideMaxEpRatio` | 10.0 | 0–1e6 | Divide fails on a target with more than this many times your max EP; 0 turns it off |
| `breakerDivideIntervalSeconds` | 5 | 1–600 | Between Divides in the white Scale Mail |
| `halfDimensionRadius` / `halfDimensionCooldownSeconds` | 12.0 / 60 | 1–64 / 0–3600 | Half Dimension's reach and cooldown |
| `compressionCooldownSeconds` | 60 | 0–3600 | Compression Divider's cooldown |
| `compressionMasteryPercent` | 100 | 0–100 | The Divine Dividing mastery Compression Divider unlocks at (100: mastered) |
| `compressEnergyPercent` | 5 | 0–100 | The compress crushes magicules and aura to this % of max and holds them there while the target stays Divided |
| `compressExecutePercent` | 5 | 0–100 | A mob (not a player or a boss) at or under this % of its magicules and aura when compressed is crushed out of existence |
| `compressVanishEpPercent` | 70 | 0–100 | The compress also crushes out of existence a mob (not a player, a boss or Rias) whose max EP is at most this % of yours, however full it is; 0 turns this off |
| `whiteScaleMailDamageCutPercent` | 20.0 | 0–100 | The white Scale Mail (and the white dragon) cuts every hit by this %, after armour; not `/kill` or the void |
| `whiteScaleMailMagicCutPercent` | 50.0 | 0–100 | It cuts every magic hit by this % before armour; Penetrate breaks through |
| `whiteScaleMailProjectileCutPercent` | 50.0 | 0–100 | The same for every projectile; a hit that is both is cut once, by the larger |
| `divineBreakerLongCooldownSeconds` | 150 | 0–3600 | The white Scale Mail's cooldown after a long wear (the red one's is `breakerLongCooldownSeconds`) |
| `breakerAbsorbedPowerCapPercent` | 1500 | 0–5000 | In the white Scale Mail your bonus never passes this share of your own attack (1500: ×16 in all) |
| `strongEnemyEpPercent` | 75 | 0–1000 | With `divideStrengthFloor` on, in the white Scale Mail a target with at least this % of your max EP counts one Divide more for the doubling |
| `strainCapacityPercent` / `strainVentPercent` / `strainWarnPercent` | 200 / 4 / 75 | — | The gauge's size (% of max EP), what the wings vent a second (% of the gauge), Albion's warning |
| `boostedDivideLifePercent` | 2.0 | 0–50 | Max health each of the Boosted Gear's Divides takes (it grows back) |
| `boostedDivideRecoveryMinutes` | 10 | 1–1440 | Minutes of play for 1% of it to grow back |
| `boostedDivideCooldownSeconds` | 5 | 0–600 | Between the Boosted Gear's Divides |
| `dragonDivideRadius` / `dragonDivideDamagePercent` | 8.0 / 50 | 1–64 / 0–100 | With Albion's power, how close shots at the dragon are divided away, and the share of other damage that lands |
| `reduceSeconds` / `reduceCooldownSeconds` | 10 / 60 | 1–600 / 0–3600 | How long Reduce's poison lasts, and its cooldown |
| `reduceSpiritualPercent` | 2.0 | 0–100 | % of the target's max spiritual health Reduce takes each second, on top of your attack |
| `reflectWindowTicks` / `reflectCooldownSeconds` | 30 / 20 | 1–200 / 0–3600 | How long Reflect stays open (30 = 1.5 s), and its cooldown from the press |
| `rivalsUncapped` | true | — | In a fight between a Divine Dividing holder and a Boosted Gear holder, both caps lift |
| `rivalsSeconds` | 30 | 1–600 | How long a rival fight lasts after the last hit or Divide between the two |
| `rivalsCeiling` | 24 | 3–30 | In a rival fight, neither the Divides on the rival nor the rival's Boost stacks pass this |

## `[white_juggernaut]`

Divine Dividing's [Juggernaut Drive](../divine-dividing/juggernaut-drive.md) and Transfer overload. The white dragon
shares the red one's size, stats, fuel, berserk, aftermath and silence numbers in `[juggernaut]`, and the chant's radius.

| Option | Default | Range | Meaning |
|---|---|---|---|
| `whiteJuggernautEnabled` | true | — | Off removes Albion's offer, the white chant and the Drive |
| `whiteJuggernautMasteryPercent` | 100 | 0–100 | % of Divine Dividing's mastery for Albion to offer the words (the white Scale Mail awakened too) |
| `whiteIncantationLine1` … `5` | Vali's words | — | The accepted ways to type each line |
| `whiteDragonDivideIntervalTicks` | 50 | 5–1200 | Ticks between the chain's Divides in the dragon (2.5 s) |
| `whiteDragonExtraDivides` | 2 | 0–5 | Divides the dragon lands past your cap |
| `whiteDragonAbsorbedPowerCapPercent` | 3100 | 0–100000 | The dragon's strength cap, % of your own attack (3100: ×32 in all) |
| `whiteDragonHalfDimensionRadius` | 24.0 | 1–64 | Half Dimension's reach in the dragon, in blocks |
| `whiteDragonSprintFlightMultiplier` | 3.0 | 1–10 | How many times faster the dragon flies sprinting |
| `whiteSmasherMinPercent` | 50 | 1–100 | % of the strain gauge the white Smasher needs |
| `whiteSmasherChargeTicks` | 100 | 20–1200 | The white Smasher's charge (100 = 5 s) |
| `whiteSmasherBaseDamage` | 20.0 | 0–1e6 | The white Smasher's damage before the gauge's 2^(8 × fill) (half the red one's 40) |
| `transferOverloadPercent` | 1.0 | 0–100 | Transfer overload: % of the red holder's max EP poured in for each unit of 2ⁿ − 1 (0 turns it off) |

## `[white_dragon_emperor]`

The White Dragon Emperor boss and Albion's jewel.

| Option | Default | Range | Meaning |
|---|---|---|---|
| `emperorMaxHealth` | 3000 | 100–10000 | His health |
| `emperorHitCapPercent` | 5 | 1–100 | The most one hit counts, as a percent of his max health (5: 150 of 3,000) |
| `emperorAttackWings` / `emperorAttackScaleMail` / `emperorAttackBroken` | 40 / 60 / 30 | 0–1000 | His punch in each phase, at the least |
| `emperorArmorWings` / `emperorArmorScaleMail` | 20 / 50 | 0–100 | His armour (broken uses the wings') |
| `emperorOrbDamage` | 20 | 0–1000 | One orb of light, at the least |
| `emperorDivideCap` | 2 | 1–8 | His Divides on one target at a time |
| `emperorDivideSecondsWings` / `emperorDivideSecondsScaleMail` | 10 / 5 | 1–120 | Between his Divides |
| `emperorHalfDimensionSeconds` / `emperorCompressionSeconds` | 30 / 60 | 5–600 | Between his powers |
| `emperorFleeSeconds` / `emperorAloneSeconds` | 60 / 30 | 5–600 | Broken before he flees; alone before he fades |
| `emperorXp` | 1000 | 0–100000 | His kill's XP |
| `emperorPunchPercentWings` / `emperorPunchPercentScaleMail` / `emperorPunchPercentBroken` | 8 / 12 / 6 | 0–100 | His punch in each phase, as a % of the target's max health; never less than the flat punch |
| `emperorOrbPercent` | 4 | 0–100 | An orb, as a % of the target's max health; never less than `emperorOrbDamage` |
| `emperorVentPercent` | 10 | 0–100 | His vent's burst, as a % of each one's max health; never less than his attack |
| `emperorAbsorbedAttackPercent` / `emperorAbsorbedSpeedPercent` | 25 / 10 | 0–200 / 0–100 | His attack's and speed's rise for each Divide he holds, % |
| `emperorVentAt` / `emperorVentAtAlone` | 4 / 2 | 1–16 | Divides held at which he vents, against two or more players / one |
| `emperorVentRadius` | 8 | 1–32 | Blocks his vent's burst reaches |
| `emperorLightRainSeconds` | 20 | 5–600 | Between his Light Rains on the wings |
| `emperorReflectSeconds` / `emperorReflectWindowTicks` | 20 / 60 | 5–600 / 10–400 | Between his Reflects in the Scale Mail; how long one lasts, in ticks |
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
| `demonicBlastDamageMultiplier` | 1.5 | 0–100 | The [Demonic Blast](../races/devil.md#mastery-and-the-demonic-blast)'s damage, times the orb's as it fires (night and Bishop bonuses included) |
| `demonicBlastCostMultiplier` | 2.0 | 0–100 | Its magicule cost, times the class's orb cost |
| `demonicBlastRadius` | 2.0 | 0–16 | Blocks its explosion reaches; everyone there but what it struck, the Devil and their allies takes half its damage, less behind cover; no block breaks |
| `demonicBlastCooldownSeconds` | 3 | 0–3600 | Between Demonic Blasts |
| `magicCircleSeconds` | 3 | 0–60 | The circle's channel |
| `magicCircleCostPercent` | 10 | 0–100 | % of max magicules it costs, paid on arrival |
| `magicCircleCooldownSeconds` | 60 | 0–86400 | After arriving |
| `holyWaterDamage` | 8 | 0+ | Holy Water's holy damage at the centre of its splash (half at the edge) |

## `[houses]`

The [House powers](../races/houses.md) of pure-blooded Devils. Damage and cost go in orbs, multiples of the class's Demonic Power orb.

| Option | Default | Range | Meaning |
|---|---|---|---|
| `houseRollOdds` | 20, 30, 30, 10, 10 | 0+ | Each House's share of the birth roll: Bael, Phenex, Sitri, Leviathan, Gremory |
| `gremoryDamagePercent` | 15 | 0+ | How much harder House Gremory's Power of Destruction hits than House Bael's |
| `destructionScaleFloorPercent` | 10 | 0–10000 | How weak Destruction can get against someone with more EP, % |
| `destructionOrbDamage`, `destructionOrbCost` | 1.5, 2 | 0–10000 | The Destruction Orb, in orbs |
| `destructionOrbCooldown` | 2 | 0–3600 | The Destruction Orb's cooldown, seconds |
| `destructionBulletDamage`, `destructionBulletCost` | 0.4, 0.25 | 0–10000 | One Destruction Bullet, in orbs |
| `destructionGuardUpkeep`, `destructionGuardErase` | 0.1, 1 | 0–10000 | Destruction Guard each second and each thing it erases or hit it refuses, in orbs |
| `destructionGuardCooldown` | 3 | 0–3600 | Destruction Guard's cooldown after it ends, seconds |
| `starDamage`, `starCost` | 8, 10 | 0–10000 | Extinguished Star, in orbs |
| `starCooldown` | 60 | 0–3600 | Extinguished Star's cooldown, seconds |
| `starBurstRadius` | 6 | 0–10000 | How far its burst reaches, blocks |
| `starSpiritPercent` | 25 | 0–10000 | The share of its damage also taken from spirit health, % |
| `starVanishEpPercent` | 70 | 0–100 | It erases a mob at or under this % of the Devil's EP; 0 for never |
| `starCraterRadius` | 2.5 | 0–10000 | Its crater's radius, blocks; 0 for none |
| `ruinDamage`, `ruinCost` | 1, 20 | 0–10000 | One sphere's damage and the whole cast's cost, in orbs |
| `ruinSpheres` | 12 | 0–3600 | How many spheres fly |
| `ruinRange` | 32 | 0–10000 | How far it finds foes, blocks |
| `ruinCooldown` | 120 | 0–3600 | Its cooldown, seconds |
| `phenexRegenPercents` | 5, 5, 8, 10, 15 | list | Regeneration, % of max health a second, by class |
| `phenexRegenBarCostPercent` | 30 | 0–10000 | Healing a whole bar costs this % of max magicules, in proportion |
| `phenexRebirthPrices` | 30, 45, 60, 80 | list | A rebirth's price in % of max magicules, for each in a row; the last stays |
| `phenexRebirthResetMinutes` | 5 | 0–1440 | Quiet minutes that start the price over |
| `phenexRebirthOverwhelmTimes` | 10 | 0–10000 | An attacker with this many times your max EP kills for real |
| `phenexRebirthHealthPercent` | 50 | 0–10000 | A rebirth comes back at this % of max health |
| `phenexRebirthBurstDamage` | 2 | 0–10000 | The rebirth's burst, in orbs |
| `phenexShutSeconds` | 10 | 0–3600 | How long a holy hit stills the flames, seconds |
| `phenexWingsOutSeconds` | 5 | 0–3600 | How long the wings stay out, seconds |
| `phenexWingsColdHitPercent` | 10 | 0–10000 | A cold or water hit of this % of max health puts them out |
| `flameShotDamage`, `flameShotCost` | 1.2, 1.5 | 0–10000 | Flame Shot, in orbs |
| `flameShotCooldown` | 1 | 0–3600 | Its cooldown, seconds |
| `flameBurstDamage`, `flameBurstCost` | 2, 3 | 0–10000 | Flame Burst, in orbs |
| `flameBurstCooldown` | 8 | 0–3600 | Its cooldown, seconds |
| `phoenixTearCostPercent` | 30 | 0–10000 | Making a Phoenix Tear, % of max magicules |
| `phoenixTearCooldown` | 600 | 0–86400 | Its cooldown, seconds |
| `firestormDamage`, `firestormCost` | 3, 15 | 0–10000 | Firestorm's damage a second and its cost, in orbs |
| `firestormCooldown` | 60 | 0–3600 | Its cooldown, seconds |
| `sitriNearPercent`, `sitriNearBlocks` | 25, 8 | 0–100, 0–729 | House Sitri's near-water bonus, and how many water blocks within 4 blocks count as near |
| `waterHawkDamage`, `waterHawkCost`, `waterHawkCooldown` | 1.2, 1.5, 1 | 0–10000, 0–10000, 0–3600 | Water Hawk: orbs, orbs, seconds |
| `waterSerpentDamage`, `waterSerpentCost`, `waterSerpentCooldown` | 0.5, 3, 10 | 0–10000, 0–10000, 0–3600 | Water Serpent: orbs a second, orbs, seconds |
| `waterSerpentSeconds`, `waterSerpentBossSeconds` | 3, 1 | 0–600 | How long it holds someone, and a boss |
| `waterWallCost`, `waterWallCooldown`, `waterWallSeconds` | 2, 12, 8 | 0–10000, 0–3600, 0–600 | Water Wall: orbs, seconds, how long it stands |
| `waterLionDamage`, `waterLionCost`, `waterLionCooldown` | 2, 5, 15 | 0–10000, 0–10000, 0–3600 | Water Lions: each lion's orbs, orbs for all three, seconds |
| `waterDragonDamage`, `waterDragonCost`, `waterDragonCooldown` | 5, 8, 45 | 0–10000, 0–10000, 0–3600 | Water Dragon: orbs, orbs, seconds |
| `iceLanceDamage`, `iceLanceCost`, `iceLanceCooldown` | 1.5, 3, 20 | 0–10000, 0–10000, 0–3600 | Ice Lance: orbs, orbs, seconds |
| `iceLanceFrostSeconds`, `iceLanceFrostPlayerSeconds` | 3, 1.5 | 0–600 | Its Frost on a mob, and on a player |
| `celsiusDamage`, `celsiusCost`, `celsiusCooldown` | 4, 25, 120 | 0–10000, 0–10000, 0–3600 | Celsius Cross Trigger: orbs, orbs, seconds |
| `celsiusSeconds`, `celsiusRadius` | 8, 24 | 0–600, 0–256 | How long the frozen ground lasts, and how far it reaches |
| `celsiusFrostSeconds`, `celsiusFrostPlayerSeconds` | 6, 3 | 0–600 | Its Frost on a mob, and on a player |
| `leviathanMagiculePercent` | 25 | 0–1000 | House Leviathan's extra max magicules, percent |
| `leviathanSeaPercent`, `leviathanHellPercent` | 50, 30 | 0–1000, 0–100 | How much harder its powers hit in an ocean, and how much weaker in Hell |
| `crushingDamage`, `crushingCost`, `crushingCooldown` | 1.3, 1.5, 2 | 0–10000, 0–10000, 0–3600 | Crushing Depths: orbs, orbs, seconds |
| `crushingRange`, `crushingSeconds` | 24, 1 | 0–256, 0–600 | How far it reaches, and how long it presses |
| `surgeDamage`, `surgeCost`, `surgeCooldown` | 2, 3, 6 | 0–10000, 0–10000, 0–3600 | Surge: orbs, orbs, seconds |
| `seaCallCost`, `seaCallCooldown`, `seaCallSeconds` | 4, 60, 30 | 0–10000, 0–3600, 0–3600 | Call of the Sea: orbs, seconds, how long they attack |
| `seaCallSummons` | 4 | 0–32 | How many creatures a Call makes sure of: it brings the rest, half as many again at sea. 0 brings none |
| `floodDamage`, `floodSecondDamage`, `floodCost`, `floodCooldown` | 3, 1, 15, 60 | 0–10000, 0–10000, 0–10000, 0–3600 | The Flood: orbs at the first touch, orbs a second while carried, orbs, seconds |
| `seaDragonBite`, `seaDragonBreath` | 3, 6 | 0–10000 | The Sea Dragon's bite, and its Breath a second, in orbs |
| `seaDragonPricePercent`, `seaDragonSeaPricePercent` | 2, 1 | 0–100 | What the form costs a second, percent of max magicules, away from and at sea |
| `seaDragonDryCooldown`, `seaDragonEndCooldown` | 300, 60 | 0–86400 | Its cooldown after running dry, and after ending it yourself, seconds |

## `[peerage]`

[The Peerage](../races/peerage.md): the pieces' strengths, offers, Promotion and the calling circles. The circle's
channel is the Devil's `magicCircleSeconds`.

| Option | Default | Range | Meaning |
|---|---|---|---|
| `knightSpeedPercent` | 20 | 0–1000 | A Knight's (and the Queen's) extra movement speed, % |
| `knightAttackSpeed` | 0.3 | 0–100 | A Knight's (and the Queen's) extra attack speed |
| `bishopMagiculePercent` | 25 | 0–1000 | A Bishop's (and the Queen's) extra max magicules, % |
| `bishopRegenPercent` | 25 | 0–1000 | A Bishop's (and the Queen's) faster magicule regeneration, % |
| `bishopDemonicPowerPercent` | 25 | 0–1000 | A Bishop's (and the Queen's) stronger Demonic Power, %, added to the night's |
| `rookAttack` | 2 | 0–1000 | A Rook's (and the Queen's) extra attack, flat |
| `rookArmor` | 4 | 0–1000 | A Rook's (and the Queen's) extra armour |
| `rookToughness` | 2 | 0–1000 | A Rook's (and the Queen's) extra armour toughness |
| `rookKnockbackResistance` | 0.3 | 0–1 | A Rook's (and the Queen's) extra knockback resistance |
| `longinusMinimumWorth` | 8 | 1–8 | How many Pawns a Longinus holder takes (never anything else) |
| `offerSeconds` | 60 | 5–600 | How long a player has to answer an offer |
| `declineCooldownSeconds` | 30 | 0–86400 | Before the same King can offer again to a player who said no |
| `promotionWordMinutes` | 10 | 1–1440 | How long the King's word lets a Pawn promote anywhere |
| `promotionGraceSeconds` | 5 | 0–600 | How long a Promotion lasts after leaving enemy territory |
| `promotionCooldownSeconds` | 60 | 0–86400 | Before a Pawn can promote again |
| `queenDrainPercent` | 2 | 0–100 | % of max magicules Promotion to Queen costs, at once and then every `queenDrainSeconds`; 0 makes it free |
| `queenDrainSeconds` | 5 | 1–3600 | How often the Queen's cost is paid |
| `promotionDimensions` | the Nether, the End, `tensura:labyrinth`, `tensura:boss_area` | — | Enemy territory: these dimensions |
| `promotionStructures` | `dxdtensura:ascalon_church`, `dxdtensura:white_dragon_colosseum`, `dxdtensura:stray_mansion` | — | Enemy territory: standing inside these structures (an older file gets the mansion added once) |
| `callCostPercent` | 5 | 0–100 | % of the King's max magicules a call costs, paid on arrival |
| `callCooldownSeconds` | 30 | 0–86400 | Before the King can call the same servant again |
| `travelCostPercent` | 10 | 0–100 | % of a servant's max magicules going to their King costs, paid on arrival |
| `travelCooldownSeconds` | 60 | 0–86400 | Before a servant can go to their King again |
| `pawnGrowth` | true | — | A Longinus holder on several Pawns starts with few awake and [wakes the rest](../races/peerage.md#growing-into-your-pawns) as their base max EP grows. Off: they promote as any Pawn does |
| `pawnGrowthStartEp` | 5000 | 1–1e12 | Base max EP that wakes a holder's second Pawn; each doubling wakes one more |
| `pawnGrowthTopFactor` | 2.0 | 1–10 | What all of a holder's Pawns awake multiply a Promotion's strengths by |
| `pawnGrowthRookAt` | 3 | 1–8 | Pawns awake a holder on 8 Pawns needs for the Rook. Knight and Bishop open at 1 |
| `pawnGrowthQueenAt` | 5 | 1–8 | Pawns awake a holder on 8 Pawns needs for the Queen |
| `pawnGrowthTrueQueenAt` | 8 | 1–8 | Pawns awake a holder on 8 Pawns needs for the True Queen, on top of its mastery |
| `mutationPieces` | true | — | [Mutation Pieces](../races/peerage.md#mutation-pieces). Off: no rolls and no turns, and a Mutation Piece serves as an ordinary one; servants keep theirs |
| `mutationChancePercent` | 10 | 0–100 | The chance a new King's set holds a Mutation Piece, % |
| `mutationGrowthChancePercent` | 10 | 0–100 | The chance, at each doubling of the King's base max EP, that an unused piece turns, % |
| `mutationStrengthPercent` | 25 | 0–100 | How much stronger a Mutation servant's piece strengths are, % |

## `[promotion_forms]`

[Promotion's armour forms](../boosted-gear/promotion-forms.md), for a Boosted Gear Pawn in the Scale Mail.

| Option | Default | Range | Meaning |
|---|---|---|---|
| `knightSpeedPercent` | 100 | -100–1000 | The Knight's form: extra walking speed, % of the base. The Boost's speed adds to it. |
| `knightFlight` | 2.5 | 0.1–10 | The Knight's form: flight speed, times the Scale Mail's. |
| `knightArmor` | 8 | 0–100 | The Knight's form: armour, in place of the Scale Mail's. |
| `knightToughness` | 2 | 0–100 | The Knight's form: armour toughness, in place of the Scale Mail's. |
| `knightKnockback` | 0 | 0–1 | The Knight's form: knockback resistance, in place of the Scale Mail's. |
| `knightCutPercent` | 0 | 0–100 | The Knight's form: the flat cut on every hit, in place of the Scale Mail's. |
| `knightAttackSpeed` | 1 | 0–100 | The Knight's form: extra attack speed. |
| `knightUpkeepPercent` | 0.6 | 0–100 | The Knight's form: percent of max magicules a second. |
| `rookSpeedPercent` | -40 | -100–1000 | The Rook's form: walking speed, % of the base (negative is slower). It has neither the armour's nor the Boost's speed. |
| `rookFlight` | 0.6 | 0.1–10 | The Rook's form: flight speed, times the Scale Mail's. |
| `rookArmor` | 40 | 0–100 | The Rook's form: armour, in place of the Scale Mail's. |
| `rookToughness` | 16 | 0–100 | The Rook's form: armour toughness, in place of the Scale Mail's. |
| `rookKnockback` | 1 | 0–1 | The Rook's form: knockback resistance, in place of the Scale Mail's. |
| `rookCutPercent` | 50 | 0–100 | The Rook's form: the flat cut on every hit, in place of the Scale Mail's. |
| `rookAttack` | 8 | 0–1000 | The Rook's form: extra attack, flat (the Boost stays the only multiplier). |
| `rookUpkeepPercent` | 0.6 | 0–100 | The Rook's form: percent of max magicules a second. |
| `bishopUpkeepPercent` | 1.5 | 0–100 | The Bishop's form: percent of max magicules a second. Its other numbers are the Scale Mail's. |
| `trueQueenSpeedPercent` | 100 | -100–1000 | The True Queen: extra walking speed, % of the base. The Boost's speed adds to it. |
| `trueQueenFlight` | 2.5 | 0.1–10 | The True Queen: flight speed, times the Scale Mail's. |
| `trueQueenArmor` | 40 | 0–100 | The True Queen: armour, in place of the Scale Mail's. |
| `trueQueenToughness` | 16 | 0–100 | The True Queen: armour toughness, in place of the Scale Mail's. |
| `trueQueenKnockback` | 1 | 0–1 | The True Queen: knockback resistance, in place of the Scale Mail's. |
| `trueQueenCutPercent` | 50 | 0–100 | The True Queen: the flat cut on every hit, in place of the Scale Mail's. |
| `trueQueenAttack` | 8 | 0–1000 | The True Queen: extra attack, flat. |
| `trueQueenAttackSpeed` | 1 | 0–100 | The True Queen: extra attack speed. |
| `trueQueenUpkeepPercent` | 2.5 | 0–100 | The True Queen: percent of max magicules a second. It replaces the ordinary Queen's drain. |
| `formChangeSeconds` | 5 | 0–600 | Seconds between two changes of form, plain included. |
| `formMasteryMinutes` | 3 | 0–1000 | Minutes in each of the Knight, Rook and Bishop forms, counted across uses, before the True Queen opens. |
| `trueQueenEntryPercent` | 10 | 0–100 | Percent of max magicules paid to enter the True Queen. |
| `trueQueenWaitSeconds` | 300 | 0–86400 | Seconds before the True Queen opens again, however it ended. |
| `blasterBaseDamage` | 20 | 0–1.0e6 | The Dragon Blaster's damage at 0 stacks; times 2^stacks, once to each target. |
| `blasterChargeTicks` | 40 | 1–1200 | The Dragon Blaster's charge, in ticks. |
| `blasterRange` | 64 | 8–256 | The Dragon Blaster's beams' length, in blocks. |
| `blasterRadius` | 2 | 0.5–16 | Each Dragon Blaster beam's radius, in blocks. |
| `crimsonBlasterRadius` | 2.5 | 0.5–16 | Each Crimson Blaster beam's radius, in blocks. |
| `blasterCostPercent` | 10 | 0–100 | Percent of max magicules a Dragon Blaster or Crimson Blaster costs. |
| `blasterCooldownSeconds` | 10 | 0–3600 | The Dragon Blaster's and Crimson Blaster's cooldown, in seconds. |
| `crimsonBlasterFactor` | 1.5 | 0–100 | The Crimson Blaster's damage, times the Dragon Blaster's. |
| `solidImpactBaseDamage` | 12 | 0–1.0e6 | Solid Impact's damage at 0 stacks; times 2^stacks. |
| `solidImpactReach` | 5 | 1–32 | How far Solid Impact reaches, in blocks. |
| `solidImpactKnockback` | 3 | 0–20 | How hard Solid Impact throws its target. |
| `solidImpactBlastRadius` | 3 | 0–32 | Solid Impact's shockwave's radius, in blocks. |
| `solidImpactBlastPercent` | 50 | 0–100 | What the shockwave deals, percent of Solid Impact's damage. |
| `solidImpactCooldownSeconds` | 6 | 0–3600 | Solid Impact's cooldown, in seconds. |

## `[rias]`

[Rias Gremory](../races/rias.md), her flyer and her bat. Her building generates whatever these say.

| Option | Default | Range | Meaning |
|---|---|---|---|
| `enabled` | true | — | Rias appears, her bat comes and her flyer revives; off, none of them |
| `flyerRevive` | true | — | Dying with her flyer calls her to offer you a piece and a second life |
| `familiarFlyer` | true | — | Her bat brings each player a flyer on their first night in the Overworld |
| `riasEP` | 300000 | 1–1e12 | Her EP, which a player's worth is measured against |
| `rejoinWaitDays` | 10 | 0–3650 | In-game days someone who left her waits before she takes them back |
| `wordCooldownDays` | 1 | 0–3650 | In-game days between her words to one of her Pawns |
| `villageFlyerChance` | 0.05 | 0–1 | The chance a village house chest holds a flyer |

## `[stray]`

[Stray Devils](../world/stray-devils.md) and Rias's hunts. A Stray's piece changes its class's numbers: Knight +40%
speed and −25% health, Bishop −20% health, Rook −20% speed, +50% health, +6 armour and 0.6 knockback resistance.

| Option | Default | Range | Meaning |
|---|---|---|---|
| `enabled` | true | — | Off, no Strays come at night and the lairs stay dormant (the mansions still generate) |
| `nightSpawns` | true | — | Strays come up out of the dark at night near players in the overworld |
| `nightsBetweenStrays` | 2.5 | 0.1–1000 | On average one night Stray for each player every this many nights |
| `middleClassChance` | 0.15 | 0–1 | The chance a night Stray is Middle-class rather than Low-class |
| `lowHealth`, `lowAttack`, `lowArmor` | 40, 10, 6 | 1–1,000,000 | A Low-class Stray's stats |
| `middleHealth`, `middleAttack`, `middleArmor` | 100, 25, 12 | 1–1,000,000 | A Middle-class Stray's |
| `highHealth`, `highAttack`, `highArmor` | 300, 40, 16 | 1–1,000,000 | A High-class Stray's |
| `bossHealth`, `bossAttack`, `bossArmor` | 600, 45, 20 | 1–1,000,000 | A lair boss's |
| `jobs` | true | — | Rias sends her servants after Stray Devils every few days (off: no jobs, and none to give when asked) |
| `jobEveryDays` | 3 | 1–100 | In-game days from one of her jobs starting to the next |
| `jobLengthDays` | 2 | 1–100 | In-game days a job stays open before its Stray gets away |
| `jobHighClassEp` | 100000 | 0–10<sup>12</sup> | A servant with this much EP is sent after a High-class Stray, or to a lair in range |
| `jobLairRange` | 600 | 0–10,000 | How far, in blocks, she looks for a lair to send a strong servant to |
| `jobRewardEpPercent` | 10 | 0–100 | Her reward's extra EP, as a % of the Stray's EP |
| `riasArrives` | true | — | She comes herself to finish a job's target with the Power of Destruction (off: the reward comes through a small circle) |

## `[town]`

[The Castle Town of Gremory](../world/castle-town.md).

| Option | Default | Range | Meaning |
|---|---|---|---|
| `enabled` | true | — | Whether the town exists. Off, no town generates, no rule of its applies, its circle and tickets don't work, and Rias has no map to give. A town already generated stays standing |
| `protect` | true | — | Whether the town's blocks are protected: no breaking, placing, griefing or blocks lost to explosions, for anyone but creative players and operators |
| `citizens` | 24 | 0–64 | How many citizens walk the town while a player is near it. Each one killed leaves one fewer until the next in-game day |
| `guards` | 10 | 0–12 | How many guards keep the town: the 4 gate posts first, then 3 on the wall, then the Avenue. An alarm calls more, up to 12 |
| `guardEp` | 150000 | 1–1e9 | A guard's EP |
| `guardHealth` | 120 | 1–1e6 | A guard's health |
| `guardAttack` | 14 | 0–1e6 | A guard's attack damage. Their Demonic Power orb does three quarters of it |
| `guardArmor` | 10 | 0–30 | A guard's armour |
| `wantedDays` | 1 | 1–100 | How many in-game days outside the town's square end Wanted. Coming back before that starts the count again |
| `wantedFineGold` | 1 | 0–64 | How many gold coins the Clerk takes to end Wanted |
| `devilDiscountPercent` | 10 | 0–25 | How much less a Devil pays at the stalls, %. It adds to a title's cut, and the two never come to more than 25% |
| `phoenixTearsInMarket` | true | — | Whether the Apothecary sells Phoenix Tears. Off, only a Phenex player can supply them, by trading or chests |
| `phoenixTearGold` | 16 | 1–64 | What a Phoenix Tear costs at the Apothecary, in gold coins. Friend of House Gremory and up, one a day |
| `innRoomGold` | 1 | 0–64 | What a room at the inn costs, in gold coins, once. A Devil's is free |
| `bountyEpPercent` | 5.0 | 0–100 | How much of a target's EP a kill off the bounty board gives, %, shared between aura and magicules. Half of Rias's by default |
| `hunters` | true | — | Whether hunter parties come for a player marked a Stray Devil |
| `hunterEveryDays` | 3 | 1–100 | How many in-game days pass between hunter parties, plus 0 to 2 at random |

## `[angel]`

The [Angels' and Fallen Angels'](../races/angels.md) powers. The races' own stats, EP ranges and requirements are in
`config/dxdtensura/race/angel_config.toml` and `fallen_angel_config.toml`, which are read when the game starts (a change
there needs a restart). The lists by rank go Low, Middle, High, then rank 4 and rank 5.

| Option | Default | Range | Meaning |
|---|---|---|---|
| `angelInRaceMenu` / `fallenAngelInRaceMenu` | true / true | — | Low-class Angel and Low-class Fallen Angel in Tensura's race menu (its starting, random and Reincarnation lists) |
| `angelFlightSpeed` / `fallenAngelFlightSpeed` | 0.8, 1.0, 1.2, 1.5, 2.0 | 0+ | Flight speed on the wings per rank, times creative flight |
| `lightSpearDamage` | 6, 12, 24, 48, 96 | 0+ | Light Spear's damage per rank (a hybrid's by Devil class); the Boost never multiplies it |
| `lightSpearCost` | 100, 400, 1800, 7500, 30000 | 0+ | Its magicule cost per rank (also the Great Spear's at its shortest charge) |
| `lightSpearCooldownSeconds` | 1 | 0–3600 | Between Light Spears |
| `holyBurnSeconds` | 2 | 0–60 | Seconds of Tensura's Holy Damage the races' light leaves on what holy things hurt |
| `holyBurnAmplifier` | 0, 0, 0, 1, 2 | 0+ | The burn's strength per rank (0: 2 damage every 5 ticks, 1: 4, 2: 6) |
| `blessingHeal` / `blessingCost` | 4 … 64 / 300 … 90000 | 0+ | Health Blessing heals, and its magicule cost, per Angel rank |
| `blessingRadius` / `blessingCooldownSeconds` | 8.0 / 20 | 0–64 / 0–3600 | Blessing's reach and cooldown |
| `greatSpearFullDamage` / `greatSpearFullCost` | 24 … 384 / 500 … 150000 | 0+ | The Great Spear's damage and magicule cost at full charge, per Fallen Angel rank |
| `greatSpearMinSeconds` / `greatSpearFullSeconds` | 0.5 / 3.0 | 0–60 | The shortest hold that throws, and the hold for a full charge |
| `greatSpearRadius` / `greatSpearCooldownSeconds` | 4.0 / 10 | 0–32 / 0–3600 | The burst's reach, and the cooldown |
| `holyBarrierChancePercent` | 10 | 0–100 | % chance of being born with Holy Barrier, rolled once per player the first time they become an Angel |
| `holyBarrierRadius` / `holyBarrierSeconds` | 4.0 / 10 | 0–32 / 0–3600 | The dome's radius and how long it lasts |
| `holyBarrierCostPercent` / `holyBarrierCooldownSeconds` | 10.0 / 60 | 0–100 / 0–86400 | % of max magicules it costs, and the wait after it ends |
| `holyLightningChancePercent` | 10 | 0–100 | % chance of being born with Holy Lightning, rolled once per player the first time they become a Fallen Angel |
| `holyLightningDamage` / `holyLightningCost` | 12 … 192 / 200 … 60000 | 0+ | Holy Lightning's holy damage and magicule cost per rank |
| `holyLightningRange` / `holyLightningRadius` | 32.0 / 2.0 | 0–128 / 0–16 | How far it reaches, and how far around the strike it hits |
| `holyLightningCooldownSeconds` | 5 | 0–3600 | Between strikes |
| `holyLightningWeakDamagePercent` / `holyLightningWeakCostPercent` | 50 / 20 | 0+ | Decreased Power, % of the strike's damage and cost |
| `holyLightningWeakRadius` / `holyLightningWeakCooldownSeconds` | 1.25 / 3 | 0–16 / 0–3600 | Its radius and cooldown |
| `holyLightningStrongDamagePercent` / `holyLightningStrongCostPercent` | 300 / 200 | 0+ | Increased Power, likewise (the cost also prices a try at learning the storm) |
| `holyLightningStrongRadius` / `holyLightningStrongCooldownSeconds` | 3 / 7 | 0–16 / 0–3600 | Its radius and cooldown |
| `holyLightningBlastDamagePercent` / `holyLightningBlastCostPercent` | 50 / 20 | 0+ | The Blast: % of the strike's damage a hit, % of its cost a second |
| `holyLightningBlastRange` | 30 | 0–128 | The beam's reach |
| `holyLightningStormDamagePercent` / `holyLightningStormCostPercent` | 200 / 1000 | 0+ | The storm: % of the strike's damage a bolt, % of its cost once |
| `holyLightningStormWaves` | 30 | 1–720 | Its waves, one every 5 s |
| `holyLightningStormRadius` | 30 | 0–64 | Blocks round you it strikes |
| `holyLightningStormGroundBolts` | 10 | 0–50 | The most bolts a wave drops on random ground |
| `hybridHolyLightningRoll` | true | — | A Fallen Angel reborn as a hybrid has one more try at Holy Lightning |
| `angelDayBonusPercent` / `angelDayRegenPercent` | 25 / 25 | 0–1000 | Heaven's Grace: % more Light Spear damage and % faster magicules under the open daytime sky |
| `angelHellSlowPercent` | 10 | 0–100 | Hell's Weight: % slower in Hell |
| `sinInnocent` / `sinGuardian` / `sinPet` / `sinPlayer` / `sinDeadlySkill` | 20 / 10 / 20 / 40 / 60 | 0–100 | Sin for killing a villager or trader, a golem, a pet or subordinate, a player who hadn't hurt the Angel, and for learning a Deadly Sin skill (100 makes an Angel fall) |
| `sinPlayerGraceSeconds` | 30 | 0–3600 | How long a hit is remembered: a player who hurt the Angel within it is fair game, isn't blessed, and is pushed out of Holy Barrier |
| `sinFadePerDay` | 10 | 0–100 | Sin that fades each in-game day |
| `sinWarning` | 50 | 0–100 | Sin at which the wings start to flicker black and the warning shows |

## `[light_weapons]`

[Light weapons](../races/light-weapons.md), for Angels and Fallen Angels. Lists are per rank, Low first.

| Option | Default | Range | Meaning |
|---|---|---|---|
| `lightSwordAttack` | 4, 8, 16, 32, 64 | 0 or more | The Light Sword's attack, added to the holder's own |
| `lightSwordCost` | 25, 100, 450, 1875, 7500 | 0 or more | Magicules for a sword hit that lands |
| `lightGuardCost` | 25, 100, 450, 1875, 7500 | 0 or more | Magicules for a blow the guard blocks |
| `lightBowDamage` | 4.5, 9, 18, 36, 72 | 0 or more | A shot's damage at full draw |
| `lightBowCost` | 50, 200, 900, 3750, 15000 | 0 or more | Magicules for a shot at full draw |
| `lightHeldSpearAttack` | 3, 6, 12, 24, 48 | 0 or more | A held Light Spear's attack |
| `lightHeldSpearCost` | 20, 80, 360, 1500, 6000 | 0 or more | Magicules for a held spear's hit that lands |
| `lightBowMinDrawTicks` | 5 | 1–20 | The shortest draw that shoots |
| `lightArrowRange` | 96 | 8–512 | How far a bolt flies, in blocks |
| `lightWeaponCooldownSeconds` | 1 | 0–3600 | A mode's cooldown after forming a weapon |
| `lightWeaponMasteryGapTicks` | 20 | 0–1200 | The least ticks between two hits that earn mastery |

## `[twilight]`

[Twilight Healing](../twilight-healing/index.md). Each pair grows in a straight line from a new holder's value to the
mastered one.

| Option | Default | Range | Meaning |
|---|---|---|---|
| `addTwilightHealingToReincarnationPool` | true | — | Add Twilight Healing to (true) or remove it from (false) Tensura's `startingSkills` at start-up (the only way to get it) |
| `touchReach` | 4.0 | 1–16 | How far, in blocks, Touch reaches to the one under the crosshair |
| `touchRateNew` / `touchRateMastered` | 0.20 / 0.50 | 0–1 | Touch's heal a second, as a share of the healed one's max health |
| `arrowHealNew` / `arrowHealMastered` | 0.15 / 0.30 | 0–1 | A fully drawn Healing Arrow's heal, as a share of max health |
| `arrowDrawSeconds` | 1.0 | 0.05–10 | Seconds to draw the bow fully |
| `arrowRange` | 48 | 1–256 | How far, in blocks, an arrow flies before it fades |
| `fieldRateNew` / `fieldRateMastered` | 0.05 / 0.10 | 0–1 | The Healing Field's heal a second, as a share of max health |
| `fieldRadiusNew` / `fieldRadiusMastered` | 8.0 / 12.0 | 1–64 | The Field's radius in blocks |
| `fieldSeconds` | 10 | 1–600 | How long the Field stays open |
| `fieldCooldownSeconds` | 30 | 0–3600 | The Field's cooldown after it closes |
| `barPercentNew` / `barPercentMastered` | 20 / 10 | 0–100 | The % of the healer's max magicules a target's whole health bar costs (a part of a bar costs that part) |
| `arrowsAtMastery` / `fieldAtMastery` | 0.40 / 0.70 | 0–1 | The mastery share at which Healing Arrows and the Field open |
| `masteryPerBar` | 5.0 | 0–1000 | Mastery points for each full health bar restored to someone else, before Tensura's gain and `masteryGainMultiplier` |
| `selfMasteryShare` | 0.25 | 0–1 | The share of that a holder earns healing themselves |

## `[sword_birth]`

[Sword Birth](../sword-birth/index.md). Each pair grows in a straight line from a new holder's value to the mastered one.

| Option | Default | Range | Meaning |
|---|---|---|---|
| `addSwordBirthToReincarnationPool` | true | — | Add Sword Birth to (true) or remove it from (false) Tensura's `startingSkills` at start-up (the only way to get it) |
| `epShare` | 1.0 | 0–10 | A sword opens at this share of its own EP in Tensura's data, compared with the holder's max EP |
| `lifeSecondsNew` / `lifeSecondsMastered` | 60 / 180 | 1–3600 | How long a copy lasts, in seconds |
| `maxCopies` | 2 | 1–36 | How many copies a holder can have at once; one more makes the oldest fade |
| `maxAttack` | 30 | 0–10000 | The most attack a copy or a blade takes from its sword; weaker swords keep their own |
| `priceFloorPercent` / `priceTopPercent` | 1 / 10 | 0–100 | % of max magicules a sword with no EP, and a sword at the holder's own EP, costs |
| `priceMasteredCut` | 0.5 | 0–1 | How much of the price full mastery takes off |
| `elementsAtMastery` / `lineAtMastery` / `ringAtMastery` | 0.50 / 0.40 / 0.70 | 0–1 | The mastery share at which the elements, Blade Line and Blade Ring open |
| `flameSeconds` / `flameBonus` | 5 / 0.20 | 0–600 / 0–10 | How long Flame sets a target alight, and the share of a hit it adds on anything not fire-immune |
| `frostSeconds` / `frostBonus` | 3 / 0.10 | 0–600 / 0–10 | How long Frost chills a target, and the share of a hit it adds on anything that can freeze |
| `lightEatingBonus` | 0.50 | 0–10 | The share of a hit Light-Eating adds on a holy foe |
| `lineLengthNew` / `lineLengthMastered` | 12 / 20 | 1–128 | Blade Line's length, in blocks |
| `lineShareNew` / `lineShareMastered` | 0.60 / 1.00 | 0–100 | Blade Line's hit, as a share of the holder's attack with the chosen sword |
| `linePriceTimes` / `lineCooldownSeconds` | 2 / 6 | 0–100 / 0–3600 | Blade Line's price, in times the chosen sword's, and its cooldown in seconds |
| `ringRadiusNew` / `ringRadiusMastered` | 5 / 8 | 1–64 | Blade Ring's radius, in blocks |
| `ringShareNew` / `ringShareMastered` | 0.50 / 0.80 | 0–100 | Blade Ring's hit, as a share of the holder's attack with the chosen sword |
| `ringPriceTimes` / `ringCooldownSeconds` | 3 / 12 | 0–100 / 0–3600 | Blade Ring's price, in times the chosen sword's, and its cooldown in seconds |


[Sword of Betrayer](../sword-birth/sword-of-betrayer.md):

| Option | Default | Range | Meaning |
|---|---|---|---|
| `betrayerEnabled` | true | — | Sword of Betrayer, Sword Birth's Balance Breaker. Off: nobody awakens it and the state can't start. |
| `betrayerAwakenMastery` | 0.40 | 0–1 | Sword Birth's mastery (a share of full) from which Sword of Betrayer can awaken, by every route. |
| `betrayerFromCrystal` | true | — | A Holy Factor Crystal awakens Sword of Betrayer in a holder who qualifies (no factor, no burn). |
| `betrayerFromFreed` | true | — | Helping beat Freed Sellzen awakens Sword of Betrayer in every holder who qualifies. |
| `holyDemonicAttackBonus` | 20 | 0–10,000 | The attack a holy-demonic copy adds to its sword's. |
| `holyDemonicMaxAttack` | 50 | 0–10,000 | The most attack a holy-demonic copy or blade has (maxAttack for the others). |
| `betrayerSwordAttack` | 50 | 0–10,000 | The Sword of Betrayer's own attack, the sword in hand for the state (Noroi's number). |
| `betrayerHolyShare` | 0.5 | 0–10 | A holy-demonic hit's extra share on what holy things hurt (Devils, the undead, Strays). |
| `betrayerDemonicShare` | 0.5 | 0–10 | A holy-demonic hit's extra share on a holy foe (Angels, Brave Saints, holy wielders). A target that is both takes the larger once. |
| `betrayerPriceShare` | 0.5 | 0–1 | In Sword of Betrayer every price is this share of the usual. |
| `betrayerReachTimes` | 1.5 | 1–4 | In Sword of Betrayer Blade Line and Blade Ring reach this many times as far. |
| `wallRadius` | 3 | 1–8 | Sword Wall's radius, in blocks. |
| `wallSecondsNew` | 6 | 1–120 | How long Sword Wall stands at no mastery, in seconds. |
| `wallSecondsMastered` | 10 | 1–120 | How long Sword Wall stands at full mastery, in seconds. |
| `wallStrengthNew` | 200 | 0–10,000 | What Sword Wall takes before it breaks at no mastery, % of the holder's max health. |
| `wallStrengthMastered` | 400 | 0–10,000 | What Sword Wall takes before it breaks at full mastery, % of the holder's max health. |
| `wallShare` | 0.5 | 0–10 | Sword Wall's rising blades hit for this share of the holy-demonic attack. |
| `wallPriceTimes` | 3 | 0–100 | Sword Wall costs this many times the chosen sword's price (halved in the state). |
| `wallCooldownSeconds` | 20 | 0–3600 | Sword Wall's cooldown, in seconds. |
| `absorbHolyPercent` | 50 | 0–100 | Holy Absorption: the % of holy damage taken in Sword of Betrayer that the swords eat. |
| `absorbCapPercent` | 100 | 0–10,000 | Holy Absorption's store holds at most this % of the holder's max health. |
| `betrayerLongCooldownSeconds` | 150 | 0–86,400 | Sword of Betrayer's cooldown after its time runs out, or after an end by choice past breakerShortEndSeconds, in seconds. |

## `[balor_view]`

[Forbidden Balor View](../balor-view/index.md). Lore mode's factor is `balorTimeFactor` in [`[lore_mode]`](#lore_mode).

| Option | Default | Range | Meaning |
|---|---|---|---|
| `addBalorViewToReincarnationPool` | true | — | Add Forbidden Balor View to (true) or remove it from (false) Tensura's `startingSkills` at start-up (the only way to get it) |
| `timeNewSeconds` / `timeMasteredSeconds` | 2 / 6 | 0.1–600 | How long a stop lasts at no mastery and at full mastery, on a target no stronger than the holder |
| `noStopRatio` | 5 | 1–1,000,000 | A target with this many times the holder's max EP or more can't be stopped; below it the time shrinks in proportion |
| `playerMaxSeconds` | 3 | 0.1–60 | The longest a player is stopped, Lore mode included |
| `eyeRange` / `viewRange` | 32 / 24 | 1–256 | Evil Eye's and Forbidden View's reach, in blocks |
| `viewHalfAngle` | 45 | 1–90 | Forbidden View's cone, as half its width in degrees |
| `worldRadius` | 20 | 1–128 | Stop the World's radius, in blocks |
| `vampireWorldRadius` | 30 | 1–128 | Stop the World's radius for the Vampire line, in blocks |
| `maxTargets` | 128 | 1–1024 | The most targets one stop catches, nearest first |
| `eyePricePercent` / `viewPricePercent` / `worldPricePercent` | 5 / 15 / 30 | 0–100 | % of max magicules each mode costs, up front |
| `eyeCooldownSeconds` / `viewCooldownSeconds` / `worldCooldownSeconds` | 30 / 60 / 120 | 0–3600 | Each mode's cooldown at no mastery |
| `masteredCooldownCut` | 0.5 | 0–1 | How much of every cooldown full mastery takes off |
| `viewAtMastery` / `worldAtMastery` | 0.40 / 0.70 | 0–1 | The mastery share at which Forbidden View and Stop the World open |
| `misfireBelowMastery` | 0.40 | 0–1 | A misfire can happen under this mastery share; 0 turns misfires off |
| `misfireHealthShare` | 0.30 | 0–1 | The share of max health a hit must take the holder from above to below to set it off |
| `misfireGapSeconds` | 60 | 0–3600 | The least time between two misfires |
| `heldKnockbackCap` | 2.5 | 0.1–10 | The most a stopped target is thrown sideways when its stop ends, in blocks a tick |
| `restShare` | 1.0 | 0–10 | How long a target rests after a stop, as a share of how long it was stopped; no press or misfire catches it then. 0 turns it off for mobs |
| `restPlayerSeconds` | 3 | 0–600 | The least a player rests after a stop, in seconds |

## `[sacred_gears]`

| Option | Default | Range | Meaning |
|---|---|---|---|
| `humanOnly` | true | — | [Sacred Gears are born only in humans](../getting-started/first-gear.md#only-in-humans): the reincarnation roll gives a gear only to a race in the `dxdtensura:sacred_gear_hosts` tag (the Human line), Tensura's race menu takes a gear from a holder reborn as another race (with a new unique instead), and Albion's jewel grants Divine Dividing only to a human. Off, every race can roll one again |

## `[race_mastery]`

Mastery for the races' skills: Heaven's Light, Fallen Light, Fallen Blood and Demonic Power, out of 1,000.

| Option | Default | Range | Meaning |
|---|---|---|---|
| `raceMasteryPerUse` | 2.0 | 0–1000 | Mastery (times Tensura's per-use gain) for each use that hits a living thing or heals someone |
| `raceMasteredCostPercent` | 50.0 | 0–100 | At full mastery the powers cost this % of their usual: the Light Spear, the Great Spear's whole charge, Blessing and the Demonic Power orb (never the Demonic Blast) |
| `raceMasteredDamagePercent` | 125.0 | 0–1000 | At full mastery the same powers deal (or heal) this % of their usual, on top of Heaven's Grace and Devil's Night |

## `[brave_saints]`

The [Brave Saints](../races/brave-saints.md). The calling circle's charge time is the Devil's `magicCircleSeconds`, and
every lower card gives its share of the Ace's numbers by place (the 7 half).

| Option | Default | Range | Meaning |
|---|---|---|---|
| `aceAttack` | 3.0 | 0–1000 | The Ace's extra attack, flat |
| `aceArmor` | 4.0 | 0–1000 | The Ace's extra armour |
| `aceHealth` | 8.0 | 0–1000 | The Ace's extra max health |
| `aceMagiculePercent` | 25 | 0–1000 | The Ace's extra max magicules, % |
| `aceRegenPercent` | 25 | 0–1000 | The Ace's faster magicule regeneration, % |
| `aceLightSpearPercent` | 25 | 0–1000 | The Ace's stronger Light Spear, %, added to Heaven's Grace by day and a Blackjack's |
| `longinusLowestCard` | 11 | 1–12 | The lowest card a Longinus holder takes, by place (11 is the Queen) |
| `offerSeconds` | 60 | 5–600 | How long a player has to answer a card |
| `declineCooldownSeconds` | 30 | 0–3600 | Before the same Seraph can offer again to a player who said no |
| `handRange` | 16 | 1–128 | Blocks round the presser within which cards join a hand |
| `handSeconds` | 30 | 1–3600 | How long a hand's power lasts |
| `handWaitSeconds` | 120 | 0–86400 | From a press until the hand's cards join another, in either game |
| `sameSuitPercent` | 150 | 100–1000 | A hand in one suit gives this % of its numbers (a Pair, Two Pair, Three or Four of a Kind, a Full House, a Blackjack's attack) |
| `judgementRange` | 24 | 1–128 | Blocks round the presser that Heaven's Judgement reaches |
| `judgementLightSpearMultiple` | 2.0 | 0–100 | Heaven's Judgement's damage, in Light Spears at the Seraph's rank |
| `callCostPercent` | 5 | 0–100 | % of the Seraph's max magicules a call costs, paid on arrival |
| `callCooldownSeconds` | 30 | 0–3600 | Before the Seraph can call the same holder again |
| `travelCostPercent` | 10 | 0–100 | % of a holder's max magicules going to their Seraph costs, paid on arrival |
| `travelCooldownSeconds` | 60 | 0–3600 | Before a holder can go to their Seraph again |
| `joker` | true | — | [The Joker](../races/brave-saints.md#the-joker): a 13th card in every deck, wild in hands. Off: it's out of every pick and hand; holders keep it |
| `jokerAcePercent` | 125 | 100–300 | The Joker's bonus against the Ace's, % |

## `[durandal]`

[Durandal and the Holy Factor](../durandal/index.md).

| Option | Default | Range | Meaning |
|---|---|---|---|
| `holyFactorBirthChancePercent` | 5 | 0–100 | % chance of being born with the Holy Factor, rolled once per player |
| `waveCostPercent` | 4.0 | 0–100 | % of max magicules a full Holy Wave costs (the shortest charge 60% of it), times up to 2 while wild |
| `waveCooldownSeconds` | 3 | 0–3600 | Seconds between Holy Waves |
| `waveRange` | 20.0 | 1–128 | Blocks a Holy Wave flies |
| `waveBreaksBlocks` | false | — | Whether a Holy Wave breaks the soft blocks in its way and digs the line it runs along (hardness 1.5 or less, no block entities, with `mobGriefing` on) |
| `tamedAttack` | 70.0 | 0–10000 | Durandal's attack, two-handed, at 1,000 mastery (it starts at 23) |
| `replicaTamedAttack` | 37.0 | 0–10000 | A replica's attack at 1,000 mastery; in Lore mode it gains `replicaPower`'s share of the true sword's growth instead |
| `holyStrikePercent` | 50 | 0–1000 | Durandal's holy strike, % of the hit, on what holy things hurt and Stray Devils |
| `wildSplashPercent` | 6.0 | 0–100 | % of max health a wave splashes its wielder for while the aura is wholly wild (never below half) |
| `masteryPerWave` | 4 | 0–1000 | Durandal mastery (out of 1,000) a wave earns when it hits a foe |
| `masteryPerHit` | 1 | 0–1000 | Durandal mastery a melee hit earns, once a second at most |
| `devilBurnPercent` | 0 | 0–100 | % of max health a second Durandal burns a wielder whom holy things hurt, a Devil with the Holy Factor (0, the default since 0.2.81, is no burn; Lore mode turns it off whatever this says) |
| `devilBurnFloorPercent` | 50 | 0–100 | The burn never takes them below this % of max health |
| `refusalDamage` | 2.0 | 0–100 | Damage Durandal deals someone who isn't a holy wielder taking it in hand (never below one heart) |
| `tamedCuts` | true | — | Whether a fully tamed Durandal cuts through Resistances, Nullifications and barriers up to Guardian (Penetrate's level settings set how far) |
| `tamedCutCostPercent` | 0.5 | 0–100 | % of max magicules a tamed cut costs when it meets one of those defences, once a tick at most |

## `[nekomata]`

The [Nekomata and Nekoshou](../races/nekomata.md). Each list goes by rank: Low, Middle, High, Elder, Daiyoukai, or a hybrid's Devil class.
The races' own stats, EP ranges and requirements are in `config/dxdtensura/race/nekomata_config.toml` and `nekoshou_config.toml`.

| Option | Default | Range | Meaning |
|---|---|---|---|
| `nekomataInRaceMenu` | true | — | Low-class Nekomata in Tensura's race menu (its starting, random and Reincarnation lists) |
| `nekoshouChancePercent` | 10 | 0–100 | The chance a player becoming a Nekomata is born a Nekoshou; one roll per player |
| `catSpeedPercent` | 10, 12, 15, 20, 25 | list | Cat form's extra speed, % |
| `catJumpBlocks` | 2, 2, 2.5, 3, 4 | list | How high a cat jumps in cat form, blocks |
| `catAirSteps` | 1, 1, 2, 4, 6 | list | Air steps, back on landing |
| `catKeepsCreepersAway` | true | — | Creepers and phantoms keep away from anyone with ears and tails out |
| `toukiHandDamage` | 4, 8, 16, 32, 64 | list | Touki's extra damage on a bare-handed hit |
| `toukiSpiritDamage` | 1, 2, 4, 8, 16 | list | Its spirit damage |
| `toukiCutPercent` | 10, 12, 15, 20, 25 | list | How much less damage the holder takes, % |
| `toukiSpeedPercent` | 5.0 | 0–100 | Touki's extra speed, % |
| `toukiUpkeepPercent` | 1.0 | 0–100 | % of max aura a second |
| `toukiStartPercent` | 5.0 | 0–100 | It won't start under this % of max aura |
| `toukiCooldownSeconds` | 5 | 0–3600 | Its cooldown after it ends |
| `toukiBlockadeSeconds` | 3 | 0–3600 | Tensura's Energy Blockade on a target hit bare-handed |
| `kiBulletDamage` | 6, 12, 24, 48, 96 | list | Ki Bullet's damage |
| `kiBulletCost` | 100, 400, 1800, 7500, 30000 | list | Its aura cost |
| `kiBulletSpiritPercent` | 25.0 | 0–1000 | Its spirit damage, % of its damage |
| `kiBulletCooldownSeconds` | 1 | 0–3600 | Its cooldown |
| `kiHealBarSeconds` | 10 | 1–3600 | Ki Healing: seconds held to restore a whole bar |
| `kiHealBarPercent` / `kiHealMasteredPercent` | 30.0 / 15.0 | 0–100 | % of max aura for a whole bar restored, and the same at full mastery |
| `kiHealCooldownSeconds` | 3 | 0–3600 | Its cooldown after it ends |
| `kiLifeDrivePoints` / `kiLifeDividePoints` | 1.0 / 2.0 | 0–100 | A Nekoshou's payback: points of the Drive's life debt, and of the Divides' |
| `kiLifeMinutes` | 20 | 0–10080 | How long a Nekoshou waits between paybacks, minutes |
| `auraSenseRadius` | 16, 24, 32, 48, 64 | list | Aura Sense's reach, blocks |
| `auraSenseUpkeepPercent` | 0.2 | 0–100 | % of max aura a second |
| `kashaDamage` | 12, 24, 48, 96, 192 | list | Kasha's damage; a cast hits a target once |
| `kashaCost` | 500, 2000, 9000, 37500, 150000 | list | Its aura cost |
| `kashaCooldownSeconds` | 10 | 0–3600 | Its cooldown |
| `kashaRange` | 24 | 1–128 | How far the wheels roll, blocks |
| `kashaBurnSeconds` | 5 | 0–3600 | How long a plain Nekomata's Kasha burns a target |
| `youjutsuMasteryPerUse` | 8.0 | 0–1000 | Youjutsu's mastery (times Tensura's per-use gain) for each art that poisons, holds or fools something |
| `poisonMistCost` | 300, 1200, 5400, 22500, 90000 | list | Poison Mist's magicule cost |
| `poisonMistDamage` | 2, 4, 8, 16, 32 | list | Its damage a second; twice this on Devils and Youkai |
| `poisonMistRange` | 24 | 1–128 | How far away it can be cast, blocks |
| `poisonMistRadius` | 5.0 | 0.5–32 | Its radius, blocks |
| `poisonMistSeconds` | 8 | 1–3600 | How long it lasts |
| `poisonMistCooldownSeconds` | 30 | 0–3600 | Its cooldown |
| `mudBindCost` | 200, 800, 3600, 15000, 60000 | list | Mud Bind's magicule cost |
| `mudBindSeconds` | 2, 2, 3, 3, 4 | list | How long it holds a target, from when it's first caught |
| `mudBindRadius` | 3.5 | 0.5–32 | The mud's radius, blocks |
| `mudBindPatchSeconds` | 4 | 1–3600 | How long the mud lies |
| `mudBindCooldownSeconds` | 20 | 0–3600 | Its cooldown |
| `veilCost` | 300, 1200, 5400, 22500, 90000 | list | Veil's magicule cost |
| `veilSeconds` | 15 | 1–3600 | How long it lasts |
| `veilCooldownSeconds` | 45 | 0–3600 | Its cooldown, from when it ends |
| `veilReach` | 3.0 | 0–64 | How close a mob must be to find someone in a Veil, blocks |
| `mirageCost` | 400, 1600, 7200, 30000, 120000 | list | Mirage's magicule cost |
| `mirageCopies` | 1, 2, 2, 3, 3 | list | How many copies it makes |
| `mirageSeconds` | 10 | 1–3600 | How long a copy lasts if nothing hits it |
| `mirageCooldownSeconds` | 40 | 0–3600 | Its cooldown |
| `maliceTouki` / `maliceBullet` / `maliceHeal` / `maliceKasha` | 1 / 1 / 1 / 5 | 0–100 | Malice for 10 s of Touki, a bullet, 2 s of healing, a cast |
| `maliceDarkFactor` | 3 | — | How much faster it gathers in Hell and miasma |
| `maliceFadeDay` / `maliceFadeNight` | 2 / 1 | — | How much fades a minute |
| `maliceWarning` | 50 | — | Where the warning shows and the tails start to flicker |
| `maliceBerserkSeconds` | 15 | — | How long the berserk lasts |
| `maliceAfter` | 30 | — | Malice left after it |
| `maliceToukiCooldownSeconds` | 30 | — | Touki's cooldown after it |

## `[valkyrie]`

The [Valkyries](../races/valkyrie.md). Each list goes by rank: Valkyrie Trainee, Valkyrie, Valhalla Guard, Chief Valkyrie, Brynhildr, or a
hybrid's Devil class. The races' own stats, EP ranges, requirements and the aspectual spells each rank teaches (`[learnableMagics]`) are in
`config/dxdtensura/race/valkyrie_config.toml`.

| Option | Default | Range | Meaning |
|---|---|---|---|
| `valkyrieInRaceMenu` | true | — | Valkyrie Trainee in Tensura's race menu (its starting, random and Reincarnation lists in reincarnation_config.toml). Off takes it out. The races' own numbers are in config/dxdtensura/race/valkyrie_config.toml |
| `valkyrieFlightSpeed` | 0.8, 1, 1.2, 1.5, 2 | list | A Valkyrie's flight speed by rank, the rune circle's |
| `norseFormulaCost` | 10, 15, 20, 25, 30 | list | Norse Formula: how much cheaper all magic is by rank, % |
| `norseFormulaChant` | 10, 20, 30, 40, 50 | list | Norse Formula: how much faster all chants are by rank, % |
| `runeDamage` | 6, 12, 24, 48, 96 | list | A Rune's damage by rank |
| `runeCost` | 100, 400, 1800, 7500, 30,000 | list | A Rune's magicule cost by rank |
| `fullBurstCircles` | 6, 8, 12, 16, 20 | list | A normal Full Burst's most circles by rank |
| `fullBurstGeniusCircles` | 12, 20, 35, 55, 80 | list | A genius's Full Burst's most circles by rank |
| `runeBarrierSoak` | 40, 80, 160, 320, 640 | list | How much Rune Barrier soaks by rank |
| `runeBarrierCost` | 200, 800, 3600, 15,000, 60,000 | list | Rune Barrier's magicule cost by rank |
| `enhancementPercent` | 10, 15, 20, 25, 30 | list | Enhancement's attack and speed by rank, %. Steps of 5 |
| `enhancementCost` | 150, 600, 2700, 11,250, 45,000 | list | Enhancement's magicule cost by rank |
| `runeSealSeconds` | 3, 3, 4, 4, 5 | list | Rune Seal's seconds by rank, on an equal |
| `runeSealCost` | 150, 600, 2700, 11,250, 45,000 | list | Rune Seal's magicule cost by rank |
| `runeSwordAttack` | 4, 8, 16, 32, 64 | list | The Rune Sword's attack by rank |
| `runeSwordCost` | 25, 100, 450, 1875, 7500 | list | The magicules a Rune Sword's hit costs by rank |
| `runeSpearAttack` | 3, 6, 12, 24, 48 | list | The Rune Spear's attack in the hand by rank |
| `runeSpearCost` | 20, 80, 360, 1500, 6000 | list | The magicules a Rune Spear's hit costs by rank |
| `battleDressArmor` | 4, 8, 12, 16, 20 | list | The Battle Dress's armour by rank |
| `battleDressToughness` | 0, 2, 4, 6, 8 | list | The Battle Dress's armour toughness by rank |
| `battleDressMagicResistPercent` | 5, 10, 15, 20, 25 | list | The Battle Dress's cut to Tensura magic's hits by rank, % |
| `valkyrieGeniusMagiculePercent` | 25 | 0–1000 | A genius's extra max magicules, % |
| `norseFormulaGeniusBonus` | 10 | 0–100 | A genius's Norse Formula: points more on both cost and chant |
| `runeThunderRange` | 6 | 0–64 | How far a Thunder Rune jumps, blocks |
| `runeThunderPercent` | 50 | 0–1000 | A Thunder Rune's jump's damage, % of the hit's |
| `runeWindKnockback` | 1.5 | 0–16 | A Wind Rune's knockback |
| `fullBurstShotPercent` | 50 | 0–1000 | A normal Full Burst's shot's damage, % of a Rune's |
| `fullBurstCirclePricePercent` | 40 | 0–1000 | A normal Full Burst's circle's price, % of a Rune's |
| `fullBurstGeniusPercent` | 250 | 0–1000 | A full sheet's volley's whole damage, % of a normal full burst's volley's |
| `fullBurstSpread` | 8 | 0–64 | How far from the aim a normal burst's shot lands, blocks |
| `fullBurstSplash` | 2 | 0–64 | How far a normal burst's shot reaches where it lands, blocks |
| `fullBurstGeniusSpread` | 16 | 0–64 | How far from the aim a genius's shot lands, blocks |
| `fullBurstGeniusSplash` | 4 | 0–64 | How far a genius's shot reaches where it lands, blocks |
| `fullBurstBreaksBlocks` | true | — | If true, each Full Burst blast breaks the blocks around where it lands, as TNT would: up to stone and metal blocks, never obsidian, bedrock or anything holding items, with no drops. Needs the mobGriefing and skillGriefing rules on, and claims are respected |
| `fullBurstBreakRadius` | 1.5 | 0–8 | How far round where it lands a normal burst's blast breaks blocks, blocks |
| `fullBurstGeniusBreakRadius` | 2 | 0–8 | How far round where it lands a genius's blast breaks blocks, blocks |
| `sakeTipsySeconds` | 120 | 1–3600 | How long a bottle of Sake leaves you Tipsy, seconds. A tipsy genius's Full Burst is a drunken one |
| `sakeCirclesPercent` | 150 | 100–300 | A tipsy genius's Full Burst opens this percent of their rank's circles (150: half as many again, 120 at Brynhildr) |
| `sakeDrainPercent` | 200 | 100–400 | A tipsy genius's Full Burst costs this percent of a sober one's (200: all their magicules instead of half) |
| `sakeParalysisSeconds` | 10 | 0–600 | How long a tipsy genius is paralysed when their Full Burst ends, seconds (Tensura's Paralysis) |
| `townSakeGold` | 1 | 0–64 | What a bottle of Sake costs at the Castle Town's inn, in gold coins |
| `fullBurstRange` | 96 | 1–256 | How far a Full Burst aims, blocks |
| `runeBarrierArcDegrees` | 75 | 0–180 | Rune Barrier stops hits within this many degrees of the look |
| `runeBarrierGeniusPercent` | 50 | 0–1000 | A genius's Rune Barrier, % stronger |
| `runeBarrierRookPercent` | 50 | 0–1000 | A Rook's Rune Barrier, % stronger |
| `runeBarrierMasteredPercent` | 25 | 0–1000 | Rune Barrier at full mastery, % stronger |
| `enhancementAllyRange` | 12 | 0–64 | How far Enhancement reaches a friend, blocks |
| `runeSealRange` | 24 | 1–128 | How far Rune Seal reaches, blocks |
| `runeSealBossPercent` | 50 | 0–100 | Rune Seal's time on a boss, % |
| `valkyrieGeniusChancePercent` | 10 | 0–100 | The % chance a player becoming a Valkyrie is born a genius: one roll per player, kept through race resets |
| `runeCooldownSeconds` | 1 | 0–3600 | The four Runes' shared cooldown, in seconds |
| `runeFireSeconds` | 4 | 0–3600 | How long a Fire Rune sets its target alight, in seconds |
| `runeIceSeconds` | 3 | 0–3600 | How long an Ice Rune slows its target, in seconds |
| `fullBurstOpenTicks` | 2 | 1–200 | Ticks between a normal burst's circles, before chant speed |
| `fullBurstGeniusOpenSeconds` | 4 | 0.05–60 | How long a genius's whole sheet takes to form, in seconds, timed to its song; chant speed doesn't shorten it |
| `fullBurstGeniusFireSeconds` | 11 | 1–120 | The longest a genius's Full Burst fires, in seconds |
| `fullBurstGeniusOpenPercent` | 10 | 0–100 | What forming a genius's whole sheet costs, % of max magicules, shared over its circles |
| `fullBurstGeniusFirePercent` | 40 | 0–100 | What a genius's whole fire costs, % of max magicules, shared over its shots; letting go early pays less |
| `fullBurstShotTicks` | 40 | 2–400 | Once the circles are open, each fires a blast every this many ticks while the key is held |
| `fullBurstFireSeconds` | 8 | 1–120 | The longest a Full Burst fires, in seconds |
| `fullBurstShotPricePercent` | 10 | 0–1000 | A normal Full Burst's blast's price, % of a Rune's |
| `fullBurstCooldownSeconds` | 30 | 0–3600 | Full Burst's cooldown from its end, in seconds |
| `fullBurstEmptyCooldownSeconds` | 1 | 0–3600 | Full Burst's cooldown if no circle opened, in seconds |
| `runeBarrierSeconds` | 15 | 1–3600 | How long Rune Barrier stands, in seconds |
| `runeBarrierCooldownSeconds` | 10 | 0–3600 | Rune Barrier's cooldown from its end, in seconds |
| `runeBarrierBrokenCooldownSeconds` | 20 | 0–3600 | Rune Barrier's cooldown if it broke, in seconds |
| `enhancementSeconds` | 60 | 1–3600 | How long Enhancement lasts, in seconds |
| `enhancementMasteredSeconds` | 75 | 1–3600 | How long Enhancement lasts at full mastery, in seconds |
| `enhancementCooldownSeconds` | 60 | 0–3600 | Enhancement's cooldown from the cast, in seconds |
| `enhancementAllyRank` | 2 | 0–5 | The rank from which Enhancement falls on friends too |
| `runeSealCooldownSeconds` | 20 | 0–3600 | Rune Seal's cooldown, in seconds |
| `runeWeaponCooldownSeconds` | 1 | 0–3600 | The cooldown on forming a rune weapon or throwing the spear, in seconds |
| `battleDressCooldownSeconds` | 3 | 0–3600 | The cooldown between Battle Dress changes, in seconds |
| `townValkyrieDiscountPercent` | 10 | 0–100 | The Castle Town market's cut for a Valkyrie, % |
| `seidrSoulsHeld` | 1, 2, 3, 5, 7 | list | Seiðr: Chosen Souls held, Valkyrie Trainee to Brynhildr; full mastery holds one more |
| `seidrSoulSeconds` | 30 | 1–3600 | How long a Chosen Soul hangs where it died, in seconds |
| `seidrSoulRadius` | 16 | 1–128 | How near someone with Seiðr a boss or strong foe must die for a soul, in blocks |
| `seidrBossSoulRadius` | 64 | 1–256 | How near someone with Seiðr a boss must die for a soul, in blocks. Whoever kills it gets one wherever they stand |
| `seidrChooseRadius` | 6 | 1–64 | How near a soul must be for Choose the Slain to take it, in blocks |
| `seidrStrongFoePercent` | 50 | 0–10,000 | A foe that isn't a boss leaves a soul if its EP is at least this much of a holder's, % |
| `seidrChooseCooldownSeconds` | 1 | 0–3600 | Choose the Slain's cooldown after taking a soul, in seconds |
| `einherjarCost` | 150, 600, 2700, 11,250, 45,000 | list | Call Einherjar's fee in magicules, by rank, through Norse Formula; half once Seiðr is mastered |
| `einherjarAttack` | 6, 10.5, 19, 36, 70 | list | An Einherjar's attack by rank, from a soul as strong as its caller; a weaker soul gives less, down to a quarter |
| `einherjarHealth` | 40, 120, 300, 1500, 4000 | list | An Einherjar's health by rank, from a soul as strong as its caller; a weaker soul gives less, down to a quarter |
| `einherjarAtOnce` | 1, 1, 2, 2, 3 | list | How many Einherjar a Valkyrie can have out at once, by rank |
| `einherjarSeconds` | 60 | 1–3600 | How long an Einherjar fights, in seconds |
| `einherjarCooldownSeconds` | 5 | 0–3600 | Call Einherjar's cooldown, in seconds |
| `einherjarMinRatio` | 0.25 | 0–1 | The weakest a soul makes a warrior, as a share of a soul as strong as its caller |

## `[kitsune]`

The [Kitsune and the Nine-Tailed Fox](../races/kitsune.md). Each list goes by rank: Low, Middle, High, Elder, Daiyoukai, or a hybrid's Devil
class. The races' own stats, EP ranges and requirements are in `config/dxdtensura/race/kitsune_config.toml` and `kyuubi_config.toml`.

| Option | Default | Range | Meaning |
|---|---|---|---|
| `kitsuneInRaceMenu` | true | — | Low-class Kitsune in Tensura's race menu (its starting, random and Reincarnation lists). Off takes it out. The races' own numbers are in config/dxdtensura/race/kitsune_config.toml and kyuubi_config.toml |
| `kyuubiChancePercent` | 10 | 0–100 | The % chance a player becoming a Kitsune is born a Nine-Tailed Fox instead: one roll per player, kept through race resets |
| `kitsuneFoxTouches` | true | — | Minecraft's foxes trust anyone with fox ears and tails out or in the fox body, and chickens run from them |
| `kyuubiFlamePercent` | 125 | 0–1000 | A Nine-Tailed Fox's Fox Fire against a Kitsune's, % of its damage and size |
| `foxSpeedPercent` | 10, 12, 15, 20, 25 | list | Ears out: extra speed by rank, %: Low, Middle, High, rank 3, rank 4 (a hybrid's Devil class) |
| `foxJumpBlocks` | 2, 2, 2.5, 3, 4 | list | Ears out: how high a fox jumps by rank, in blocks |
| `foxSenseRadius` | 8, 12, 16, 20, 24 | list | Ears out and sneaking: how far the fox senses outline living things by rank, blocks (a quarter more for a Nine-Tailed Fox) |
| `foxBodyScale` | 0.4 | 0.1–1 | The fox body's size against the player's |
| `foxBodySpeedPercent` | 40 | 0–500 | The fox body's extra speed on top of the ears-out speed, % |
| `foxBodyJumpBlocks` | 4, 4, 5, 6, 8 | list | The fox body: how high it jumps by rank, in blocks (a sprinting pounce keeps the ears-out height) |
| `foxBiteDamage` | 4, 8, 16, 32, 64 | list | The fox body's bite: added to the race's own attack by rank (items' attack doesn't count) |
| `foxBodyCooldownSeconds` | 2 | 0–3600 | Fox Transformation's cooldown, in seconds |
| `foxBodyNoticeBlocks` | 4 | 0–128 | The fox body: mobs notice it only this close, blocks, until it strikes (then from half as far as anyone) |
| `foxPounceBitePercent` | 150 | 0–1000 | The fox body's pounce bites the first enemy it meets: % of its attack |
| `foxBodyFirePercent` | 125 | 0–1000 | Fox Fire in the fox body: % of its damage |
| `foxBodyFireCostPercent` | 75 | 0–1000 | Fox Fire in the fox body: % of its cost |
| `greatFoxScale` | 5.5 | 1–16 | The Great Fox's size against the player's (Part 2) |
| `greatFoxSeconds` | 30, 45, 60 | list | How long the Great Fox lasts, seconds: High-class, Elder, Daiyoukai |
| `greatFoxPricePercent` | 30 | 0–100 | The Great Fox's price at the start, % of max magicules |
| `greatFoxCooldownMinutes` | 10 | 0–1440 | The Great Fox's cooldown, minutes |
| `leyRadius` | 64 | 1–512 | How far the ley point's bonuses reach, blocks, in its own dimension |
| `leyRefill` | 3 | 1–100 | By the ley point: how many times as fast magicules and aura refill |
| `leyFlamePercent` | 125 | 0–1000 | By the ley point: Fox Fire's damage, % |
| `foxfireDamage` | 6, 12, 24, 48, 96 | list | Foxfire: the ball's damage by rank |
| `foxfireCost` | 100, 400, 1800, 7500, 30,000 | list | Foxfire: magicules by rank |
| `foxfireCooldownSeconds` | 1 | 0–3600 | Foxfire's cooldown, in seconds |
| `foxfireRange` | 48 | 1–256 | How far a Foxfire ball flies, blocks |
| `foxfireBurstRadius` | 1.5 | 0–32 | How far a Foxfire ball's burst reaches, blocks |
| `foxBurnDamage` | 1, 2, 4, 8, 16 | list | Fox Fire's blue burn: damage a second by rank |
| `foxBurnSeconds` | 4 | 0–3600 | How long the blue burn lasts, seconds |
| `foxBurnMasteredSeconds` | 6 | 0–3600 | How long the blue burn lasts at full Fox Fire mastery, seconds |
| `kitsunebiDamage` | 4, 8, 16, 32, 64 | list | Kitsunebi: each wisp's damage by rank |
| `kitsunebiCost` | 300, 1200, 5400, 22,500, 90,000 | list | Kitsunebi: magicules a cast by rank |
| `kitsunebiSeconds` | 30 | 1–3600 | How long Kitsunebi's wisps circle, seconds |
| `kitsunebiCooldownSeconds` | 15 | 0–3600 | Kitsunebi's cooldown after the last wisp goes, seconds |
| `foxBreathDamage` | 8, 16, 32, 64, 128 | list | Fox Breath: damage a second by rank, in four pulses |
| `foxBreathCost` | 150, 600, 2700, 11,250, 45,000 | list | Fox Breath: magicules a second by rank |
| `foxBreathLength` | 6 | 1–64 | Fox Breath's cone, blocks long (a quarter more for a Nine-Tailed Fox) |
| `foxBreathAngle` | 30 | 1–180 | Fox Breath's cone, degrees wide |
| `foxBreathMaxSeconds` | 5 | 1–600 | The longest a Fox Breath hold lasts, seconds |
| `foxBreathCooldownSeconds` | 8 | 0–3600 | Fox Breath's cooldown after it ends, seconds |
| `foxPillarDamage` | 15, 30, 60, 120, 240 | list | Foxfire Pillar: damage by rank |
| `foxPillarCost` | 500, 2000, 9000, 37,500, 150,000 | list | Foxfire Pillar: magicules by rank |
| `foxPillarRange` | 32 | 1–256 | How far away a Foxfire Pillar can be raised, blocks |
| `foxPillarWidth` | 2 | 0.5–32 | A Foxfire Pillar's width, blocks (a quarter more for a Nine-Tailed Fox) |
| `foxPillarHeight` | 6 | 1–64 | A Foxfire Pillar's height, blocks |
| `foxPillarCooldownSeconds` | 10 | 0–3600 | The Foxfire Pillar's cooldown, seconds |
| `foxIllusionDamage` | 4, 8, 16, 32, 64 | list | Fox Illusion: a struck copy's burst damage by rank |
| `foxIllusionCost` | 400, 1600, 7200, 30,000, 120,000 | list | Fox Illusion: magicules by rank |
| `foxIllusionSeconds` | 10 | 1–3600 | How long Fox Illusion's copies stay, seconds |
| `foxIllusionCooldownSeconds` | 25 | 0–3600 | Fox Illusion's cooldown, seconds |
| `bewitchSeconds` | 15, 20, 25, 30, 40 | list | Bewitch: how long a mob fights for you by rank, seconds |
| `bewitchCost` | 500, 2000, 9000, 37,500, 150,000 | list | Bewitch: magicules by rank |
| `bewitchEpPercent` | 75 | 0–1000 | Bewitch takes only a mob whose max EP is at most this % of yours |
| `bewitchRange` | 16 | 1–128 | How far Bewitch reaches, blocks |
| `bewitchCooldownSeconds` | 30 | 0–3600 | Bewitch's cooldown, seconds |
| `foxStepRange` | 8, 10, 12, 14, 16 | list | Fox Step: how far it blinks by rank, blocks |
| `foxStepCost` | 150, 600, 2700, 11,250, 45,000 | list | Fox Step: magicules by rank |
| `foxStepCooldownSeconds` | 3 | 0–3600 | Fox Step's cooldown, seconds |
| `sunshowerRadius` | 12, 16, 20, 24, 32 | list | Sunshower Barrier: the dome's radius by rank, blocks |
| `sunshowerCost` | 1000, 4000, 18,000, 75,000, 300,000 | list | Sunshower Barrier: magicules on top of sunshowerMaxPercent, by rank |
| `sunshowerSeconds` | 30 | 1–3600 | How long a Sunshower Barrier stands, seconds |
| `sunshowerMaxPercent` | 5 | 0–100 | Sunshower Barrier: % of max magicules it costs, on top of its row |
| `sunshowerCooldownSeconds` | 120 | 0–36,000 | The Sunshower Barrier's cooldown, seconds |

## `[fenrir]`

[Fenrir](../world/fenrir.md) and the tamed wolf.

| Option | Default | Range | Meaning |
|---|---|---|---|
| `fenrirMaxHealth` | 4000 | 100–100,000 | Fenrir's health. |
| `fenrirHitCapPercent` | 5 | 1–100 | The most one hit on Fenrir counts, % of his max health (only /kill, the void and Lore mode's vanish go past it). |
| `fenrirClawPercent` | 6 | 0–100 | His claw hits (the lunge, the pounce's landing, Skyward Leap, the Howl): % of the target's max health. |
| `fenrirClawFloor` | 40 | 0–10,000 | His claw hits never deal less than this (his attack). |
| `fenrirBitePercent` | 8 | 0–100 | His God Slayer bite (and each of Devour's bites): % of the target's max health. It skips armour and barriers. |
| `fenrirBiteFloor` | 50 | 0–10,000 | His bite never deals less than this. |
| `fenrirMightyFactor` | 2 | 1–10 | His bite on the mightiest (Demon Lords, True Heroes, Satan-class Devils, Seraphs, a Heavenly Dragon holder in armour or a Drive) is this many times as hard. |
| `fenrirWoundSeconds` | 10 | 0–120 | How long his bite's wound lasts, seconds: nothing heals the wounded. |
| `fenrirPinSeconds` | 6, 4, 3 | list | How long Gleipnir's pins hold, seconds, in order (the last repeats, and every pin is the last once he is unbound). 1 to 8 entries. |
| `fenrirAnchorChannelSeconds` | 2 | 1–30 | How long use is held on a Gleipnir anchor to light it, seconds. |
| `fenrirAnchorLitSeconds` | 15 | 1–300 | How long a lit anchor stays lit, seconds. |
| `fenrirAnchorRestSeconds` | 20 | 0–600 | How long the two anchors that pinned him rest before they can be lit again, seconds. |
| `fenrirPupHealth` | 400 | 1–10,000 | Skoll's and Hati's health each. |
| `fenrirPupPercent` | 3 | 0–100 | A pup's nip or pounce: % of the target's max health. |
| `fenrirPupFloor` | 15 | 0–10,000 | A pup's hits never deal less than this. |
| `fenrirAloneSeconds` | 30 | 5–600 | With no one to fight near his stone this long, seconds, he lies back down, healed (the star is spent). |
| `fenrirXp` | 1500 | 0–100,000 | The XP his kill gives. |
| `fenrirYieldDivides` | 5 | 1–8 | The white Juggernaut Drive's Divides on him in his last phase that make him yield. |
| `fenrirYieldSeconds` | 10 | 1–60 | How long he lies yielded for the Drive's holder to tame him, seconds. |
| `tamedFenrirHealth` | 300 | 1–10,000 | The tamed Fenrir's health, small. |
| `tamedFenrirAttack` | 16 | 0–1000 | The tamed Fenrir's attack, small. |
| `tamedFenrirBigSeconds` | 30 | 1–600 | How long the tamed Fenrir's big form lasts, seconds. |
| `tamedFenrirBigCooldownSeconds` | 300 | 0–3600 | The big form's cooldown, seconds. |
| `tamedFenrirAwaySeconds` | 300 | 0–3600 | How long the tamed Fenrir stays away after he drops to 1 health, seconds. |
| `fangWoundSeconds` | 3 | 0–60 | The wound from Fenrir's Fang and the tamed Fenrir's bite, seconds. |
| `oneFenrirPerWorld` | true | — | While a tamed Fenrir lives, every binding stone lies empty. Off, the stones can still be used, but he still won't yield to anyone while a tamed one lives. |

## `[excalibur]`

[Excalibur's fragments](../excalibur/index.md) and Freed Sellzen.

| Option | Default | Range | Meaning |
|---|---|---|---|
| `fragmentHolyStrikePercent` | 25 | 0–100 | A fragment's holy strike on a foe holy things hurt: % of the hit, times its power (a replica's half). |
| `rapidlySpeedPercent` | 30 | 0–100 | Excalibur Rapidly held in the main hand: extra walking speed, %. |
| `rapidlyDashDistance` | 8 | 1–32 | Rapidly's flash step: how far it dashes, blocks. |
| `rapidlyCostPercent` | 2 | 0–100 | Rapidly's flash step: % of max magicules. |
| `rapidlyCooldownSeconds` | 4 | 0–600 | Rapidly's flash step: cooldown, seconds. |
| `destructionRadius` | 4 | 1–16 | Destruction's slam: how far round the impact it hits, blocks. |
| `destructionCostPercent` | 4 | 0–100 | Destruction's slam at full charge: % of max magicules (60% of it at the shortest charge). |
| `destructionCooldownSeconds` | 5 | 0–600 | Destruction's slam: cooldown, seconds. |
| `destructionBreaksBlocks` | true | — | Destruction's slam leaves a small crater (no drops; needs mobGriefing and Tensura's skillGriefing, and respects claims). |
| `destructionCraterRadius` | 1.5 | 0–4 | Destruction's crater: the blocks whose middles are this close to the impact break, blocks. |
| `mimicSpearReach` | 2 | 0–16 | Mimic's spear: extra reach, blocks. |
| `mimicWhipReach` | 6 | 0–16 | Mimic's whip: its whole reach, blocks. |
| `mimicWhipPull` | 3 | 0–8 | Mimic's whip: how far a hit pulls the foe toward the wielder, blocks (less by knockback resistance). |
| `nightmareCopies` | 3 | 1–8 | Nightmare: how many copies of the wielder appear (a replica's are fewer). |
| `nightmareSeconds` | 8 | 0–600 | Nightmare: how long the copies last, seconds (a replica's half). |
| `nightmareCostPercent` | 3 | 0–100 | Nightmare: % of max magicules. |
| `nightmareCooldownSeconds` | 20 | 0–600 | Nightmare: cooldown, seconds. |
| `transparencySeconds` | 10 | 0–600 | Transparency: how long the wielder is gone, seconds (a replica's half). |
| `transparencyReach` | 3 | 0–16 | Transparency: mobs lose the vanished wielder beyond this, blocks. |
| `transparencyAmbushPercent` | 50 | 0–100 | Transparency: the first melee hit while vanished does this % more, and ends it. |
| `transparencyCostPercent` | 3 | 0–100 | Transparency: % of max magicules. |
| `transparencyCooldownSeconds` | 30 | 0–600 | Transparency: cooldown, seconds, counted from the use. |
| `blessingRadius` | 8 | 1–32 | Blessing's holy ground: its radius, blocks. |
| `blessingSeconds` | 20 | 0–600 | Blessing's holy ground: how long it lasts, seconds (a replica's half). |
| `blessingHolyStrikePercent` | 25 | 0–100 | Blessing's holy ground: the wielder's side's hits on a foe holy things hurt inside it add this % as holy damage. |
| `blessingCostPercent` | 4 | 0–100 | Blessing: % of max magicules. |
| `blessingCooldownSeconds` | 40 | 0–600 | Blessing: cooldown, seconds. |
| `rulerSeconds` | 30 | 0–600 | Ruler: how long a commanded mob obeys, seconds (a replica's half). |
| `rulerRange` | 16 | 1–64 | Ruler: how far the wielder can command, blocks. |
| `rulerCostPercent` | 5 | 0–100 | Ruler: % of max magicules. |
| `rulerCooldownSeconds` | 60 | 0–600 | Ruler: cooldown, seconds. |
| `rulerReplicaChancePercent` | 25 | 0–100 | Once the true Ruler is claimed, the % chance the White Dragon Emperor drops a replica when he dies. |
| `freedNightChancePercent` | 25 | 0–100 | Freed Sellzen: the % chance, once a night, that a ruined church near a player has him waiting in its nave. |
| `freedChurchRange` | 96 | 16–256 | Freed Sellzen: how near a ruined church a player must be for it to roll, blocks. |
| `freedChurchWaitDays` | 3 | 0–30 | Freed Sellzen: in-game days a church he visited waits before he can come again. |
| `fusedHolyStrikePercent` | 50 | 0–100 | The fused Excalibur's holy strike: % of the hit, times the average of its fragments' powers. |
| `fusedAttackPerFragment` | 5 | 0–100 | The fused Excalibur's attack: 22 and this much for each fragment past the first. |
| `rulerFusedCostShare` | 50 | 0–100 | With Ruler fused into the same sword, every other power costs this % of its price. |
| `exDurandalAttackBonus` | 10 | 0–100 | Ex-Durandal: attack on top of Durandal's at the wielder's taming. |
| `auraPerHit` | 2 | 0–100 | Ex-Durandal's stored aura: added by a melee hit that takes health (once a second at most). |
| `auraPerWave` | 8 | 0–100 | Ex-Durandal's stored aura: added by a Holy Wave that hits at least one foe. |
| `auraPerPower` | 4 | 0–100 | Ex-Durandal's stored aura: added by a sheath power that hits at least one foe. |
| `releaseLength` | 40 | 8–128 | Ex-Durandal's giant slash: how far it runs, blocks. |
| `releaseWidth` | 7 | 1–16 | Ex-Durandal's giant slash: how wide it is, blocks. |
| `releaseDamageMultiplier` | 3 | 0–20 | Ex-Durandal's giant slash: damage as a multiple of the wielder's attack. |
| `releaseBreaksBlocks` | false | — | Ex-Durandal's giant slash digs its middle line (by Full Burst's block rules; needs mobGriefing and Tensura's skillGriefing). |
| `auraTransferMastery` | 500 | 0–1000 | Aura Transfer: the Durandal skill's mastery at which it is learned. |
| `auraTransferSeconds` | 30 | 0–600 | Aura Transfer: how long the other sword glows, seconds. |
| `auraTransferAttackBonus` | 6 | 0–100 | Aura Transfer: the glowing sword's extra attack. |
| `auraTransferCooldownSeconds` | 60 | 0–600 | Aura Transfer: cooldown, seconds. |
| `auraTransferGauge` | 20 | 0–100 | Aura Transfer into Ex-Durandal's own sheath: stored aura added. |

## `[absorption_line]`

[Absorption Line](../absorption-line/index.md).

| Option | Default | Range | Meaning |
|---|---|---|---|
| `addAbsorptionLineToReincarnationPool` | true | — | Put Absorption Line in Tensura's reincarnation roll (the only way to get it). |
| `lineReach` | 24 | 1–128 | How far a line reaches along the holder's look, in blocks; also the longest a line can be. |
| `lineMinLength` | 3 | 1–64 | The shortest a new line is, in blocks: something closer is held at this length. |
| `reelBlocksPerSecond` | 5 | 0–100 | How fast holding the key reels the lines in, in blocks a second. |
| `linesNew` | 1 | 1–64 | How many lines a new holder can have out at once (block and ally lines count). |
| `linesAt40` | 2 | 1–64 | How many lines at prisonAtMastery (40%). |
| `linesAt70` | 3 | 1–64 | How many lines at flameAtMastery (70%). |
| `linesMastered` | 5 | 1–64 | How many lines at full mastery. |
| `holdRatio` | 2 | 0–1,000,000 | A target whose max EP is up to this many times the holder's is held at the line's length. Stronger ones slip: they drag the line along and keep draining. |
| `noDrainRatio` | 5 | 1–1,000,000 | A target whose max EP is this many times the holder's, or more, throws a line off. Between 1 and this, the drain, the prison and the flames shrink in proportion. |
| `slipSnapDistance` | 32 | 1–256 | A slipping target's line snaps when it gets this far from the holder, in blocks. |
| `tieKeepDistance` | 48 | 1–512 | Any line whose two ends get this far apart ends, in blocks: a holder walking off from an enemy tied to a block, a teleport, a pearl. |
| `energyDrainPercentNew` | 2 | 0–100 | % of the target's max magicules and of its max aura a line drinks each second, new. |
| `energyDrainPercentMastered` | 4 | 0–100 | The same % at full mastery. |
| `bloodDrainPercent` | 1 | 0–100 | % of the target's max health a line drinks each second, healing the line's far end. |
| `bloodDrainMin` | 0.5 | 0–1000 | The least health a line drinks each second, before the EP share. |
| `playerBloodPerSecond` | 1 | 0–1000 | The most health a player loses each second to every line on them together. |
| `pourPercent` | 2 | 0–100 | % of the holder's max magicules an ally line pours into the ally each second. |
| `pourFloorPercent` | 5 | 0–100 | An ally line stops pouring while the holder is under this % of their max magicules. |
| `linePricePercent` | 1 | 0–100 | % of max magicules a line costs when it takes hold. Holding, drinking and reeling are free. |
| `prisonPricePercent` | 10 | 0–100 | % of max magicules Shadow Prison costs. |
| `flamePricePercent` | 15 | 0–100 | % of max magicules Blaze Black Flare costs. |
| `fieldPricePercent` | 30 | 0–100 | % of max magicules Delete Field costs, paid even with no enemy inside. |
| `prisonCooldownSeconds` | 40 | 0–3600 | Shadow Prison's cooldown where it opens, in seconds. |
| `flameCooldownSeconds` | 30 | 0–3600 | Blaze Black Flare's cooldown where it opens, in seconds. |
| `fieldCooldownSeconds` | 90 | 0–3600 | Delete Field's cooldown, in seconds. |
| `masteredCooldownCut` | 0.5 | 0–1 | How much of Shadow Prison's and Blaze Black Flare's cooldowns full mastery takes off (0.5 halves them), falling in a line from where each mode opens. |
| `prisonNewSeconds` | 2 | 0.1–600 | How long Shadow Prison pins a target where it opens, in seconds, on a target no stronger than the holder (by max EP). |
| `prisonMasteredSeconds` | 6 | 0.1–600 | How long Shadow Prison pins at full mastery, in seconds. |
| `playerPrisonSeconds` | 3 | 0.1–60 | The longest Shadow Prison pins a player, in seconds. |
| `flamePercentAt70` | 1.5 | 0–100 | % of max health the black flames burn each second where the mode opens. |
| `flamePercentMastered` | 2.5 | 0–100 | The same % at full mastery. |
| `playerFlamePerSecond` | 2 | 0–1000 | The most health a player loses each second to every black flame on them together. |
| `maxFlames` | 3 | 1–64 | How many targets one holder's black flames burn at once; one more puts out the oldest. |
| `flameKeepDistance` | 64 | 1–512 | The black flames go out on a target this far from the holder, in blocks. |
| `fieldRadius` | 10 | 1–128 | Delete Field's radius round the holder, in blocks. |
| `fieldSeconds` | 8 | 0.1–600 | How long Delete Field lasts, and holds a target no stronger than the holder, in seconds. |
| `playerFieldSeconds` | 4 | 0.1–60 | The longest Delete Field holds a player, in seconds. |
| `gearDampShare` | 0.5 | 0–1 | How strong another Sacred Gear works while a line drinks from its holder (0.5 is half). |
| `vritraWakeBlood` | 4 | 0–10,000 | The health a holder's lines must drink from Heavenly Dragons, in total, to wake Vritra. |
| `prisonAtMastery` | 0.40 | 0–1 | The mastery share at which Shadow Prison opens (and the second line). |
| `flameAtMastery` | 0.70 | 0–1 | The mastery share at which Blaze Black Flare opens (and the third line). |

## `[asia]`

[Asia Argento](../races/asia.md).

| Option | Default | Range | Meaning |
|---|---|---|---|
| `enabled` | true | — | Asia Argento, Rias's NPC Bishop. Off: no Asia at all. Rias's own [rias] enabled off turns her off too. |
| `lostNun` | true | — | Asia first comes as a lost nun near a village, once per world, to be walked to the old school building. Off: she's in the clubroom from the start. |
| `lostNunDays` | 3 | 1–30 | In-game days before the lost nun finds her own way to Rias. |
| `companion` | true | — | Rias's servants can take Asia along as a healer. Off: nobody can. |
| `ep` | 40,000 | 1000–10,000,000 | Her EP: three quarters magicules, a quarter aura (her Bishop piece adds its own). |
| `health` | 60 | 1–1000 | Her max health. |
| `refillMinutes` | 10 | 1–120 | Minutes for her magicules to refill from empty to full (faster where the land is rich in magicules). |
| `lowPercent` | 10 | 1–50 | Below this % of her max magicules she stops healing to rest. |
| `resumePercent` | 50 | 1–100 | She heals again from this % of her max magicules (never below lowPercent). |
| `healBelowPercent` | 70 | 1–100 | She heals her side when they're below this % of their max health. |
| `selfHealBelowPercent` | 50 | 1–100 | She heals herself below this % of her max health, when nobody else needs her (out and lost). |
| `arrowRange` | 32 | 9–64 | How far she shoots a healing arrow, in blocks. |
| `catchUpBlocks` | 24 | 8–128 | Further than this many blocks behind, she catches up (by a circle when out with a servant). |
| `aggroChancePercent` | 25 | 0–100 | The % chance per heal that a monster attacking the one she healed turns on her. |
| `aggroRange` | 16 | 0–64 | How near, in blocks, a monster must be for her heal to draw it. |
| `restDays` | 1 | 0–30 | In-game days she rests after being knocked out (sleeping counts). |
| `trainingPoints` | 25 | 0–1000 | Twilight Healing mastery points a practice with her gives, once per in-game day. |

## `[michael]`

[Michael](../races/michael.md).

| Option | Default | Range | Meaning |
|---|---|---|---|
| `enabled` | true | — | Michael, the NPC Seraph: off, he doesn't come down or appear, no feathers drift down and Deal for Michael does nothing; his holders keep their cards. |
| `michaelEP` | 300,000 | 1–1,000,000,000 | Michael's base max EP: what a player's or a card's worth is measured against when he deals. |
| `sunriseFeather` | true | — | His white feather drifts down to a human or pure Angel at their first sunrise in the overworld. |
| `churchFeatherChance` | 0.5 | 0–1 | The chance that a ruined church's chest holds one of his feathers. |
| `monsterCards` | 4 | 0–12 | How many of his cards one holder may give to monsters they've beaten (Deal for Michael). |

## `[multiplayer]`

For servers with more than one player. See [Multiplayer and servers](multiplayer.md) for how they fit together.

| Option | Default | Range | Meaning |
|---|---|---|---|
| `bossShareWindowSeconds` | 60 | 1–3600 | A boss's EP is shared among the players who hit it within this many seconds of its death. |
| `bossDropReserveSeconds` | 30 | 0–600 | A boss's drops can be picked up only by those who fought it for this many seconds (0: by anyone). |
| `bossHealthPerFighterPercent` | 50 | 0–500 | Extra boss health for each fighter past the first, as a percentage of its health. |
| `bossHealthMaxFactor` | 4 | 1–50 | The most a boss's health can grow to from its fighters, as a multiple. |
| `autoReleaseEnabled` | false | — | Free a one-per-server thing (Divine Dividing, the tamed Fenrir, Rias's pieces, Michael's cards) when its holder has been offline for autoReleaseDays. |
| `autoReleaseDays` | 30 | 1–365 | Days offline before autoReleaseEnabled frees what they hold. |
| `asiaOutMinutes` | 60 | 0–1440 | How long Asia stays out with a player before she goes home, in minutes (0: no limit). |
| `noMarkKingAwayDays` | 7 | 0–365 | Leaving a King who has been offline this many days leaves no Stray Devil mark (0: it always does). |
| `pvpHitCapPercent` | 40 | 1–100 | The most one hit of this mod's gear or skills can take from a player, as a percentage of their max health (Lore mode is exempt). |
| `cutsceneImmunityAfterTicks` | 20 | 0–400 | On a server, how many ticks past the transformation a cutscene still keeps hits off (20 ticks a second). |
| `bargainServerProtectSeconds` | 10 | 1–60 | On a server, how long the Bargain's open offer keeps hits off, in seconds. |
| `lineOnPlayerSeconds` | 15 | 1–300 | How long an Absorption Line can hold a player, in seconds. |
| `lineOnPlayerRestSeconds` | 30 | 0–600 | How long after that the same player can't be held again, in seconds. |
| `markHuntEnabled` | true | — | Whether the Hunters' Office can post a marked player at all. |
| `markHuntMaxHunters` | 3 | 1–50 | How many hunters can be after one marked player at once. |
| `offerHitSeconds` | 10 | 0–120 | No Evil Piece or card offer to a player who was hit within this many seconds (0: any time). |
| `petGagRange` | 64 | 1–1024 | How close a player must be, in the same dimension, for one of the [easter eggs](#easter_eggs) to go off for them. |
| `townMinCitizens` | 6 | 0–200 | The fewest citizens the Castle Town keeps, however many were killed that day. |
| `serveHealMinutes` | 30 | 0–1440 | How long after one a player can be healed by being given an Evil Piece or a card again, in minutes. |

## `[salvation_rose]`

[Salvation Rose](../salvation-rose/index.md), its Balance Breaker [Cycle of Salvation](../salvation-rose/index.md#cycle-of-salvation)
and [the witch](../salvation-rose/index.md#the-witch).

| Option | Default | Range | Meaning |
|---|---|---|---|
| `addSalvationRoseToReincarnationPool` | true | — | Put Salvation Rose in Tensura's reincarnation roll (the only way to get it). |
| `arrowDamageNew` | 6 | 0–10000 | A Rose Arrow's damage at no mastery. |
| `arrowDamageMastered` | 14 | 0–10000 | A Rose Arrow's damage at full mastery. |
| `splitNew` | 3 | 1–16 | How many arrows a full draw splits into at the start. |
| `splitAt50` | 4 | 1–16 | How many arrows a full draw splits into from 50% mastery. |
| `splitMastered` | 5 | 1–16 | How many arrows a full draw splits into at full mastery. |
| `splitDistance` | 6 | 0.5–64 | How far out a full draw's arrow splits, in blocks. |
| `seekDegreesPerTick` | 20 | 0–180 | The most a split arrow turns in a tick, in degrees. |
| `arrowRange` | 96 | 1–256 | How far a Rose Arrow flies, in blocks. |
| `arrowSpeed` | 3 | 0.1–16 | A Rose Arrow's speed, in blocks a tick. |
| `burstRadius` | 2 | 0–16 | How far an arrow's burst reaches, in blocks. |
| `burstShare` | 0.5 | 0–10 | A burst's damage to other enemies, as a share of the arrow's. |
| `fullDrawTicks` | 20 | 1–200 | Ticks to a full draw. |
| `minDrawTicks` | 5 | 1–200 | The shortest draw that shoots anything, in ticks. |
| `bowFadeTicks` | 40 | 0–1200 | How long the bow stays out after the last shot, in ticks. |
| `lostSoulBonusPercent` | 50 | 0–1000 | How much harder the gear hits a lost soul (a Stray Devil, undead or daemon), in percent. |
| `rainReach` | 48 | 1–128 | How far away Arrow Rain can be opened, in blocks. |
| `rainRadiusAt40` | 6 | 1–64 | Arrow Rain's radius when it opens, in blocks. |
| `rainRadiusMastered` | 10 | 1–64 | Arrow Rain's radius at full mastery, in blocks. |
| `rainDelayTicks` | 20 | 0–1200 | Ticks between the press and Arrow Rain's first strike. |
| `rainSeconds` | 4 | 1–120 | How long Arrow Rain falls, in seconds. |
| `rainStrikeTicks` | 10 | 1–200 | Ticks between Arrow Rain's strikes. |
| `rainShare` | 0.5 | 0–10 | An Arrow Rain strike's damage, as a share of a Rose Arrow's. |
| `purifyRadius` | 8 | 1–64 | Purify's reach, in blocks. |
| `purifyLostSoulShare` | 1 | 0–10 | Purify's strike on a lost soul, as a share of a Rose Arrow's damage. |
| `purifyHolderLight` | 10 | 0–100 | The light another holder gets from your Purify. |
| `wishChargeTicks` | 60 | 1–1200 | Ticks to charge a Wish Arrow. |
| `wishDamage` | 200 | 0–100000 | A Wish Arrow's damage. |
| `wishWidth` | 2 | 0–16 | How far from its path a Wish Arrow hits, in blocks. |
| `wishRange` | 96 | 1–256 | How far a Wish Arrow flies, in blocks. |
| `arrowPricePercent` | 0.5 | 0–100 | A full Rose Arrow's price, in percent of max magicules. |
| `rainPricePercent` | 10 | 0–100 | Arrow Rain's price, in percent of max magicules. |
| `purifyPricePercent` | 8 | 0–100 | Purify's price, in percent of max magicules. |
| `wishPricePercent` | 30 | 0–100 | Wish Arrow's price, in percent of max magicules. |
| `rainCooldownSeconds` | 30 | 0–3600 | Arrow Rain's cooldown when it opens, in seconds. |
| `purifyCooldownSeconds` | 30 | 0–3600 | Purify's cooldown when it opens, in seconds. |
| `wishCooldownSeconds` | 120 | 0–3600 | Wish Arrow's cooldown, in seconds. |
| `masteredCooldownCut` | 0.5 | 0–1 | The share of a power's cooldown that full mastery takes off. |
| `lightArrow` | 1 | 0–100 | The light a Rose Arrow shot at half draw or more takes. |
| `lightRain` | 8 | 0–100 | The light Arrow Rain takes. |
| `lightPurify` | 6 | 0–100 | The light Purify takes. |
| `lightWish` | 25 | 0–100 | The light Wish Arrow takes. |
| `lightBigHit` | 5 | 0–100 | The light a hit of despair takes (see bigHitPercent). |
| `lightAllyDeath` | 15 | 0–100 | The light an ally's death takes (see allyDeathRadius). |
| `bigHitPercent` | 25 | 0–100 | The share of max health in one hit that counts as despair, in percent. |
| `allyDeathRadius` | 32 | 0–256 | How near an ally has to die to dim the gem, in blocks. |
| `lightKill` | 2 | 0–100 | The light killing a hostile living thing gives. |
| `lightLostSoul` | 4 | 0–100 | The light killing a lost soul gives. |
| `lightBoss` | 15 | 0–100 | The light helping to kill a boss gives. |
| `lightSaved` | 15 | 0–100 | The light saving a Stray Devil gives. |
| `lightQuietPer30s` | 1 | 0–100 | The light each 30 quiet seconds give. |
| `lightQuietCap` | 50 | 0–100 | The most the gem recovers by quiet alone. |
| `lightFullStrength` | 50 | 1–100 | The light from which the gear hits at full strength. |
| `lightWeakestShare` | 0.5 | 0–1 | The gear's strength as the gem nears dark, as a share. |
| `darkRestSeconds` | 60 | 0–3600 | How long a dark gem rests, in seconds. |
| `lightAfterRest` | 20 | 1–100 | The light a gem comes back with after its rest. |
| `rainAtMastery` | 0.4 | 0–1 | The mastery share at which Arrow Rain opens. |
| `purifyAtMastery` | 0.7 | 0–1 | The mastery share at which Purify opens. |
| `saveFadeTicks` | 30 | 1–600 | How long a saved Stray Devil takes to fade, in ticks. |
| `bossHelpRadius` | 64 | 1–256 | How near a holder who hurt a boss has to be when it dies to share its light, in blocks. |
| `roseAwakenMastery` | 70 | 0–100 | The mastery, in percent, from which the small white creature offers his contract when the gem would go dark (Cycle of Salvation). |
| `contractOfferSeconds` | 15 | 1–600 | How long the contract screen stays open before it closes as "Not yet", in seconds. |
| `contractRetryMinutes` | 10 | 0–1440 | How long after an offer the creature waits before offering again, in minutes. |
| `salvationRadius` | 24 | 0–128 | How near the holder in Cycle of Salvation an ally has to be for Salvation to catch their killing blow, in blocks. |
| `salvationHealthPercent` | 20 | 1–100 | The health, in percent of max, someone Salvation caught is left with. |
| `cycleHitBonusPercent` | 50 | 0–1000 | How much harder every hit of the gear lands in Cycle of Salvation, in percent. |
| `cycleLostSoulBonusPercent` | 100 | 0–1000 | The lost-soul bonus in Cycle of Salvation, in percent (in place of lostSoulBonusPercent). |
| `cycleDrawTicks` | 10 | 1–200 | How long a full Rose Arrow draw takes in Cycle of Salvation, in ticks. |
| `wishBlastRadius` | 15 | 0–32 | In the goddess form: the radius of the Wish Arrow's blast where it first meets the ground, in blocks (0: none). |
| `wishBlastEdgeShare` | 0.5 | 0–1 | The share of a Wish Arrow's damage the blast still deals at its edge; it deals all of it at its middle (1: all of it everywhere). |
| `seekRange` | 48 | 0–128 | How far ahead of the holder the split arrows look for enemies, in blocks. |
| `seekConeDegrees` | 30 | 1–90 | How far off the holder's aim an enemy can be for the split arrows to seek it, in degrees. |
| `witchSeconds` | 130 | 5–600 | The witch: how long the form lasts, in seconds. |
| `witchRageSeconds` | 90 | 0–600 | The witch: how many of the form's last seconds she rages, striking anything near, allies too. |
| `witchWarnSeconds` | 5 | 0–60 | The witch: how many seconds before raging the warning comes. |
| `witchSilenceMinutes` | 15 | 0–1440 | The witch: how long the whole gear is silent after the form, in minutes. |
| `witchAfterSeconds` | 60 | 0–3600 | The witch: how long Weakness II and Slowness II last after the form, in seconds. |
| `witchLegDamage` | 24 | 0–100000 | The witch: a leg's strike. |
| `witchLegReach` | 32 | 1–128 | The witch: how far ahead the legs strike, in blocks. |
| `witchLegCooldownTicks` | 20 | 1–1200 | The witch: ticks between the legs' strikes. |
| `witchLegsStart` | 3 | 1–64 | The witch: her legs at the start. |
| `witchLegsEverySeconds` | 6 | 1–600 | The witch: one more leg every this many seconds. |
| `witchRageStrikeTicks` | 10 | 1–1200 | The witch: ticks between the raging witch's strikes. |
| `witchPullRadius` | 16 | 1–64 | The witch: how far round the holder the pull reaches, in blocks. |
| `witchPullSpeed` | 0.25 | 0–4 | The witch: how fast the pull drags, in blocks a tick. |
| `witchPullDamage` | 6 | 0–100000 | The witch: what the pull drains from each enemy a second. |
| `witchPullHealShare` | 0.5 | 0–10 | The witch: the share of what the pull drains that heals the holder. |
| `loreWitchLegFactor` | 5 | 1–1000 | The witch under Lore mode: how many times as hard a leg strikes. |
| `witchRainShare` | 0.75 | 0–100 | The witch's Rain of Legs: each falling leg's strike, as a share of witchLegDamage. |
| `witchRainCooldownSeconds` | 8 | 0–600 | The witch's Rain of Legs: seconds between rains. |
| `witchEmbraceShare` | 2 | 0–100 | The witch's Embrace: her arms' blow, as a share of witchLegDamage. |
| `witchEmbraceCooldownSeconds` | 10 | 0–600 | The witch's Embrace: seconds between embraces. |
| `witchMireShare` | 0.25 | 0–100 | The witch's Mire of Despair: what it drains each second from everything in it, as a share of witchLegDamage. |
| `witchMireCooldownSeconds` | 20 | 0–600 | The witch's Mire of Despair: seconds between mires. |
| `witchRageMoveSeconds` | 8 | 1–600 | The raging witch: seconds between the big moves (the rain, her embrace, the mire) she uses on her own. |

## `[lore_mode]`

The numbers for [Lore mode](../lore-mode.md). The mode itself is the game rule `dxdLoreMode`, for each world. None of this does
anything with the rule off.

| Option | Default | Range | Meaning |
|---|---|---|---|
| `boostLimitStartEp` | 100 | 1–1e12 | The max EP that counts 0 Boost stacks; one more stack each time max EP doubles from here, never under the form's cap |
| `boostCeiling` | 30 | 1–30 | The most Boost stacks anyone holds, the rage stack and the dragon's extras included |
| `divideCeiling` | 30 | 3–30 | The most Divides on one target |
| `upkeepPercent` | 0.1 | 0–100 | % of max magicules a Scale Mail costs a second |
| `bishopFormUpkeepPercent` | 0.25 | 0–100 | % of max magicules the Bishop's form costs a second (the Knight and the Rook cost `upkeepPercent`, as the plain Scale Mail does) |
| `bargainSeconds` | 10 | 1–3600 | The longest the Bargain's early Scale Mail lasts |
| `transferEfficiency` | 1.0 | 0–1 | How much of the Boost's extra power a Transfer gives (1 is the whole ×2ⁿ) |
| `compressVanishBossPercent` | 50 | 0–100 | The compress vanishes a boss or a player whose max EP is at or under this % of the holder's (0: never) |
| `replicaPower` | 0.2 | 0–1 | What a Durandal Replica leaves of the Holy Wave and the holy strike |
| `swordBirthCopies` | 16 | 1–64 | How many of Sword Birth's copies a holder can have at once |
| `balorTimeFactor` | 2.0 | 0.1–100 | How many times longer a Forbidden Balor View stop lasts; a player is still stopped for `playerMaxSeconds` at most |
| `pieceKnightSpeedPercent` | 60 | 0–1000 | A Knight's and a Queen's extra speed, % of their base, in the air too |
| `pieceKnightAttackSpeed` | 1 | 0–100 | A Knight's and a Queen's extra attack speed |
| `pieceKnightDodgePercent` | 25 | 0–100 | A Knight's and a Queen's chance to dodge melee and projectiles, % |
| `pieceKnightStep` | 0.5 | 0–10 | How much higher a Knight and a Queen step, in blocks |
| `pieceKnightArmorPenalty` | 4 | 0–30 | The armour a Knight gives up. A Queen doesn't |
| `pieceBishopMagiculePercent` | 100 | 0–1000 | A Bishop's and a Queen's extra max magicules, % of their base |
| `pieceBishopRegenPercent` | 100 | 0–1000 | A Bishop's and a Queen's faster magicule regeneration, % |
| `pieceBishopDemonicPowerPercent` | 100 | 0–1000 | A Bishop's and a Queen's stronger Demonic Power, %, added to the night's |
| `pieceBishopMagicCostPercent` | 25 | 0–100 | How much cheaper magic is for a Bishop and a Queen, % |
| `pieceBishopChantPercent` | 50 | 0–1000 | How much faster a Bishop and a Queen chant, % |
| `pieceRookAttackStartEp` | 100 | 1–1e12 | The base max EP a Rook's and a Queen's attack starts counting doublings from |
| `pieceRookAttackPerDoubling` | 1 | 0–1000 | Flat attack a Rook and a Queen gain per doubling of base max EP (the Boost stays the only multiplier) |
| `pieceRookAttackMin` | 2 | 0–1000 | The least flat attack a Rook and a Queen have |
| `pieceRookArmor` | 12 | 0–1000 | A Rook's and a Queen's extra armour |
| `pieceRookToughness` | 8 | 0–1000 | A Rook's and a Queen's extra armour toughness |
| `pieceRookKnockbackResistance` | 1 | 0–1 | A Rook's and a Queen's knockback resistance (1 is all) |
| `pieceRookCutPercent` | 30 | 0–100 | % a Rook and a Queen take off every hit. The higher of this and a Scale Mail's cut applies, not both |
| `pieceRookKnockback` | 1.5 | 0–100 | How much harder a Rook's and a Queen's hits knock back |
| `pieceRookMiningPercent` | 100 | 0–10000 | How much faster a Rook and a Queen mine, % |
| `pieceRookSpeedPenaltyPercent` | 10 | 0–100 | The speed a Rook gives up, % of their base. A Queen doesn't |

## Client settings

Each player also has a **client** config, `config/dxdtensura-client.toml`. You can edit it in game: Mods → Devil x
Slime → Config.

| Option | Default | Meaning |
|---|---|---|
| `ddraigLines` | `ALL` | How much of Ddraig you see: `ALL`, `IMPORTANT` (teaching, warnings and story lines; Rias's lines count as important) or `OFF` |
| `screenShake` | true | Shake the camera for the Explosion, the Scale Mail forming and a Dragon Shot landing close by |
| `gearEffects` | `ALL` | `ALL`; `MOMENTS` (no lingering auras or motes); or `OFF` (no effects, no light from the gear, no rage tint). Poses and sounds always play |
| `gearSongs` | `ALL` | Whose gear songs play: `OFF` for none, `OWN` for your own only, `ALL` for others' nearby too. Each song's own setting below still applies |
| `cutscenes` | true | Film Balance Breaker (both Scale Mails) and Juggernaut Drive forming: the full cutscene the first time, a short one after (the white Scale Mail plays its full one every time). Off, they form at once |
| `modelStyle` | `NEW` | `NEW` (the remodelled, outlined models) or `CLASSIC` (the blocky models from before); changes at once. The gauntlet's three forms, the Scale Mail, Juggernaut Drive's dragon and Ascalon's blade on the gauntlet and the Scale Mail (the sword itself, its relic and the skull keep their look). The first time you hold the Boosted Gear a screen asks which look you want, with a picture of each |
| `modelStyleAsked` | `false` | Whether that screen has been answered (any way out counts, keeping the current look); set it back to `false` to be asked again |
| `kingMarker` | true | As a servant in a peerage, show where your King is at the top of the screen |
| `huntMarker` | true | On one of Rias's [hunts](../world/stray-devils.md#riass-hunts), show where the Stray Devil is at the top of the screen |
| `handRow` | true | With a Brave Saint card or a deck, show the hand you could play (or the wait) at the bottom left |
| `seraphMarker` | true | As a Brave Saint, show where your Seraph is at the top of the screen |
| `flightLean` | true | Lean a player flying on the mod's wings or in a Scale Mail into the flight (flat out sprint-flying, banking into turns, and along the flight while [soaring](../getting-started/flight.md)). With TR: Nightmare installed, its own flight pose is left off them; turn this off to fly upright and let Nightmare's pose take over |
| `dragonFlight` | true | [Dragon flight](../getting-started/flight.md): soaring with momentum when you sprint-fly on the mod's wings. Off, flight works as before |
| `flightCameraTilt` | 100 | How far the camera rolls with a bank while soaring, 0 to 100% |
| `flightRollSpin` | true | Turn the camera with you in a barrel roll. Off, the camera stays upright |
| `wingMotion` | true | Living wings: the race wings and the Scale Mails answer your movement, breathe when you stand still and beat with the flight. Off, they keep the old slow beat, and the Scale Mail's leather lies flat |
| `townSky` | true | The purple sky and the great moon over the [Castle Town](../world/castle-town.md). Off, Hell keeps its own sky there |
| `trueQueenMusic` | true | Play Cardinal Crimson Promotion for as long as someone near you is in the [True Queen](../boosted-gear/promotion-forms.md#the-true-queen), on the Jukebox volume slider, in place of the game's music |
| `abilityWheel` | true | **New ability controls**: the [mode wheel](../getting-started/mode-wheel.md) on Left Alt + a slot key, a quick tap flipping back, and the Scale Mail and the True Queen moving the key you pressed onto their first move and back. Off (0.2.67), Alt steps one mode as in Tensura and your keys stay where you put them |
| `abilityWheelSkills` | true | Show your other skills from this addon round the mode wheel's edge, so one key can reach any of them |
| `fullBurstMusic` | true | Play a genius [Valkyrie's](../races/valkyrie.md#full-burst) Full Burst song when someone near you fires one, on the Jukebox volume slider, in place of the game's music |
| `betrayerMusic` | true | Play [Sword of Betrayer's](../sword-birth/sword-of-betrayer.md) song once each time someone near you enters it, on the Jukebox volume slider, in place of the game's music |
| `gpuModels` | true | Draw the race wings from a copy kept on the graphics card: the same look, far faster. Turn it off if they look wrong with another mod. Iris shader packs always get the old way |
| `goddessEyes` | true | Cycle of Salvation turns the holder's eyes gold, a gold pixel over each eye's inner pixel on the default face. Turn it off for a skin whose eyes are painted elsewhere |
| `roseMusic` | true | Play [Cycle of Salvation's](../salvation-rose/index.md#cycle-of-salvation) song for as long as someone near you is in it, and the witch's songs while she's out, on the Jukebox volume slider, in place of the game's music |
| `bentArms` | true | Salvation Rose's shooting poses bend the arms at the elbow (with bendy-lib, packed in the mod). Turn it off for straight arms, for instance if another mod's player model clashes with bending |
| `witchSky` | true | Near [the witch](../salvation-rose/index.md#the-witch) the sky turns to blood dusk, a vortex turns overhead, the fog closes in and ash falls. Off, the sky stays as it is |
