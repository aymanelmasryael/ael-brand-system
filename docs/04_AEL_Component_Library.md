# 04 — AEL Component Library

Each component is documented in five layers:
1. **Purpose** — Why this component exists
2. **Design Intent** — What visual/UX goal it serves
3. **Anatomy** — Structure diagram and token mapping
4. **Tokens** — Exact design tokens used
5. **Reference Implementation** — Current HTML/CSS (may change per implementation)

---

## 1. Navigation Bar

### Purpose
Provide persistent access to all sections and reinforce brand identity on every scroll position.

### Design Intent
The nav should feel like a floating glass panel — present but unobtrusive. It communicates brand confidence through fixed positioning, subtle transparency, and a clean two-side layout (logo left, links right). On mobile it collapses into a full-screen overlay, preserving the same hierarchy.

### Anatomy
```
┌──────────────────────────────────────────────────────────────┐
│  [AEL Logo]  AEL  │  [Home] [Work] [About] [Contact]  [≡]  │  ← 56px height
└──────────────────────────────────────────────────────────────┘
     ← max-width: 1200px, centered →
```

| Element | Token | Value |
|---------|-------|-------|
| Container bg | `--ael-nav-bg` | `rgba(11, 18, 32, 0.85)` |
| Blur | `--ael-glass-blur` | `blur(20px)` |
| Border bottom | `--ael-border` | `1px solid rgba(255,255,255,0.06)` |
| Height | `--ael-nav-height` | `56px` |
| Link color (default) | `--ael-text-secondary` | `#8899AA` |
| Link color (hover) | `--ael-text` | `#E6EEF8` |
| Logo font | `--ael-text-lg` + `700` weight | `1.125rem` |

### Tokens Used
- `--ael-z-nav` (100)
- `--ael-space-3`, `--ael-space-6` (container padding)
- `--ael-space-2`, `--ael-space-3` (link padding)
- `--ael-radius-sm` (link border-radius)
- `--ael-transition-base` (hover transitions)

### Reference Implementation

```html
<nav class="ael-nav" role="navigation" aria-label="Main navigation">
  <div class="ael-nav-container">
    <a href="#hero" class="ael-nav-logo" aria-label="AEL Digital Studio - Home">
      <img src="ael-logo.svg" alt="AEL Logo" width="32" height="32">
      <span>AEL</span>
    </a>
    <ul class="ael-nav-links" role="menubar">
      <li role="none"><a href="#hero" role="menuitem">Home</a></li>
      <li role="none"><a href="#work" role="menuitem">Work</a></li>
      <li role="none"><a href="#about" role="menuitem">About</a></li>
      <li role="none"><a href="#contact" role="menuitem">Contact</a></li>
    </ul>
    <button class="ael-nav-toggle" aria-label="Toggle navigation menu" aria-expanded="false">
      <svg aria-hidden="true"><use href="#menu"></use></svg>
    </button>
  </div>
</nav>
```

```css
.ael-nav {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: var(--ael-z-nav);
  background: rgba(11, 18, 32, 0.85);
  backdrop-filter: blur(20px);
  -webkit-backdrop-filter: blur(20px);
  border-bottom: 1px solid rgba(255, 255, 255, 0.06);
}
.ael-nav-container {
  display: flex;
  align-items: center;
  justify-content: space-between;
  max-width: 1200px;
  margin: 0 auto;
  padding: var(--ael-space-3) var(--ael-space-6);
  height: 56px;
}
.ael-nav-logo {
  display: flex;
  align-items: center;
  gap: var(--ael-space-2);
  font-weight: 700;
  font-size: var(--ael-text-lg);
  color: var(--ael-text);
  text-decoration: none;
}
.ael-nav-links { display: flex; list-style: none; gap: var(--ael-space-1); }
.ael-nav-links a {
  padding: var(--ael-space-2) var(--ael-space-3);
  border-radius: var(--ael-radius-sm);
  color: var(--ael-text-secondary);
  font-size: var(--ael-text-sm);
  font-weight: 500;
  transition: var(--ael-transition-base);
  text-decoration: none;
}
.ael-nav-links a:hover {
  color: var(--ael-text);
  background: var(--ael-glass-bg);
}
```

