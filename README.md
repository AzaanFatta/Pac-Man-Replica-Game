# 🟡 Pac‑Man Replica (Python + Pygame)

![Gameplay](assets/screenshots/gameplay.png)

> A from‑scratch, modernized Pac‑Man built with **Python** and **Pygame** — featuring smooth animation, ghost AI personalities, power‑up logic, score/lives UI, and a resizable window that preserves a crisp retro vibe.

<p align="center">
  <a href="https://img.shields.io/badge/python-3.10%2B-blue.svg"><img alt="Python" src="https://img.shields.io/badge/python-3.10%2B-blue.svg"></a>
  <a href="https://img.shields.io/badge/pygame-2.x-green.svg"><img alt="Pygame" src="https://img.shields.io/badge/pygame-2.x-green.svg"></a>
  <a href="https://img.shields.io/badge/platform-macOS%7CWindows%7CLinux-informational"><img alt="Platforms" src="https://img.shields.io/badge/platform-macOS%7CWindows%7CLinux-informational"></a>
</p>

---

## ✨ Highlights

- **Arcade‑style board renderer** — walls, arcs, tunnels, pellets, and power pellets drawn from a tile map (`boards`) for pixel‑perfect paths.
- **Ghost AI personalities** — `Blinky`, `Pinky`, `Inky`, and `Clyde` each use distinct turning heuristics and dynamic targets (chase, scatter, frightened, return‑to‑box when eaten).
- **Fully animated player** — 4‑frame sprite mouth animation with rotations for all directions.
- **Game states** — startup countdown, power‑up timer with flicker, win/lose screens, lives UI, and score accumulation.
- **Performance‑friendly loop** — 60 FPS tick with tight collision checks and minimal allocations.
- **Resizable window** — one‑line `pygame.SCALED | pygame.RESIZABLE` gives instant scaling while keeping all game logic in a stable 900×950 “logical resolution.”

---

## 🎮 Controls

| Key | Action |
|---|---|
| ⬅️ / ➡️ / ⬆️ / ⬇️ | Move Pac‑Man (queued turns supported) |
| **Space** | Restart after win/lose |
| **Esc / Close** | Quit |

---

## 🧠 Ghost Behavior (at a glance)

Each ghost is a `Ghost` instance with:
- **State:** `direction`, `speed`, `dead` (eaten), `in_box`, and a **dynamic target**.
- **Per‑tile collision** via board grid (R/L/U/D) using the current logical tile (`num1`, `num2`) so turns only occur at legal junctions.
- **Targeting during normal mode:**
  - **Blinky**: direct pursuit (straight‑line bias; only turns on collision when blocked).
  - **Pinky**: prioritizes horizontal choices; vertical only on collision → good ambusher.
  - **Inky**: favors vertical turns; horizontal turns primarily on collision → pinches vertically.
  - **Clyde**: opportunistic; switches directions when advantageous to close distance.
- **Power‑up (frightened):** ghosts flee to a “runaway” target based on the player quadrant; if eaten, they switch to `dead` and head to **return target** (ghost box), then revive.

> See `Ghost.move_blinky/inky/pinky/clyde()` for the micro‑policies and `get_targets()` for the chase/scatter/return logic.

---

## 🧱 Board & Collision System

- The maze is driven by `boards` (a 2D int grid). Each integer encodes a **tile primitive**:
  - `1` pellet • `2` power pellet • `3–8` wall segments/arcs • `9` door into the ghost box.
- The renderer uses the grid to draw lines/arcs at scaled tile centers — ensuring **identical gameplay feel** across resolutions.
- Player & ghosts use **center‑point sampling** plus small radii to check collision against tiles at junctions only, enabling smooth turns without clipping.

---

## 🖼️ UI & Game States

- Bottom HUD shows **Score** and **Lives** (sprite icons).  
- **Power‑up indicator** lights up while energized; flickers before expiration.  
- Modal cards for **Game Over** and **Victory** with instant restart on **Space**.

---

## 🏎️ Performance Notes

- Fixed timestep via `timer.tick(fps)` at **60 FPS**.
- Minimal per‑frame allocations; images pre‑scaled to 45×45 for consistent blits.
- Tunnel wrap and box‑bounds checks use branch‑light comparisons for speed.

---

## 🧪 Testing

A `unittest` test file can be added (e.g., `tests/test_game.py`) to validate deterministic helpers like `check_position`, `check_collide`, or target selection. Ensure test classes start with `Test` and methods with `test_` so discovery isn’t an “Empty suite.”

---

## 🚀 Getting Started

### Prereqs
- Python **3.10+**
- `pip install -r requirements.txt` (create a venv if you prefer)

`requirements.txt`:
```txt
pygame>=2.5.0
```

### Run
```bash
python Pacmann.py
```

> On macOS, the window is resizable. The game renders to a logical 900×950 surface and scales up/down smoothly.

---

## 🧩 Project Structure (suggested)

```
Pac-Man-Replica-Game/
├─ assets/
│  ├─ ghost_images/
│  │  ├─ red.png pink.png blue.png orange.png powerup.png dead.png
│  ├─ player_images/
│  │  ├─ 1.png 2.png 3.png 4.png
│  └─ screenshots/
│     └─ gameplay.png    # ← put your screenshot here
├─ board.py              # tile map(s) for the maze
├─ Pacmann.py            # main game loop & entities
├─ requirements.txt
└─ README.md
```

---

## 🧮 Key Implementation Details

- **Logical Resolution:** `WIDTH=900`, `HEIGHT=950`. All tile math derives from `(HEIGHT-50)//32` and `WIDTH//30` so board geometry scales consistently.
- **Animation:** 4‑frame player cycle using `counter // 5` for a natural mouth‑open cadence at 60 FPS.
- **Input Buffering:** `direction_command` queues the next desired direction; it commits only when `turns_allowed` allows it at a junction, delivering responsive cornering.
- **Power‑Up Flow:** eating a power pellet sets `powerup=True` and starts `power_counter`; ghosts slow (`ghost_speeds=[1,1,1,1]`) and switch sprites. Eaten ghosts grant exponential points `score += (2 ** eaten_count) * 100` and return to box. Flicker triggers near timeout.
- **Tunnel Wrap:** left/right teleport uses sprite bounds to re‑enter from the opposite side without visible pop.
- **Reset:** spacebar re‑seeds positions, resets counters, deep‑copies `boards` to restart cleanly.

---

## 🛣️ Roadmap Ideas

- Sound effects & background loop (waka, power, ghost eat, death).
- High‑score persistence.
- Difficulty curve (ghost speed ramps, pellet clustering, smarter targeting).
- Multiple mazes / dynamic board loader.
- Touch / controller input.
- CI for linting & tests (pre‑commit hooks, GitHub Actions).

---

## 🙌 Credits

- Built by **Azaan Fatta** in Python/Pygame.
- Inspired by the original **PAC‑MAN®** by Namco (all trademarks are property of their respective owners).
- Thanks to the Pygame community and open‑source contributors.

---

## 📸 Adding Screenshots & GIFs

1. Create the folder: `assets/screenshots/`
2. Save your screenshot as `assets/screenshots/gameplay.png` (this README references that path).
3. (Optional) Add a short gameplay GIF and include it like:

```markdown
![GIF](assets/screenshots/gameplay.gif)
```

---

## 📄 License

MIT — use, modify, and have fun. See `LICENSE`.
