# Back on the Counter

Personal dispensary shift warm-up app: counselling scripts, back-counter flow, bilingual (EN/中文) lines,
daily drill, viva circuit, cases and spaced review. A single static page, installable as a PWA and usable offline.

## Layout

| File | Purpose |
|---|---|
| `index.html` | The whole app (content, styles, logic) |
| `manifest.webmanifest`, `icons/` | Install-to-home-screen metadata and icons |
| `sw.js` | Offline cache. **Bump `VERSION` whenever you deploy** so phones pick up the new build |
| `.github/workflows/pages.yml` | Deploys to GitHub Pages on every push to `main` |

Progress (streak, spaced-review boxes) is stored in the browser's `localStorage` under `botc:*`.
It is per device/browser and is not synced.

## Run locally

    python3 -m http.server 8000   # then open http://localhost:8000

(The service worker only registers over `http://localhost` or `https`, not `file://`.)

## Your details

Nothing personal is stored in the code. Your roster and workplace name are set in the app (**⚙ Settings**) and
kept in your browser's `localStorage` (`botc:settings`), along with your streak and review boxes (`botc:sd-state`).
Use **Settings → Export progress** to back them up or move them to another device.

## Deploy

1. Push to `main`. The workflow in `.github/workflows/pages.yml` publishes the site.
2. One-off, in the repo: **Settings → Pages → Build and deployment → Source: GitHub Actions**.
3. Optional but recommended: **Settings → Branches → default branch → `main`**, so the Pages environment accepts deploys from `main`.
4. The app is served at `https://<user>.github.io/Back-on-the-counter/`.
5. On your phone: open the URL, then **Share → Add to Home Screen** (iOS) or **Install app** (Android/Chrome).

The repo is public (free GitHub Pages needs that). Early commits contained a roster and a store name before
those moved into Settings; they remain in git history unless it is rewritten.

## Disclaimer

Reference scripts for personal use. Clinical judgement and current protocols always override.
