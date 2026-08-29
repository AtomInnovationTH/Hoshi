# Hoshi

A quiet valley, generated entirely by code — and a hang-glider to read its air.

This is a fork of a lovely CodePen valley (credit below) with one mission: **make the flying real.**
Real airspeed, real lift, real consequences for pointing the nose the wrong way. The valley was
already worth a walk; now it's worth an hour in the air.

**[▶ Play now](https://atominnovationth.github.io/Hoshi/)**

[![The viaduct over the river at first light, the village on the far bank, mountains behind](screenshots/hero.png)](screenshots/hero.png)

## Flying in thirty seconds

1. Click to be there.
2. **Hold `SPACE`** — a short hold and your feet leave the grass. Keep holding to climb.
3. Let go and glide. The mouse is your stick. Find something going up and stay in it.

That's genuinely all you need. Everything below just makes you better at it.

## Controls

| Key | In the air |
|---|---|
| Mouse / `↑` `↓` | Steer the glide (stick convention: `↓` pulls the nose up) |
| `SPACE` | Hold to take off · tap or hold to flap and climb |
| `W` | Tuck for speed (`+ Shift` tucks harder) |
| `S` | Spread the wings & slow down |
| `A` `D` / `←` `→` | Banked turn — slow **and** steep is a tight circle, which is how you core a thermal |
| `CTRL` | Dive |
| `F` | Land (the flare is taken care of) |
| `T` | Summon the train — its stack plume is lift too |
| `M` / `B` | Rain / squall |
| `H` `TAB` | Settings · HUD |

## Reading the air

The air is the whole game, and it's all visible if you know where to look:

- **Ridge lift** — wind striking a slope has nowhere to go but up. Fly the windward face and the
  hill carries you for free.
- **Thermals** — columns of rising air, marked the way real pilots find them: **chimney smoke
  leans into them and birds circle inside them**. Follow the birds; they're never wrong.
- **Thermals don't stop at the puffy bits** — ride one to cloudbase and the cloud keeps pulling.
  You can climb into the white, get spat out the top, and pick your next cloud from above.
- **Trees are soft, but they're there** — brush a canopy and you'll hear it, feel the drag, and
  scatter the birds.

## Instruments

The essentials sit top-right while you're airborne:

- **SPD** — airspeed in km/h. Speed is life; watch it in turns.
- **ALT** — altitude in metres.
- **VARIO** — a needle **and an audio tone**: climbing beeps, rising pitch, faster with stronger
  lift. Sink is silent. You can fly lift by ear with your eyes on the scenery.
- **WIND** — where the air is pushing you, relative to your nose.
- **Stall warning** — hold the nose too high and bleed too much speed and the wing lets go: a
  buffet, a warning, and the nose drops until it's flying again. Give it room near the ground.

## Run it yourself

It's a single file. Serve the folder and open it:

```sh
python3 -m http.server 8000
# → http://localhost:8000/
```

`index.html` is the whole game: no build step, no assets, nothing to install
(three.js loads from a CDN). Every blade of grass, ripple, cloud and cottage is computed at load.

[![The river under the viaduct arches, raking light](screenshots/overlook.png)](screenshots/overlook.png)

## Credits and licence

- **Original scene:** this project is a fork of the beautiful procedural valley by
  [lentils801 on CodePen](https://codepen.io/editor/lentils801/pen/019f9b4b-10d7-7f77-817f-f4eb83fdb289) —
  the terrain, the mood, the whole reason to be here. Thank you. This fork's contribution is the
  flying: the hang-glider model (speed-to-fly polar, stall, swoop, ground effect), the living air
  (ridge lift, thermals, cloud suck, gust turbulence), the instruments, and the tuning.
- **[three.js](https://github.com/mrdoob/three.js)** (MIT) — the only library used.
- The flight model is kept honest by a headless-browser test harness (flight envelope, air fields,
  perf budgets) that lives outside this repo.

[MIT](LICENSE), code and art alike.