### CSS Class Reference
| Class | Element | Purpose |
|-------|---------|---------|
| `.ael-nav` | `<nav>` | Fixed top bar container |
| `.ael-nav-container` | `<div>` | Flex wrapper, max-width 1200px |
| `.ael-nav-logo` | `<a>` | Logo link with icon + text |
| `.ael-nav-links` | `<ul>` | Horizontal nav link list |
| `.ael-nav-toggle` | `<button>` | Mobile hamburger toggle |

---

## 2. Hero Section

### Purpose
Make an immediate, memorable impression that communicates the brand philosophy within seconds of page load.

### Design Intent
The hero should feel expansive (full viewport), aspirational (light, gradient text), and technical (terminal component). The gradient glow behind the heading creates depth. The terminal grounds the aspirational message in the "Engine Over Output" philosophy — this is not just a claim, it's demonstrated.

### Anatomy
```
┌──────────────────────────────────────────────────────────────┐
│  [Tag: "Visionary Architect"]                                │  ← centered
│  [Gradient Heading: I Build Systems That Generate...]        │  ← 2.5rem, weight 300
│  [Subtitle: "Define the vision..."]                          │  ← secondary color
│  ┌──────────────── Terminal ────────────────────┐           │
│  │  ● ● ●  AEL_engine.sh                        │           │
│  │  $ ./ael-engine --mode=create --output=impact │           │
│  │  > [typewriter text]▊                        │           │
│  └──────────────────────────────────────────────┘           │
│  [Primary CTA]  [Secondary CTA]                              │
│                                                              │
│  ← Decorative radial gradient glow behind content →          │
└──────────────────────────────────────────────────────────────┘
     ← min-height: 100vh, centered →
```

### Tokens Used
- `--ael-text-4xl` (2.5rem) — heading
- `--ael-text-lg` (1.125rem) — subtitle
- `--ael-space-12` (3rem) — padding-top
- `--ael-space-6` (1.5rem) — horizontal padding
- `--ael-space-6`, `--ael-space-8` — spacing between elements
- Gradient: `linear-gradient(135deg, #0074FF, #00FFCC)` — heading accent
- Glow: `radial-gradient(circle, rgba(0,116,255,0.15), transparent 70%)`

### Reference Implementation

```html
<section id="hero" class="ael-hero">
  <div class="ael-hero-content">
    <div class="ael-hero-tag">
      <span class="ael-tag">Visionary Architect</span>
    </div>
    <h1 class="ael-hero-title">
      I Build Systems That<br>Generate<span class="ael-gradient-text"> Outcomes</span>
    </h1>
    <p class="ael-hero-subtitle">Define the vision — orchestrate AI to build it.</p>
    <div class="ael-terminal" role="region" aria-label="Terminal output">...</div>
    <div class="ael-hero-actions">
      <a href="#work" class="ael-btn ael-btn-primary">Explore My Work ...</a>
      <a href="#contact" class="ael-btn ael-btn-secondary">Get in Touch</a>
    </div>
  </div>
</section>
```

```css
.ael-hero {
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: var(--ael-space-12) var(--ael-space-6);
  position: relative;
  overflow: hidden;
}
.ael-hero-content { max-width: 800px; text-align: center; position: relative; z-index: var(--ael-z-base); }
.ael-hero-title {
  font-size: var(--ael-text-4xl);
  font-weight: 300;
  line-height: 1.2;
  margin: var(--ael-space-6) 0;
  color: var(--ael-text);
}
.ael-gradient-text {
  background: linear-gradient(135deg, #0074FF, #00FFCC);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}
```

---

## 3. Terminal Component

### Purpose
Demonstrate the "Engine Over Output" philosophy interactively. The terminal is the brand's signature element — it is the engine producing output in real time.

### Design Intent
A simulated terminal window with macOS-style traffic light dots, a file title "AEL_engine.sh", and a typewriter effect. The teal prompt symbol (`$` / `>`) and cursor reinforce the technical aesthetic. The typewriter cycles through phrases that describe what AEL builds — showing, not telling, the brand promise.

### Anatomy
```
┌────────────────────────────────────────────────┐
│  ● ● ●  AEL_engine.sh        ← title bar      │  ← rgba(0,0,0,0.4) bg
├────────────────────────────────────────────────┤    1px blue-tinted border
│  $ ./ael-engine --mode=create --output=impact  │  ← command line
│  > [typewriter text]▊                          │  ← animated output
└────────────────────────────────────────────────┘
     ← max-width: 520px →
```

