# 🟡 Pac-Man Replica (Python + Pygame)

<p align="center">
  <img src="https://github.com/user-attachments/assets/3b0e3e48-422c-4b04-b95f-547e15adbda1" alt="Pac-Man Gameplay" width="600"/>
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
  <img src="https://github.com/user-attachments/assets/23830faa-5165-439b-9a63-8d29a06a12ed" width="260" style="margin-right:10px"/>
  <img src="https://github.com/user-attachments/assets/1623082c-4ebd-4136-8411-576846d86b94" width="260" style="margin-right:10px"/>
  <img src="assets/screenshots/gameover.png" width="260"/>
</p>

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

## 🧩 Gameplay Gallery

| Power-Up Mode | Classic Chase | Game Over |
|:--------------:|:--------------:|:----------:|
| <img src="assets/screenshots/powerup.png" width="250"/> | <img src="assets/screenshots/chase.png" width="250"/> | <img src="assets/screenshots/gameover.png" width="250"/> |

> Each frame captures the essence of the original — bright colors, fast movement, and relentless ghosts.

---

## 🧠 Behind the Game

This Pac-Man clone was coded from scratch to explore **game AI**, **real-time animation**, and **state management** in Python.  
It blends low-level logic (collision detection, timers, movement paths) with clean object-oriented structure for clarity and performance.

- Each ghost uses simple yet distinctive logic patterns to simulate personalities.  
- Player movement uses **tile-based logic** to ensure perfect turns.  
- All sprites are hand-scaled and centered for pixel-perfect accuracy.  
- Designed to teach — and showcase — **how much you can do with Python alone**.

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

## 🎨 Design Philosophy

This version of Pac-Man was made to **honor the simplicity of retro games** while writing everything manually — no pre-made engines, just Python logic and creativity.

> “It’s not about copying the original — it’s about understanding what made it feel alive.”

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

## 💡 Future Enhancements

🔊 **Sound FX & Music** — waka-waka loop, ghost alerts, and victory tones  
🏆 **High Score System** — persistent local leaderboard  
🗺️ **Multiple Mazes** — unlockable maps or procedural generation  
🎮 **Controller Support** — plug-and-play with joystick events  
🌈 **Themed Modes** — night mode, neon glow, or retro CRT filter  

---

## 🙌 Credits

Built with ❤️ by **Azaan Fatta**  
Developed in **Python 3.10** using **Pygame 2.x**  

> Inspired by the original *PAC-MAN®* by Namco — recreated purely for educational and creative purposes.

<p align="center">
  <img src="https://upload.wikimedia.org/wikipedia/en/5/59/Pac-man.png" width="120"/><br/>
  <sub>Retro spirit. Modern code.</sub>
</p>
