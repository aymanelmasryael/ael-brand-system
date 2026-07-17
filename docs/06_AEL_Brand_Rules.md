# 06 — AEL Brand Rules

Brand rules are divided into two categories:
- **Canonical Rules** — timeless identity constraints that define what AEL is
- **Current Implementation** — how the rules are applied in the current website

Canonical rules are permanent. Implementation details may change with the site.

---

## Part I — Canonical Brand Rules

These rules define the AEL identity itself. They should change only if the brand philosophy changes.

### Rule C1 — Dark Mode Only
The AEL brand lives on dark backgrounds. The base background is deep navy (`#0B1220` range). No light mode.

### Rule C2 — Custom SVG Logo
The AEL logo is the custom grid-block SVG pattern — never a text approximation, never a raster image.

### Rule C3 — Three Pillars Philosophy
All brand communication must be consistent with the Three Pillars: Artist Over Tool, Substance Over Noise, Engine Over Output.

### Rule C4 — Bilingual Identity
Brand content exists in both English and Arabic. English is primary for technical/UI content. Arabic appears alongside English in philosophical content.

### Rule C5 — Premium Technical Aesthetic
The visual language is "premium tech": dark backgrounds, colored glow effects, glassmorphism, monospace accents. No skeuomorphism, no flat design, no playful/casual styling.

### Rule C6 — Engine Over Output Principle
The brand never presents itself as producing one-off artifacts. The value is in the system, not the output. (Terminal, prompt frameworks, generators — not "logos" or "images.")

### Rule C7 — No External Dependencies (Core)
The portfolio must remain self-contained — no external CSS/JS frameworks. Single-file deployment is the standard.

### Rule C8 — SVG Sprite for Icons
Icons must be served via inline SVG sprite. No icon fonts, no external icon CDNs.

### Rule C9 — Copyright & Attribution
Footer must always display: `© 2026 Ayman Elmasry — AEL Digital Studio. All rights reserved.`

### Rule C10 — Fixed Navigation
Primary navigation is always available (fixed position). The brand must be accessible from any scroll position.

---

## Part II — Current Website Implementation

These rules describe how the canonical rules are realized in `www.aymanelmasry.com`. They may be updated or replaced in future implementations.

### Rule I1 — Glassmorphism Pattern
```css
background: rgba(255, 255, 255, 0.03);
backdrop-filter: blur(12px);
-webkit-backdrop-filter: blur(12px);
border: 1px solid rgba(255, 255, 255, 0.06);
border-radius: 12px;
```

**Purpose**: Creates depth without heavy shadows. Implementation may change (e.g., different blur, different opacity).

### Rule I2 — Glow Instead of Shadow
Cards use colored glow (`0 0 20px rgba(color, 0.3)`) on hover — not traditional drop shadows.

**Why**: Glow reinforces the "premium tech" aesthetic. Neutral drop shadows are used only for depth on modals.

### Rule I3 — Gradient Text for Key Words
Hero headings and section titles use `background-clip: text` with `linear-gradient(135deg, #0074FF, #00FFCC)`.

**Implementation**: `.ael-gradient-text` class — may use different gradient angles or color stops in the future.

### Rule I4 — Primary CTA Gradient
Buttons use `linear-gradient(135deg, #0074FF, #6C47FF)` with `box-shadow: 0 4px 15px rgba(0, 116, 255, 0.3)` and `translateY(-2px)` on hover.

### Rule I5 — Terminal Signature Component
An interactive terminal with typewriter effect appears in the hero section.

**Typewriter timing**: 50ms/char typing, 2000ms pause, 30ms/char delete, 500ms between phrases.

### Rule I6 — Section Header Pattern
Every section follows: tag → gradient-enhanced title → description. Centered with `margin-bottom: 3rem`.

### Rule I7 — Full-Height Hero
Hero section uses `min-height: 100vh` with flexbox centering.

### Rule I8 — Responsive Breakpoints
- `max-width: 768px`: Nav collapses to hamburger, grids go single column, hero text reduces
- `max-width: 480px`: Further size reductions

### Rule I9 — Monospace Tags
Tags use `font-family: var(--ael-font-mono)` with color-tinted backgrounds:
```css
background: rgba(brand-color, 0.1);
color: brand-color-at-~60%-lightness;
```

### Rule I10 — External Link Security
All external links use `target="_blank" rel="noopener noreferrer"`.

### Rule I11 — Form Validation Pattern
Forms validate on submit via vanilla JS. Fields get `.error` or `.success` classes. Error messages use `role="alert"`.

### Rule I12 — Scroll Behavior
Navigation links scroll smoothly to sections. The nav bar blurs background on scroll (`backdrop-filter: blur(20px)`).

### Rule I13 — No Carousels
Content uses static grids. No auto-rotating sliders or carousels.

### Rule I14 — AELProductionEngine Class
All JS is encapsulated in a class:
```javascript
class AELProductionEngine {
  constructor() { /* ... */ }
  init() { /* ... */ }
  initTypewriter() { /* ... */ }
  initFormValidation() { /* ... */ }
  initNavToggle() { /* ... */ }
  initScrollReveal() { /* ... */ }
  initYear() { /* ... */ }
}
```

---

## Part III — Prohibited Patterns

These are explicitly excluded from the AEL brand:

| Pattern | Reason |
|---------|--------|
| Light mode | Contradicts premium tech aesthetic |
| Bootstrap/Tailwind | Contradicts self-contained principle |
| jQuery | Unnecessary dependency |
| Carousels/sliders | Contradicts Substance Over Noise |
| Stock photos | Contradicts original creation |
| Competitor references | Contradicts Substance Over Noise |
| Emoji in UI | Unprofessional in formal brand context |
| ALL CAPS (except badges) | Reads as shouting |
| Underlined links (unless hover) | Modern web convention |
| Serif fonts | Outside brand aesthetic |
| Raster logo | Logo is SVG-only |
