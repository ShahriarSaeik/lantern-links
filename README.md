# Lantern Links

A small, original light-routing puzzle for the browser. Rotate the tiles to carry light from the glowing core to every lantern.

**▶ Play it free:** on [WebGame.fun](https://webgame.fun/), a site with free browser games (no download or sign-up). It is also playable on this repository's GitHub Pages site.

## How to play
- **Tap or click** a tile to turn it clockwise. **Right-click**, or a **long-press** on a phone, turns it counter-clockwise.
- **Keyboard:** arrow keys move the highlight, and Space or Enter rotates the tile (Shift turns it the other way).
- A level is solved when every tile is part of one lit network and all lanterns glow.
- **Undo** with the button or the **Z** key, up to 3 times per level. **R** scrambles the level again (if you have made moves, press it twice).
- Each level has a **par**: the number of clockwise taps that solve it from the starting position. Finish within par for three stars.
- Levels never run out. The board grows from 4×4 to 10×10 as you progress. Your level, best moves, stars and the board you are working on are saved in your browser.
- Small sound effects are made in the browser with Web Audio, with no audio files. The speaker button mutes them.

## How the levels are made
- Each level is a random **spanning tree** on the grid, built with a randomised depth-first search from the centre tile.
- A spanning tree connects every cell with no loops, so every level is guaranteed to have a solution.
- Lanterns are the leaves of the tree (tiles with a single connection).
- Each tile is then turned a random number of quarter turns.
- The random generator is seeded by the level number, so level 12 is the same puzzle for everyone.

## Tech
- One `index.html` file with plain JavaScript, Canvas 2D and Web Audio.
- No libraries, no build step, no tracking. About 40 KB.
- Works on phones, tablets and desktops, and can be embedded in an iframe.

## Run locally
Open `index.html` in any modern browser, or serve the folder with any static server.

## License
MIT. See [LICENSE](LICENSE). Made by [WebGame.fun](https://webgame.fun/).

## Changelog
- **1.2 (2026-11-14):** on wide screens the title, stats and buttons move to a side panel, so the board gets even space above and below. Spacing is more even and the background is softer.
- **1.3 (2026-11-14):** on phones and other tall screens the title, stats, board and buttons sit together in the middle, with the stats shown as tiles and larger buttons in two rows.
- **1.4 (2026-11-15):** Undo is limited to 3 uses per level. The button shows how many are left, and Restart or a new level gives all 3 back.
- **1.5 (2026-11-15):** bug fixes (Lit counts tiles, no stray win card, side panel fits at 800×600, timer and sound pause when hidden or in help, Restart asks once, Next only after a solve, a message when undos run out, reduced-motion support) and nicer feel: the board in progress survives a reload, long-press turns a tile back, light spreads along the path, and the board redraws only when something changes.
- **1.1 (2026-11-14):**
  - The board is now centred and sized to the largest square that fits any screen or iframe.
  - Added undo, par and star ratings, a timer, sound with a mute button, a how-to-play card and a win animation.
  - Added keyboard shortcuts Z and R.
- **1.0 (2026-11-12):** first release.
