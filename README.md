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

## Deploy

1. Merge to `main`.
2. Repo **Settings → Pages → Source: GitHub Actions** (one-off).
3. The app is served at `https://<user>.github.io/Back-on-the-counter/`.
4. On your phone: open the URL, then **Share → Add to Home Screen** (iOS) or **Install app** (Android/Chrome).

Note: GitHub Pages on a free plan needs a public repo. The content is generic counselling scripts, but check
you're comfortable with it being public (the footer and roster name a store location, "CW Sunnybank Plaza"), or
host privately (Cloudflare Pages + Access, Netlify password, etc.).

## Disclaimer

Reference scripts for personal use. Clinical judgement and current protocols always override.
