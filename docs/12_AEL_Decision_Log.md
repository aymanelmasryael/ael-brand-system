# 12 — AEL Decision Log

## Purpose

Records the rationale behind brand and design decisions. Prevents drift and preserves context for future maintainers.

---

## 01 — Font: Inter

| Field | Value |
|-------|-------|
| **Decision** | Use Inter as primary typeface |
| **Date** | 2024 (initial site) |
| **Alternatives considered** | SF Pro (Apple-only), Helvetica (overused), Manrope (less versatile) |
| **Why Inter** | Open-source, designed for screens, excellent readability at all weights (300–700), available on Google Fonts with `display=swap`, works on macOS and Windows natively. Supports Arabic fallback via system-ui. |
| **Trade-offs** | Adds one external request to Google Fonts. No variable weight support used (individual weights loaded). |
| **Status** | ✅ Confirmed |

---

## 02 — Monospace: System Font Stack

| Field | Value |
|-------|-------|
| **Decision** | Use system monospace stack rather than loading a custom font |
| **Date** | 2024 |
| **Alternatives considered** | JetBrains Mono, Fira Code (Google Fonts) |
| **Why system stack** | Terminal and tags use small amounts of monospace text — not worth an additional font request. Stack `'SF Mono', 'Fira Code', 'Roboto Mono', monospace` covers all major platforms. |
| **Trade-offs** | Inconsistent glyph rendering across platforms. |
| **Status** | ✅ Confirmed |

---

## 03 — Brand Color: #0074FF

| Field | Value |
|-------|-------|
| **Decision** | `#0074FF` as primary brand blue |
| **Date** | 2024 |
| **Alternatives considered** | `#0066FF`, `#0088FF`, `#0055CC` |
| **Why #0074FF** | Sits between pure `#0066FF` (too dark) and `#0088FF` (too cyan). At `hsl(213, 100%, 50%)` it reads as a deep, trustworthy blue that contrasts well against `#0B1220` background (5.8:1 ratio). Works in both solid and gradient contexts. |
| **Trade-offs** | Slightly less vibrant than #0088FF on bright screens. |
| **Status** | ✅ Confirmed |

---

## 04 — Supporting Colors

| Color | Why |
|-------|-----|
| **Gold #FFD700** | Premium and vision — contrasts blue well, signals achievement |
| **Teal #00FFCC** | Innovation and flow — pairs naturally with blue in gradients |
| **Purple #6C47FF** | Depth and creativity — used in gradient transitions from blue |
| **Pink #FF4D8D** | Energy and distinction — for accent highlights |

The four supporting colors were chosen to create a "tech premium" palette. All are at ~50% lightness, ensuring consistency against the dark background.

---

## 05 — Dark Mode Only

| Field | Value |
|-------|-------|
| **Decision** | Dark theme only — no light mode |
| **Date** | 2024 |
| **Alternatives considered** | Light mode toggle, `prefers-color-scheme` auto-switch |
| **Why dark only** | The brand aesthetic depends on glow effects, glassmorphism, and color-pop on dark backgrounds. A light mode would require a complete reimagining of the visual language, effectively a second brand. As a personal site, the owner's preference (dark) is authoritative. |
| **Trade-offs** | Excludes users who strongly prefer light mode. Some contrast-sensitive users may struggle (mitigated by high-contrast ratios on all text). |
| **Status** | ✅ Confirmed |

---

## 06 — Glassmorphism

| Field | Value |
|-------|-------|
| **Decision** | Glassmorphism (`backdrop-filter: blur(12px)`) for all cards |
| **Date** | 2024 |
| **Alternatives considered** | Solid cards, gradient borders, neumorphism |
| **Why glassmorphism** | Creates depth without heavy shadows. The `rgba(255,255,255,0.03)` background with `blur(12px)` gives a subtle frosted-glass effect that feels premium and technical. Matches the "digital studio" positioning. |
| **Trade-offs** | `backdrop-filter` is not supported in older browsers (Safari requires `-webkit-` prefix). Performance cost on low-end devices. |
| **Status** | ✅ Confirmed |

---

## 07 — Single-File Architecture

| Field | Value |
|-------|-------|
| **Decision** | All CSS and JS inlined in a single HTML file |
| **Date** | 2024 |
| **Alternatives considered** | Separate CSS/JS files, build tool (Vite, Parcel) |
| **Why single file** | Portfolio is a single page with no routing. Inlining eliminates HTTP requests, simplifies deployment (one file to update), and achieves Lighthouse 100/100. No framework or build step needed. |
| **Trade-offs** | Not scalable beyond single-page scope. Poor developer experience for larger projects. |
| **Status** | ✅ Confirmed for portfolio — ❌ Not recommended for multi-page projects |

