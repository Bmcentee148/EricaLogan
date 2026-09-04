# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

A marketing site **spec build** for Erica Logan Clothing Boutique (Islip, NY) — a pitch, not a finished, paid-for site. It's a static, single-page site: no build system, no package manager, no framework. The entire site is `index.html` (CSS in a `<style>` block, JS in two inline `<script>` blocks) plus `img/` and `favicon.ico`.

Read `README.txt` before making changes — it is the living spec and contains a detailed PRODUCTION CHECKLIST (blockers, unconfirmed facts, placeholder copy, missing sections) plus "HOW THINGS WORK" maintenance notes and a sources list for every factual claim on the page. Keep `README.txt` in sync with `index.html` when you change something it documents (e.g. hours, prices, address, the checklist itself).

## Commands

There is no build/lint/test tooling in this repo (no `package.json`). To preview:

```
python3 -m http.server 8000   # then open http://localhost:8000
```

Do **not** open `index.html` directly via `file://` to test the contact form — Netlify Forms only works once deployed, and the map/form JS assumes it's served over HTTP(S). Deploying is done by dragging the whole project folder onto netlify.com/drop (not `index.html` alone) — the page depends on `img/`.

## Architecture

Single file, top to bottom:
1. `<head>` — meta/OG/Twitter tags, canonical URL, JSON-LD (`application/ld+json`) for the business — several of these currently point at the placeholder `https://REPLACE-WITH-DOMAIN.com`.
2. `<style>` — all CSS, no preprocessor.
3. Announcement bar → header/nav (with a separate mobile nav panel, `#mobile-nav`) → hero → New Arrivals (product cards) → What We Carry (category cards) → Visit Us (hours, map, contact form) → Follow Along → footer.
4. A small inline `<script>` right after `<head>` sets up the mobile nav toggle, computes the "Open now / Closed" badge, lazy-loads the Google Map iframe on click, handles the Netlify contact form submit via `fetch`, sets the footer copyright year, and drives scroll-reveal animation via `IntersectionObserver`. All vanilla JS, no dependencies.

### Data that is duplicated on purpose — keep all copies in sync

- **Opening hours** live in three places and must be changed together: the visible `<dl class="hours">` list, the `HOURS` object in the inline script (drives the open/closed badge, computed in `America/New_York` regardless of visitor timezone), and `openingHoursSpecification` in the JSON-LD.
- **The domain** placeholder `https://REPLACE-WITH-DOMAIN.com` appears 7 times (canonical, `og:url`, `og:image`, `twitter:image`, twice in JSON-LD) and must all be replaced together before launch.
- The footer intentionally does **not** repeat the hours (already in 3 places above); it links to `#visit` instead.

### Product images: 3 sizes per slug, required

Each product needs exactly three files at the same slug, generated from a 1000×1503 (2:3 portrait) source:
```
img/products/<slug>-400.webp
img/products/<slug>-520.webp
img/products/<slug>-820.webp
```
These match the `srcset` ladder in `index.html` (phone→400, desktop→520, retina→820); missing a size serves the wrong resolution. When adding/swapping a product, update slug, name, price, and alt text in the New Arrivals section together. Keep photography consistent (same hanger, rail, distance, light) since the grid only reads as a set when framing matches.

### The map is click-to-load — do not make it eager

The Google Maps embed (`#mapwrap` / `#mapcard` / `#mapbtn`) is built lazily by JS only when the user clicks "Show map" — it costs ~1.8MB of third-party JS/tiles vs. ~545KB for the rest of the page, and eager-loading it materially hurts Core Web Vitals (a real ranking factor). Don't change this to load on page load.

### Images are separate files, not inlined/base64

This lets `srcset` serve device-appropriate sizes and lets images cache independently across the weekly product-photo swap. Don't inline images as data URIs.

## Content rules

Do not invent or "improve" factual content (prices, address, phone, owner names, hours, categories) — every factual claim on the page traces to a specific source, listed at the bottom of `README.txt`. If a fact isn't sourced there, treat it as unverified and flag it in the PRODUCTION CHECKLIST rather than asserting it. Placeholder copy is marked inline in `index.html` and in README.txt section C — flag it rather than silently making it sound final.
