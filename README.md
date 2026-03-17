# Noir Absolu

> A cinematic, single-page landing experience for a luxury fragrance brand — built as a freelance portfolio concept.

---

## Live Demo

🔗 **[noir-absolu.netlify.app](https://noir-absolu.netlify.app)**

---

## Screenshot

![Noir Absolu — Hero Section](https://placehold.co/1440x900/0a0a0a/c9a96e?text=Screenshot+coming+soon)

_Full-page screenshot — see the [live demo](https://noir-absolu.netlify.app) for the animated experience._

---

## Overview

Noir Absolu is a dark, cinematic landing page for a fictional luxury perfume house. The aesthetic references Tom Ford Beauty and Aesop — monochromatic black with restrained gold accents, editorial typography, and choreographed motion.

The entire project ships as a **single `index.html` file** with no build step, no bundler, and no runtime dependencies beyond a Google Fonts CDN link and Tailwind CSS via CDN.

---

## Tech Stack

| Layer | Choice | Why |
|-------|--------|-----|
| Markup | Semantic HTML5 | `<section>`, `<article>`, `<nav>`, `<blockquote>`, `<cite>` — correct document outline |
| Styling | CSS custom properties + Tailwind CSS (CDN) | Design tokens via `:root`, utility classes for layout |
| Motion | Vanilla CSS `@keyframes` + JS `IntersectionObserver` | 60 fps, no GSAP, no ScrollMagic |
| Fonts | Google Fonts — Cormorant Garamond, Jost | Serif display + geometric sans |
| Icons | Material Symbols Outlined | Thin-weight icon set, variable font |

**Zero npm. Zero build step. Open and run.**

---

## Features

- **Preloader** — branded name pulses with a gold bar animation; fades out after assets load
- **Hero entrance** — staggered `translateY` + `opacity` animation on three elements after preloader dismissal
- **Scroll reveal** — `IntersectionObserver` triggers a staggered fade-up on every card and section heading as they enter the viewport
- **Parallax text** — oversized outlined "ABSOLU" moves horizontally on scroll via `requestAnimationFrame`, with reduced travel on mobile to prevent overflow
- **Cursor glow** — a 520px radial gold gradient follows the cursor via `rAF`-throttled `mousemove`; desktop only (`pointer: fine` media query)
- **Infinite marquee** — CSS `@keyframes` scrolls a duplicated ingredient list seamlessly; pauses on hover
- **Hover effects** — gold border glow + `translateY(-4px)` lift on collection cards; rising gold fill from bottom on the CTA button; underline draw on nav links
- **Responsive design** — fluid `clamp()` typography and spacing, hamburger drawer on mobile, tested at 375 / 768 / 1024 / 1440 px
- **Reduced motion** — `@media (prefers-reduced-motion: reduce)` disables all animations globally

---

## Page Sections

1. Fixed navigation with scroll-triggered frosted-glass effect
2. Full-viewport hero with typographic composition
3. Ingredient marquee ticker
4. Split-layout brand story with SVG bottle illustration
5. Parallax typographic break — "ABSOLU"
6. Fragrance notes grid (Top / Heart / Base)
7. Editorial pull quote with `<blockquote>` + `<cite>`
8. Product collection grid (Eau de Nuit, Ombre Sauvage, Sillage Noir)
9. Full-bleed call-to-action
10. Footer with navigation links

---

## Running Locally

No install required.

```bash
# Option 1 — just open it
open index.html         # macOS
start index.html        # Windows

# Option 2 — local dev server with live reload
npx live-server . --port=3000

# Option 3 — Python (no Node required)
python -m http.server 8000
# then visit http://localhost:8000
```

---

## Project Structure

```
noir-absolu/
├── index.html          # Entire project — HTML + inline CSS + inline JS
├── design-system.md    # Color palette, typography scale, animation guidelines
└── README.md
```

---

## Design System

Full tokens documented in [`design-system.md`](./design-system.md).

| Token | Value |
|-------|-------|
| Background | `#0A0A0A` |
| Gold accent | `#C9A96E` |
| Ivory text | `#F5F0E8` |
| Stone (muted) | `#A89F94` |
| Display font | Cormorant Garamond 300–500 |
| Body font | Jost 200–400 |

---

## Tools Used

| Tool | Role |
|------|------|
| [Claude Desktop](https://claude.ai/download) | Primary development environment — wrote all HTML, CSS, and JS |
| [Google Stitch MCP](https://stitch.withgoogle.com) | Generated initial UI screen mockups from text prompts |
| [21st.dev Magic MCP](https://21st.dev) | Component inspiration and UI reference |

This project was built entirely through **natural language prompts** inside Claude Desktop using MCP (Model Context Protocol) tool integrations — no manual IDE editing.

---

## Accessibility

- Semantic landmarks: `<nav>`, `<main>`, `<section aria-labelledby>`, `<footer>`
- All images have descriptive `alt` text
- Decorative elements carry `aria-hidden="true"`
- Mobile menu managed with `aria-expanded`, `aria-hidden`, and focus trapping
- `prefers-reduced-motion` respected — all animations disabled for users who opt out

---

## Built For

This is a **freelance portfolio concept project** — not affiliated with any real fragrance brand. It demonstrates:

- High-fidelity UI implementation from a design brief
- Performant, dependency-free vanilla web development
- Motion design and interaction choreography without heavy libraries
- AI-assisted development workflow using Claude + MCP tooling

---

<p align="center">
  <sub>Designed &amp; built by <a href="https://github.com/Raw3a-Gamal">@Raw3a-Gamal</a> · 2024</sub>
</p>
