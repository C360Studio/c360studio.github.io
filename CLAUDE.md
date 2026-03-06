# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static marketing/blog site for **C360 Studio's Semstreams** product — a Go framework for streaming pipelines that produce live semantic knowledge graphs. Hosted on GitHub Pages at `c360studio.github.io`.

## Architecture

This is a plain HTML/CSS static site with no build step, no bundler, no framework, and no JavaScript.

### File Structure

- `index.html` — Landing page for Semstreams
- `blog.html` — Blog listing page
- `posts/*.html` — Individual blog post pages (e.g., `comms-suck.html`)
- `styles.css` — Shared stylesheet (all pages link to this)
- `360 logo round {50,75,100}.png` — Logo assets at different sizes

### Navigation and Linking

- Root pages (`index.html`, `blog.html`) link to `styles.css` and assets directly
- Blog posts in `posts/` use `../` prefixed paths to reach root assets, stylesheets, and pages
- External links point to `github.com/C360Studio/semstreams`

## Development

No build or test commands. Serve locally:

```bash
python3 -m http.server 8000
```

## Design System

All styles live in `styles.css`, using CSS custom properties in `:root`:

- **Colors**: Dark theme — `--bg: #0d0f0e`, `--orange: #e8430a` (accent), `--green: #4a7c59` (tags), `--text: #c8ccc9`
- **Fonts**: `Barlow Condensed` (headings), `IBM Plex Mono` (nav/labels/code), `IBM Plex Sans` (body)
- **Breakpoint**: Single responsive breakpoint at `768px`
- **Logos**: `360 logo round 50.png` used in nav and footer; larger sizes available for other contexts

## Conventions

- Blog posts are added by creating a new HTML file in `posts/` and adding a post card entry in `blog.html`
- The nav and footer markup are duplicated across all pages and must be kept in sync manually
- All CSS changes go in `styles.css` — no inline styles in HTML (except minor one-off overrides)
