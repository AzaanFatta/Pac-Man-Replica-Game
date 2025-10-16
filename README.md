# 🟡 Pac-Man Replica (Python + Pygame)

<p align="center">
  <img src="https://github.com/user-attachments/assets/3b0e3e48-422c-4b04-b95f-547e15adbda1" alt="Pac-Man Gameplay" width="300"/>
</p>

> A from-scratch, modernized **Pac-Man** built with **Python** and **Pygame** — complete with smooth animations, unique ghost behavior, power-up logic, and a responsive arcade maze that scales beautifully across all platforms.

<p align="center">
  <a href="https://img.shields.io/badge/python-3.10%2B-blue.svg"><img alt="Python" src="https://img.shields.io/badge/python-3.10%2B-blue.svg"></a>
  <a href="https://img.shields.io/badge/pygame-2.x-green.svg"><img alt="Pygame" src="https://img.shields.io/badge/pygame-2.x-green.svg"></a>
  <a href="https://img.shields.io/badge/platform-macOS%7CWindows%7CLinux-informational"><img alt="Platforms" src="https://img.shields.io/badge/platform-macOS%7CWindows%7CLinux-informational"></a>
</p>

---

## 🎮 Overview

This project recreates the charm of the **original Pac-Man** while adding a modern programming twist.  
Every character, wall, pellet, and animation frame is fully coded and rendered using Python — no external game engine.
<p align="center">
  <img src="https://github.com/user-attachments/assets/16f38720-5b1f-4fa5-9cf2-50d84dc6c104" width="35" style="margin-right:10px"/>
  <img src="https://github.com/user-attachments/assets/f40f48e7-67f9-4e4e-b2e5-caca81a22ed0" width="35" style="margin-right:10px"/>
  <img src="https://github.com/user-attachments/assets/9bec807a-6d6f-4cfd-ba74-144351853474" width="35" style="margin-right:10px"/>
  <img src="https://github.com/user-attachments/assets/04f4179f-4cfb-42f1-b3de-bed9f8013c79" width="35" style="margin-right:10px"/>


---

## ✨ Highlights

- 🧱 **Authentic Arcade Maze** — glowing blue walls, perfect cornering, and classic pellet placement.  
- 👻 **Distinct Ghost Personalities** — each ghost uses different pursuit logic, creating unpredictable encounters.  
- ⚡ **Power-Up Mode** — eat a large pellet to flip the chase and hunt the ghosts instead.  
- 🕹️ **Fluid Controls** — fast, buffered direction changes ensure instant turns at intersections.  
- 💀 **Life & Score System** — persistent score tracking with lives displayed in the HUD.  
- 🖥️ **Resizable Game Window** — dynamic scaling while maintaining crisp visuals.  
- 🧠 **Optimized for 60 FPS** — precise collision checks and preloaded assets for smooth gameplay.  

---

## 🕹️ Controls

| Key | Action |
|:--:|:--|
| ⬅️ / ➡️ / ⬆️ / ⬇️ | Move Pac-Man |
| **Space** | Restart after game over or win |
| **Esc / Close** | Quit the game |

---

## 👻 Ghost Behavior (at a glance)

Each ghost is a `Ghost` instance with:
- **State:** `direction`, `speed`, `dead` (eaten), `in_box`, and a **dynamic target**.
- **Per‑tile collision** via board grid (R/L/U/D) using the current logical tile (`num1`, `num2`) so turns only occur at legal junctions.
- **Targeting during normal mode:**
  - **Blinky**: direct pursuit (straight‑line bias; only turns on collision when blocked).
  - **Pinky**: prioritizes horizontal choices; vertical only on collision → good ambusher.
  - **Inky**: favors vertical turns; horizontal turns primarily on collision → pinches vertically.
  - **Clyde**: opportunistic; switches directions when advantageous to close distance.
- **Power‑up (frightened):** ghosts flee to a “runaway” target based on the player quadrant; if eaten, they switch to `dead` and head to **return target** (ghost box), then revive.

---

## 🧠 Behind the Game

This Pac-Man clone was coded from scratch to explore **game AI**, **real-time animation**, and **state management** in Python.  
It blends low-level logic (collision detection, timers, movement paths) with clean object-oriented structure for clarity and performance.

- Each ghost uses simple yet distinctive logic patterns to simulate personalities.  
- Player movement uses **tile-based logic** to ensure perfect turns.  
- All sprites are hand-scaled and centered for pixel-perfect accuracy.  
- Designed to teach — and showcase — **how much you can do with Python alone**.

---

## 🖼️ UI & Game States

- Bottom HUD shows **Score** and **Lives** (sprite icons).  
- **Power‑up indicator** lights up while energized; flickers before expiration.  
- Modal cards for **Game Over** and **Victory** with instant restart on **Space**.

---


## 🧱 Board & Collision System

- The maze is driven by `boards` (a 2D int grid). Each integer encodes a **tile primitive**:
  - `1` pellet • `2` power pellet • `3–8` wall segments/arcs • `9` door into the ghost box.
- The renderer uses the grid to draw lines/arcs at scaled tile centers — ensuring **identical gameplay feel** across resolutions.
- Player & ghosts use **center‑point sampling** plus small radii to check collision against tiles at junctions only, enabling smooth turns without clipping.

---

## 🎨 Design Philosophy

This version of Pac-Man was made to **honor the simplicity of retro games** while writing everything manually — no pre-made engines, just Python logic and creativity.

Special attention was given to:
- Smooth animation flow  
- Realistic ghost spacing and unpredictability  
- Player turn responsiveness  
- Visual clarity on all screen sizes  

---

## 🏁 Performance & Polish

- Constant **60 FPS** with minimal CPU usage  
- Dynamic scaling with `pygame.SCALED | pygame.RESIZABLE`  
- Efficient rendering loop with static object caching  
- Instant restart and clean state resets for endless replayability  


---


## 🚀 How to Play Locally

### 1️⃣ Install Requirements
```bash
pip install pygame
```

### 2️⃣ Run the Game
```bash
python Pacmann.py
```

That’s it — the game launches instantly with full controls and scoring.  
*(Compatible with macOS, Windows, and Linux)*

---

## 🙌 Credits

Built by **Azaan Fatta**  
Developed in **Python 3.10** using **Pygame 2.x**  

> Inspired by the original *PAC-MAN®* by Namco — recreated purely for educational and creative purposes.

<p align="center">
  <img src="https://github.com/user-attachments/assets/768c3989-02c9-4db6-a6af-d21a8fbf19f1" width="120"/><br/>
</p>
