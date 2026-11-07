# Compatibility and known limits

## Other mods

| Mod | How it works with Devil x Slime |
|---|---|
| **Tensura: Reincarnated** | Required, 2.0.1.3 or newer (2.0.1.4 works too). Older versions won't load |
| **Photon** | Required on clients; draws every effect. Photon also draws them under Iris shaders, with its own settings in `photon-client.toml` |
| **Player Animator** | Required on clients; the poses |
| **LambDynamicLights** | Optional: the gear's glow lights up the blocks around it |
| **Particle Core** | Works. Older versions of Devil x Slime crashed with it ("Ticking Particle"); that is fixed |
| **Elite Tensura** | Works. Hits from this mod don't count toward Elite Tensura's single-hit damage records, which would otherwise hand out permanent attack bonuses |
| **Tensura Drowsiness Guard** | Works. Older versions lost this mod's effects on save; that is fixed |
| **FTB Chunks** and other claim mods | Works. A Juggernaut Drive's walk, Extinguished Star's crater and Celsius Cross Trigger's frozen water leave claimed land alone |
| **Shader packs** (Iris) | The effects still show. A shader pack's own bloom can make them brighter. Under a shader pack the race wings are drawn the old, slower way (see `gpuModels`), and the tongues of a Phenex's wings stay straight. Forbidden Balor View's drain becomes a flat tint, and its screen edges and grey stay off. Other looks under shaders are untested |
| **TR: Nightmare** | Works. Its flight pose is left off players flying on this mod's wings or in a Scale Mail, so they no longer turn upside down. Turn the client setting `flightLean` off to fly upright and let Nightmare's pose take over |
| **Other mods' structures** | Works. Our structures check what else would generate nearby and keep a dozen blocks clear of it |
| **Bendy-arm animation mods**, bulky chest armour models | May clip through the rigid gauntlet |

## Tensura's own skills

- **The [mode wheel](../getting-started/mode-wheel.md)** opens only for this addon's skills. Tensura's own skills and
  other mods' keep Tensura's one-step Alt switching.
- **Clones** (Body Double, Reaper) copy your skills, but their copy of the Boosted Gear starts idle: no stacks, no ×2ⁿ,
  and never your stored Ascalon. A copy of the Durandal skill never carries the sword.
- **Plundering skills** can't steal any of the Sacred Gears, and copying skills don't copy Albion's power.
- **Skill and Character Reset Scrolls** take the Holy Factor away, and each gives one fresh
  [roll](../durandal/index.md#being-born-with-it).
- **A Character Reset Scroll** rolls a pure Devil's [House](../races/houses.md#the-roll) again. A Race Reset Scroll keeps it.
- **Tensura's race menu** (a Race Reset Scroll, the Reincarnation spell) takes a Sacred Gear from a holder who picks a
  race that isn't human. See [Only in humans](../getting-started/first-gear.md#only-in-humans).
- **Magic Interference** and dispels end Balance Breaker and Juggernaut Drive.
- **Infinite Regeneration's death save** still holds against Penetrate and the Longinus Smasher.

## Known limits

- **First person:** you see the gauntlet in first person only with an **empty main hand** (or holding a map), and only as
  a right-handed player. Holding any other item hides your arm and the gauntlet. In third person it always shows.
- **Slim (Alex) skins** use the same gauntlet shape, so there can be a gap of up to one pixel, like vanilla chestplates.
- **The Scale Mail** hides your worn armour, elytra and cape. A mod that replaces those layers may still show them.
- **Ascalon's skull** is a model: only its own block is solid, so you can walk into its jaws and horns.
- **The red Juggernaut Drive** can't fly. The white one does.
- **A walking dragon's breaks:** what hangs on a broken block (torches, flowers, wall signs) still pops off as an item. The game does that.
- **The race wings** are drawn from the graphics card since 0.1.84, far faster. If another mod makes them look wrong,
  turn the client setting `gpuModels` off.
