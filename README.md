# WELLNESS HQ v1.0

A mobile-friendly, offline-first personal wellness PWA built with plain HTML, CSS and JavaScript. No build tools, dependencies, accounts or API keys required.

## Features
- Daily weight, steps, sleep, water, mood, energy and notes
- Food diary with calories, protein, carbs and fat
- Workout log with duration, intensity and notes
- Body measurements (waist, hips, lower belly, thigh)
- Editable targets and simple trends
- Local persistent browser storage, JSON export/import, offline app shell

## Run locally
From this directory, run `python3 -m http.server 8000`, then open `http://localhost:8000` in a browser. On a computer, `localhost` means that computer; for Android use the deployed HTTPS link.

## Deploy free to GitHub Pages
1. Sign in to GitHub and create a **new public repository** called `wellness-hq` (do not upload any personal health backups or secrets).
2. Upload **all files in this folder**, keeping them at the repository root: `index.html`, `style.css`, `app.js`, `sw.js`, `manifest.webmanifest`, `icon.svg` and `README.md`.
3. In the repository, go to **Settings → Pages**. Under **Build and deployment**, choose **Deploy from a branch**.
4. Select branch `main` and folder `/(root)`, then save.
5. Wait for the Pages deployment. Open the URL GitHub displays (usually `https://YOUR-USERNAME.github.io/wellness-hq/`).
6. On Android Chrome, open the HTTPS link and use the menu → **Add to Home screen** or **Install app** (wording varies). Open it from your home screen.

## Important privacy and storage limitations
- All wellness data is stored **only in the local browser profile** via localStorage, not in GitHub or a server.
- GitHub Pages is public hosting for code, not a private health-data database. Do **not** commit backups, passwords, or personal records to the repository.
- Browser data may be deleted by clearing site storage, uninstalling or switching browsers/devices. Use **Settings → Export backup** regularly and save the JSON securely. Restoring replaces current records.
- No cross-device synchronization, authentication, Fitbit integration, food-photo AI or automated coaching in this MVP.
- Initial calorie, protein, steps and sleep targets are editable examples, not medical recommendations.
- Browser localStorage is not encrypted by this app; use a device screen lock and do not use shared devices for private data.

## Next version roadmap
1. More robust IndexedDB storage and backup reminders.
2. Optional secure login and private cloud sync with a suitable backend and access rules.
3. Google Health Connect / Fitbit data import, subject to permissions, APIs and Android constraints.
4. Food photos and AI-assisted estimates, with explicit review before saving.
5. Strength progression, recovery trends, weekly summaries and evidence-informed coaching.

## Manual acceptance test
1. Save a daily check-in; refresh and confirm values remain.
2. Add food and workout entries; refresh and confirm entries remain.
3. Switch dates and confirm entries are date-specific.
4. Save targets and check dashboard updates.
5. Export backup, delete one entry, restore backup and confirm it returns.
6. After initial load, enable airplane mode and reopen the installed app; app shell should load from service-worker cache (where supported).
