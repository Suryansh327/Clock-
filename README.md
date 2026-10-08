# WaveClock — Ocean Time 🌊

An ocean-themed, installable web app/PWA with:
- India Standard Time (Asia/Kolkata), date and 24-hour display
- Stopwatch with milliseconds toggle, lap recording, start/pause/resume/reset
- Countdown timer with hours/minutes/seconds, pause/resume/reset
- End-of-timer sound, vibration where supported, and browser notification permission
- Touch-friendly controls, keyboard shortcuts, animated wave motion and ocean styling
- Offline app shell after first visit (service worker)

## Run on Windows and Android

**Recommended (installable app):** Host the folder on an HTTPS static host (for example GitHub Pages). A PWA service worker generally does not work from a `file://` URL.

**Windows (Edge or Chrome):**
1. Open the hosted HTTPS address.
2. Choose the browser's Install app option (or the install icon in the address bar, if shown).
3. Pin it to Start/taskbar if desired.

**Android (Chrome):**
1. Open the hosted HTTPS address in Chrome.
2. Tap ⋮ → **Add to Home screen** or **Install app**.
3. Open WaveClock from the home screen.

**Quick local preview:** open `index.html` directly. Clock, stopwatch, and timer should work, but install/offline features and notification behavior can be limited in `file://` mode.

## Keyboard shortcuts
- `1` — India time
- `2` — Stopwatch
- `3` — Timer
- `Space` — start/pause stopwatch, or timer when its tab is active
- `L` — stopwatch lap
- `R` — reset current stopwatch/timer
- `Enter` — start/pause timer when timer tab is active

Shortcuts are disabled while typing into inputs.

## Important notification limitation
A browser notification is best-effort and depends on browser permissions/platform behavior. This lightweight PWA does not include a server push service, so do not rely on it as an alarm if the browser/app is fully closed or the operating system suspends it. Keep the app open for the most reliable timer alert.

## Files
- `index.html` — app UI and logic
- `manifest.webmanifest` — PWA installation metadata
- `service-worker.js` — offline app shell cache
- `icon.svg` — app icon

## Testing notes
A static sanity-check script (`test_app.py`) is included. It checks required features and basic PWA files; it is not a substitute for device/browser testing. Test sound/notifications on the target device and grant permissions when prompted.
