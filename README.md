# 🎵 LyricVault — Synced Lyrics Explorer

<div align="center">

![LyricVault](https://img.shields.io/badge/LyricVault-v6-f2c200?style=for-the-badge&logo=music&logoColor=black)
![Static](https://img.shields.io/badge/Static-No%20Build%20Step-brightgreen?style=for-the-badge)
![Vanilla JS](https://img.shields.io/badge/Vanilla-JS%20%2F%20HTML%20%2F%20CSS-f7df1e?style=for-the-badge&logo=javascript&logoColor=black)
![Powered by LRCLIB](https://img.shields.io/badge/API-LRCLIB-blue?style=for-the-badge)

**A fast, modern lyrics explorer powered by the open [LRCLIB](https://lrclib.net) API.**  
Search any song, view synced lyrics with a highlight player, copy or download `.lrc` files — all in a single static page.

[🌐 Live Demo (Surge)](https://lyrics-fetch.surge.sh) · [🌐 Live Demo (GitHub Pages)](https://anonymousv73x.github.io/SYNCED-LYRICS-FETCHER-DOWNLOADER/) · [![Gmail](https://img.shields.io/badge/Contact-Gmail-red?logo=gmail&logoColor=white)](mailto:alexamanikalume@gmail.com)

</div>

---

## ✨ Features

| Feature | Details |
|---|---|
| ⚡ **Instant Search** | 120ms debounce, results as you type |
| 🗄️ **Smart Caching** | 30-min in-memory + `sessionStorage` cache — survives page refresh |
| 🔄 **Stale-While-Revalidate** | Serves cache instantly, refreshes in background |
| 🎯 **Hover Prefetch** | Fetches lyric details before you even click |
| 🎵 **Synced Highlight Player** | Active lyric line highlighted in real-time with smooth scroll |
| 📋 **Copy Lyrics** | One-click clipboard copy of plain or synced lyrics |
| 💾 **Download .lrc** | Download the synced lyric file directly |
| 🔍 **Lookup by Signature** | Find a track by artist + title + optional album/duration |
| 🔢 **Fetch by LRCLIB ID** | Direct numeric ID lookup |
| 📤 **Publish Lyrics** | Contribute synced lyrics — proof-of-work solved in-browser |
| 🌙 **Dark / Light Theme** | Persisted via `localStorage` |
| 📱 **Fully Responsive** | Mobile menu, touch-friendly, no iOS zoom issues |
| 🚀 **Zero Dependencies** | Pure HTML + CSS + JS — no npm, no bundler, no framework |

---

## 🖥️ Screenshots

> Search tab — instant results with synced/plain badges

> Lyrics modal — highlight player with copy & download controls

---

## 🚀 Deploy in 30 Seconds

### Surge.sh
```bash
npm install -g surge
cd "LYRICS DOWNLOAD"
surge . lyrics-fetch.surge.sh
```

### GitHub Pages
Push to a repo, go to **Settings → Pages → Source: main branch / root**.

### Locally
Just open `index.html` in any browser. No server needed.

---

## 📁 File Structure

```
LYRICS DOWNLOAD/
├── index.html      # Single-page app shell, all tabs, modal
├── style.css       # Tokens, layout, dark/light theme, animations
└── script.js       # All logic — search, cache, player, publish
```

No `package.json`. No `node_modules`. No build step. Three files, done.

---

## 🔌 API — Powered by LRCLIB

All data comes from the free, open [LRCLIB API](https://lrclib.net). No API key required.

| Endpoint | Used for |
|---|---|
| `GET /api/search?q=` | Free-text search |
| `GET /api/get?artist_name=&track_name=` | Lookup by signature |
| `GET /api/get/{id}` | Fetch by numeric ID |
| `GET /api/get-cached` | Cached variant (faster, may be stale) |
| `POST /api/request-challenge` | Proof-of-work for publishing |
| `POST /api/publish` | Submit new lyrics |

---

## ⚡ Performance Details

- **DocumentFragment rendering** — cards inserted in a single reflow
- **Event delegation** — one listener on the grid, not one per card
- **Cached DOM node array** — lyric line elements stored on modal open; zero DOM queries per animation frame
- **Binary search** — active lyric line found in O(log n) per frame
- **rAF-based smooth scroll** — easeInOutQuad, no browser scroll jank
- **GPU compositing** — `will-change: transform` + `contain: layout style` on cards and modal
- **sessionStorage cache** — search results persist across refreshes for 30 minutes

---

## 🎮 Keyboard Shortcuts

| Key | Action |
|---|---|
| `⌘K` / `Ctrl+K` | Focus search from anywhere |
| `Space` | Play / Pause (modal open) |
| `R` | Restart lyrics from beginning |
| `Esc` | Close modal |

---

## 🛠️ Built With

- **HTML5** — semantic, accessible markup
- **CSS3** — custom properties, `color-mix()`, `backdrop-filter`, CSS Grid
- **Vanilla JS (ES2022)** — no libraries, no transpilation
- **[LRCLIB](https://lrclib.net)** — open lyrics database
- **[Outfit](https://fonts.google.com/specimen/Outfit)** — Google Fonts

---

## 📄 License

MIT — do whatever you want with it.

---

<div align="center">
Made with ☕ · Powered by <a href="https://lrclib.net">LRCLIB</a>
</div>
