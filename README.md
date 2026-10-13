<div align="center">

# Typing Speed Test ⌨️

**A clean, minimalist typing speed test — no frameworks, no build step, no dependencies.**

[![Live Demo](https://img.shields.io/badge/Live%20Demo-Try%20it%20now-3b82f6?style=for-the-badge)](https://zaafirrr.github.io/typing-speed-test/)

</div>

---

## Features

- **30s and 60s modes** — switch before a test or between attempts
- **Live stats** — WPM, countdown timer and accuracy update with every keystroke
- **Character-by-character feedback** — correct characters turn dark, mistakes highlight in red
- **10 varied passages** — selected randomly; request a new one from the results screen
- **Keyboard shortcuts** — `Esc` to restart mid-test, `Tab` to restart from the results screen
- **Single file** — everything is self-contained in `index.html`; just open it in any browser
- **Responsive** — works on desktop and mobile

---

## How WPM and accuracy are calculated

### WPM (net)

```
wpm = correctChars / 5 / elapsedMinutes
```

The standard five-characters-per-word convention is used. Only **correctly** typed characters count — both speed and accuracy are rewarded. This is *net WPM*, the figure used by most professional typing assessments.

### Accuracy

```
accuracy = correctChars / charsAttempted × 100
```

`charsAttempted` is the cursor position — how far into the passage you've typed. Backspacing to fix a mistake removes the character from both sides, so accuracy reflects the precision of what's currently on screen rather than a cumulative history of every wrong key ever pressed.

### Errors

Total wrong keypresses during the test, **including** ones you corrected with backspace. This measures how rough the session was overall, independent of what you fixed.

---

## Running locally

No install required — just open `index.html` in any modern browser:

```bash
# macOS
open index.html

# Windows
start index.html

# Linux
xdg-open index.html
```

Or serve it over a local HTTP server:

```bash
# Python 3
python -m http.server 8000
# → open http://localhost:8000

# Node.js
npx serve .
```

---

## Deploying to GitHub Pages

1. Push this repository to GitHub.
2. Go to **Settings → Pages**.
3. Under **Source**, choose **Deploy from a branch**.
4. Select `main` and the root folder `/`, then click **Save**.

Your live URL will appear within a minute or two:

```
https://<your-username>.github.io/typing-speed-test/
```

---

## File structure

```
typing-speed-test/
└── index.html   — everything: markup, styles and logic in one self-contained file
```

---

## Browser support

Works in all modern browsers (Chrome, Firefox, Safari, Edge). No polyfills or transpilation needed.

> **Note:** Typing tests work best on a physical keyboard. Mobile soft keyboards vary in how they report keystrokes and may give inconsistent results on some devices.