---

## 08 — Terminal as Signature Component

| Field | Value |
|-------|-------|
| **Decision** | Include an interactive terminal in the hero section |
| **Date** | 2024 |
| **Alternatives considered** | Static tagline, animated text only, video background |
| **Why terminal** | Represents the "Engine Over Output" pillar in interactive form. The typewriter effect demonstrates the brand philosophy in action — the terminal is the engine, the text is the output. Creates immediate differentiation from conventional portfolio hero sections. |
| **Trade-offs** | Adds JS complexity. Typewriter animation may distract from core message on first visit. Not accessible to screen readers without `aria-label` (mitigated with `role="region"`). |
| **Status** | ✅ Confirmed |

---

## 09 — Section Anchor Navigation (SPA-like)

| Field | Value |
|-------|-------|
| **Decision** | Use `#id` anchors for same-page navigation |
| **Date** | 2024 |
| **Alternatives considered** | JS scroll-to with pushState, multi-page, full SPA with router |
| **Why anchors** | Zero JS required for basic navigation. Native browser smooth scrolling. URL updates with `#section`. Works without JavaScript. Simple and reliable. |
| **Trade-offs** | No animated scroll between sections (added as progressive enhancement via JS). No history state management (each anchor adds a history entry). |
| **Status** | ✅ Confirmed |

---

## 10 — SVG Sprite Sheet for Icons

| Field | Value |
|-------|-------|
| **Decision** | Inline SVG sprite sheet (Font Awesome Free 6.4.0) — no icon fonts |
| **Date** | 2024 |
| **Alternatives considered** | Font Awesome CDN, individual SVG files, icon font (Glyphicons) |
| **Why SVG sprite** | Single request (inline, so zero requests). Icons are infinitely scalable. Color controlled via CSS `currentColor`. Only the icons used are included. No FOUT/FOIT. |
| **Trade-offs** | Manual icon selection/embedding. Larger HTML file size. |
| **Status** | ✅ Confirmed |

---

## 11 — Email: ayman@aymanelmasry.me

| Field | Value |
|-------|-------|
| **Decision** | Use `ayman@aymanelmasry.me` as primary email |
| **Date** | 2025 (migrated from `info@aymanelmasry.com`) |
| **Alternatives considered** | `info@`, `hello@`, `contact@` |
| **Why ayman@** | Personal brand over generic mailbox. Shorter, more direct, more professional for a personal studio. `.me` domain reinforces personal/individual positioning. |
| **Trade-offs** | Some users expect `info@` or `hello@` for business inquiries. `ayman@aymanelmasry.me` is longer than ideal. |
| **Status** | ✅ Current |

---

## 12 — No External Dependencies (Except Fonts)

| Field | Value |
|-------|-------|
| **Decision** | Zero external JS/CSS dependencies — Google Fonts is the only external request |
| **Date** | 2024 |
| **Alternatives considered** | Bootstrap, Tailwind, GSAP, Three.js |
| **Why zero deps** | Portfolio needs minimal interactivity. Vanilla JS handles everything needed (typewriter, form validation, nav toggle, scroll reveal). Avoiding dependencies keeps the file small (~200KB), eliminates third-party risk, and ensures Lighthouse 100/100. |
| **Trade-offs** | More manual code to write and maintain. No animations library (scroll reveal is custom). |
| **Status** | ✅ Confirmed |

---

## 13 — Logo: Grid Block Pattern

| Field | Value |
|-------|-------|
| **Decision** | Abstract A-E-L grid pattern in SVG |
| **Date** | 2024 |
| **Alternatives considered** | Text logo, icon + text, monogram |
| **Why grid pattern** | Represents the "Engine Over Output" philosophy — the logo is a system of blocks forming letters. The blue `#0074FF` blocks on white path create a distinctive, technical identity. The 226.77×226.77 viewBox allows precise positioning. |
| **Trade-offs** | Not immediately readable as "AEL" at small sizes (mitigated by text label next to logo in nav). |
| **Status** | ✅ Confirmed |

---

## Decision Log Protocol

### When to add an entry
- A new brand/design decision is made
- An existing decision is changed or overridden
- A trade-off is discovered after implementation

### Entry format
```
## {number} — {title}

| Field | Value |
|-------|-------|
| **Decision** | What was decided |
| **Date** | When |
| **Alternatives considered** | What else was evaluated |
| **Why** | Rationale |
| **Trade-offs** | What was sacrificed |
| **Status** | ✅ Confirmed / ⚠️ Under Review / ❌ Superseded |
```
