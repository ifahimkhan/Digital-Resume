# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

A static HTML/CSS digital resume website for Mohammed Fahim Khan, hosted via GitHub Pages at `https://ifahimkhan.github.io/Digital-Resume/`.

No build system, package manager, or JavaScript framework — pure HTML and CSS. Open any `.html` file directly in a browser to preview.

## File Structure

- `index.html` — Main resume page
- `styles/main.css` — Single stylesheet for all pages
- `assets/` — Images and the downloadable PDF resume (`Fahim_Resume.pdf`)
- `chessClock.html`, `mindreaderapp.html`, `mindreader-privacy-policy.html`, `project1.html` — Additional project/app pages

## Theme Switching

The site defaults to **dark mode**. To switch to light mode, edit the CSS variable assignments in `styles/main.css` under `:root`:

```css
--mainTextColor: var(--mainTextColor-light);
--secondaryTextColor: var(--secondaryTextColor-light);
--mainLinkColor: var(--mainLinkColor-light);
--mainBorderColor: var(--mainBorderColor-light);
--mainBgColor: var(--mainBgColor-light);
```

Both light and dark color tokens are defined in `:root`; only the active assignments (lines 16–20) need to change.

## Deployment

Changes pushed to the `master` branch are automatically served via GitHub Pages. No CI/CD pipeline — deployment is immediate on push.
