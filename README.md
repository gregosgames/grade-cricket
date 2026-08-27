# Grade Cricket

Arcade cricket built on two meters: **Swagger** when you bat, **Hostility**
when you bowl. Stick-figure 2D, side-on, browser and mobile.

The thesis is dominance, not accumulation. Most cricket games reward you for
staying in. This one rewards you for taking the game away from someone.

**Play:** open `index.html`. That's the whole game — one self-contained file,
no build step, no external requests, no asset files. The art is drawn and the
audio is synthesised.

## Controls

One thumb does everything.

| | Touch | Keyboard |
|---|---|---|
| Aim | drag from wherever you pressed | `1`–`6` |
| Play the shot | release on the ball | release `Space` |
| Control shot | tap and release quickly | short `Space` |
| Attacking shot | hold, then release on the ball | hold `Space` |
| Premeditate + raise the backlift | start holding *before* the bowler lets go | — |
| Bowl | drag to set your line, tap the length bar, tap the seam dial | `Space` |
| Mute | — | `M` |

Holding from before the bowler's release raises your backlift: a wider timing
window for having shown your hand. From island senior the bowler reads it and
changes his length.

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
