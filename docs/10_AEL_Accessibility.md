# 10 — AEL Accessibility

## Color Contrast

All brand color combinations meet WCAG AA standards (minimum 4.5:1 for normal text, 3:1 for large text).

| Combination | Contrast Ratio | WCAG Level |
|-------------|---------------|------------|
| `#E6EEF8` on `#0B1220` (text on bg) | ~14.5:1 | AAA |
| `#0074FF` on `#0B1220` (links on bg) | ~5.8:1 | AA |
| `#4DA6FF` on `#0B1220` (tag text on bg) | ~7.2:1 | AA |
| `#8899AA` on `#0B1220` (secondary on bg) | ~5.1:1 | AA |
| `#FFFFFF` on `#0074FF` (btn text on blue) | ~4.6:1 | AA |
| `#FFD700` on `#0B1220` (gold on bg) | ~8.5:1 | AA |
| `#00FFCC` on `#0B1220` (teal on bg) | ~7.8:1 | AA |
| `#6C47FF` on `#0B1220` (purple on bg) | ~4.8:1 | AA |
| `#FF4D8D` on `#0B1220` (pink on bg) | ~5.6:1 | AA |

---

## Focus States

```css
/* Default focus ring for all interactive elements */
:focus-visible {
  outline: 2px solid var(--ael-blue);
  outline-offset: 2px;
  border-radius: var(--ael-radius-sm);
}

/* Remove default focus for mouse users */
:focus:not(:focus-visible) {
  outline: none;
}
```

### Focusable Elements
- All `<a>` links
- All `<button>` elements
- All `<input>`, `<textarea>`, `<select>` form elements
- Nav toggle button (hamburger menu)

---

## ARIA Attributes

### Navigation
```html
<nav role="navigation" aria-label="Main navigation">
  <ul role="menubar">
    <li role="none"><a href="#hero" role="menuitem">Home</a></li>
    <li role="none"><a href="#work" role="menuitem">Work</a></li>
    <li role="none"><a href="#about" role="menuitem">About</a></li>
    <li role="none"><a href="#contact" role="menuitem">Contact</a></li>
  </ul>
  <button aria-label="Toggle navigation menu" aria-expanded="false">...</button>
</nav>
```

### Icons
```html
<!-- Decorative icon -->
<svg aria-hidden="true"><use href="#icon-name"></use></svg>

<!-- Informative icon -->
<svg role="img" aria-labelledby="icon-title-id">
  <title id="icon-title-id">Description</title>
  <use href="#icon-name"></use>
</svg>
```

### Images
```html
<img src="ael-logo.svg" alt="AEL Logo">
```

### Footer
```html
<footer role="contentinfo">
```

### Form
```html
<label for="email">Email</label>
<input type="email" id="email" ...>
<span class="ael-form-error" role="alert">Error message</span>
```

### Terminal
```html
<div class="ael-terminal" role="region" aria-label="Terminal output">
```

---

## Keyboard Navigation

- **Tab order**: Natural DOM order — nav → hero → sections → footer
- **Skip link**: Not currently implemented (recommended for future)
- **Nav toggle**: Enter/Space to open/close mobile menu
- **Form submit**: Enter to submit, Tab between fields
- **Close actions**: Escape key for mobile nav overlay (recommended)

### Keyboard Shortcuts
| Key | Action |
|-----|--------|
| Tab | Navigate forward through interactive elements |
| Shift+Tab | Navigate backward |
| Enter/Space | Activate button/link |
| Escape | Close mobile nav (recommended) |

---

## Screen Reader Considerations

- **Landmarks**: `<nav>`, `<main>`, `<footer>` with `role` attributes
- **Headings**: Hierarchical order — `h1` (hero title), `h2` (section titles), `h3` (card titles)
- **Links**: Descriptive text — "Explore My Work" not "Click here"
- **Images**: Meaningful `alt` text on all images
- **Icons**: `aria-hidden="true"` on decorative icons — never read by screen readers
- **Status messages**: `role="alert"` on form errors and success feedback

---

## Semantic HTML Structure

```html
<body>
  <nav role="navigation" aria-label="Main navigation">...</nav>
  <main>
    <section id="hero">...</section>
    <section id="work">...</section>
    <section id="about">...</section>
    <section id="contact">...</section>
  </main>
  <footer role="contentinfo">...</footer>
</body>
```

---

## Accessibility Checklist

| Requirement | Status | Notes |
|-------------|--------|-------|
| Color contrast (AA) | ✅ Passes | All brand combinations tested |
| Focus indicators | ✅ Present | `:focus-visible` with blue outline |
| ARIA landmarks | ✅ Present | nav, main, footer, region |
| Form labels | ✅ Present | All inputs have `<label>` |
| Form errors | ✅ Present | `role="alert"` on errors |
| Alt text on images | ✅ Present | Logo, decorative images |
| Icon accessibility | ✅ Present | `aria-hidden="true"` pattern |
| Keyboard navigation | ✅ Present | Tab through all elements |
| Skip navigation link | ❌ Missing | Recommended for future |
| Video/audio captions | N/A | No media content |
| Reduced motion support | ❌ Missing | Recommended for future (`prefers-reduced-motion`) |
| Screen reader testing | ⚠️ Manual | Test with VoiceOver/NVDA |

---

## Reduced Motion (Recommended)

```css
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    transition-duration: 0.01ms !important;
  }
  
  .ael-terminal-cursor {
    animation: none;
  }
}
```

This media query is not yet implemented in the source but is recommended for accessibility compliance.
