# Noir Absolu — Design System Reference

> Aesthetic direction: Tom Ford meets Aesop. Dark, cinematic, moody, premium.
> Paste this file into future conversations to maintain consistency.

---

## 1. COLOR PALETTE

| Role                  | Name            | Hex       | Usage                                      |
|-----------------------|-----------------|-----------|--------------------------------------------|
| Primary Background    | Obsidian        | `#0A0A0A` | Page background, section fills             |
| Secondary Background  | Carbon          | `#141414` | Cards, nav, elevated surfaces              |
| Tertiary Surface      | Ash             | `#1E1C1A` | Subtle section breaks, borders             |
| Accent — Primary      | Antique Gold    | `#C9A96E` | CTAs, highlights, decorative lines         |
| Accent — Muted        | Burnished Brass  | `#8A6E42` | Secondary accents, icon strokes            |
| Heading Text          | Ivory           | `#F5F0E8` | H1–H3, hero copy                           |
| Body Text             | Stone           | `#A89F94` | Paragraphs, captions, labels               |
| Subtle Text           | Graphite        | `#5C564F` | Placeholders, disabled, fine print         |
| Border / Divider      | Smoke           | `#2A2520` | Hairlines, card outlines                   |
| Overlay               | Veil            | `rgba(10,10,10,0.72)` | Hero overlays, modal backdrops |

### CSS Custom Properties

```css
:root {
  --color-bg-primary:    #0A0A0A;
  --color-bg-secondary:  #141414;
  --color-bg-surface:    #1E1C1A;
  --color-accent:        #C9A96E;
  --color-accent-muted:  #8A6E42;
  --color-text-heading:  #F5F0E8;
  --color-text-body:     #A89F94;
  --color-text-subtle:   #5C564F;
  --color-border:        #2A2520;
  --color-overlay:       rgba(10, 10, 10, 0.72);
}
```

---

## 2. TYPOGRAPHY

### Font Stack

| Role          | Font                  | Google Fonts Import              | Weights      |
|---------------|-----------------------|----------------------------------|--------------|
| Display/Hero  | **Cormorant Garamond** | `family=Cormorant+Garamond`      | 300, 400, 500 |
| Headings      | **Playfair Display**  | `family=Playfair+Display`        | 400, 500     |
| Body / UI     | **Jost**              | `family=Jost`                    | 200, 300, 400 |

### Google Fonts Import (single link)

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,500;1,300;1,400&family=Jost:wght@200;300;400&family=Playfair+Display:wght@400;500&display=swap" rel="stylesheet">
```

### Type Scale

| Token        | Font                  | Size (desktop) | Size (mobile) | Weight | Line Height | Letter Spacing      |
|--------------|-----------------------|----------------|---------------|--------|-------------|---------------------|
| `.display`   | Cormorant Garamond    | 96px / 6rem    | 52px          | 300    | 1.0         | `0.02em`            |
| `h1`         | Cormorant Garamond    | 72px / 4.5rem  | 42px          | 400    | 1.05        | `0.01em`            |
| `h2`         | Playfair Display      | 48px / 3rem    | 32px          | 400    | 1.15        | `0`                 |
| `h3`         | Playfair Display      | 32px / 2rem    | 24px          | 400    | 1.25        | `0`                 |
| `h4`         | Jost                  | 13px / 0.8rem  | 12px          | 300    | 1.4         | `0.25em` (ALL CAPS) |
| `p` / body   | Jost                  | 16px / 1rem    | 15px          | 300    | 1.8         | `0.01em`            |
| `.caption`   | Jost                  | 13px / 0.8rem  | 12px          | 200    | 1.6         | `0.05em`            |

### Letter-Spacing Rules

- **ALL CAPS labels, eyebrows, navlinks:** `letter-spacing: 0.20em–0.30em` — always uppercase + tracking, never bold
- **Serif display text:** `letter-spacing: 0.02em` max — serifs breathe, don't stretch
- **Body copy:** `letter-spacing: 0.01em` — barely perceptible, improves readability on dark bg

### CSS Typography Tokens

```css
:root {
  --font-display:   'Cormorant Garamond', Georgia, serif;
  --font-heading:   'Playfair Display', Georgia, serif;
  --font-body:      'Jost', system-ui, sans-serif;

  --text-display:   clamp(3.25rem, 8vw, 6rem);
  --text-h1:        clamp(2.625rem, 6vw, 4.5rem);
  --text-h2:        clamp(2rem, 4vw, 3rem);
  --text-h3:        clamp(1.5rem, 2.5vw, 2rem);
  --text-h4:        0.8rem;
  --text-body:      1rem;
  --text-caption:   0.8rem;
}
```

---

## 3. SPACING & LAYOUT

### Section Padding

| Context       | Top / Bottom Padding   | Left / Right Padding  |
|---------------|------------------------|-----------------------|
| Desktop       | `160px` (10rem)        | `80px` (5rem)         |
| Tablet        | `100px` (6.25rem)      | `40px` (2.5rem)       |
| Mobile        | `72px` (4.5rem)        | `24px` (1.5rem)       |
| Hero section  | `200px` top, `160px` bottom (desktop) | full-bleed |

### Spacing Scale (base-8)

```
4px   — micro gap (icon padding, badge inset)
8px   — xs
16px  — sm
24px  — md
32px  — lg
48px  — xl
64px  — 2xl
96px  — 3xl
128px — 4xl
```

### Grid System

- **Columns:** 12-column grid
- **Gutter:** `32px` desktop / `16px` mobile
- **Max content width:** `1280px` (`80rem`)
- **Max text column width:** `680px` — never let body copy run wider
- **Centered layout with:** `margin-inline: auto; padding-inline: clamp(1.5rem, 5vw, 5rem);`

### CSS Layout Tokens

```css
:root {
  --max-width:       80rem;       /* 1280px */
  --max-prose:       42.5rem;     /* 680px  */
  --gutter:          clamp(1.5rem, 5vw, 5rem);
  --section-py:      clamp(4.5rem, 10vw, 10rem);
  --grid-cols:       12;
  --grid-gap:        clamp(1rem, 2.5vw, 2rem);
}

