# AEL Brand System — Versioning Strategy

## Version Format

```
MAJOR.MINOR.PATCH
```

Example: `v1.0.0`

---

## Version Bump Rules

### MAJOR — Brand Philosophy / Identity Changes

Increment when:
- Brand philosophy (Three Pillars) changes
- Primary logo redesigned
- Core brand color (`#0074FF`) changes
- Studio name or legal identity changes
- Target audience or market positioning shifts

### MINOR — New Capabilities

Increment when:
- New component added to library
- New design token categories introduced
- New product documentation added
- New platform/medium added (e.g., mobile app, print)
- Existing documentation restructured

### PATCH — Corrections & Refinements

Increment when:
- Typo or formatting fixes
- Token value corrections
- Usage guideline clarifications
- Example code updates
- Screenshot/image updates
- Metadata updates (email, links, years)

---

## Pre-release Suffixes

| Suffix | Meaning | Used When |
|--------|---------|-----------|
| `-alpha.1` | Early draft | First extraction, unvalidated |
| `-beta.1` | Under review | Content complete, pending audit |
| `-rc.1` | Release candidate | Approved, final review |

---

## Version Lifecycle

```
alpha → beta → rc → stable (v1.0.0) → v1.0.1 (patch) → v1.1.0 (minor) → v2.0.0 (major)
```

---

## Compatibility Policy

- **MAJOR versions**: May break all downstream usage — migration guide required
- **MINOR versions**: Backward compatible — existing implementations continue working
- **PATCH versions**: Fully compatible — no migration needed

---

## Version Storage

- `CHANGELOG.md` — human-readable history
- `tokens/` JSON files include `"version": "x.x.x"` field
- Git tags: `git tag v1.0.0`

---

## Current Version

**v1.0.0** — 2026-07-18 — Initial extraction and documentation.
