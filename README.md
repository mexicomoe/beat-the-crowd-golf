[README.md](https://github.com/user-attachments/files/30472915/README.md)
# Beat the Crowd — Golf

A one-day prediction game for spectators at a professional golf tournament. Scan a QR code, spend about a minute making picks before play, then watch a leaderboard move as the round happens.

**Your score is styled as a golf score.** You start at 83, good calls take strokes off, lowest score wins the day. The range is protected: never below 59, never above 84.5.

---

## What's in here

| File | What it is |
|---|---|
| `index.html` | **The demo.** The whole thing — one file. |

Open it by double-clicking. No internet needed: fonts, images and data are all inside the file, so it runs with the WiFi off and installs to a phone home screen.

---

## ⚠️ Read this before editing `index.html`

**This file contains about 31 versions stacked on top of each other.** Each round of changes added new definitions at the bottom rather than editing the old ones. You'll find comments like `v12 COVER (assignment wins over all prior)` and `v31: demo notes 1-11`.

**JavaScript runs the *last* definition of anything.** `scrTitle` is defined six times; only the sixth runs. Roughly a third of the file is code that never executes.

**What this means in practice:** if you change something and nothing happens, you edited a dead copy. Search for *every* occurrence and change the last one — or all of them.

The dead layers are harmless and were left alone deliberately. Stripping a third of a 4,800-line file is exactly the kind of change that breaks something invisibly, and there's no way to test it properly before the event.

---

## The current scoring — r4

| Setting | Value |
|---|---|
| Starting score | **83** |
| Floor (lowest possible) | **59** |
| Maximum strokes off | 24 — *calculated as start minus floor, never set directly* |
| Ceiling | 84.5 |

**The contests**

| Contest | Pays |
|---|---|
| Who Goes Low? — your man shoots the low round of the 25 | 2.0 / 3.0 / 5.0 by group · ties pay everyone |
| Best-score guess — call the day's low round | 2.0, minus 0.4 a stroke, nothing at 5+ off |
| Low Rounds — each of your five in the day's best scores | 1.5 top three · 0.5 in range |
| Skills — four bars, each of your five who clears one | 0.6 a man |
| Ace — any of your five holes out on a par 3 | 2.0 |
| Virtual Skins — your designated man wins your skins game | 2.0 |
| Bear Trap Snare — your designated man over 15·16·17 | −3.0 to **+1.5** |
| Who Birdies Next? — live, every 30 minutes | 0.5 birdie · 1.0 eagle · 5.0 day cap |

**The Bear Trap holds the only penalties in the game.** Add one anywhere else and the 84.5 ceiling moves.

**The four Skills bars** (calibrated for PGA National on 100 real rounds): Go Long −4 across the par 5s · Get Shorty −2 across the par 3s · Clean Card bogey-free · Bounce Back four bogeys answered with a birdie.

---

## What changed in r4

1. **"The Field" removed.** It paid 1.5 for something that happened ~70% of days and returned about twenty times what any named pick did. No price could fix it.
2. **Who Goes Low is scoped to the card** — the low round among the 25, not the tournament. Before this, the low round came from off the card most days, so *every* patron who named a man lost.
3. **Skills is threshold-based**, computed from hole-by-hole scores. No paid statistics feed.
4. **All five players score everywhere.** The old best-of-five rule is gone.
5. **Low Rounds** replaces top finishers, scored on the day's round scores rather than tournament standing. Thirty values became three.
6. **Base 78 → 83, floor 60 → 59.** 59 is the magic number in golf; a patron having an extraordinary day should be allowed to print it.
7. **Five birdie windows** instead of two, all from the real card.
8. **Sponsor slots** on every screen.

---

## The demo replays the real 2026 Cognizant Sunday

Nothing is staged.

- **Nicolai Højgaard and Brooks Koepka** both shot 65 — both in Group C, both paying 5.0, a genuine tie
- **Shane Lowry** led through 54 holes, then went 3-6-5 on the Bear Trap for +4 and lost the tournament
- **Nico Echavarria** won at −17 with a bogey-free round

Best possible card scores **62.3**. A card that misses everything scores **82.0**.

---

## Not in this repository

- **The scoring engine** — TypeScript, 44 tests passing, separate from the demo
- **The specification** — the master handoff document
- **The admin console specification** — what an operator can change without new code

---

## History

Every upload here is saved. Click **History** on any file to see every version and restore any of them. When you upload, write down what changed — that one line is what makes this worth doing.