.container {
  width: 100%;
  max-width: var(--max-width);
  margin-inline: auto;
  padding-inline: var(--gutter);
}
```

---

## 4. ANIMATION GUIDELINES

### Easing Curves

```css
:root {
  --ease-luxury:    cubic-bezier(0.25, 0.1, 0.0, 1.0);   /* primary — slow out, felt arrival */
  --ease-reveal:    cubic-bezier(0.16, 1, 0.3, 1);        /* scroll reveals — spring-like */
  --ease-hover:     cubic-bezier(0.4, 0, 0.2, 1);         /* UI hover — material standard */
  --ease-out-expo:  cubic-bezier(0.19, 1, 0.22, 1);       /* hero entrances              */
}
```

### Timing Reference

| Interaction          | Duration      | Easing           | Notes                              |
|----------------------|---------------|------------------|------------------------------------|
| Hover (color/border) | `250ms`       | `--ease-hover`   | Buttons, links, card borders       |
| Hover (scale/glow)   | `400ms`       | `--ease-luxury`  | Product cards, image zoom          |
| Scroll reveal        | `700ms–900ms` | `--ease-reveal`  | Stagger siblings by `80ms`         |
| Hero text entrance   | `1000ms`      | `--ease-out-expo`| Split by line, delay `150ms/line`  |
| Page transition      | `600ms`       | `--ease-luxury`  | Fade + slight upward drift (20px)  |
| Modal open/close     | `350ms`       | `--ease-luxury`  | Opacity + scale from `0.97→1`      |

### Scroll Reveal Pattern

```css
/* Initial state — apply via JS class */
.reveal {
  opacity: 0;
  transform: translateY(28px);
  transition:
    opacity  var(--ease-reveal) 800ms,
    transform var(--ease-reveal) 800ms;
}

.reveal.is-visible {
  opacity: 1;
  transform: translateY(0);
}
```

```js
// Stagger siblings on intersection
const observer = new IntersectionObserver((entries) => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      const siblings = entry.target.parentElement.querySelectorAll('.reveal');
      siblings.forEach((el, i) => {
        el.style.transitionDelay = `${i * 80}ms`;
        el.classList.add('is-visible');
      });
    }
  });
}, { threshold: 0.15 });
```

### Hover Micro-interactions

- **Gold accent line:** `scaleX(0 → 1)` on hover, origin left, `300ms --ease-luxury`
- **Image zoom:** `scale(1 → 1.04)` inside `overflow: hidden`, `500ms --ease-luxury`
- **Button:** background opacity fade + letter-spacing nudge `+0.02em`, `250ms`
- **Nav links:** thin underline draw, no color change (color is already muted/gold)

---

## 5. DESIGN PRINCIPLES

### I. Restraint as Luxury
> "What is absent speaks louder than what is present."

Whitespace (here: darkspace) is the primary design element. Never fill space for the sake of filling it. One strong element per visual zone. Resist the urge to add — remove instead. Copy should be sparse, sentences short, silence between sections intentional.

### II. Tactile Before Digital
> "Every element should feel like it could exist in physical form."

Textures over flat fills. Hairline borders over thick strokes (`1px`, never `2px`). Typography that recalls letterpress — serifs, weight contrast, wide tracking on small caps. Imagery should evoke materiality: glass, resin, smoke, linen, aged paper.

### III. Slow Reveals, Never Instant
> "Luxury does not rush. Neither does this interface."

Animations are never snappy or bouncy — they arrive, they settle. Nothing pops in; everything glides. User interactions (hover, scroll, click) should feel weighted, like lifting a heavy object with precision. Fast = cheap. Deliberate = rare.

---

## QUICK REFERENCE CARD

```
BG PRIMARY   #0A0A0A    ACCENT       #C9A96E
BG SECONDARY #141414    TEXT HEAD    #F5F0E8
BG SURFACE   #1E1C1A    TEXT BODY    #A89F94

DISPLAY FONT  Cormorant Garamond 300
HEADING FONT  Playfair Display 400
BODY FONT     Jost 200–300

SECTION PAD   160px desktop / 72px mobile
MAX WIDTH     1280px content / 680px prose
HOVER SPEED   250ms (color) / 400ms (transform)
REVEAL SPEED  800ms + 80ms stagger
EASING        cubic-bezier(0.25, 0.1, 0.0, 1.0)
```

---

*Noir Absolu Design System — v1.0*
*For freelance portfolio use. Maintain this file as the single source of truth.*
