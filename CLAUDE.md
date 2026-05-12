# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Deployment

The site is deployed via Cloudflare Workers/Pages. The live URL is `king.lukebranca.workers.dev`. It deploys automatically from the **`main`** branch — changes only go live when merged/pushed to `main`.

When making changes, always ensure they end up on `main`. Feature branches won't update the live site.

## Structure

This is a single-page static site. Everything served lives in `Marty/`:

- `Marty/index.html` — the entire site: all HTML, CSS (in `<style>`), and JS (in `<script>`) in one file
- `Marty/images/` — hero photo, project photos
- `Marty/videos/` — before/after reels shown in the Videos section
- `wrangler.jsonc` — Cloudflare Workers config; `assets.directory` points to `./Marty`

There is no build step, bundler, or package manager. Edit `index.html` directly.

## Mobile breakpoint

The responsive breakpoint is `@media (max-width: 900px)` at the bottom of the `<style>` block (~line 882). Desktop layout uses multi-column CSS Grid and `margin-left: auto` to push `.hero-left` to the right half of the screen — this persists on mobile unless explicitly overridden.
