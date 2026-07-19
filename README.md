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
- `collapse.html` — **Collapse**, a divide *puzzle*: you start with a full board
  and no spawns, and must swipe to slide-and-divide until a single tile remains.
  Every level is generated in reverse (and solver-checked) so it's guaranteed
  solvable; clear one to get a harder, bigger level.
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
- **Only composite (non-prime) numbers spawn**, starting with the ten smallest
  (`4, 6, 8, 9, 10, 12, 14, 15, 16, 18`). Primes only ever show up as *results*
  of a division; `1`s are still produced in-game when two equal tiles divide.
- **Levels:** every 15 spawns, the level ticks up and one bigger composite joins
  the spawn pool. Small numbers stay in the mix, so the board keeps moving while
  the ceiling slowly rises. Each level-up pops a big **Level N** over the board,
  pulses the board, and recolors the tiles: they're **monochrome**, all sharing
  one hue that changes with every level (values are told apart by shade) — so
  every level looks a little different.
- Pick a **grid size** (4×4 / 5×5 / 6×6). There's no difficulty setting — the
  levels are the difficulty curve.
- The header shows your current **Score**, current **Level**, and **Best** — and
  the Best box also shows the **max level reached**. Score, best score, and max
  level are saved per grid size, along with your in-progress game.

## Collapse — how to play

- A **puzzle** built on Divide's rules. You start with a **full board** of numbers
  and **no tiles ever spawn** — your job is to **reduce the whole board to a single
  tile**.
- **Swipe** (or arrow keys / WASD) to slide every tile to a wall; adjacent tiles
  combine when one divides the other (`larger ÷ smaller`; equal pairs → `1`, and a
  `1` is a divide-through identity — no annihilation here).
- Reduce everything to **one tile** to solve the level; each solve hands you a
  **harder, sometimes bigger** level (4×4 → 5×5 → 6×6, with larger numbers and more
  prime factors in play).
- **Undo** (`u`), **Restart** (`r`) the level, or ask for a **Hint** (`h`) — the hint
  flashes the direction of a known solving move (and warns you if the current
  position is a dead end).
- Every level is generated **in reverse** from a single tile and then
  **solver-verified**, so it is guaranteed to be solvable. Level, moves, best level
  reached, and your in-progress board are saved on your device.

## Enabling GitHub Pages (one-time)

Repo **Settings → Pages → Build and deployment → Source: Deploy from a branch**,
branch **`main`**, folder **`/ (root)`**. Every push to `main` then updates the site.
