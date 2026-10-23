# Installation

Devil x Slime runs on **Minecraft 1.21.1** with **NeoForge**. Put the mod jar and everything below into your `mods`
folder.

## Required on the client and the server

| Mod | Version |
|---|---|
| Minecraft | 1.21.1 |
| NeoForge | 21.1.x (built and tested on 21.1.259) |
| Tensura: Reincarnated | **2.0.1.3 or newer** |
| ManasCore | 4.0.0.2 or newer |
| Architectury API | 13.0.8 (Tensura needs it) |
| GeckoLib | 4.9.2 (Tensura needs it) |
| SmartBrainLib | 1.16.11 (Tensura needs it) |
| TerraBlender | 4.1.0.8 (Tensura needs it) |

If you already play Tensura: Reincarnated, you have all of these except Devil x Slime itself.

!!! warning "Older Tensura versions"
    Tensura 2.0.1.0 to 2.0.1.2 are not supported, and NeoForge will refuse to start with them. Update Tensura to
    2.0.1.3 or newer.

## Required on the client only

The gear's effects and poses need these on every player's game. A dedicated server doesn't need them.

| Mod | Version | What it does |
|---|---|---|
| Photon | 2.2.7 or newer, with LDLib2 (2.2.40+) and KilaGraph (21.1.0.15+) | Draws the effects: sparks, auras, beams, wings of light |
| Player Animator | 2.0.4 or newer | The poses: raising the gauntlet, pushing your palm out, bracing for the Explosion |

## Optional

| Mod | Version | What it adds |
|---|---|---|
| LambDynamicLights | 4.8 or newer | The gear's glow lights up the blocks around you: the gems, held stacks, the Explosion, the Scale Mail and a Dragon Shot in flight |

## On a server

- Install the required mods on the server and on every player's client. The client-only mods go on the clients.
- The mod has a **server config** for every rule and number, and NeoForge sends it to players as they join. See
  [Configuration](../reference/configuration.md).
- The mod adds its Sacred Gears to Tensura's reincarnation roll by **editing Tensura's own config file**. See
  [Your first Sacred Gear](first-gear.md#server-owners-the-reincarnation-roll) for what it changes and how to turn it off.

## Updating

Replace the old Devil x Slime jar with the new one. Your server config keeps the values you changed yourself, and any
default that a new version changed is updated for you.

!!! danger "Close the game first"
    Swap jars only while the game is closed. Replacing a mod jar while Minecraft is running crashes it.