### Tokens Used
- Background: `rgba(0, 0, 0, 0.4)`
- Border: `1px solid rgba(0, 116, 255, 0.2)`
- Radius: `--ael-radius-lg` (12px)
- Font: `--ael-font-mono`
- Header bg: `rgba(255, 255, 255, 0.03)`
- Prompt/cursor: `--ael-teal` (#00FFCC)
- Command text: `--ael-text-secondary` (#8899AA)
- Output text: `--ael-text` (#E6EEF8)
- Cursor blink: `1s step-end infinite`

### Typewriter Timing (JS)
| Phase | Speed | Duration |
|-------|-------|----------|
| Typing | 50ms per char | Variable |
| Pause (post-type) | — | 2000ms |
| Deleting | 30ms per char | Variable |
| Pause (post-delete) | — | 500ms |

### Reference Implementation

```html
<div class="ael-terminal" role="region" aria-label="Terminal output">
  <div class="ael-terminal-header">
    <span class="ael-terminal-dot"></span>
    <span class="ael-terminal-dot"></span>
    <span class="ael-terminal-dot"></span>
    <span class="ael-terminal-title">AEL_engine.sh</span>
  </div>
  <div class="ael-terminal-body">
    <div class="ael-terminal-line">
      <span class="ael-terminal-prompt">$</span>
      <span class="ael-terminal-command">./ael-engine --mode=create --output=impact</span>
    </div>
    <div class="ael-terminal-line">
      <span class="ael-terminal-prompt">></span>
      <span class="ael-terminal-output" id="typewriter-text"></span>
      <span class="ael-terminal-cursor">▊</span>
    </div>
  </div>
</div>
```

```css
.ael-terminal {
  background: rgba(0, 0, 0, 0.4);
  border: 1px solid rgba(0, 116, 255, 0.2);
  border-radius: var(--ael-radius-lg);
  font-family: var(--ael-font-mono);
  text-align: left;
  margin: var(--ael-space-8) auto;
  max-width: 520px;
  overflow: hidden;
}
.ael-terminal-header {
  display: flex; align-items: center; gap: 6px;
  padding: var(--ael-space-3) var(--ael-space-4);
  background: rgba(255, 255, 255, 0.03);
  border-bottom: 1px solid rgba(255, 255, 255, 0.06);
}
.ael-terminal-dot { width: 10px; height: 10px; border-radius: 50%; background: rgba(255,255,255,0.2); }
.ael-terminal-title { margin-left: auto; font-size: var(--ael-text-xs); color: var(--ael-text-secondary); }
.ael-terminal-body { padding: var(--ael-space-4); }
.ael-terminal-line { margin-bottom: var(--ael-space-2); font-size: var(--ael-text-sm); }
.ael-terminal-prompt { color: var(--ael-teal); margin-right: var(--ael-space-2); }
.ael-terminal-command { color: var(--ael-text-secondary); }
.ael-terminal-output { color: var(--ael-text); }
.ael-terminal-cursor { color: var(--ael-teal); animation: blink 1s step-end infinite; }
```

---

## 4. Cards (3 Variants)

### 4.1 Glass Card (Default)

**Purpose**: Display grouped content (projects, services, features) in a consistent, premium container.

**Design Intent**: Frosted glass effect that feels lightweight yet substantial. The card should sit on the dark background without competing, but lift subtly on hover with a blue glow.

**Anatomy**
```
┌──────────────────────────────────┐
│  [icon]                          │  ← decorative SVG
│  Title                           │  ← --ael-text-lg, weight 600
│  Description text here.          │  ← --ael-text-base, #8899AA
│  [tag] [tag] [tag]               │  ← .ael-tag elements
└──────────────────────────────────┘
```

**Tokens**
| Property | Token |
|----------|-------|
| Background | `rgba(255, 255, 255, 0.03)` |
| Blur | `blur(12px)` |
| Border | `1px solid rgba(255, 255, 255, 0.06)` |
| Radius | `--ael-radius-lg` (12px) |
| Padding | `--ael-space-6` (24px) |
| Hover bg | `rgba(255, 255, 255, 0.06)` |
| Hover glow | `0 0 20px rgba(0, 116, 255, 0.3)` |

### 4.2 Featured Card

**Purpose**: Highlight one item as primary or recommended within a set.

**Intent**: Adds a 3px gradient top border that draws the eye. Otherwise identical to glass card.

**Token**: `--ael-card-accent` = `linear-gradient(135deg, #0074FF, #00FFCC)`, height 3px, positioned absolute top.

### 4.3 Stat Card

**Purpose**: Display numerical metrics with visual emphasis.

**Intent**: Large gradient number creates impact. Simple label below keeps the focus on the number.

**Tokens**: Number uses `--ael-text-4xl`, weight 700, gradient `linear-gradient(135deg, #0074FF, #00FFCC)` with `background-clip: text`.

### Reference Implementation

```html
<div class="ael-card">
  <div class="ael-card-icon"><svg aria-hidden="true"><use href="#icon-name"></use></svg></div>
  <h3 class="ael-card-title">Card Title</h3>
  <p class="ael-card-description">Description text.</p>
  <div class="ael-card-tags"><span class="ael-tag">Tag</span></div>
</div>

<div class="ael-card ael-card-featured">
  <div class="ael-card-accent" style="background: linear-gradient(135deg, #0074FF, #00FFCC);"></div>
  <div class="ael-card-content">...</div>
</div>

<div class="ael-stat-card">
  <span class="ael-stat-number">99+</span>
  <span class="ael-stat-label">Projects</span>
</div>
```

---

## 5. Buttons (4 Variants)

### Purpose
Provide clear, consistent calls to action across the site with appropriate visual hierarchy.

### Design Intent
Buttons should feel tactile despite being flat design. Primary buttons use gradient + glow to communicate importance. Secondary buttons are outlined for balanced hierarchy. Ghost buttons are minimal for tertiary actions.

### Anatomy
```
[Primary]    ┌──────────────────────┐  ← gradient bg, white text, pill shape
             │  Explore My Work  → │
             └──────────────────────┘
[Secondary]  ┌──────────────────────┐  ← transparent, white border
             │    Get in Touch      │
             └──────────────────────┘
[Ghost]      ┌──────────────────────┐  ← transparent, secondary text
             │     Learn More       │
             └──────────────────────┘
[Icon]       [🔗]                    ← circular 40×40
```

### Token Grid

| Variant | Background | Text | Border | Hover |
|---------|-----------|------|--------|-------|
| Primary | `linear-gradient(135deg, #0074FF, #6C47FF)` | #FFFFFF | None | `translateY(-2px)` + glow |
| Secondary | transparent | #E6EEF8 | `1px solid rgba(255,255,255,0.2)` | Blue border + blue tint bg |
| Ghost | transparent | #8899AA | None | Text lighten + glass bg |
| Icon | transparent | #8899AA | `1px solid rgba(255,255,255,0.1)` | Blue border + blue tint |

All buttons: `border-radius: 9999px`, `font-weight: 600`, `font-size: 13px`, `transition: 250ms cubic-bezier(0.4, 0, 0.2, 1)`.

---

## 6. Tags & Badges (4 Color Variants)

### Purpose
Categorize and label content with minimal visual footprint.

### Design Intent
Tags use monospace font and brand-tinted transparent backgrounds — they look technical, not decorative. The four color variants map to the four supporting brand colors.

### Token Grid

| Variant | Background | Text |
|---------|-----------|------|
| Blue (default) | `rgba(0, 116, 255, 0.1)` | `#4DA6FF` |
| Gold | `rgba(255, 215, 0, 0.1)` | `#FFD700` |
| Teal | `rgba(0, 255, 204, 0.1)` | `#00FFCC` |
| Purple | `rgba(108, 71, 255, 0.1)` | `#6C47FF` |

Badges: gradient bg (`linear-gradient(135deg, #0074FF, #6C47FF)`), white text, uppercase, `font-weight: 700`.

---

## 7. Form Elements

### Purpose
Collect user inquiries with clear validation feedback.

### Design Intent
Forms match the dark glass aesthetic. Inputs sit slightly inset with transparent backgrounds. Focus state uses blue glow ring. Error/success states use red (`#FF4466`) and green (`#00CC88`) borders.

### Anatomy
```
┌──────────────────────────────────────┐
│  Name                                │  ← label, 13px semibold
│  ┌────────────────────────────────┐  │
│  │ Your name                      │  │  ← input, dark bg
│  └────────────────────────────────┘  │
│  ○ Please enter your name            │  ← error message (hidden unless .error)
│                                      │
│  [Send Message →]                    │  ← primary button
└──────────────────────────────────────┘
     ← max-width: 560px →
```

### Tokens
- Input bg: `rgba(255, 255, 255, 0.03)`
- Input border: `1px solid rgba(255, 255, 255, 0.1)`
- Focus ring: `0 0 0 3px rgba(0, 116, 255, 0.15)`
- Error border: `#FF4466`
- Success border: `#00CC88`
- Radius: `--ael-radius-md` (8px)

---

## 8. Footer

### Purpose
Provide copyright, navigation, and social links in a closing brand statement.

### Design Intent
The footer is spacious and calm. Three-column layout separates brand (logo + tagline), quick links, and social connections. A thin top border separates it from content. The copyright line sits at the bottom in small, secondary text.

### Anatomy
```
┌──────────────────────────────────────────────────────────────┐
│  [Logo] AEL Digital Studio   │ Quick Links  │   Connect     │
│  Design drives the vision..  │ Work         │   [GitHub]    │
│                              │ About        │   [LinkedIn]  │
│                              │ Contact      │   [X] [IG]    │
├──────────────────────────────────────────────────────────────┤
│         © 2026 Ayman Elmasry — AEL Digital Studio           │
└──────────────────────────────────────────────────────────────┘
     ← grid: 2fr 1fr 1fr →
```

---

## 9. Section Header Pattern

### Purpose
Introduce each major content section with consistent visual hierarchy.

### Design Intent
Three-element pattern: a monospace tag labels the section, a gradient-enhanced title provides the heading, and a description paragraph offers context. All centered.

### Anatomy
```
┌───────────────────────────────────────────────┐
│           [tag: "Section Label"]              │
│     Section  [Gradient Accent] Heading        │  ← 2rem, weight 300
│     Optional description paragraph.           │
└───────────────────────────────────────────────┘
     ← text-align: center →
```

### CSS Class Reference
| Class | Purpose |
|-------|---------|
| `.ael-section-header` | Center-aligned container, `margin-bottom: 3rem` |
| `.ael-section-title` | 2rem, weight 300, gradient on key words via `.ael-gradient-text` |
| `.ael-section-description` | Secondary text, `max-width: 600px`, `margin: 0 auto` |

---

## 10. Social Icons Set

### Purpose
Link to all AEL social platforms with consistent visual treatment.

### Design Intent
SVG icons at 20×20 in footer, 24×24 in hero/contact. Default color is secondary text (`#8899AA`), hover transitions to brand blue (`#0074FF`). Always wrapped in `<a>` with `target="_blank" rel="noopener noreferrer"`.

### Platform Order
GitHub → LinkedIn → X → Instagram → CodePen

### SVG Icon Reference
| Platform | Icon ID | Hover Color |
|----------|---------|-------------|
| GitHub | `#github` | `#0074FF` |
| LinkedIn | `#linkedin` | `#0074FF` |
| X | `#x-twitter` | `#0074FF` |
| Instagram | `#instagram` | `#0074FF` |
| CodePen | `#codepen` | `#0074FF` |

---

## 11. SVG Sprite Sheet

### Purpose
Serve all icons in a single, inline, zero-request bundle.

### Design Intent
Icons are Font Awesome Free 6.4.0 symbols embedded in a hidden `<svg>` at the end of `<body>`. Each icon is a `<symbol>` with a unique `id`, viewBox, and SVG path data. Icons are referenced with `<use href="#id">`.

### Structure
```html
<svg style="display: none;" aria-hidden="true">
  <defs>
    <symbol id="check" viewBox="0 0 24 24"><path d="..."/></symbol>
    <symbol id="code" viewBox="0 0 24 24"><path d="..."/></symbol>
    <!-- one per icon -->
  </defs>
</svg>
```

### Active Icons
check, code, terminal, globe, github, linkedin, x-twitter, instagram, codepen, arrow-up-right, menu, close, sun, moon, sparkle, cubes

---

## Component States Matrix

| Component | Default | Hover | Focus | Active | Disabled | Mobile |
|-----------|---------|-------|-------|--------|----------|--------|
| Nav link | #8899AA | #E6EEF8 + glass bg | :focus-visible outline | #0074FF | — | Full overlay |
| Primary btn | Blue→Purple gradient | Lift + glow | Outline | — | Opacity 0.5 | Full width |
| Glass card | Frosted glass | Lift + blue glow | — | — | — | Full width |
| Input | Dark + border | — | Blue ring | — | Opacity 0.5 | Full width |
| Tag | Tinted bg + mono | — | — | — | — | Inline |
| Icon link | #8899AA | #0074FF | Outline | — | — | Touch target 44px |
