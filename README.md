# 🔊 WackyFlip-Audio

Sound Engine & Music Integration
Custom audio systems and music logic powering immersive, responsive, and dynamic soundscapes across the [Wacky Flip](https://wackyflip.com/) game universe.

---

## 🎧 Overview

`WackyFlip-Audio` contains all the core systems, utilities, and logic responsible for **music playback, SFX triggers, audio transitions**, and real-time sound effects used across all Wacky Flip games and the platform itself. This repo ensures sound design in [Wacky Flip](https://wackyflip.com/) is not just an afterthought—but a key part of the fun, feedback, and feel.

Whether you're flipping bottles, blasting off with recoil physics, or completing a rainbow obstacle course, `WackyFlip-Audio` makes sure every moment sounds just right.

---

## 🔥 Features

* 🎵 **Dynamic Music System**
  Supports layered music tracks that adapt to gameplay events (e.g., level cleared, speed increased, player health low).

* 🔔 **SFX Trigger Engine**
  Lightweight utility to bind sound effects to in-game events using simple, declarative syntax.

* 🎚️ **Audio Mixer Utility**
  Balance music, UI sounds, ambient effects, and gameplay SFX with adjustable mix channels.

* 🧠 **Context-Aware Playback**
  Switch or fade tracks based on game state (menu, gameplay, win/fail, pause, etc.).

* 🎮 **Game Engine Integrations**
  Works with WackyFlip-Core and WackyFlip-Mobile for real-time sound handling across web and mobile.

* 🧩 **Custom Formats Support**
  Compatible with `.mp3`, `.ogg`, `.wav`, and sprite-based SFX sheets.

---

## 📁 Directory Structure

```
WackyFlip-Audio/
├── src/
│   ├── core/                  # Base audio engine (HTML5 + WebAudio APIs)
│   ├── sfx/                   # Sound effect triggers and definitions
│   ├── music/                 # Music playback and state handlers
│   ├── mixer/                 # Volume channels and EQ settings
│   ├── utils/                 # Format loaders, fade logic, time sync
│   └── integration/           # Wrappers for Web, Mobile, and Core engine
├── assets/                    # Demo sound files for testing (not final assets)
│   ├── jump.wav
│   └── menu-theme.mp3
├── examples/
│   └── browser-demo.html      # Live demo of music transitions + triggers
├── README.md
└── LICENSE
```

---

## 🎮 Example Use

```js
import { playSFX, playMusic, setVolume } from 'wackyflip-audio';

// Start background music when entering gameplay
playMusic('bg-gameplay', { loop: true, fadeIn: 1000 });

// Play jump sound on user action
playSFX('jump');

// Mute all audio (e.g., when paused)
setVolume('master', 0);
```

> See `/examples/browser-demo.html` for live usage in a minimal browser game loop.

---

## 🧱 Tech Stack

* **Web Audio API** (for mixing and precise control)
* **Howler.js** (optional integration for mobile compatibility)
* **Custom audio sprites** for memory efficiency on mobile
* **FFmpeg tools** for bundling audio files (see `/tools` in the repo)

---

## 📦 Integration Targets

* [`WackyFlip-Web`](https://github.com/wackyflipgame/WackyFlip-Web) – Web-based games using dynamic SFX
* [`WackyFlip-Core`](https://github.com/wackyflipgame/WackyFlip-Core) – Central engine for triggering audio feedback
* [`WackyFlip-Mobile`](https://github.com/wackyflipgame/WackyFlip-Mobile) – Works with Cordova/Capacitor for native audio layers

---

## 🧪 Development Setup

```bash
git clone https://github.com/wackyflipgame/WackyFlip-Audio.git
cd WackyFlip-Audio
npm install
npm run dev
```

You can preview changes in `/examples/browser-demo.html`.

---

## 🧠 Audio Standards

* **SFX**: Mono, under 1MB, `.wav` or `.ogg`
* **Music**: Stereo `.mp3` or `.ogg`, max 320kbps
* **Naming**: Use `camelCase` keys (e.g., `menuClick`, `jumpBoost`, `victoryTheme`)
* **Mixing**: Group SFX and music into logical channels: `ui`, `gameplay`, `ambient`, `master`

---

## 🤝 Contributing

Have your sound library? Want to help refactor the audio engine? Jump in!

* Submit SFX packs or music snippets (must be license-free or original)
* Propose improvements to mixer performance or preload handling
* Help integrate spatial or positional audio for future updates

---

## 🧾 License

MIT License © Wacky Flip Studios
Demo sounds in `/assets` are for development only and not licensed for distribution.
