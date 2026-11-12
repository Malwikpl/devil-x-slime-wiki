# Dragon flight

Since **0.2.107**, flight on this mod's wings has two modes. **Hovering** is the flight you know: WASD, Space and Shift at your plain
flight speed, for aiming, fighting and building. **Soaring** is new: it has momentum, you steer by looking, a dive builds speed and a
climb bleeds it, and you can glide.

## Who soars

- [Devils](../races/devil.md), [Angels and Fallen Angels](../races/angels.md) and hybrids, on their wings.
- House Phenex's [wings of fire](../races/houses.md).
- [Valkyries](../races/valkyrie.md), on their runes, a little lighter (below).
- [Divine Dividing's](../divine-dividing/index.md) wings of light.
- Both Scale Mails ([red](../boosted-gear/balance-breaker.md) and [white](../divine-dividing/balance-breaker.md)), with every
  [Promotion form](../boosted-gear/promotion-forms.md), and [Cycle of Salvation's](../salvation-rose/index.md#cycle-of-salvation) wings.

It works in creative too while the wings are out. Tensura's own flight skills, plain creative flight, the Sea Dragon and Juggernaut
Drive's dragon fly as before.

## Starting

While flying, hold **Sprint** and **W**. You soar from your speed or the hover speed, whichever is faster, heading where you look.
Letting go of W or Sprint afterwards doesn't end it.

## The keys

| Key | While soaring |
|---|---|
| Mouse | Steers: the flight turns toward where you look, a little behind it |
| W | Flaps: gains speed up to cruise and holds a climb of up to about 60° |
| No key | Glides: you keep your momentum and lose it slowly when level (about 20 s from cruise to a stall) |
| Space | A boost flap, at the rhythm of your wings' own stroke. Held, it keeps flapping and tops you up to top speed |
| S | Air-brakes. Out of a dive the wings snap open and hold for a second or more, and you keep following the dive. Below the hover speed you're hovering again |
| Shift | Tucks the wings: a faster dive, up to **twice your cruise speed**, but you turn half as well |
| A or D, held | A small sideways slip and a little more bank |
| A or D, double-tapped | A **barrel roll**: a full turn that way with a slide of 5 blocks, at most once a second. It works while hovering too. It only moves you; it doesn't make you invulnerable |

While you soar, Minecraft's own up and down (Space and Shift) are off: only the mouse climbs and dives.

## Speeds

- **Hovering** is your plain flight speed.
- **Cruise** is the old sprint-flight speed, with every class, mastery and form bonus. A Satan-class Devil cruises at about 44 blocks a
  second.
- **A dive** reaches 1.5 times cruise, and **a Shift dive** twice cruise. Opened up again, the extra speed bleeds off over a second or
  two.

## Back to hovering

- Braking below the hover speed.
- A stall: too slow on a climb, or at the end of a long glide. With the keys still held you stay hovering: let go of W or Sprint, or press
  Sprint again, to soar.
- Water, lava or any other fluid.
- A wall or a ceiling that takes more than half your speed. It does no damage.
- A stop: Balor View, a time stop or a cutscene.

Landing, being Grounded or putting the wings away ends flight as before. Knockback still pushes you while you soar.

## Valkyries

Valkyries fly by their runes, so their soaring is lighter: quicker turns, W climbs anything, even straight up, with no stall, a dive tops
out at 1.2 times cruise, with no key they slow to a hover in about 2 s, and the bank and the camera's tilt are half.

## What you see

- **The body** lies along the flight: flat when level, head down in a dive, banked up to 60° in a turn, tipped back when braking.
- **The wings** beat and pose by what you're doing: big strokes in a hover (slower and heavier the bigger the wings), one huge stroke on a
  boost, spread and still in a glide, swept back in a dive, a narrow V when tucked, cupped forward when braking.
- **Trails**: thin white ribbons stream from the wingtips (a Valkyrie's hands) at cruise and above, with a little glow at night.
- **The camera** tilts with the bank, up to 45°, spins with a barrel roll and rises behind you in third person. Aiming still goes where
  the crosshair is. The view widens up to 15% in a dive (Minecraft's "FOV Effects" slider applies).
- **The wind** rises with your speed, for you alone.
- **Other players** see your soaring from your movement: the body, the bank, the wings and the trails, and your barrel rolls.

[Rias](../races/rias.md) and the [Castle Town's](../world/castle-town.md) flying Devils beat their wings the new way too.

## Settings

In the client config (Mods → Devil x Slime → Config), see [Client settings](../reference/configuration.md#client-settings):

- `dragonFlight` (on): off turns all of it off, back to the old flight and wings.
- `flightCameraTilt` (100%): how far the camera tilts in a bank, 0 for none.
- `flightRollSpin` (on): spins the camera with a barrel roll.
- `flightLean` and `wingMotion` work as before: the body's lean and the living wings.
