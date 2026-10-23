# Compatibility and known limits

## Other mods

| Mod | How it works with Devil x Slime |
|---|---|
| **Tensura: Reincarnated** | Required, 2.0.1.3 or newer. Older versions won't load |
| **Photon** | Required on clients; draws every effect. Photon also draws them under Iris shaders, with its own settings in `photon-client.toml` |
| **Player Animator** | Required on clients; the poses |
| **LambDynamicLights** | Optional: the gear's glow lights up the blocks around it |
| **Particle Core** | Works. Older versions of Devil x Slime crashed with it ("Ticking Particle"); that is fixed |
| **Elite Tensura** | Works. Hits from this mod don't count toward Elite Tensura's single-hit damage records, which would otherwise hand out permanent attack bonuses |
| **Tensura Drowsiness Guard** | Works. Older versions lost this mod's effects on save; that is fixed |
| **Shader packs** (Iris) | The effects still show. A shader pack's own bloom can make them brighter. Other looks under shaders are untested |
| **Bendy-arm animation mods**, bulky chest armour models | May clip through the rigid gauntlet |

## Tensura's own skills

- **Clones** (Body Double, Reaper) copy your skills, but their copy of the Boosted Gear starts idle: no stacks, no ×2ⁿ,
  and never your stored Ascalon.
- **Plundering skills** can't steal either Sacred Gear, and copying skills don't copy Albion's power.
- **Magic Interference** and dispels end Balance Breaker and Juggernaut Drive.
- **Infinite Regeneration's death save** still holds against Penetrate and the Longinus Smasher.

## Known limits

- **First person:** you see the gauntlet in first person only with an **empty main hand** (or holding a map), and only as
  a right-handed player. Holding any other item hides your arm and the gauntlet. In third person it always shows.
- **Slim (Alex) skins** use the same gauntlet shape, so there can be a gap of up to one pixel, like vanilla chestplates.
- **The Scale Mail** hides your worn armour, elytra and cape. A mod that replaces those layers may still show them.
- **Ascalon's skull** is a model: only its own block is solid, so you can walk into its jaws and horns.
- **Juggernaut Drive** can't fly.
