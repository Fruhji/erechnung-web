# AGENTS.md — erechnung-web

Device-detection redirect landing page for the **E-Rechnung Mobil** app. Private Fruhji
app. Live: https://fruhji.github.io/erechnung-web/

## What it is
A bare static site, deployed via GitHub Pages. iOS visitors get redirected straight to
the App Store; Android redirect is currently disabled (`PLAY_LIVE = false` in the
inline script) until the Play release goes public — Android visitors just see the page.

## Files
- `docs/index.html` — the entire site: inline `<script>` does the UA-sniffing redirect
  (`location.replace`), inline `<style>` covers light/dark. No other pages.
- `docs/.nojekyll` — disables Jekyll processing (required, do not remove).
- `.github/workflows/pages.yml` — deploys `docs/` to GitHub Pages via the official
  `actions/*-pages` actions on every push to `main`.

## Making a change
No build step, no dependencies, no tests. Edit `docs/index.html` directly (store URLs
are hardcoded in the script block at the top), commit, push to `main` — the workflow
deploys automatically. To flip Android on, set `PLAY_LIVE = true` once the Play listing
is public.

## Conventions
- Git identity: `leon.mons2@gmail.com`. Branding: **Fruhji** (never the real name).
- No emojis — typographic marks (`·` `–` `—`) instead.
