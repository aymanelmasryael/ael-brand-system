# AEL Brand System — Contribution & Governance

## Ownership

**Brand Owner**: Ayman Elmasry — sole decision-maker for all brand identity changes.

**Repository maintainer**: `@aymanelmasryael`

---

## Governance Model

**Single-owner model**: Ayman Elmasry is the sole authority on brand identity. Suggestions and contributions are welcome but all decisions are unilateral.

---

## Who Can Propose Changes

| Role | Can propose | Can approve |
|------|------------|-------------|
| Ayman Elmasry | ✅ Yes | ✅ Yes |
| Contributors | ✅ Yes (via PR/issue) | ❌ No |
| Automated tools | ❌ No | ❌ No |

---

## Change Types & Approval

### Type A — Cosmetic (Patch)
- Typo fixes
- Formatting corrections
- Screenshot/image updates
- Link/URL updates

**Approval**: Self-merge by owner. PR reviewed within 48 hours for contributors.

### Type B — Content (Minor)
- New component documentation
- New product entry
- Token value corrections
- Clarifications and examples

**Approval**: Owner reviews and merges. Must not contradict existing brand rules.

### Type C — Identity (Major)
- Philosophy pillar changes
- Logo redesign
- Primary color change
- Studio name change
- Removal or restructuring of core documentation

**Approval**: Owner only. Requires a Decision Log entry explaining rationale.

---

## When to Change the Primary Color

The primary brand color `#0074FF` should only change if:
1. The entire brand is being repositioned
2. Legal/trademark issues arise with the current color
3. A deliberate, documented brand refresh is underway

Color changes must be accompanied by:
- A Decision Log entry
- Updated visual identity document
- Updated all token JSON files
- A migration guide for downstream consumers

---

## When to Add a New Component

A component may be added to the library if:
1. It appears in at least two different contexts on the live site
2. It has distinct visual styling from existing components
3. It is used consistently (same pattern repeated with data variation)

Components should not be added for:
- One-off design elements
- Experimental or draft pages
- Third-party embeds

---

## How to Add a New Product

1. Create `products/{product-name}/README.md` with product overview
2. Create `products/{product-name}/design.md` with brand-specific guidelines
3. Create `products/{product-name}/tokens.json` with product-specific tokens
4. Create `products/{product-name}/components.md` with component variations
5. Add entry to `products/README.md` index

---

## Versioning

See [VERSIONING.md](./VERSIONING.md) for full version strategy.

- Patch: cosmetic fixes, typo corrections
- Minor: new components, products, tokens
- Major: brand philosophy, identity, or structural changes

---

## Review Process

### For Contributors
1. Open an issue describing the proposed change
2. Fork the repository
3. Make changes on a descriptive branch
4. Submit pull request referencing the issue
5. Owner reviews within 7 days
6. Changes merged or feedback provided

### For Owner
1. Make changes directly on `main` or a feature branch
2. Update CHANGELOG.md
3. Bump version per VERSIONING.md
4. Tag release if applicable

---

## Communication

- **Issues**: Bug reports, suggestions, questions
- **Pull requests**: Concrete changes with descriptions
- **Discussions**: Future directions, philosophical questions

---

## Licensing

All brand system documentation is © 2026 AEL Digital Studio — Ayman Elmasry. All rights reserved.

The brand system documents the identity — it is not a license to use the identity. Brand assets (logo, colors, design system) may not be used without explicit written permission from Ayman Elmasry.
