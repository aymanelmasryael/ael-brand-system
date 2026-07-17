# 08 — AEL GitHub Standards

## Repository Naming Convention

**Pattern**: `ael-{project-name}` (lowercase, hyphen-separated)

**Examples**:
- `ael-1000-prompts-library`
- `ael-3d-particle-backgrounds-library`
- `ael-ai-chat-interface`
- `ael-analytics-dashboard`
- `ael-code-analyzer`
- `ael-color-os`
- `ael-design-system`
- `ael-image-color-extractor`
- `ael-learn-github-course`
- `ael-learn-opencode-course`
- `ael-markdown-cms`
- `ael-omega-particles`
- `ael-omega-platform`
- `ael-particles-lab`
- `ael-prompt-framework`

**Exceptions**:
- `aymanelmasryael` (profile repo — no `ael-` prefix)
- `aymanelmasryael.github.io` (portfolio — follows GitHub Pages convention)
- `AEL-Sovereign-CS50x-2026-2027` (uses capital letters for official course name)

---

## Repository Structure

### Standard Layout
```
{repo-name}/
├── README.md
├── LICENSE (if applicable)
├── screenshot.svg  (optional, for profile display)
└── src/
    └── ...
```

### Required Files
- `README.md` — see template below
- `index.html` or main entry point for web projects

---

## README Template

```markdown
# AEL Project Name

[![AEL Digital Studio](https://raw.githubusercontent.com/aymanelmasryael/aymanelmasryael/main/ael-logo.svg)](https://www.aymanelmasry.com)

**AEL Digital Studio** — [One-line description of project]

---

## Overview

Brief description (2-3 sentences) of what this project does and why it exists.

---

## Features

- Feature 1
- Feature 2
- Feature 3

---

## Quick Start

```bash
# Instructions here
```

---

## Links

- [Live Demo](https://aymanelmasryael.github.io/{repo-name})
- [Portfolio](https://www.aymanelmasry.com)

---

© 2026 Ayman Elmasry — AEL Digital Studio. All rights reserved.
```

---

## README Guidelines

- **Logo**: Top center, linked to portfolio. Use `https://raw.githubusercontent.com/aymanelmasryael/aymanelmasryael/main/ael-logo.svg`
- **Description**: One line after logo, "AEL Digital Studio — ..."
- **Formatting**: GitHub-flavored Markdown
- **Sections**: Overview → Features → Quick Start → Links → Copyright

---

## GitHub Pages Setup

- **Source**: Deploy from `main` branch (root or `/docs`)
- **Required**: `.nojekyll` file in root for non-Jekyll builds
- **Custom domain**: `www.aymanelmasry.com` (CNAME record)
- **CDN for assets**: `https://cdn.jsdelivr.net/gh/aymanelmasryael/{repo}/screenshot.svg`

---

## CDN Pattern for Screenshots

```
https://cdn.jsdelivr.net/gh/aymanelmasryael/{repo}/screenshot.svg
```

Used in GitHub profile's "Pinned" section and project READMEs for visual previews.

---

## Profile README (`aymanelmasryael/README.md`)

- Located in `aymanelmasryael/profile/README.md`
- Content: Logo → Name & Title → Tagline → Three Pillars → Pinned Projects
- The `aymanelmasryael` repo (not `aymanelmasryael.github.io`) controls the GitHub profile

---

## Versioning

- **Assets**: Use framework version numbers (e.g., AEL Vision Framework v2.2)
- **Repository**: No strict semantic versioning required — use descriptive tags
- **README**: Update copyright year annually
- **Releases**: Use GitHub Releases for major versions

---

## Active Repositories (19)

| # | Repo | Pages |
|---|------|-------|
| 1 | `AEL-Sovereign-CS50x-2026-2027` | ✅ |
| 2 | `ael-1000-prompts-library` | ✅ |
| 3 | `ael-3d-particle-backgrounds-library` | ✅ |
| 4 | `ael-ai-alignment-quotes` | ✅ |
| 5 | `ael-ai-chat-interface` | ✅ |
| 6 | `ael-analytics-dashboard` | ✅ |
| 7 | `ael-code-analyzer` | ✅ |
| 8 | `ael-color-os` | ✅ |
| 9 | `ael-design-system` | ✅ |
| 10 | `ael-image-color-extractor` | ✅ |
| 11 | `ael-learn-github-course` | ✅ |
| 12 | `ael-learn-opencode-course` | ✅ |
| 13 | `ael-markdown-cms` | ✅ |
| 14 | `ael-omega-particles` | ✅ |
| 15 | `ael-omega-platform` | ✅ |
| 16 | `ael-particles-lab` | ✅ |
| 17 | `ael-prompt-framework` | ✅ |
| 18 | `aymanelmasryael` (profile) | — |
| 19 | `aymanelmasryael.github.io` (portfolio) | ✅ |
