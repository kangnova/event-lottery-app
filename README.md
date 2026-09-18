# 🎰 Event Lottery App — Cinematic 3-Reel Lucky Draw

[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/HTML)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![Web Crypto API](https://img.shields.io/badge/Web_Crypto_API-Fair_Random-10b981?style=for-the-badge)](https://developer.mozilla.org/en-US/docs/Web/API/Web_Crypto_API)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](LICENSE)

An interactive, high-performance, cinematic 3-reel slot machine lucky draw web application designed for live events, streaming, and stage presentations. Built with zero external frameworks or heavy dependencies using pure HTML5, CSS3, and Vanilla JavaScript.

🌐 **Live Demo:** [https://kangnova.github.io/event-lottery-app/](https://kangnova.github.io/event-lottery-app/)

---

## ✨ Key Features

- 🎰 **Cinematic 3-Reel Slot Machine**: Dynamic physical lever animation, 3D curved cylinder shading, and 24 FPS video/motion background integration.
- 🔐 **Multi-Layer Security System**:
  - **Master Password Security Gate**: Full-screen modal overlay protecting application startup (`UNDIAN2026`).
  - **PIN Protected Setup**: PIN lock (`1234`) preventing unauthorized changes during live events.
  - **Global Anti-Inspect Protection**: Disabled right-click context menu, `F12`, `Ctrl+Shift+I/J`, `Ctrl+U`, and `Ctrl+S` keybindings.
- 🎲 **Cryptographically Fair Randomizer**: Uses `window.crypto.getRandomValues()` to guarantee unbiased winner selection.
- 🎯 **Preset Winners Queue**: Event organizers can preload predetermined winner lists while retaining full random spinning visual effects.
- 🔊 **Web Audio Synthesizer**: Procedural audio effects generated dynamically via Web Audio API (reel ticks, decelerations, applause, and fanfare).
- ⚙️ **Live Customization**:
  - Custom event title and logo upload support.
  - Adjustable spin duration (3s, 5s, 7s, 10s, or custom duration).
  - Real-time stage controls and winner list export (`.txt` / `.json`).

---

## 🚀 Live Demo & How to Run

### **1. Online Live Demo**
Access the deployed app directly in your browser:
➡️ **[https://kangnova.github.io/event-lottery-app/](https://kangnova.github.io/event-lottery-app/)**

> **Default Access Credentials:**
> - **Master Password:** `UNDIAN2026`
> - **Setup PIN:** `1234`

### **2. Local Setup**
No build step or server required! Simply clone the repository and open `index.html`:

```bash
# Clone the repository
git clone https://github.com/kangnova/event-lottery-app.git

# Open directory
cd event-lottery-app

# Open index.html in any modern web browser
```

---

## 🛠️ Built With

- **HTML5 & CSS3**: Custom responsive glassmorphism UI system.
- **Vanilla JavaScript (ES6+)**: Core state machine and UI rendering.
- **Web Crypto API**: High-entropy cryptographically secure random number generation.
- **Web Audio API**: Real-time sound synthesis.

---

## 📄 License

Distributed under the MIT License. See `LICENSE` for details.
