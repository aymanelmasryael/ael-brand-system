# 02 — AEL Visual Identity

## Logo

**File**: `ael-logo.svg`

- **ViewBox**: `0 0 226.77 226.77`
- **Display size**: 80×80 (inline)
- **Type**: Custom AEL grid pattern — blue block matrix
- **Structure**: SVG path + rect elements representing a 7×7 grid block pattern
- **Colors used**: `#ffffff` (top-left path), `#0074FF` (all rect elements)
- **Path element**: Top-left L-shaped block in white `d="m97.19,48.59v16.2h-32.4v-16.2c0-8.94-7.25-16.2-16.2-16.2s-16.2,7.25-16.2,16.2v16.2H0v-16.2c0-5.68.98-11.13,2.76-16.2C9.44,13.52,27.44,0,48.59,0s39.16,13.52,45.83,32.4c1.79,5.07,2.76,10.52,2.76,16.2Z"`
- **Grid blocks**: 18 blue rect elements (32.4×32.4 each) forming the A, E, L letter shapes

### Logo Usage Rules

- **Minimum clear space**: 16px on all sides
- **Minimum size**: 32px (inline nav), 80px (hero)
- **Background**: Always on dark backgrounds (`#0B1220` or darker)
- **Do not**: Recolor, rotate, distort, or place on light backgrounds
- **Do not**: Add drop shadows that alter the block geometry
- **Allowed**: Inline in nav, hero section, footer, GitHub profile README

---

## Color System

### Brand Palette (extracted from source code)

| Token | Hex | RGB | HSL | Usage |
|-------|-----|-----|-----|-------|
| `--ael-blue` | `#0074FF` | `rgb(0, 116, 255)` | `hsl(213, 100%, 50%)` | Primary brand, CTAs, links, active states |
| `--ael-gold` | `#FFD700` | `rgb(255, 215, 0)` | `hsl(51, 100%, 50%)` | Accent, highlights, badges, premium indicators |
| `--ael-teal` | `#00FFCC` | `rgb(0, 255, 204)` | `hsl(168, 100%, 50%)` | Secondary accent, success states, innovation |
| `--ael-purple` | `#6C47FF` | `rgb(108, 71, 255)` | `hsl(252, 100%, 64%)` | Depth, creativity sections, decorative |
| `--ael-pink` | `#FF4D8D` | `rgb(255, 77, 141)` | `hsl(339, 100%, 65%)` | Energy, distinction elements, highlights |

### Background & Text

| Token | Hex | RGB | Usage |
|-------|-----|-----|-------|
| `--ael-bg` | `#0B1220` | `rgb(11, 18, 32)` | Page background (deep navy) |
| `--ael-text` | `#E6EEF8` | `rgb(230, 238, 248)` | Primary text (ice white) |

### Semantic Colors (from source CSS)

| Token | Hex | RGB | Usage |
|-------|-----|-----|-------|
| `--ael-text-secondary` | `#8899AA` | `rgb(136, 153, 170)` | Secondary text, meta |
| `--ael-border` | `rgba(255,255,255,0.08)` | — | Subtle borders, dividers |
| `--ael-glass-bg` | `rgba(255,255,255,0.03)` | — | Glassmorphism card backgrounds |
| `--ael-glass-border` | `rgba(255,255,255,0.06)` | — | Glassmorphism card borders |
| `--ael-glass-hover` | `rgba(255,255,255,0.06)` | — | Glass card hover state |
| `--ael-tag-bg` | `rgba(0,116,255,0.1)` | — | Tag/badge background |
| `--ael-tag-text` | `#4DA6FF` | `rgb(77, 166, 255)` | Tag/badge text |
| `--ael-success` | `#00CC88` | `rgb(0, 204, 136)` | Success states, form valid |
| `--ael-error` | `#FF4466` | `rgb(255, 68, 102)` | Error states, form invalid |
| `--ael-warning` | `#FFAA00` | `rgb(255, 170, 0)` | Warning states |

### Gradient Definitions (from source CSS)

