# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static HTML email signature templates for logistics companies, hosted on GitHub Pages at `https://thefrisb.github.io/globe-logistics/`. Each branch represents a different company's signature (e.g., `main` = Globe Logistics Inc., `bergenstar` = Bergenstar Inc.).

## No Build System

This is a pure HTML/CSS project with no dependencies, no package manager, and no build/test/lint commands. Edit `index.html` directly.

## Deployment

Files are served directly via GitHub Pages. All image `src` attributes must use absolute URLs pointing to `https://thefrisb.github.io/globe-logistics/` for email client compatibility.

## Architecture

`index.html` is the sole source file — a self-contained HTML email signature using:
- **Table-based layout** (required for email client compatibility)
- **Inline CSS only** (email clients strip `<style>` blocks)
- **Font:** Lucida Sans Unicode, sans-serif

### Signature Sections (top to bottom)
1. Logo + contact name/title
2. Contact info (office, fax, afterhours, email) with `tel:` links
3. Website + MC number
4. Social media icons (Facebook, LinkedIn) — icons hosted as PNGs in repo root
5. Legal/notice text
6. Policy table (e.g., accessorial charges) — not present in all branches

## Branching Convention

Each branch is a separate company's signature. Changes to one company's signature should stay on that company's branch. The `todo.txt` file (untracked) tracks pending changes for the current branch's company.

## Key Constraints

- All images must be PNG for maximum email client support (WebP has limited email client support)
- Keep all styling inline — no external stylesheets or `<style>` tags
- Use `<table>` layout, not CSS flexbox/grid
- Phone numbers use `tel:` links with raw digits (e.g., `tel:12018229699`)
- Color values are defined inline per-element; search-and-replace to update brand colors
