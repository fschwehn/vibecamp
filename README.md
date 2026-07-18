# vibecamp

A tiny **pocket arcade** — a set of self-contained, mobile-first games served from
GitHub Pages. No build step, no dependencies: each game is a single HTML file.

## Structure

- `index.html` — the hub/home page that lists the games as tappable cards.
- `divide.html` — **Divide**, a 2048-style game built around division.
- `equate.html` — **Equate**, a sliding game with numbers *and* operators
  (`+ − ×`); slide a number into an operator to arm it (`5−`), then into another
  number to run it. Only primes spawn; numbers and operators spawn alternately.
- `ascend.html` — **Ascend**, a leveled variant of Divide: only composite
  (non-prime) numbers spawn, starting small, and the spawn pool grows a level at
  a time — the deeper you go, the bigger the numbers.
- Add a new game by dropping a self-contained `<name>.html` in the repo and
  adding one entry to the `GAMES` array in `index.html`.

## Play it

Once GitHub Pages is enabled, the arcade is live at:
`https://<your-username>.github.io/vibecamp/`

## Divide — how to play

- **Swipe** (or arrow keys / WASD) to slide the tiles.
- Two tiles combine when the smaller divides the larger → result is `larger ÷ smaller`.
- Equal tiles divide to `1`; a `1` annihilates any tile it merges with.
- Pick a **difficulty** (Calm / Mild / Normal / Hard) — it changes the spawn mix.
- Pick a **grid size** (4×4 / 5×5 / 6×6).
- Set the **max number** (8–512) — the largest spawnable tile. The spawn pool is
  built from it at runtime, so raise it for more complexity or lower it for a
  gentler game.
- **Tap a tile** to pop up its divisors — the smaller numbers it can combine
  with (1 and the number itself are left out; primes are flagged).
- Tap **↻ Replay** (or press `r`) to re-watch the last move in slow motion: the
  board slides, then every pair is highlighted and collapsed in turn with a pill
  spelling out the division (e.g. `12 ÷ 3 = 4`). It's purely a visual aid — it
  never changes your score — so replay it as many times as you like.
- Score, best score (per difficulty, grid size *and* max number), and your
  in-progress game are saved on your device.

## Ascend — how to play

- A leveled variant of **Divide** — same slide-and-divide rules, but the spawn
  pool is different and it grows as you play.
- **Only composite (non-prime) numbers spawn**, starting with the smallest ones
  (`4, 6, 8, 9`). Primes only ever show up as *results* of a division; `1`s are
  still produced in-game when two equal tiles divide.
- **Levels:** every 10 spawns, the level ticks up and one bigger composite joins
  the spawn pool. Small numbers stay in the mix, so the board keeps moving while
  the ceiling slowly rises.
- Pick a **grid size** (4×4 / 5×5 / 6×6). There's no difficulty setting — the
  levels are the difficulty curve.
- The header shows your current **Score**, current **Level**, and **Best** — and
  the Best box also shows the **max level reached**. Score, best score, and max
  level are saved per grid size, along with your in-progress game.

## Enabling GitHub Pages (one-time)

Repo **Settings → Pages → Build and deployment → Source: Deploy from a branch**,
branch **`main`**, folder **`/ (root)`**. Every push to `main` then updates the site.
