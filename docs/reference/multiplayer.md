# Multiplayer and servers

Devil x Slime works on a dedicated server and on a LAN world. This page is for players who play together and for the people who run
the server. Every number below is a default that the server owner can change in the [configuration](configuration.md).

## The same version everywhere

**A server and everyone on it need the same version of Devil x Slime.** Since 0.2.84 a client on another version is refused when it
joins, so update the server and every player together.

Install the mod and its requirements on the server and on every client, as on [Installation](../getting-started/installation.md). The
client-only mods there (Photon and Player Animator) aren't needed on a dedicated server.

Only the server's settings count: NeoForge sends the server config to each player as they join. Each player keeps their own
[client settings](configuration.md#client-settings).

## Fighting together

- **Boss rewards are shared.** A boss's EP goes to everyone who hit it in the 60 s before it died, by the damage each dealt. Its drops are
  kept for its fighters for 30 s, and the [White Dragon Emperor's](../world/white-dragon-emperor.md) jewel needs a hit on him first.
- **Bosses grow with the party.** A boss gains half its health for each fighter past the first, up to 4 times its health.
- Your pets, subordinates, teammates and players you can't harm count as allies: area moves pass them by, and Cycle of Salvation's
  catch reaches them.

## Player against player

- **PvP off is respected**, by hits and by everything that lands without one: Divide, Mud Bind, Poison Mist, Holy Ground, the Sword Wall's
  teleport, Fox Fire and the rest.
- **One blow from this mod's gear or skills takes at most 40%** of a player's max health, outside [Lore mode](../lore-mode.md), and
  multi-hit moves respect a player's hurt frames.
- **Protection is shorter on a server.** A cutscene protects you only until the transformation and a second after it, the Bargain's open
  offer for 10 s, and Cycle of Salvation's contract offer for 10 s too.
- An [Absorption Line](../absorption-line/index.md) holds a player for 15 s, then can't take the same player for 30 s.
- A [Balor View](../balor-view/index.md) misfire spares your allies.
- No Evil Piece or Brave Saint card can be offered to someone who was hit in the last 10 s.
- Only a player who could hurt the owner can hit their tamed [Fenrir](../world/fenrir.md).
- The [witch](../salvation-rose/index.md#the-witch) in her rage strikes other players only where her holder could hurt them anyway.

## Claims and terrain

The moves that dig respect claims, spawn protection, adventure mode, Tensura's `skillGriefing` game rule and other mods' block-break
checks, and never break chests or anything else that holds items: Juggernaut Drive's burst, the Longinus Smasher, the Blasters, Solid
Impact, Dragon Shot's crater and the Holy Wave's ground. Nothing puts broken terrain back.

!!! tip "A safe start for a new server"
    Until you know your players, turn the terrain damage off: `dragonShotBreaksBlocks = false` in
    [`[boosted_gear]`](configuration.md#boosted_gear) and `/gamerule skillGriefing false`. Keep [Lore mode](../lore-mode.md) off on an
    open server: it lifts the 40% cap and makes the Longinus gears as strong as in the story.

## The Stray Devil mark

A servant who leaves their King carries the [Stray Devil mark](../world/stray-devils.md#the-stray-devil-mark), and with PvP on the
[Castle Town's](../world/castle-town.md#hunters-and-the-mark) Hunters' Office posts the player marked longest. On a server:

- the marked player is told;
- hunters see a rough 64-block square, not an exact spot;
- at most 3 hunters can be after one player, and a hunt pays no renown;
- leaving a King who has been offline for 7 days leaves no mark;
- `markHuntEnabled` turns the hunt off.

A King can hide where they are from their own servants with `/dxdtensura hideking`.

## Players who stop coming

Some things exist once per server: Divine Dividing, the tamed Fenrir, Rias's pieces and Michael's cards. If a holder stops playing,
an operator can free them (online or not):

| Command | Frees |
|---|---|
| `/dxdtensura divinedividing release <player>` | Divine Dividing |
| `/dxdtensura fenrir release <player>` | The tamed Fenrir |
| `/dxdtensura rias release <player>` | A servant of Rias |
| `/dxdtensura peerage release <player>` | A servant of a player King |
| `/dxdtensura bravesaints release <player>` | A card holder, whose card goes back |

`autoReleaseEnabled` (off by default) does it by itself for anyone offline for `autoReleaseDays` (30). [Asia](../races/asia.md) goes home
after 60 minutes out with a player, so one player can't keep her.

## Fair play

- Logging out doesn't end Reduce or the compress: they carry on when you come back.
- Being given an Evil Piece or a card heals you only once in 30 minutes.
- Dividing a friend pays no Absorbed Power or mastery.
- The Castle Town keeps at least 6 citizens, however many were killed that day.
- Michael's feather and Rias's flyer can only be picked up by the player they're for.
- Holy swords are treasure: anyone can take them.

## Sound and screen

- **Gear songs** (client setting `gearSongs`): `ALL` plays other players' gear songs near you as well as your own, `OWN` only yours, `OFF`
  none. Each song's own setting still applies.
- Other players' big moments shake your screen half as much as your own.
- Invisible players show no gear auras.

## Settings

The `[multiplayer]` section holds the numbers on this page: see [`[multiplayer]`](configuration.md#multiplayer). The
[easter eggs](configuration.md#easter_eggs) need a second player; no spoilers here.
