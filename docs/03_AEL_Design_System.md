# 03 — AEL Design System

## Design Tokens

All values are exact extractions from `www.aymanelmasry.com` source CSS.

### Spacing Scale

| Token | Value | Usage |
|-------|-------|-------|
| `--ael-space-1` | `0.25rem` (4px) | Micro spacing, icon gaps |
| `--ael-space-2` | `0.5rem` (8px) | Tight spacing, tag padding |
| `--ael-space-3` | `0.75rem` (12px) | Button padding, small gaps |
| `--ael-space-4` | `1rem` (16px) | Card padding, section gaps |
| `--ael-space-5` | `1.25rem` (20px) | Form elements padding |
| `--ael-space-6` | `1.5rem` (24px) | Medium spacing |
| `--ael-space-8` | `2rem` (32px) | Large spacing, grid gaps |
| `--ael-space-10` | `2.5rem` (40px) | Section padding |
| `--ael-space-12` | `3rem` (48px) | Hero padding top |
| `--ael-space-16` | `4rem` (64px) | Section margins |
| `--ael-space-20` | `5rem` (80px) | Major sections separation |
| `--ael-space-24` | `6rem` (96px) | Page section gaps |

### Border Radius

| Token | Value | Usage |
|-------|-------|-------|
| `--ael-radius-xs` | `4px` | Tags, badges |
| `--ael-radius-sm` | `6px` | Small cards, inputs |
| `--ael-radius-md` | `8px` | Cards, buttons, forms |
| `--ael-radius-lg` | `12px` | Large cards, modals |
| `--ael-radius-xl` | `16px` | Hero section, containers |
| `--ael-radius-2xl` | `20px` | Featured cards |
| `--ael-radius-3xl` | `24px` | Extra large containers |
| `--ael-radius-full` | `9999px` | Pill buttons, avatar |

### Box Shadows

| Token | Value | Usage |
|-------|-------|-------|
| `--ael-shadow-sm` | `0 1px 3px rgba(0,0,0,0.3)` | Subtle cards |
| `--ael-shadow-md` | `0 4px 6px rgba(0,0,0,0.3)` | Medium cards |
| `--ael-shadow-lg` | `0 10px 25px rgba(0,0,0,0.4)` | Large cards, modals |
| `--ael-shadow-glow` | `0 0 20px rgba(0,116,255,0.3)` | Blue glow effect |
| `--ael-shadow-glow-teal` | `0 0 20px rgba(0,255,204,0.3)` | Teal glow effect |
| `--ael-shadow-glow-gold` | `0 0 20px rgba(255,215,0,0.3)` | Gold glow effect |
| `--ael-shadow-inner` | `inset 0 1px 2px rgba(0,0,0,0.4)` | Inner shadow for inputs |

### Motion & Transitions

| Token | Value | Usage |
|-------|-------|-------|
| `--ael-transition-base` | `250ms cubic-bezier(0.4, 0, 0.2, 1)` | Default transitions |
| `--ael-transition-fast` | `150ms cubic-bezier(0.4, 0, 0.2, 1)` | Micro-interactions |
| `--ael-transition-slow` | `400ms cubic-bezier(0.4, 0, 0.2, 1)` | Page transitions |
| `--ael-transition-spring` | `500ms cubic-bezier(0.34, 1.56, 0.64, 1)` | Spring-like effects |

### Z-Index Scale

| Token | Value | Usage |
|-------|-------|-------|
| `--ael-z-base` | `1` | Content |
| `--ael-z-dropdown` | `10` | Dropdowns |
| `--ael-z-nav` | `100` | Navigation |
| `--ael-z-modal` | `1000` | Modals, overlays |
| `--ael-z-tooltip` | `1001` | Tooltips |

### Glassmorphism

All cards use the glassmorphism pattern:

```css
background: rgba(255, 255, 255, 0.03);
backdrop-filter: blur(12px);
-webkit-backdrop-filter: blur(12px);
border: 1px solid rgba(255, 255, 255, 0.06);
border-radius: var(--ael-radius-lg);
```

Hover state:
```css
background: rgba(255, 255, 255, 0.06);
border-color: rgba(255, 255, 255, 0.1);
box-shadow: var(--ael-shadow-glow);
```

---

## Grid & Layout

### Page Structure

- **Max width**: 1200px (`max-width: 1200px; margin: 0 auto;`)
- **Padding**: `padding: 0 var(--ael-space-6);`
- **Section gap**: `gap: var(--ael-space-20)` between major sections

### Grid System

- **Card grid**: `grid-template-columns: repeat(auto-fit, minmax(320px, 1fr)); gap: var(--ael-space-6);`
- **Feature grid**: `grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: var(--ael-space-6);`
- **Stats grid**: `grid-template-columns: repeat(3, 1fr);` (for stat counters)
- **Footer grid**: `grid-template-columns: 2fr 1fr 1fr; gap: var(--ael-space-10);`

### Breakpoints (from media queries)

| Breakpoint | Target |
|------------|--------|
| `max-width: 768px` | Tablets, mobile |
| `max-width: 480px` | Small mobile |

### Responsive Behavior (from source)

- At 768px: Nav collapses to hamburger menu; grids go single column; hero text reduces font size; card grids become single column
- At 480px: Further size reductions and spacing adjustments

---

## Component Containers

### Section Pattern

```css
section {
  padding: var(--ael-space-20) 0;
}
```

### Card Pattern

```css
.ael-card {
  background: var(--ael-glass-bg);
  backdrop-filter: blur(12px);
  -webkit-backdrop-filter: blur(12px);
  border: 1px solid var(--ael-glass-border);
  border-radius: var(--ael-radius-lg);
  padding: var(--ael-space-6);
  transition: var(--ael-transition-base);
}
```

### Terminal Pattern

```css
.ael-terminal {
  background: rgba(0, 0, 0, 0.4);
  border: 1px solid rgba(0, 116, 255, 0.2);
  border-radius: var(--ael-radius-lg);
  font-family: var(--ael-font-mono);
}
```
