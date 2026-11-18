# OVRA — “Every Workout” Landing Page

A single-file, static landing page for **OVRA**, a fictional athletic knitwear label. The design features a light misty-orchid palette across three sections: a framed hero with a cut-out athlete, a “WORKOUT” photo collage, and a “Fresh Fits” marquee/lookbook card.

<img width="1900" height="891" alt="Screenshot 2026-11-18 184059" src="https://github.com/user-attachments/assets/6d128d55-9720-4f14-900f-604a9f96badc" />

## Project structure

- `index.html` — Complete page with inline CSS and JavaScript (no frameworks, no build step, no external libraries).

## Getting started

1. Open `index.html` directly in a modern browser, **or** serve the folder locally (recommended for consistent font/asset loading), e.g.:
   - `npx serve .`
   - `python -m http.server`
2. View at desktop (designed around 1440×956) and mobile widths (phone layout below 821px).

## Page sections

1. **Hero** — Notched OVRA header, navigation, gradient sky panel with ray lines, large athlete cut-out, headline/CTAs, avatar stack, intro copy, and a video preview card.
2. **WORKOUT collage** — Layered photo cards with an outlined “WORKOUT” wordmark and supporting copy.
3. **Fresh Fits marquee** — Opposing scrolling type rows and a central cycling look card with animated title/tag.

## Implementation notes

- **Single file:** All styles and behavior live inside `index.html`.
- **Typography:** [Archivo](https://fonts.google.com/specimen/Archivo) variable font (WOFF2, weights 100–900, widths 62–125%) loaded from Google Fonts static hosting. “Stencil” lettering is achieved via per-letter CSS masks.
- **Assets:** Hero/collage/marquee imagery and crops are loaded from the provided remote image URLs (Higgs CDN / CloudFront sources) at runtime; no assets are re-hosted in this repo.
- **Scaling & layout:** CSS/JS scaling based on a 1440×956 design frame (`u/uw`), with a dedicated phone layout below 821px width.
- **Motion:** Intro timeline, strip-reveal transitions, letter wipes, scroll-linked marquee motion, and timed look cycling. Includes a JS-enabled visibility failsafe and respects `prefers-reduced-motion: reduce` (renders the final static state without motion).
- **Scrolling:** Custom eased wheel scrolling on non-touch wheel input; native behavior preserved for touch, keyboard, and scrollbars.

## Browser support

Best experienced in current Chromium, Firefox, and Safari browsers with support for CSS custom properties, `calc()`, variable fonts, Web Animations/`requestAnimationFrame`, and CSS masking/backdrop effects used by the design.
