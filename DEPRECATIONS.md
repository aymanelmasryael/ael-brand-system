# AEL Brand System — Deprecations

Tracks design decisions, patterns, or assets that were explicitly removed or replaced, along with the rationale.

---

## D01 — Email: info@aymanelmasry.com

| Field | Value |
|-------|-------|
| **Deprecated** | 2025 |
| **Replaced by** | `ayman@aymanelmasry.me` |
| **Reason** | Brand consolidation from generic `info@` to personal `ayman@`. The `.me` domain aligns with the personal studio positioning. |
| **Status** | ❌ Fully deprecated — no active references |
| **Migration** | All identity files, SEO metadata, and brand docs updated in v1.0.0 |

---

## D02 — Multiple Separate Identity Files

| Field | Value |
|-------|-------|
| **Deprecated** | 2026-07-18 |
| **Replaced by** | `AEL-Brand-System/` structured documentation architecture |
| **Reason** | `AEL_IDENTITY.md`, `AEL_IDENTITY_EN.md`, `AEL_IDENTITY_AR.md` served as loose identity notes. The brand system now provides structured, versioned, and governed documentation. |
| **Status** | ⚠️ Deprecated — identity files kept as historical reference but brand system is canonical |
| **Note** | The three identity files remain in the workspace for backward reference but will not be updated further. All changes go through `AEL-Brand-System/`. |

---

## Deprecation Protocol

### When to deprecate
- A pattern, component, or asset is replaced by a better alternative
- A decision is reversed by new information
- An external dependency is removed

### To deprecate
1. Add entry to this file with date, replacement, and reason
2. Update CHANGELOG.md noting the deprecation
3. Update all relevant documentation to reference the new pattern
4. Remove or clearly mark deprecated assets in the workspace
5. Consider adding a migration guide if the deprecation affects downstream consumers

### Deprecation states
| State | Meaning |
|-------|---------|
| ✅ Active | Current and recommended |
| ⚠️ Deprecated | Still present but not recommended — will be removed |
| ❌ Removed | No longer present — historical record only |
