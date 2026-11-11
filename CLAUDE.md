# CLAUDE.md

This file provides guidance to coding agents when working with code in this repository.

## Project Overview

Static overview and portfolio site for **C360 Studio's SemEngine and the `sem*` family** — a Go semantic knowledge graph platform (`semengine`, succeeding `semstreams`) along with optional semantic add-ons (`semvocab`, `semembed`, `semsparql`), products (`semteams`, `semsource`, `semconnect`), Go tooling (`ateam`, `servicesim`), governance (`haag`), and experimental labs (`semselect`, `semboids`, `semdragon`, `semmachina`). Hosted on GitHub Pages at `c360studio.github.io`.

## Architecture

Plain HTML/CSS static site with no build step, bundler, framework, or JavaScript.

### File Structure

- `index.html` — SemEngine-first landing page featuring the native HTML/CSS/SVG `sem*` family map, architecture overview, and current focus
- `projects.html` — Detailed portfolio catalog split into **Production** and **Labs**
- `styles.css` — Shared stylesheet across all pages
- `360 logo round {50,75,100}.png` — Logo assets at different sizes

### Navigation and Linking

- Root pages (`index.html`, `projects.html`) link to `styles.css` and assets directly
- External repository links point to `github.com/C360Studio/*`

## Development

No build or test commands. Serve locally:

```bash
python3 -m http.server 8000
```

## Design System

All styles live in `styles.css`, using CSS custom properties in `:root`:

- **Colors**: Dark industrial theme — `--bg: #0d0f0e`, `--orange: #e8430a` (primary accent), `--green: #4a7c59` (core/governance), `--teal: #3f7d8c` (optional add-ons), `--amber: #d4a843` (next/labs), `--text: #c8ccc9`
- **Fonts**: `Barlow Condensed` (headings), `IBM Plex Mono` (nav/labels/badges/code), `IBM Plex Sans` (body)
- **Breakpoints**: Responsive breakpoints at `980px` (portfolio board columns) and `768px` (mobile layout)
- **Logos**: `360 logo round 50.png` used in nav and footer; larger sizes available for other contexts

## Conventions

- Nav and footer markup are shared across `index.html` and `projects.html` and must be kept in sync manually
- Keep CSS rules in `styles.css` rather than inline styles
- Tone: pragmatic, capability-forward systems engineering prose — concrete and verifiable without marketing fluff or defensiveness
