# 07 — AEL Social Identity

## Unified Handle

**`@aymanelmasryael`** across all platforms.

---

## Platform Profiles

### GitHub — `@aymanelmasryael`

**URL**: https://github.com/aymanelmasryael

**Profile content order**:
1. Banner: AEL Brand System logo (`ael-logo.svg`) — centered, width 120px
2. Bio: "Visionary · AI Orchestrator · Brand Designer · Founder @ AEL Digital Studio"
3. Secondary line: "Design drives the vision, AI powers the build."
4. Location: Egypt
5. Website: https://www.aymanelmasry.com
6. Pinned repositories: Top projects (AEL- prefix repos)

**README structure** (`profile/README.md`):
```markdown
![AEL Logo](https://raw.githubusercontent.com/aymanelmasryael/aymanelmasryael/main/ael-logo.svg)

**Ayman Elmasry** — *Visionary · AI Orchestrator · Brand Designer · Founder @ AEL Digital Studio*

Design drives the vision, AI powers the build.

---

### The Three Pillars

... (pillar content)
```

**Repository naming**: `ael-{project-name}` for AEL projects. See [08_AEL_GitHub_Standards.md](./08_AEL_GitHub_Standards.md).

---

### LinkedIn — `@aymanelmasryael`

**URL**: https://linkedin.com/in/aymanelmasryael

**Headline**: Visionary · AI Orchestrator · Brand Designer · Founder @ AEL Digital Studio

**About section**: AEL Digital Studio founder bio with Three Pillars.

**Featured**: GitHub repositories, client projects, certifications.

---

### X (Twitter) — `@aymanelmasryael`

**URL**: https://x.com/aymanelmasryael

**Display name**: Ayman Elmasry | AEL Digital Studio

**Bio**: Visionary · AI Orchestrator · Brand Designer · Founder @ AEL Digital Studio

**Avatar**: `AEL.png` (profile picture)

**Header**: Brand gradient (`#0074FF` to `#00FFCC`) or custom graphic.

---

### Instagram — `@aymanelmasryael`

**URL**: https://instagram.com/aymanelmasryael

**Display name**: Ayman Elmasry | AEL Digital Studio

**Bio**: Visionary · AI Orchestrator · Brand Designer · Founder @ AEL Digital Studio

**Content**: Portfolio work, process breakdowns, brand visuals.

---

### CodePen — `@aymanelmasryael`

**URL**: https://codepen.io/aymanelmasryael

**Display name**: Ayman Elmasry

**Bio**: Visionary · AI Orchestrator · Brand Designer · Founder @ AEL Digital Studio

**Content**: CSS experiments, animations, component prototypes.

---

## Social Link Patterns

### HTML Structure (used in footer)
```html
<a href="https://github.com/aymanelmasryael"
   aria-label="GitHub"
   target="_blank"
   rel="noopener noreferrer">
  <svg aria-hidden="true"><use href="#github"></use></svg>
</a>
```

### SVG Icon Reference
| Platform | Icon ID | Color (hover) |
|----------|---------|---------------|
| GitHub | `#github` | `#0074FF` |
| LinkedIn | `#linkedin` | `#0074FF` |
| X | `#x-twitter` | `#0074FF` |
| Instagram | `#instagram` | `#0074FF` |
| CodePen | `#codepen` | `#0074FF` |

### Social Icon Sizes
- Footer: 20×20
- Hero/Contact: 24×24
- GitHub README: 24×24 (inline with text)

---

## Avatar & Imagery Standards

### Profile Photo
- **File**: `AEL.png`
- **Usage**: GitHub avatar, LinkedIn, X, Instagram
- **Style**: Professional headshot, dark background

### Brand Logo
- **File**: `ael-logo.svg`
- **Usage**: GitHub organization, README, website nav, OG image overlay
- **Format**: Always SVG — never PNG/JPG for logo

### Open Graph Image
- **File**: `ael-og-image.png`
- **Dimensions**: 1200×630 (standard OG ratio)
- **Content**: AEL Logo + "AEL Digital Studio" branding

### Business Card
- **File**: `AEL-Business-Card-Rev-1.png`
- **Format**: Digital/print-ready
- **Content**: Logo, name, title, contact info, QR code (optional)
