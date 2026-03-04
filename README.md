# Layla — UX Designer Portfolio

A responsive, accessible portfolio built on a structured design system. Muted Surf color palette, Plus Jakarta Sans typography, and WCAG 2.1 AA compliant throughout.

---

## Design System

The design system lives in `design-system/` and is the single source of truth for all visual decisions. Every page imports it before `styles.css`.

```html
<link rel="stylesheet" href="design-system/design-system.css">
<link rel="stylesheet" href="styles.css">
```

### Files

| File | Purpose |
|------|---------|
| `design-system/tokens.json` | Machine-readable token definitions (W3C Design Token format) |
| `design-system/design-system.css` | CSS custom properties generated from tokens |
| `design-system/index.html` | Token reference documentation |

---

## Color Tokens

### Muted Surf Palette

| Token | Value | Usage |
|-------|-------|-------|
| `--color-slate-500` | `#3d3d5c` | Hero backgrounds, navigation |
| `--color-pink-500` | `#E63980` | Primary CTA, buttons, accents |
| `--color-seafoam-500` | `#00D9A3` | Footer hover, success states |
| `--color-purple-500` | `#5B2A86` | Inline links (8.2:1 on cream — AAA) |
| `--color-neutral-50` | `#FFF8F0` | Page background (cream) |
| `--color-neutral-900` | `#2d2d2d` | Primary text (charcoal) |

Each brand color has a 10-step scale (50–900). Use the numbered tokens for precise control:

```css
/* Examples */
background: var(--color-slate-500);
color: var(--color-pink-600);   /* hover state — darker */
border: 1px solid var(--color-neutral-300);
```

### Shorthand Aliases

For convenience, the design system also exposes shorthand aliases used throughout `styles.css`:

```css
--color-slate        /* = --color-slate-500 */
--color-slate-light  /* = #4a4a6a (gradient second stop) */
--color-pink         /* = --color-pink-500 */
--color-pink-hover   /* = --color-pink-600 */
--color-seafoam      /* = --color-seafoam-500 */
--color-purple       /* = --color-purple-500 */
--color-cream        /* = --color-neutral-50 */
--color-charcoal     /* = --color-neutral-900 */
--color-text         /* = --color-neutral-900 */
--color-text-light   /* = --color-neutral-600 */
--color-white        /* = --color-neutral-0 (#ffffff) */
--color-border       /* = #e5e5e5 */
```

### Semantic Aliases

```css
--color-background      /* page background */
--color-surface         /* card/panel background */
--color-text-primary    /* main body text */
--color-text-secondary  /* muted text, metadata */
--color-text-link       /* link color (purple) */
--color-text-link-hover /* link hover color (pink) */
--color-brand-accent    /* pink — primary interactive */
--color-brand-highlight /* seafoam — success/footer accent */
--color-focus-ring      /* pink — keyboard focus outline */
```

### Dark Mode

Apply `data-theme="dark"` to `<html>` to activate dark mode. Semantic alias tokens remap automatically.

```html
<html lang="en" data-theme="dark">
```

### Semantic States

```css
--color-success-base  /* #00917a — AA on white */
--color-warning-base  /* #b45309 — AA on white */
--color-error-base    /* #dc2626 — AA on white */
--color-info-base     /* #5B2A86 — AAA on white */
```

---

## Typography

**Single font family:** Plus Jakarta Sans — warm, geometric humanist sans-serif loaded from Google Fonts.

```css
--font-primary  /* Plus Jakarta Sans stack */
--font-family-mono  /* JetBrains Mono — code blocks, labels */
```

### Type Scale (Major Third, 1.25× ratio)

| Token | Size | Usage |
|-------|------|-------|
| `--font-size-step2` | 0.75rem | Labels, meta, captions |
| `--font-size-step3` | 0.875rem | Small body, card meta |
| `--font-size-step4` | 1rem | Base body copy |
| `--font-size-step5` | 1.25rem | Lead paragraphs, h4 |
| `--font-size-step6` | 1.563rem | H3 / subheadings |
| `--font-size-step7` | 1.953rem | H2 / section titles |
| `--font-size-step8` | 2.441rem | H1 / page titles |
| `--font-size-step9` | 3.052rem | Display / hero headings |
| `--font-size-hero` | fluid clamp | Super-display (fluid) |

