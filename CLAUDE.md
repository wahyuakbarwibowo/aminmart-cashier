# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

Static marketing/support site + direct APK distribution for the `app-cashier` Android app (sibling repo `../app-cashier`). Deployed to GitHub Pages (`github.io/aminmart-cashier/` — see the GA cookie config in `config.js`). No build system, no package manager, no tests, no linter. All site copy is in Indonesian.

## Run

Open `index.html` in a browser (needs internet for the Tailwind CDN and Google Fonts), or `python3 -m http.server` — a server is needed for the `fetch('stats.json')` calls to work.

## Architecture

- Each page is a self-contained HTML file: Tailwind via CDN, custom CSS (glassmorphism, fonts) in an inline `<style>` block, page JS in inline `<script>` blocks. There is no shared stylesheet or templating.
- `config.js` is the only shared code, loaded by every page. It holds GA4 setup, `NAVBAR_CONFIG` (logo, brand, nav links), and renders the navbar into `<div id="navbar-container">` on `DOMContentLoaded`, plus the dark-mode toggle (persisted in `localStorage.theme`, class-based `dark:` variants) and the mobile hamburger menu. **Adding a page = adding a link to `NAVBAR_CONFIG.links`.** Note: `renderNavbar()` (document.write version) is legacy; the live path is the `DOMContentLoaded` handler, which duplicates the same nav HTML — keep both in sync if editing the navbar markup.
- Pages: `index.html` (landing), `install.html` (APK install guide incl. RawBT printer setup), `contact.html` (support), `delete-account.html` (Play Store data-deletion compliance — don't remove), `stats.html` (analytics view).
- Stats are client-side only: inline scripts on each page count page views / `.apk` download clicks into `localStorage.websiteStats`, seeded from `stats.json`. `stats.html` reads `stats.json`. `update-stats.js` (Node) and `update-stats.php` are server-side updaters that don't run on GitHub Pages — they're inert unless self-hosted.

## APK distribution

APKs are committed binaries under `apk/` (currently `apk/cashier/app-release.apk`). Download links in `index.html` and `install.html` point to that path with the `download` attribute — the download-click tracker selects on `a[href*=".apk"][download]`, so keep both attributes when touching those links. "Updating the APK" in this repo means replacing the binary and committing (see git history: `fix: update apk`).
