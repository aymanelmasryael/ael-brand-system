# 09 — AEL SEO Standards

## HTML Metadata Template

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Ayman Elmasry | Visionary Architect · AI Orchestrator · Brand Designer</title>
  <meta name="description" content="Ayman Elmasry — Visionary Architect, AI Orchestrator, and Brand Designer at AEL Digital Studio. Design drives the vision, AI powers the build.">
  <meta name="keywords" content="Ayman Elmasry, AEL Digital Studio, AI Orchestrator, Brand Designer, Visionary Architect, prompt engineering, design systems">
  <meta name="author" content="Ayman Elmasry">
  <meta name="robots" content="index, follow">
</head>
```

---

## Open Graph Tags

```html
<!-- Open Graph -->
<meta property="og:type" content="website">
<meta property="og:title" content="Ayman Elmasry | Visionary Architect · AI Orchestrator · Brand Designer">
<meta property="og:description" content="Define the vision — orchestrate AI to build it. Design drives the vision, AI powers the build.">
<meta property="og:image" content="https://www.aymanelmasry.com/ael-og-image.png">
<meta property="og:url" content="https://www.aymanelmasry.com">
<meta property="og:site_name" content="AEL Digital Studio">
<meta property="og:locale" content="en_US">
```

### OG Image Specifications
- **Dimensions**: 1200×630 pixels (1.91:1 ratio)
- **Format**: PNG
- **Content**: AEL logo + "AEL Digital Studio" branding
- **Max size**: 8MB
- **URL**: `https://www.aymanelmasry.com/ael-og-image.png`

---

## Twitter Card Tags

```html
<!-- Twitter Card -->
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:site" content="@aymanelmasryael">
<meta name="twitter:creator" content="@aymanelmasryael">
<meta name="twitter:title" content="Ayman Elmasry | Visionary Architect · AI Orchestrator · Brand Designer">
<meta name="twitter:description" content="Define the vision — orchestrate AI to build it. Design drives the vision, AI powers the build.">
<meta name="twitter:image" content="https://www.aymanelmasry.com/ael-og-image.png">
```

---

## Structured Data (JSON-LD)

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Person",
  "name": "Ayman Elmasry",
  "alternateName": "AEL Digital Studio",
  "url": "https://www.aymanelmasry.com",
  "email": "ayman@aymanelmasry.me",
  "telephone": "+20 111 330 0073",
  "jobTitle": ["Visionary Architect", "AI Orchestrator", "Brand Designer"],
  "knowsLanguage": ["Arabic", "English"],
  "sameAs": [
    "https://github.com/aymanelmasryael",
    "https://linkedin.com/in/aymanelmasryael",
    "https://x.com/aymanelmasryael",
    "https://instagram.com/aymanelmasryael",
    "https://codepen.io/aymanelmasryael"
  ]
}
</script>
```

---

## Performance Standards

- **Target**: Lighthouse 100/100 (all categories)
- **No external blocking resources**: All CSS and JS inline
- **Font loading**: Google Fonts (Inter) with `display=swap` — only external request
- **Images**: SVG for logo, PNG for OG image — optimized
- **No render-blocking JavaScript**: Script at end of `<body>`

---

## Canonical URL

```html
<link rel="canonical" href="https://www.aymanelmasry.com">
```

---

## Additional Meta

```html
<!-- Theme Color -->
<meta name="theme-color" content="#0B1222">

<!-- Favicon (fallback SVG) -->
<link rel="icon" type="image/svg+xml" href="ael-logo.svg">

<!-- Language -->
<html lang="en">
```

---

## SEO Content Rules

| Element | Required | Format |
|---------|----------|--------|
| Title Tag | Yes | `Ayman Elmasry | Visionary Architect · AI Orchestrator · Brand Designer` |
| Meta Description | Yes | 150-160 characters, includes "Design drives the vision, AI powers the build." |
| OG Title | Yes | Same as page title |
| OG Description | Yes | Same as meta description |
| OG Image | Yes | 1200×630 PNG with AEL logo |
| Twitter Card | Yes | `summary_large_image` |
| JSON-LD | Yes | Person schema with all social profiles |
| Canonical | Yes | `https://www.aymanelmasry.com` |
| Robots | Yes | `index, follow` |
| Sitemap | Recommended | `sitemap.xml` |
| hreflang | If bilingual | `en` and `ar` variants |

---

## URL Structure

- **Portfolio**: `https://www.aymanelmasry.com` (single page)
- **GitHub Pages**: `https://aymanelmasryael.github.io/{repo-name}`
- **Custom CDN**: `https://cdn.jsdelivr.net/gh/aymanelmasryael/{repo}/screenshot.svg`
- **Section anchors**: `https://www.aymanelmasry.com/#work`, `#about`, `#contact`
