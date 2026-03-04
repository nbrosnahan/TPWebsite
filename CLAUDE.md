# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Is

A Hugo static site for [tumblingpotato.org](https://tumblingpotato.org) — a 90s-style "under construction" splash page. No themes, no npm, no build tooling beyond Hugo itself.

## Commands

```bash
# Serve locally with live reload
hugo server

# Build for production (outputs to ./public/)
hugo --minify
```

Hugo version in CI: **0.157.0 extended**.

## Architecture

This is a minimal, no-theme Hugo site. All structure is hand-built in `layouts/`:

| File | Purpose |
|------|---------|
| `layouts/_default/baseof.html` | Shell: `<html>`, `<head>`, inlined CSS |
| `layouts/index.html` | Homepage content only (defines the `main` block) |
| `layouts/partials/worker-icon.html` | Inline SVG for the construction worker figure |
| `assets/css/main.css` | All styles — inlined at build time via `resources.Get` + `minify` |
| `content/_index.md` | Minimal frontmatter; content is driven by the layout, not this file |
| `static/CNAME` | Custom domain for GitHub Pages |

**CSS is inlined** — `baseof.html` uses `resources.Get "css/main.css" | minify` and emits it as a `<style>` block. There is no external stylesheet.

## Deployment

Push to `main` → GitHub Actions builds with Hugo and deploys to GitHub Pages. Workflow at `.github/workflows/deploy.yml`.

## Design Intent

The page is intentionally retro (90s aesthetic): Comic Sans, blinking elements, marquee, construction banners, visitor counter, webring. Preserve this when making changes.
