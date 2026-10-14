# MINICAL

A minimalist, **Apple / iOS-styled** habit calendar. Each day in the month view is
rendered as an iPhone-style widget. Pure vanilla HTML/CSS/JS — no build step, no
dependencies, data stays in your browser.

## Features

- **Month view** — every day is an iOS widget (squircle card, SF-style type, habit dots) over real ukiyo-e artwork.
- **Week view** — a card of habit lines with tappable stations for Mon–Sun and a today guide.
- **Day drawer** — tap a day to toggle habits and write a journal note (autosaved).
- **Two habit kinds** — simple **done / not done** habits, or **count** habits with a target number (e.g. Water 8). Count chips show the running number; the drawer has a −/+ stepper.
- **Streaks** — current and best streak per habit, with a bump animation when a streak grows.
- **Stats & heat map** — check-ins, perfect days, completion %, and a monthly heat grid.
- **Themes** — Day / Night / Auto (follows the OS). Night is the default.
- **Full screen** — the ⤢ button (or `F`) toggles full screen.
- **Backup** — export / import all data as JSON.
- **Keyboard** — `←`/`→` navigate, `M`/`W` views, `D`/`A`/`N` theme, `F` full screen, `T` today, `Esc` close.

Font uses the system stack, so it renders as **SF Pro on Apple devices** and the
closest native system font elsewhere.

## Artwork

Each day shows a different **public-domain** Japanese woodblock print (Hokusai,
Hiroshige, and others), embedded in the file as compressed data URIs. Its opacity
fades in as more of that day's habits are completed. Source: Wikimedia Commons.

## Run locally

Just open `index.html` in a browser, or serve the folder:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Deploy to GitHub Pages

This repo ships with a workflow at `.github/workflows/pages.yml` that publishes the
site on every push to `main`.

```bash
git init
git add .
git commit -m "MINICAL"
git branch -M main
git remote add origin https://github.com/<your-username>/<your-repo>.git
git push -u origin main
```

Then in the repo: **Settings → Pages → Build and deployment → Source: GitHub Actions**.
Your site goes live at `https://<your-username>.github.io/<your-repo>/`.

> Prefer no Actions? You can instead set **Source: Deploy from a branch** → `main` /
> `root` and Pages will serve `index.html` directly (`.nojekyll` is already included).

## Data

Everything is stored under `minical.v1` in `localStorage`. Use **Export** to make a
JSON backup and **Import** to restore it on any device.
