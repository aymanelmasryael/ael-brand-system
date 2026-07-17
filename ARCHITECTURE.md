# AEL Brand System — Architecture

## System Overview

The AEL Brand System follows a layered architecture where each layer depends on the layers below it. Changes in lower layers propagate upward; changes in upper layers should not require lower-layer modifications.

```
┌─────────────────────────────────────────────────────────────┐
│                     Brand Foundation                        │
│   Philosophy · Positioning · Bio · Pillars · Credentials   │
│                     01_AEL_Brand_Foundation.md              │
└───────────────────────┬─────────────────────────────────────┘
                        │ informs
                        ▼
┌─────────────────────────────────────────────────────────────┐
│                      Visual Identity                        │
│   Logo · Colors · Typography · Iconography · Gradients     │
│                     02_AEL_Visual_Identity.md               │
└───────────────────────┬─────────────────────────────────────┘
                        │ parameterizes
                        ▼
┌─────────────────────────────────────────────────────────────┐
│                       Design Tokens                         │
│   colors.json · typography.json · spacing.json · etc.      │
│                     tokens/ (JSON)                          │
└───────────────────────┬─────────────────────────────────────┘
                        │ instantiates
                        ▼
┌─────────────────────────────────────────────────────────────┐
│                 Design System & Components                  │
│   Spacing · Radius · Shadows · Nav · Hero · Cards · Forms  │
│              03_Design_System + 04_Component_Library        │
└───────────────────────┬─────────────────────────────────────┘
                        │ composes
                        ▼
┌─────────────────────────────────────────────────────────────┐
│                        Products                             │
│   AEL Vision Framework · Prompt Library · Omega Platform    │
│                     products/                               │
└───────┬─────────────────────────────────┬───────────────────┘
        │                                 │
        ▼                                 ▼
┌────────────────┐               ┌────────────────────────────┐
│ Digital Assets │               │      Governance Layer      │
│  Website · App │               │  Rules · Decisions · Vers. │
│  GitHub · PDFs │               │  Deprecations · Contrib.   │
│  Social Media  │               │  06, 12, CHANGELOG, etc.   │
└────────────────┘               └────────────────────────────┘
```

---

## Layer Relationships

### Layer 1: Brand Foundation
The immutable core. Changes here (philosophy, positioning) require a MAJOR version bump.

**Dependencies**: None. This is the root.

**Files**: `01_AEL_Brand_Foundation.md`, `05_AEL_Content_Guidelines.md`

### Layer 2: Visual Identity
Translates philosophy into concrete visual primitives.

**Dependencies**: Layer 1 (what we communicate determines how we look)

**Files**: `02_AEL_Visual_Identity.md`

### Layer 3: Design Tokens
Machine-readable values that parameterize the visual identity.

**Dependencies**: Layer 2 (tokens are the values of the visual primitives)

**Files**: `tokens/colors.json`, `tokens/typography.json`, `tokens/spacing.json`, `tokens/components.json`

### Layer 4: Design System & Components
Reusable UI patterns that instantiate the tokens.

**Dependencies**: Layers 2 and 3 (components use tokens to express the visual identity)

**Files**: `03_AEL_Design_System.md`, `04_AEL_Component_Library.md`, `10_AEL_Accessibility.md`, `11_AEL_Code_Standards.md`

### Layer 5: Products
Specific applications and outputs that compose components into experiences.

**Dependencies**: Layer 4 (products use components)

**Files**: `products/` directory

### Cross-Cutting — Governance Layer
Rules, decisions, versioning, and processes that apply to all layers.

**Files**: `06_AEL_Brand_Rules.md`, `12_AEL_Decision_Log.md`, `VERSIONING.md`, `CHANGELOG.md`, `DEPRECATIONS.md`, `CONTRIBUTING.md`, `ROADMAP.md`, `ARCHITECTURE.md`

---

## Data Flow

```
Philosophy ──► Principles ──► Visual Primitives ──► Token Values
     ↑                                                    │
     │                                                    ▼
     │                                           Component CSS
     │                                                    │
     └─────── All layers reference the philosophy ────────┘
```

- Changes flow **downward** (philosophy change affects everything)
- Feedback flows **upward** (implementation reveals philosophy gaps)
- The governance layer **observes** all layers

---

## Single Source of Truth

```
┌──────────────────────────────────────────────┐
│           AEL-Brand-System/                  │
│  ┌───────┐  ┌──────────┐  ┌────────────┐    │
│  │ Docs  │  │  Tokens  │  │  Products  │    │
│  └───┬───┘  └────┬─────┘  └─────┬──────┘    │
│      └───────────┼──────────────┘            │
│                  ▼                           │
│         Canonical Reference                  │
└──────────────────────────────────────────────┘
         │                   │
         ▼                   ▼
   aymanelmasry.com    GitHub Repositories
   (implementation)    (product projects)
```

All implementations reference the brand system. The brand system does not reference implementations (except as examples).

---

## File Dependency Map

```
01_Brand_Foundation ───────────────────────────────────────────┐
                                                                │
02_Visual_Identity ──► tokens/colors.json                      │
                   ──► tokens/typography.json                  │
                   ──► 09_SEO_Standards                        │
                   ──► 07_Social_Identity                      │
                                                                │
03_Design_System ──► tokens/spacing.json                       │
                  ──► tokens/components.json                   │
                                                                │
04_Component_Library ──► tokens/components.json                │
                     ──► 10_Accessibility                      │
                     ──► 11_Code_Standards                     │
                                                                │
05_Content_Guidelines ──► 01_Brand_Foundation                  │
                                                                │
06_Brand_Rules ──► 02_Visual_Identity                          │
              ──► 03_Design_System                              │
              ──► 04_Component_Library                         │
                                                                │
08_GitHub_Standards ──► products/                              │
                                                                │
12_Decision_Log ──► All layers                                 │
```

**Note**: Arrows represent "references" or "depends on." No circular dependencies exist.

---

## Usage Guidelines

### For Implementers (building a new AEL project)
1. Start with **01** (Brand Foundation) — understand the philosophy
2. Reference **02 + tokens/** — extract colors, typography, spacing
3. Use **04 + 03** — compose components from the library
4. Validate against **06** — ensure brand rules are followed
5. Check **10** — confirm accessibility compliance

### For Maintainers (updating the brand system)
1. Add decision to **12_AEL_Decision_Log.md** first
2. Update the affected layer(s)
3. Update **tokens/** JSON files if values change
4. Update **06_AEL_Brand_Rules.md** if the change affects rules
5. Log in **CHANGELOG.md**
6. Bump version per **VERSIONING.md**

### For Contributors (proposing changes)
1. Read **CONTRIBUTING.md** — understand governance
2. Check **ROADMAP.md** — see if it's already planned
3. Check **DEPRECATIONS.md** — make sure it hasn't been tried and rejected
4. Open an issue or PR with reference to the relevant layer(s)
