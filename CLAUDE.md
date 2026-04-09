# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

A static HTML/CSS/JS digital resume and portfolio for Mohammed Fahim Khan, hosted via GitHub Pages at `https://ifahimkhan.github.io/Digital-Resume/`.

No build system, package manager, or framework. Pure HTML, CSS, and vanilla JavaScript. Open `index.html` directly in a browser to preview.

## Architecture

### Core files

| File | Purpose |
|------|---------|
| `index.html` | Main portfolio page — all sections (hero, about, skills, experience, projects, contact) live here as inline HTML |
| `style.css` | Primary stylesheet (root-level) — design system variables, all component styles, light/dark themes, responsive breakpoints |
| `script.js` | All interactivity — theme toggle, loader, custom cursor, navbar scroll, hamburger menu, typing animation, scroll-reveal, stat counters, contact form |
| `styles/main.css` | **Legacy** stylesheet from an older version of the site; not linked by `index.html` |

### Standalone pages

`chessClock.html`, `mindreaderapp.html`, `mindreader-privacy-policy.html`, `project1.html` — separate project/app landing pages with their own inline styles. These are independent of the main portfolio's design system.

### Assets

- `assets/Fahim_Resume.pdf` — downloadable resume linked from the About section
- `assets/images/` — profile photo and preview screenshots

## Design System

CSS custom properties are defined in `:root` (dark mode default) and `[data-theme="light"]` in `style.css`:

- Color tokens: `--bg`, `--bg2`, `--bg3`, `--card`, `--card2`, `--accent`, `--accent2`, `--text`, `--text2`, `--text3`, `--border`, `--border2`
- Typography: `--mono` (JetBrains Mono), `--sans` (Space Grotesk)
- Layout: `--radius`, `--radius-lg`, `--transition`, `--shadow`

Theme switching is JS-driven (`script.js`): toggling the `#themeToggle` checkbox sets `data-theme="light"` on `<html>` and persists to `localStorage`. No manual CSS edits needed.

## Key UI Patterns

- **Projects section**: Cards are hardcoded HTML in `index.html` (`<div class="project-card featured reveal">`), not rendered from a JS data array. To add/remove projects, edit the HTML directly inside `<div class="projects-grid">`.
- **Scroll animations**: Elements with class `reveal` are animated on scroll via IntersectionObserver in `script.js`.
- **Responsive breakpoints**: `1024px` (tablet — hero card hidden, grids collapse to single column) and `768px` (mobile — hamburger nav, stacked layouts).

## Deployment

Push to `master` branch deploys automatically via GitHub Pages. No CI/CD pipeline.
