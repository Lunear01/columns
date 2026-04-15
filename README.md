# CSC258 Assembly Project: Columns

A fully-featured implementation of the classic **Columns** puzzle game, written entirely in **MIPS assembly language** for the University of Toronto's CSC258 (Computer Organization) course.

> **Note:** The source code is encrypted (`columns.zip.gpg`) to preserve academic integrity.

---

## Screenshots

<table>
  <tr>
    <td align="center"><b>Piece Spawning</b></td>
    <td align="center"><b>Mid-Game</b></td>
  </tr>
  <tr>
    <td><img src="assets/Screenshot From 2026-04-15 11-49-00.png" width="300"/></td>
    <td><img src="assets/Screenshot From 2026-04-15 11-49-15.png" width="300"/></td>
  </tr>
  <tr>
    <td align="center"><b>Stacking Up</b></td>
    <td align="center"><b>Game Over</b></td>
  </tr>
  <tr>
    <td><img src="assets/Screenshot From 2026-04-15 11-49-23.png" width="300"/></td>
    <td><img src="assets/Screenshot From 2026-04-15 11-49-38.png" width="300"/></td>
  </tr>
</table>

---

## About the Game

Columns is a color-matching puzzle game in the style of classic arcade titles. Three-color pieces fall into a vertical well; the player rotates the colors within each piece and positions it horizontally to form matches of three or more identical colors in a row, column, or diagonal. Matched tiles are cleared, remaining tiles fall, and the game ends when the stack reaches the top of the well.

### Features

- Smooth piece falling and gravity mechanics
- Horizontal movement and in-place color rotation
- Next-piece preview panel
- Match detection across rows, columns, and diagonals
- Pause and resume game
- Restart game
- Cascade clears after matched tiles are removed
- Pixel-font **GAME OVER** screen with animations
- Rendered using bitmap display

---

## Controls

| Key | Action |
|-----|--------|
| `a` | Move piece left |
| `d` | Move piece right |
| `s` | Soft drop |
| `w` | Rotate colors within piece |
| `r` | Restart game | 
| `p` | Pause/resume game |
| `q` | End game session |

---

## Running the Game

This project runs in the **MARS/SATURN MIPS Simulator** with the bitmap display and keyboard MMIO tools enabled.

1. Install [MARS](http://courses.missouristate.edu/KenVollmar/MARS/) [SATURN](https://github.com/1whatleytay/saturn).
2. Decrypt the source (requires the key):
   ```bash
   gpg --decrypt columns.zip.gpg | tar -xz
   ```
3. Open MARS/SATURN and load `columns.asm`.
4. Enable **Tools → Bitmap Display** and **Tools → Keyboard and Display MMIO Simulator**.
5. Configure the bitmap display:
   - Unit width/height: `8`
   - Display width: `256`, Display height: `256`
   - Base address: `0x10008000` (static data)
6. Click **Assemble**, then **Run**.

---

## License

See [LICENSE](LICENSE) for details.
