# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Portfolio website for Brookelyn Rose, an artist and illustrator. Static single-page site — no build tools, no package manager, no frameworks. Just open `index.html` in a browser.

## Deployment

- **Hosted on GitHub Pages** (legacy deploy from `main` branch): https://bryan-legend.github.io/brookelyn-rose-portfolio/
- **Repo**: https://github.com/Bryan-Legend/brookelyn-rose-portfolio
- Push to `main` triggers automatic deployment. To force a rebuild: `gh api repos/Bryan-Legend/brookelyn-rose-portfolio/pages/builds -X POST`
- Git identity for this repo: `Bryan-Legend` / `Bryan-Legend@users.noreply.github.com`

## Architecture

- **`index.html`** — The live site. Single file with embedded CSS and vanilla JS. ~1,750 lines.
- **`index-v1.html`** — Archived previous design iteration (Playfair Display + Lato fonts, simpler layout).
- **`Art/`** — ~57 image assets (JPG, PNG, JPEG, GIF). Filenames contain spaces. Organized by project series:
  - Imago (comic pages 1-4, character art)
  - Kandy Knight (poster, character lineup, carriage, assets)
  - Studies (10 reference/result pairs: Cat, Monk, Profile, Goblin, Woman, Hair Model, Old Man, Pirate, Pirate 2, Vampire)
  - Arya Stark (4-step progression: Sketch → Sketch 2 → Inkwork → Colored)
  - Rufus and Penelope, Storyboard, Concept to Model, Fifth Grader
  - 14 standalone illustrations
- **`Art/Originals/`** — High-res source files for studies.

## Key Design Details

- **Fonts**: Cormorant Garamond (headings), Nunito Sans (body), Caveat (handwritten accents) via Google Fonts
- **Color palette** (CSS custom properties in `:root`): blush, cream, rose, dusty-rose, deep-rose, burgundy, warm-purple, light-mauve, charcoal, warm-gray, off-white, paper
- **Aesthetic**: Editorial art-book style — asymmetric layouts, section number watermarks, paper grain overlay, staggered scroll-reveal animations, glass-morphism lightbox
- **Sections**: Hero (split layout) → Imago → Kandy Knight → Illustrations (masonry) → Studies (reference/result pairs) → Character Design → Contact

## Working With This Codebase

- All changes go in `index.html`. CSS and JS are embedded inline — no external files.
- Image paths use `Art/` prefix with spaces in filenames (e.g., `Art/Imago the Mouse.jpg`). Always verify exact filenames — some are `.jpeg` not `.jpg` (Arya Stark Colored/Inkwork).
- The Kandy Knight Poster is low-res — its display is intentionally constrained (not full-width) to avoid graininess.
- `Concept to Model.png` is a single image containing both concept art and 3D model side-by-side. It's displayed as two cards using CSS `object-position` cropping (concept=right, model=left).
- `5th Grader Render.jpg` is actually a painting of a child's sketch, not a 3D render. Labeled accordingly in the UI.
- The `frontend-design` plugin is enabled (`.claude/settings.json`) for elevated design work.

## Contact Info (referenced in footer)

- Email: brookelynlivingston@gmail.com
- Instagram: https://www.instagram.com/artbybrookelyn/
- Available for commission & hire — remote or local in Utah
