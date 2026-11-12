# Lantern Links

A small, original light-routing puzzle for the browser. Rotate the tiles to carry light from the glowing core to every lantern.

**▶ Play it free:** on [WebGame.fun](https://webgame.fun/), a site with free browser games (no download or sign-up). It is also playable on this repository's GitHub Pages site.

## How to play
- **Tap or click** a tile to turn it clockwise. **Right-click** turns it counter-clockwise.
- **Keyboard:** arrow keys move the highlight, and Space or Enter rotates the tile (Shift turns it the other way).
- A level is solved when every tile is part of one lit network and all lanterns glow.
- Levels never run out. The board grows from 4×4 to 10×10 as you progress, and your level and best move counts are saved in your browser.

## How the levels are made
- Each level is a random **spanning tree** on the grid, built with a randomised depth-first search from the centre tile.
- A spanning tree connects every cell with no loops, so every level is guaranteed to have a solution.
- Lanterns are the leaves of the tree (tiles with a single connection).
- Each tile is then turned a random number of quarter turns.
- The random generator is seeded by the level number, so level 12 is the same puzzle for everyone.

## Tech
- One `index.html` file with plain JavaScript and Canvas 2D.
- No libraries, no build step, no tracking. About 15 KB.
- Works on phones, tablets and desktops, and can be embedded in an iframe.

## Run locally
Open `index.html` in any modern browser, or serve the folder with any static server.

## License
MIT. See [LICENSE](LICENSE). Made by [WebGame.fun](https://webgame.fun/).
