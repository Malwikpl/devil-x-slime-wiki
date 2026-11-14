# Your own sound pack

Want the gears to shout in English, or swap any sound for one of your own? You don't need to code. A **resource
pack** swaps the mod's sound files for yours, and it takes about 10 minutes.

**You need:**

- Your audio clips. mp3 or wav is fine; you'll convert them.
- [Audacity](https://www.audacityteam.org/) (free) to convert them to `.ogg`.
- [7-Zip](https://www.7-zip.org/) (free), only if you want to listen to the mod's original sounds.

[Download the template pack](../assets/downloads/DxS-Sound-Pack-Template.zip){ .md-button .md-button--primary }

The template is a pack that's already set up. Unzip it into your `resourcepacks` folder (step 1 shows where that is), then
skip to step 2.

## 1. Make the pack folder

In Minecraft go to **Options → Resource Packs → Open Pack Folder**. In that folder, make this:

```
My Sound Pack/
├── pack.mcmeta
└── assets/
    └── dxdtensura/
        └── sounds/
            ├── boost.ogg
            └── (your other .ogg files)
```

`pack.mcmeta` is a text file. Open Notepad, paste this, and save it as `pack.mcmeta`:

```json
{
  "pack": {
    "pack_format": 34,
    "description": "My Devil x Slime sound pack"
  }
}
```

`34` is the number for Minecraft 1.21.1.

!!! tip "Windows hides file extensions"
    In File Explorer turn on **View → Show → File name extensions**. Otherwise Windows may quietly save
    `pack.mcmeta.txt`, and the pack won't show up.

## 2. Turn your clip into an .ogg file

In Audacity:

1. **File → Open** your clip.
2. Cut the silence at the start: select it and press Delete. If the clip starts late, the voice comes in late.
3. **File → Export Audio.** Set Format to **Ogg Vorbis** and Channels to **Mono**.
4. Name it **exactly** like the sound you're replacing, all lowercase, for example `boost.ogg`.
5. Put it in `assets/dxdtensura/sounds/`.

**Why mono:** Minecraft only places mono sounds in the world, so they come from the player and fade with distance.
Stereo plays flat at full volume. Music tracks can stay stereo.

**Too loud or too quiet?** Use **Effect → Volume and Compression → Normalize** and compare with the original.

!!! warning "Renaming doesn't convert"
    Renaming an `.mp3` to `.ogg` does **not** work. The file has to be exported as Ogg Vorbis.

## 3. Which file is which

The voice lines people ask about most:

| File | When it plays |
|---|---|
| `boost.ogg` | Boosted Gear: "Boost!" |
| `boost_burst_short.ogg`, `boost_burst_long.ogg` | A burst of quick boosts, "Boost!" again and again |
| `transfer.ogg` | "Transfer!" |
| `explosion.ogg` | "Explosion!" |
| `reset.ogg` | "Reset" (your boosts end) |
| `summon.ogg` | Summoning the gauntlet, and the gauntlet reaching its Base form |
| `gift_unlock.ogg` | The gauntlet reaching its Gift form |
| `balance_breaker.ogg` | Boosted Gear's Balance Breaker |
| `blade.ogg` | Boosted Gear's Blade mode (with Ascalon) |
| `smasher_charge.ogg` | Longinus Smasher charging |
| `divide.ogg` | Divine Dividing: "Divide!" |
| `divine_balance_breaker.ogg`, `divine_balance_breaker_short.ogg` | Divine Dividing's Balance Breaker (with and without the pause) |
| `half_dimension.ogg` | "Half Dimension" |

**Every other sound** (sound effects, roars, music) is inside the mod's jar. Open the jar from your `mods` folder with
7-Zip (right-click → 7-Zip → Open archive) and go to `assets/dxdtensura/sounds/`. Listen to the files to find the one
you want, then make your own file with the same name. Music tracks have `ost` or `music` in their names.

## 4. Turn it on and test it

1. **Options → Resource Packs**, click your pack so it moves to the **Selected** side, then Done. If you use more than
   one pack, the one on top wins.
2. Changed a file while the game is open? Press **F3 + T** to reload.
3. Test a sound without using the skill: `/playsound dxdtensura:boost master @s` (cheats must be on). Swap `boost`
   for any file name, without `.ogg`.
4. **Options → Music & Sounds → Show Subtitles** shows which sound just played.

## Not working?

- **The pack isn't in the list:** `pack.mcmeta` must sit directly inside the pack folder (or at the top of the zip),
  not one folder deeper. Check it isn't `pack.mcmeta.txt`.
- **The pack is red ("made for an older/newer version"):** `pack_format` should be `34`.
- **Silence instead of your sound:** the file isn't real Ogg Vorbis, or the path isn't exactly
  `assets/dxdtensura/sounds/`.
- **The original still plays:** the name doesn't match (lowercase, no spaces, `.ogg`). Press F3 + T after fixing it.

## Sharing your pack

Open your pack folder, select `pack.mcmeta` and `assets` together, and right-click → **Send to → Compressed (zipped)
folder**. Your friends drop that zip in their own `resourcepacks` folder.

Resource packs only change what **you** hear. Friends hear your sounds only if they install the pack too.

## Extra: several takes for one sound

To have the game pick a random take each time, add `assets/dxdtensura/sounds.json` to your pack:

```json
{
  "boost": {
    "replace": true,
    "subtitle": "subtitles.dxdtensura.boost",
    "sounds": [
      "dxdtensura:my_boost_1",
      "dxdtensura:my_boost_2"
    ]
  }
}
```

Then put `my_boost_1.ogg` and `my_boost_2.ogg` in `assets/dxdtensura/sounds/`. To make one quieter, write
`{ "name": "dxdtensura:my_boost_1", "volume": 0.7 }` in place of its line.
