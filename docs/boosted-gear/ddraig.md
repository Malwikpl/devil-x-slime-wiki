# Ddraig and his Bargain

**Ddraig**, the Red Dragon Emperor sealed in the Boosted Gear, is your partner. He talks to you in a small **speech
box** above the Sacred Gear panel: his green jewel and DDRAIG on top, the line typing out under it, then fading. A low
growl plays as he starts.

## What he says

- **Teaching**, once each: he introduces himself a few seconds after you first get the gear, then explains the Boost
  on your first summon, body strain on your first stack, the Explosion and the Reset the first time they happen, each
  evolution, your first Scale Mail, your first rage burst, and Penetrate when the Gift unlocks it.
- **Warnings:** your magicules running low or the time nearly up in the Scale Mail (once per transformation), and very
  low health while you hold stacks (at most once a minute).
- **Story lines:** a failed crisis, the awakening, running dry, and his Bargain.
- **Reactions:** a boss or a worthy enemy killed by your boosted bare fist, and getting back up after a death.

The gear's own calls ("Boost!", "Explosion!", "Reset.", "Welsh Dragon Balance Breaker!") stay on the action bar.

!!! tip "Too chatty?"
    The client setting `ddraigLines` shows `ALL` of him, only the `IMPORTANT` lines (teaching, warnings and story, no
    reactions), or nothing (`OFF`). Change it in `config/dxdtensura-client.toml` or under Mods → Devil x Slime → Config.
    It covers Albion too.

On a screen too narrow for the box, his lines go to chat instead.

## Ddraig's Bargain

Before your Balance Breaker has awakened, Ddraig offers you a deal when you're about to lose.

**When.** Any enemy (a mob or a player) leaves you alive under 30% health, with or without an Explosion, in the
**Base form** or a Gift that hasn't awakened yet. In the Gift, a hit that also counts for the awakening roll rolls
first, and a miss brings the offer. Never in the Initial form. After you refuse, he waits 2 minutes before asking again.

**Time stops.** The offer opens a screen with Ddraig's eyes, his offer and the price.

- In singleplayer the game pauses.
- On a server nothing can hurt you while it is open (30 seconds at most), and your Explosion's clock waits.
- Closing it, letting the time run out, dying or logging out all count as refusing.

**The price: your off-hand slot, for good.** Anything in it goes back to your inventory (or drops at your feet when the
inventory is full), and swapping hands does nothing. No shields or totems in the off-hand ever again.

**The deal.** The Balance Breaker mode unlocks, even in the Base form, and the Scale Mail forms right away with your
stacks and heals you to half health. Until it awakens properly, it is the **early Scale Mail**:

| | Early Scale Mail | Full Scale Mail |
|---|---|---|
| Longest it lasts | 30 s | 3 minutes |
| Flight | no | yes |
| A stack every | 5 s | 10 s |
| Countdown | always the full 10 s | 10 s, trained down to 1 s |
| Cooldown after | 10 minutes | 60 s or 5 minutes |
| Rage meter | as usual | as usual |

**Lifting the limits.** Reaching the Gift awakens your Balance Breaker for you (even while the armour is on), and
Ddraig tells you so. A successful roll in a Gift crisis lifts every limit too. Either way, the off-hand stays his.
Losing the Boosted Gear ends the deal.
