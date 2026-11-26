# Lantern Links

A small, original light-routing puzzle for the browser. Rotate the tiles to carry light from the glowing core to every lantern.

**▶ Play it free:** on [WebGame.fun](https://webgame.fun/), a site with free browser games (no download or sign-up). It is also playable on this repository's GitHub Pages site and on [itch.io](https://webgamefun.itch.io/lantern-links).

## How to play
- **Tap or click** a tile to turn it clockwise. **Right-click**, or a **long-press** on a phone, turns it counter-clockwise.
- **Keyboard:** arrow keys move the highlight, and Space or Enter rotates the tile (Shift turns it the other way).
- A level is solved when every tile is part of one lit network and all lanterns glow.
- **Undo** with the button or the **Z** key, up to 3 times per level. A small badge on the button shows how many are left. **Restart** (or **R**) scrambles the level again (if you have made moves, press it twice).
- The arrows beside the level number go to the previous or next level. Next works once the level is solved.
- Each level has a **par**: the number of turns that solve it from the starting position, where a turn back (right-click or long-press) counts as one move. Finish within par for three stars.
- Levels never run out. The board gets bigger as you progress, from 9 to 12 tiles on level 1 up to 120 tiles. Its shape fits your screen: taller on a phone, wider on a computer. Your level, best moves, stars and the board you are working on are saved in your browser.
- Small sound effects are made in the browser with Web Audio, with no audio files. The speaker button mutes them.
- The book button shows a short how-to card. Where the browser allows it, a full screen button is shown too.

## How the levels are made
- When a level starts, the game picks the number of columns and rows. The tile count stays close to a target for that level, and the shape is the one whose square tiles fill the free space best.
- Each level is a random **spanning tree** on the grid, grown from the centre tile (a growing-tree search: a mix of depth-first and random steps).
- A spanning tree connects every cell with no loops, so every level is guaranteed to have a solution.
- Lanterns are the leaves of the tree (tiles with a single connection).
- Each tile is then turned a random number of quarter turns.
- The random generator is seeded by the level number, so level 12 on a board of the same shape is the same puzzle for everyone.

## Tech
- One `index.html` file with plain JavaScript, Canvas 2D and Web Audio.
- No libraries, no build step, no tracking. About 85 KB.
- Works on phones, tablets and desktops, and can be embedded in an iframe.

## Run locally
Open `index.html` in any modern browser, or serve the folder with any static server.

## License
MIT. See [LICENSE](LICENSE). Made by [WebGame.fun](https://webgame.fun/).

Logo lettering based on Fredoka, SIL Open Font License.

## Changelog
- **1.2 (2026-11-14):** on wide screens the title, stats and buttons move to a side panel, so the board gets even space above and below. Spacing is more even and the background is softer.
- **1.3 (2026-11-14):** on phones and other tall screens the title, stats, board and buttons sit together in the middle, with the stats shown as tiles and larger buttons in two rows.
- **1.4 (2026-11-15):** Undo is limited to 3 uses per level. The button shows how many are left, and Restart or a new level gives all 3 back.
- **1.5 (2026-11-15):** bug fixes (Lit counts tiles, no stray win card, side panel fits at 800×600, timer and sound pause when hidden or in help, Restart asks once, Next only after a solve, a message when undos run out, reduced-motion support) and nicer feel: the board in progress survives a reload, long-press turns a tile back, light spreads along the path, and the board redraws only when something changes.
- **1.6 (2026-11-15):** the board shape now fits the screen (for example 4×6 on a phone and 5×4 on a wide screen), so less space is left empty. New controls: large Undo and Restart buttons with an undo badge, level arrows with the level's stars, Moves, Lit and Time tiles, a book button for how to play and a full screen button.
- **1.7 (2026-11-16):** new look for the board: pipes drawn as round tubes, lanterns with a glass body and a small flickering flame when lit, and a warmer glow. The title is now a logo with a small lantern, and the lantern is also the page icon. Small tiles are drawn with less detail so they stay clear. The rules, levels and saves are unchanged.
- **1.7.1 (2026-11-19):** the board's gold frame now shows on the left edge too in the wide (landscape) layout.
- **1.8 (2026-11-22):** a new "How to play" card: four short steps, each with a small picture, plus the level arrows and key shortcuts underneath (keys are shown only on devices with a keyboard). It shrinks to fit short screens. The rules, levels and saves are unchanged.
- **1.9.1 (2026-11-26):** a clearer win card. It shows the level number, a title that matches your stars (Perfect glow!, Nicely lit!, All lanterns lit!), a short line on how you did against par, Moves, Par and Time in three boxes, and a New best badge when you beat your record. Below three stars the Replay button reads Try again. The focus ring on Next level now shows only when you play with the keyboard.
- **1.9 (2026-11-26):** bug fixes. Par is now fair: a turn back counts as one move, so par is lower on most levels (best moves and stars you already have are kept). Levels 1 to 5 are small on every screen (about 9 to 20 tiles). Winning a level no longer scrolls the page the game is embedded in, and the game no longer takes the keyboard from that page until you click it. The level arrows ask before they throw away a board with moves, like Restart does. Holding R or Z no longer skips the Restart question or uses up all undos. Screen readers no longer read the timer every second, and the win is announced. The how-to card fits short screens (its text scrolls, the Play button stays in view), very small and very short windows stay usable, odd saved data can no longer show "NaN", the flame flicker stops behind the win card, and buttons no longer zoom on a double tap on iPhone.
- **1.1 (2026-11-14):**
  - The board is now centred and sized to the largest square that fits any screen or iframe.
  - Added undo, par and star ratings, a timer, sound with a mute button, a how-to-play card and a win animation.
  - Added keyboard shortcuts Z and R.
- **1.0 (2026-11-12):** first release.