### Font Weights

```css
--font-weight-regular:  400  /* body copy */
--font-weight-medium:   500  /* subtitles, labels */
--font-weight-semibold: 600  /* nav, buttons, UI labels */
--font-weight-bold:     700  /* headings, stats */
```

### Line Heights

```css
--line-height-tight:   1.2  /* headings */
--line-height-base:    1.7  /* body default */
--line-height-relaxed: 1.8  /* long-form, about page */
```

---

## Spacing

8px grid. Named tokens map to multiples of 0.5rem:

| Numeric token | Shorthand | Value | Usage |
|--------------|-----------|-------|-------|
| `--space-1` | `--space-xs` | 0.5rem | Icon gaps, badge padding |
| `--space-2` | `--space-sm` | 1rem | Button gaps, paragraph margins |
| `--space-3` | `--space-md` | 1.5rem | Card padding, form fields |
| `--space-4` | `--space-lg` | 2rem | Card grid gap |
| `--space-6` | `--space-xl` | 3rem | Large section gaps |
| `--space-8` | `--space-2xl` | 4rem | Section vertical padding |
| `--space-12` | `--space-3xl` | 6rem | Page-level section gaps |

---

## Shadows

```css
--shadow-md   /* 0 4px 20px rgba(0,0,0,0.08) — card default */
--shadow-lg   /* 0 8px 30px rgba(0,0,0,0.12) — card hover, modal */
--shadow-pink /* 0 4px 12px rgba(230,57,128,0.3) — button hover */
--shadow-focus /* 0 0 0 3px rgba(230,57,128,0.35) — focus ring */
```

---

## Motion

All durations respect `prefers-reduced-motion`.

```css
--motion-link-hover  /* 200ms ease-out — nav underlines, color changes */
--motion-card-hover  /* 300ms spring  — card lift with bounce */
--motion-modal-open  /* 500ms expressive — modal/drawer entrance */
```

---

## Layout

```css
--max-width:        1200px  /* wide container */
--max-width-narrow: 800px   /* article / case study */
--border-radius:    8px     /* = --radius-base */
```

Responsive breakpoints (mobile-first):

```css
/* Tablet */
@media (max-width: 768px) { ... }

/* Small mobile */
@media (max-width: 480px) { ... }
```

---

## Site Pages

| File | Description |
|------|-------------|
| `index.html` | Home — hero, featured work, differentiators, CTA |
| `about.html` | Biography, career highlights, differentiators |
| `case-study.html` | HEB Accessibility Program case study |
| `styles.css` | All component styles, references design system tokens |

### Case Study Narrative Structure

Each case study follows this arc:

1. **Challenge** — What problem existed and why it mattered
2. **Approach** — Strategy, not just tactics
3. **What I Built** — Concrete deliverables
4. **Impact** — Measurable outcomes + cultural change
5. **What I Learned** — Honest reflection

---

## Accessibility

This site is built to WCAG 2.1 AA:

- Skip-to-content link on every page
- Semantic HTML5 with proper heading hierarchy
- ARIA labels and landmarks throughout
- All color pairs tested for contrast (purple links = AAA on cream)
- Keyboard navigation with visible focus indicators
- Mobile menu controlled via ARIA `aria-expanded`
- `prefers-reduced-motion` and `prefers-contrast: high` media queries
- 44px minimum touch targets

---

## Updating Content

**Colors** — Edit `--color-*` tokens in `design-system/design-system.css`. Changes propagate everywhere automatically.

**Typography** — Update the Google Fonts link in each HTML `<head>` and the `--font-primary` token.

**Content** — Edit HTML files directly. Placeholder images (`via.placeholder.com`) should be replaced with real project screenshots (600×400px for work cards, 1200×600px for case study images).

**Adding pages** — Duplicate an HTML file, update the `<title>`, meta description, and active nav link. No new CSS needed for standard layouts.
