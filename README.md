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
- Cascade clears after matched tiles are removed
- Pixel-font **GAME OVER** screen
- Rendered using the MARS bitmap display

---

## Controls

| Key | Action |
|-----|--------|
| `A` / `←` | Move piece left |
| `D` / `→` | Move piece right |
| `S` / `↓` | Soft drop |
| `W` / `↑` | Rotate colors within piece |

---

## Running the Game

This project runs in the **MARS MIPS Simulator** with the bitmap display and keyboard MMIO tools enabled.

1. Install [MARS](http://courses.missouristate.edu/KenVollmar/MARS/) (requires Java).
2. Decrypt the source (requires the key):
   ```bash
   gpg --decrypt columns.zip.gpg | tar -xz
   ```
3. Open MARS and load `columns.asm`.
4. Enable **Tools → Bitmap Display** and **Tools → Keyboard and Display MMIO Simulator**.
5. Configure the bitmap display:
   - Unit width/height: `8`
   - Display width: `512`, Display height: `512`
   - Base address: `0x10008000` (static data)
6. Click **Assemble**, then **Run**.

---

## Implementation Highlights

- Written entirely in **MIPS32 assembly** — no high-level language constructs
- Manual memory management using the MARS static data segment
- Interrupt-driven keyboard input via memory-mapped I/O
- Frame-based game loop implemented with busy-wait timing
- Recursive flood-fill style match detection across all three axes

---

## Course Context

**CSC258 — Computer Organization**  
University of Toronto  
Covers digital logic, processor design, and low-level programming. This project serves as the capstone assembly programming assignment.

---

## License

See [LICENSE](LICENSE) for details.
