# 11 — AEL Code Standards

## Technology Stack

| Layer | Technology | Notes |
|-------|------------|-------|
| Markup | HTML5 | Semantic elements, single-file |
| Styling | CSS3 | Custom properties, flexbox, grid, glassmorphism |
| Scripting | Vanilla JS | ES6+, no frameworks, no libraries |
| Icons | SVG sprite | Font Awesome Free 6.4.0, inline |
| Fonts | Google Fonts | Inter (400, 500, 600, 700), `display=swap` |
| Deployment | GitHub Pages | `.nojekyll`, custom domain |
| Performance | Lighthouse 100/100 | Target for all pages |

---

## CSS Conventions

### Naming Convention

**Prefix**: All AEL-specific classes use the `ael-` prefix.

```css
/* ✅ Correct */
.ael-card, .ael-btn, .ael-nav, .ael-glass-card, .ael-btn-primary

/* ❌ Incorrect */
.card, .button, .nav, .primary-btn
```

### CSS Custom Properties

All design tokens use the `--ael-` prefix.

```css
/* Colors */
--ael-blue: #0074FF;
--ael-gold: #FFD700;
--ael-teal: #00FFCC;
--ael-purple: #6C47FF;
--ael-pink: #FF4D8D;

/* Spacing */
--ael-space-1: 0.25rem;
--ael-space-2: 0.5rem;
--ael-space-3: 0.75rem;
/* ... through --ael-space-24 */

/* Radius */
--ael-radius-xs: 4px;
--ael-radius-sm: 6px;
--ael-radius-md: 8px;
/* ... through --ael-radius-full */

/* Transitions */
--ael-transition-base: 250ms cubic-bezier(0.4, 0, 0.2, 1);

/* Shadows */
--ael-shadow-glow: 0 0 20px rgba(0, 116, 255, 0.3);
```

### CSS Organization (within inline `<style>`)

1. Reset / base styles
2. CSS custom properties (`:root`)
3. Typography
4. Layout / grid
5. Navigation
6. Hero section
7. Components (cards, buttons, tags, forms)
8. Terminal
9. Footer
10. Animations / keyframes
11. Media queries (`768px`, `480px`)

---

## HTML Conventions

### Structure
- Semantic HTML5 elements: `<nav>`, `<main>`, `<section>`, `<footer>`
- Single `<h1>` per page (hero title)
- Hierarchical headings: `h1` → `h2` → `h3`
- All images have `alt` text
- All form inputs have `<label>` elements
- External links use `target="_blank" rel="noopener noreferrer"`

### Self-Contained Format
- All CSS in single `<style>` block in `<head>`
- All JS in single `<script>` block at end of `<body>`
- All icons in inline SVG sprite sheet before `</body>`
- No external resources except Google Fonts

### Identifiers
- Use `id` for section anchors (`#hero`, `#work`, `#about`, `#contact`)
- Use `id` for JS hooks (`#typewriter-text`)
- Use `class` for all styling

---

## JavaScript Conventions

### Engine Architecture

All JS is encapsulated in the `AELProductionEngine` class.

```javascript
class AELProductionEngine {
  constructor() {
    this.init();
  }
  
  init() {
    this.initTypewriter();
    this.initFormValidation();
    this.initNavToggle();
    this.initScrollReveal();
    this.initYear();
  }
  
  // Methods organized by feature
}
```

### Naming
- **Classes**: PascalCase (`AELProductionEngine`)
- **Methods**: camelCase (`initTypewriter`, `validateForm`)
- **Variables**: camelCase (`typewriterText`, `currentIndex`)
- **Constants**: UPPER_SNAKE_CASE for magic numbers (`TYPING_SPEED = 50`)

### Code Organization

```javascript
class AELProductionEngine {
  constructor() { /* ... */ }
  
  /* Initialization */
  init() { /* ... */ }
  
  /* Typewriter */
  initTypewriter() { /* ... */ }
  typeText() { /* ... */ }
  deleteText() { /* ... */ }
  
  /* Form Validation */
  initFormValidation() { /* ... */ }
  validateForm(e) { /* ... */ }
  validateField(field) { /* ... */ }
  
  /* Navigation */
  initNavToggle() { /* ... */ }
  
  /* Scroll Effects */
  initScrollReveal() { /* ... */ }
  
  /* Utilities */
  initYear() { /* ... */ }
}
```

### Event Handling
- Use `addEventListener` — no inline event handlers
- Events: `DOMContentLoaded`, `click`, `submit`, `scroll`, `input`

### Patterns to Avoid
- ❌ No jQuery or other DOM libraries
- ❌ No `var` — use `const` / `let`
- ❌ No inline `onclick` attributes
- ❌ No `eval()` or `document.write()`
- ❌ No global variables (everything in the class)

---

## File Organization

### Single-File Portfolio
```
www.aymanelmasry.com.html
├── <!DOCTYPE html>
├── <html>
│   ├── <head>
│   │   ├── <meta> (charset, viewport, SEO)
│   │   ├── <title>
│   │   ├── <link> (Google Fonts)
│   │   └── <style> (all CSS)
│   └── <body>
│       ├── <nav>
│       ├── <main>
│       │   ├── <section id="hero">
│       │   ├── <section id="work">
│       │   ├── <section id="about">
│       │   └── <section id="contact">
│       ├── <footer>
│       ├── <svg> (icon sprite sheet)
│       └── <script> (all JS)
```

### Brand System Directory
```
AEL-Brand-System/
├── README.md
├── 01_*.md through 11_*.md
├── tokens/
│   ├── colors.json
│   ├── typography.json
│   ├── spacing.json
│   └── components.json
├── products/
│   └── *.md
└── assets/
    └── ...
```

---

## Quality Checks

| Check | Method | Target |
|-------|--------|--------|
| HTML validation | W3C Validator | No errors |
| CSS validation | W3C Validator | No errors |
| Lighthouse | Chrome DevTools | 100/100 all categories |
| Contrast | Accessibility tools | WCAG AA minimum |
| Mobile | Device emulation | Functional at 320px+ |
| Performance | Lighthouse | 100/100 |
| Best Practices | Lighthouse | 100/100 |
| SEO | Lighthouse | 100/100 |
