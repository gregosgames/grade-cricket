# Grade Cricket

Arcade cricket built on two meters: **Swagger** when you bat, **Hostility**
when you bowl. Stick-figure 2D, played from behind the batter, browser and mobile.

The thesis is dominance, not accumulation. Most cricket games reward you for
staying in. This one rewards you for taking the game away from someone.

**Play:** open `index.html`. That's the whole game — one self-contained file,
no build step, no external requests, no asset files. The art is drawn and the
audio is synthesised.

## Controls

**Batting** — one thumb, anywhere on the screen.

| | Touch | Keyboard |
|---|---|---|
| Aim | drag from wherever you pressed | `1`–`6` |
| Control shot | tap and release quickly | short `Space` |
| Attacking shot | hold, then release on the ball | hold `Space` |
| Premeditate + raise the backlift | start holding *before* the bowler lets go | — |
| Mute | — | `M` |

The release is your timing, how long you held is your intent, and where you
dragged is your zone. Holding from before the bowler's release raises your
backlift — a wider window for having shown your hand. From island senior the
bowler reads it and changes his length.

**Bowling** — one gesture, untimed.

| | Touch | Keyboard |
|---|---|---|
| Aim line and length | drag to the spot, **let go to bowl** | arrow keys, then `Space` |
| Pick the delivery | tap a chip | `1`–`3` |
| Change bowler | tap between overs | — |

Up the screen pitches it fuller; drag toward the side you want it on. There
is nothing to time, so the skill is where to put it and which ball to bowl.
Missing your bowler's natural length is what costs you accuracy.

**Bowler types.** Fast (heavy, bouncer, yorker), swing (out, in, slower),
seam (seam up, cross, cutter), medium pace, finger spin (off break, arm ball,
top spinner) and wrist spin (leg break, googly, slider). Swing moves in the
air; seam and spin move off the pitch. A new bowler comes on every over when
you bat.

**The wagon wheel** in the corner shows the ground, the field and where your
last shot went — from behind the stumps, anything played behind square leaves
the frame almost immediately.

## What's here

The playable slice: both batting and bowling schemes complete, two tiers
(village club and island senior), the Dossier stub that puts a fielder in your
best scoring zone, a five-over quick match through to a result card, and
endless practice modes for each discipline.

Not built: the career — regional and international tiers, selection, seasons,
the Ledger, multi-day cricket.

## Design

`docs/DESIGN.md` is the full concept and design document, with an
implementation section at the end covering what was built, where it departs
from the design and why, and the measured balance figures.

## Shipping to a portal

`Portal` in `index.html` is a guarded shim around the CrazyGames SDK
(`loadingStart`, `loadingStop`, `gameplayStart`, `gameplayStop`, `happytime`).
Every call is wrapped, so the build behaves identically with the SDK absent.
To ship, add the SDK script tag; nothing else changes.

Landscape-first at a logical 1280×720, letterboxed to any screen. Portrait
shows a rotate prompt and is dismissible.
