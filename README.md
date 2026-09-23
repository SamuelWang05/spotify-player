# StandBy for Spotify

A clone of Apple's StandBy now-playing screen, wired up to the real Spotify Web API. Runs entirely in the browser — no server, no backend, no API keys stored anywhere but your own phone.

## 1. Put it on GitHub Pages

1. Create a new **public** GitHub repo (e.g. `standby-spotify`).
2. Upload all the files in this folder (`index.html`, `manifest.json`, `icon-*.png`) to the repo root.
3. Go to **Settings → Pages**, set Source to the `main` branch, root folder. Save.
4. Wait a minute, then your app will be live at:
   `https://YOUR_USERNAME.github.io/standby-spotify/`

## 2. Create a Spotify app (one-time, ~2 minutes)

1. Open the app and follow the on-screen steps — it walks you through:
   - Opening the Spotify Developer Dashboard
   - Creating an app
   - Copying the **Redirect URI** the app shows you into your Spotify app's settings
   - Copying your **Client ID** back into the app
2. Tap **Connect Spotify** and approve access. You'll land back on the Now Playing screen.

Your Client ID and login tokens are saved only in this browser's local storage on this device — they never leave your phone except to talk directly to Spotify's own servers.

## 3. Add it to your Home Screen

1. Open your GitHub Pages link in **Safari** on your iPhone.
2. Tap the **Share** button (square with an arrow).
3. Tap **Add to Home Screen** → **Add**.
4. Launch it from the home screen icon — it opens full-screen, no Safari bars, just like a real app.

Prop your phone up (e.g. MagSafe stand) and it behaves like StandBy: album art on one side, title/artist, playback controls, and a progress bar on the other. Tap the speaker icon top-right for volume, or the other icon to switch which device is playing.

## Notes & limits

- The background is sampled live from each track's album art (an average of its pixels, darkened into a glow), so it shifts color with every song — the same idea Apple Music and StandBy use. If Spotify's image CDN ever blocks the color read in your browser, it just falls back to a plain dark background.
- **Playback control requires Spotify Premium** — the Web API's play/pause/seek/volume endpoints are Premium-only.
- Volume control only works on devices Spotify allows remote volume changes on (most desktop/mobile Spotify apps; some hardware speakers don't support it).
- The app polls Spotify roughly every 4 seconds for the current track, with the progress bar ticking locally in between — this stays well under Spotify's rate limits.
- Nothing here is affiliated with or endorsed by Apple or Spotify.