| Gradient Name | CSS Value |
|---------------|-----------|
| Hero accent | `linear-gradient(135deg, #0074FF, #00FFCC)` |
| Gold accent | `linear-gradient(135deg, #FFD700, #FFAA00)` |
| Purple accent | `linear-gradient(135deg, #6C47FF, #00FFCC)` |
| Pink accent | `linear-gradient(135deg, #FF4D8D, #FF8C00)` |
| Blue accent | `linear-gradient(135deg, #0074FF, #6C47FF)` |
| Glass overlay | `linear-gradient(180deg, rgba(255,255,255,0.03) 0%, rgba(255,255,255,0.01) 100%)` |

### Text Gradient (via `background-clip: text`)

Used on hero heading and section titles — gradient applied to text with `-webkit-background-clip: text; -webkit-text-fill-color: transparent;`.

### Color Application Rules

- **Primary backgrounds**: Always `#0B1220` — never light mode
- **Cards**: Glassmorphism with `rgba(255,255,255,0.03)` background and `rgba(255,255,255,0.06)` border
- **Links**: `#0074FF` with `#4DA6FF` hover — no underlines by default
- **Buttons**: Solid `#0074FF` or gradient backgrounds — white text
- **Badges/Tags**: `rgba(0,116,255,0.1)` background, `#4DA6FF` text
- **Glow effects**: `0 0 20px rgba(0,116,255,0.3)` for blue, `0 0 20px rgba(0,255,204,0.3)` for teal

---

## Typography

### Font Stack

```css
--ael-font-primary: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', system-ui, sans-serif;
--ael-font-mono: 'SF Mono', 'Fira Code', 'Fira Mono', 'Roboto Mono', 'Courier New', monospace;
```

### Font Sizes (from source CSS custom properties)

| Token | Value | Usage |
|-------|-------|-------|
| `--ael-text-xs` | `0.75rem` (12px) | Small labels, meta |
| `--ael-text-sm` | `0.8125rem` (13px) | Tags, badges, secondary |
| `--ael-text-base` | `0.9375rem` (15px) | Body text |
| `--ael-text-lg` | `1.125rem` (18px) | Large body, card text |
| `--ael-text-xl` | `1.25rem` (20px) | Subheadings |
| `--ael-text-2xl` | `1.5rem` (24px) | Section headings |
| `--ael-text-3xl` | `2rem` (32px) | Major headings |
| `--ael-text-4xl` | `2.5rem` (40px) | Hero heading |

### Font Weights

| Weight | Usage |
|--------|-------|
| `300` | Light — decorative text, large headings |
| `400` | Regular — body text, paragraphs |
| `500` | Medium — subheadings, nav links |
| `600` | Semibold — section titles, button text |
| `700` | Bold — hero heading, strong emphasis |

### Line Heights

- Body: `1.6`
- Headings: `1.2`
- Small text: `1.4`

### Typography Rules

- Hero heading: `--ael-text-4xl` (2.5rem), weight 300 (light), gradient text
- Section titles: `--ael-text-3xl` (2rem), weight 300
- Card titles: `--ael-text-lg` (1.125rem), weight 600
- Body text: `--ael-text-base` (0.9375rem), weight 400, color `--ael-text`
- Monospace: Used in terminal components, badges, code blocks
- No serif fonts used anywhere in the system

---

## Iconography

- **Source**: Font Awesome Free 6.4.0 (SVG sprite sheet)
- **Implementation**: Inline SVG elements with `<use href="#icon-name">` referencing sprite sheet
- **Icon prefix**: `#` (e.g., `#check`, `#code`, `#terminal`, `#globe`, `#github`, `#linkedin`)
- **Icon size**: Controlled via CSS `width` and `height` (default inline size from sprite)
- **Icon color**: Inherits `currentColor` from parent text
- **Accent icons**: Use brand colors via `fill` or `color` CSS property
- **Deployment**: SVG sprite sheet included inline in the HTML `<body>`
- **Active icon set**: check, code, terminal, globe, github, linkedin, x-twitter, instagram, codepen, arrow-up-right, menu, close, sun, moon, sparkle, cubes

### Icon Usage Rules

- Always use `<svg><use href="#icon-name"></svg>` pattern
- Add `aria-hidden="true"` to decorative icons
- Add `role="img"` with `<title>` for informative icons
- Never resize icons below 12×12 or above 32×32
- Default social icon size: 20×20 in footer, 24×24 in hero
