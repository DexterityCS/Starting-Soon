# Starting Soon Screen

A free, fully configurable "Starting Soon" overlay for OBS/Streamlabs. No login required. No watermarks. No subscriptions.

<img width="1247" height="1226" alt="Starting soon" src="https://github.com/user-attachments/assets/a09cedf5-e5b0-4d12-aef7-86fb24d286a4" />


---

## Features

- **Live countdown** — count down to a specific time (with timezone) or set a "X minutes from now" timer
- **Auto-transitions** — switches to "Starting Now!" when the timer hits zero
- **Weekly schedule** — show your stream days and times, today's slot is highlighted automatically
- **Socials row** — Twitch, Twitter/X, Discord, YouTube, TikTok — blank ones are hidden automatically
- **4 background styles** — Particles, Mesh, Retro (scanlines), Minimal
- **9 accent colors** — changes the glow, countdown, pill, and today's schedule highlight
- **No login required** — zero Twitch auth, zero API keys
- **OBS-safe** — uses `localStorage` for persistence, no `history.replaceState` errors
- **Shareable URL** — Copy URL generates a hash link you can send to others or bookmark

---

## Setup

### 1. Host it

**Option A — GitHub Pages (recommended)**
1. Fork this repo
2. Go to Settings → Pages → Source: `main` branch, `/ (root)`
3. Your widget will be live at `https://yourusername.github.io/Starting-Soon`

**Option B — Local file**
Just open `index.html` in a browser directly. Works fine for personal use.

---

### 2. Configure

Open the page in your browser. You'll see the setup UI:

| Section | What to fill in |
|---|---|
| **Channel** | Your streamer name and a short tagline |
| **Countdown** | Pick "Specific time" (with timezone) or "Minutes from now" |
| **Schedule** | Enter times for each day you stream — leave blank to hide that day |
| **Socials** | Any platform you leave blank won't appear on the widget |
| **Appearance** | Pick an accent color and background style |
| **Widget size** | Match your OBS canvas — usually 1920 × 1080 |

Click **Launch Widget →** when done.

---

### 3. Add to OBS

1. In OBS, add a new **Browser Source**
2. Check **Local file** if hosting locally, or paste your GitHub Pages URL
3. Set Width and Height to match what you entered in the setup (default 1920 × 1080)
4. Check **Shutdown source when not visible** and **Refresh browser when scene becomes active**
5. Click OK

Your config is saved in `localStorage` automatically — the widget will remember your settings every time OBS loads it.

---

### 4. Share your config (optional)

Click **Copy URL** in the setup UI — this generates a URL with your full config embedded in the hash. Anyone who opens that link will see the setup pre-filled with your settings.

---

## Countdown modes

**Specific time**
Set the time your stream starts (e.g. `20:00`) and your timezone. The widget calculates the countdown automatically. If the time has already passed today, it counts to the same time tomorrow.

**Minutes from now**
Set a number of minutes (e.g. `30`). The countdown starts from when the widget loads. Useful if you don't stream on a fixed schedule.

---

## Background styles

| Style | Description |
|---|---|
| **Particles** | Animated connected dots — color matches your accent |
| **Mesh** | Soft radial gradient blobs — moody and atmospheric |
| **Retro** | CRT scanlines + grid — great for retro or gaming streams |
| **Minimal** | Subtle radial glow on dark — clean and distraction-free |

---

## Customization

All config is handled through the setup UI — no code editing required. If you want to go deeper:

- **Fonts** — swap the Google Fonts import at the top of the file (`Syne` + `Syne Mono`)
- **Default accent** — change `--accent: #e8ff47` in the `:root` CSS block
- **Add more social platforms** — duplicate a row in the `// 04 — Socials` section and add a matching entry in `buildWidgetSocials()`

---

## Browser / OBS compatibility

| Environment | Status |
|---|---|
| OBS Browser Source | ✅ Fully supported |
| Streamlabs Browser Source | ✅ Fully supported |
| Chrome / Edge / Firefox | ✅ Fully supported |
| Local file (file://) | ✅ Works — localStorage persists |

---

## License

MIT — free to use, modify, and redistribute. Credit appreciated but not required.
