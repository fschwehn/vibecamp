# vibecamp

A tiny **pocket arcade** — a set of self-contained, mobile-first games served from
GitHub Pages. No build step, no dependencies: each game is a single HTML file.

## Structure

- `index.html` — the hub/home page that lists the games as tappable cards.
- `divide.html` — **Divide**, a 2048-style game built around division.
- `equate.html` — **Equate**, a sliding game with numbers *and* operators
  (`+ − ×`); slide a number into an operator to arm it (`5−`), then into another
  number to run it. Only primes spawn; numbers and operators spawn alternately.
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
- Toggle **Debug → Step merges** to replay each move one combine at a time —
  the board slides, then every pair is highlighted and collapsed in turn with a
  pill spelling out the division (e.g. `12 ÷ 3 = 4`). Toggle it on/off any time.
- Score, best score (per difficulty, grid size *and* max number), and your
  in-progress game are saved on your device.

## Enabling GitHub Pages (one-time)

Repo **Settings → Pages → Build and deployment → Source: Deploy from a branch**,
branch **`main`**, folder **`/ (root)`**. Every push to `main` then updates the site.
