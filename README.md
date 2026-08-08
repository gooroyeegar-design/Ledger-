# Ledger — Weight, Compounded

A premium, installable weight-loss planning PWA. Fully client-side (no backend, no signup) — a 14-question intake builds your calorie target, pace, and projected close date, then a dashboard tracks entries, streaks, and badges.

## 1. Push this to GitHub

```bash
cd weight-ledger
git init
git add .
git commit -m "Ledger: initial build"
git branch -M main
git remote add origin https://github.com/<your-username>/<repo-name>.git
git push -u origin main
```

(Or: create a new repo on github.com, then use "Add file → Upload files" and drag in everything from this folder, including the hidden `.github` folder and `.nojekyll` file — make sure your file explorer shows hidden files.)

## 2. Turn on GitHub Pages via Actions

1. On your repo, go to **Settings → Pages**.
2. Under "Build and deployment", set **Source** to **GitHub Actions**.
3. Push to `main` (or go to the **Actions** tab and manually run **"Deploy Ledger to GitHub Pages"**).
4. Wait ~30–60 seconds. Your live URL appears at the top of the Pages settings page and in the Actions run output — it'll look like:
   `https://<your-username>.github.io/<repo-name>/`

The included workflow at `.github/workflows/deploy.yml` is the exact action — it runs on every push to `main`, disables Jekyll (the thing that broke your last GitHub Pages deploy), and publishes the whole folder.

## 3. Install it on your phone

**iPhone (Safari):** open the live URL → tap the Share icon → **Add to Home Screen**.
**Android (Chrome):** open the live URL → tap the ⋮ menu → **Install app** (or **Add to Home Screen**).

It'll launch full-screen, no browser bar, with its own icon — a real installed app, entirely from a GitHub repo.

## What's inside

- `index.html` — the whole app (onboarding quiz, plan calculator, dashboard, entry log, badges)
- `manifest.json` — makes it installable
- `service-worker.js` — caches the app so it opens offline after first load
- `icons/` — app icons
- `.github/workflows/deploy.yml` — the GitHub Action that deploys to Pages
- `.nojekyll` — stops GitHub Pages from mangling files through Jekyll

## Data & Premium

All data (your plan, entries, streaks) lives in the phone's local storage — nothing leaves the device. Premium is unlocked by default since it's your own build; the toggle in Settings is there for show/if you want to gate it later.

## Notes

The calorie plan uses the Mifflin-St Jeor formula with a safety floor (1200/1500 kcal) and caps overly aggressive paces automatically. It's a general estimate, not medical advice — worth a quick check with a doctor or dietitian, especially for an aggressive goal or timeline.
