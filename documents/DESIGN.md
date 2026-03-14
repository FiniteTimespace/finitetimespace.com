# Finite Timespace — Landing Page Design Document

**Version:** 1.0
**Last Updated:** March 14, 2026
**Status:** Draft

---

## Table of Contents

1. [Overview](#overview)
2. [Inspiration References](#inspiration-references)
3. [Design Spectrum Analysis](#design-spectrum-analysis)
4. [Color System](#color-system)
5. [Typography](#typography)
6. [Logo Explorations](#logo-explorations)
7. [Content Structure](#content-structure)
8. [Implementation Notes](#implementation-notes)
9. [Summary & Next Steps](#summary--next-steps)

---

## Overview

### About Finite Timespace

Finite Timespace LLC is a solo software engineering agency based in Wyoming, USA, operated by Niki — a Senior iOS Engineer with 10+ years of experience. The agency focuses on Apple platforms (iOS, macOS) with a growing emphasis on design-conscious engineering.

### Design Goals

1. **Communicate expertise** without enterprise bloat
2. **Signal premium positioning** through restraint
3. **Reflect the solo/boutique nature** authentically
4. **Balance technical credibility** with design sensibility
5. **Create a memorable visual identity** with the Λ (lambda) mark

### Target Audience

- Startups and companies seeking senior iOS/Apple platform engineering
- Teams valuing design-conscious development
- Clients who appreciate craftsmanship over scale

---

## Inspiration References

### Reference Sites Analyzed

| # | Website | URL | Category | Key Takeaways |
|---|---------|-----|----------|---------------|
| 1 | Weatherlight | weatherlight.com | Agency | Text-only, client list as proof, anti-portfolio, premium restraint |
| 2 | iA (Information Architects) | ia.net | Agency/Product | Typography-first, "design is invisible", Swiss-Japanese precision |
| 3 | Josh Horowitz | joshuahhh.com | Personal | Plain HTML, academic minimalism, living document |
| 4 | Conduit (Psiphon) | conduit.psiphon.ca | Product | Extreme simplicity, single accent, trust through restraint |
| 5 | Dia Browser (Release Notes) | diabrowser.com/release-notes/latest | Product | Warm pastels, editorial typography, grainy gradients |
| 6 | Dia Browser (Homepage) | diabrowser.com | Product | Video-first, use-case sections, testimonials |
| 7 | Seena Labs | getseena.io | SaaS | Dark mode, multi-accent, product mockups |
| 8 | Hello Robo | hellorobo.co | Agency | Enterprise polish, video case studies, awards |

### Logo Inspiration

**THE TRANSITION.** — A visual identity from a music/video project featuring:
- Condensed bold sans-serif, all-caps
- Vibrant color block (pink/magenta) as background
- White knockout text
- Period as punctuation/design element
- Works over any imagery

---

## Design Spectrum Analysis

### Positioning Spectrum

```
WORST FIT                                                              BEST FIT
FOR FINITE TIMESPACE                                                   FOR FINITE TIMESPACE

◄──────────────────────────────────────────────────────────────────────────────►

Seena      Hello       Dia          Dia         Conduit    Josh        iA.net    Weatherlight
Labs       Robo        Homepage     Release                Horowitz
                                    Notes
  │          │           │            │            │          │           │            │
  ▼          ▼           ▼            ▼            ▼          ▼           ▼            ▼

 SaaS      Enterprise   Product     Editorial    Mission   Academic    Typography   Solo agency
 startup   team agency  marketing   warmth       focused   authenticity + product   anti-portfolio
 energy    with video   with CTA    personality  single    living doc  restraint    client list
           case studies overload               purpose                             text-only
```

### Fit Ranking

| Rank | Site | Fit | Rationale |
|------|------|-----|-----------|
| 1 | **Weatherlight** | ✓✓✓ Perfect | Solo agency model, text-only, client list, anti-portfolio |
| 2 | **iA.net** | ✓✓ Great | Typography obsession, restraint, product + philosophy |
| 3 | **Josh Horowitz** | ✓ Good | Authentic, living document, hacker credibility |
| 4 | **Conduit** | ✓ Good | Extreme simplicity, trust-focused |
| 5 | **Dia Release Notes** | ⚠️ Decent | Warm editorial feel, but product-focused |
| 6 | **Dia Homepage** | ⚠️ Okay | Too much product marketing for services |
| 7 | **Hello Robo** | ❌ Poor | Enterprise team energy, would seem pretentious |
| 8 | **Seena Labs** | ❌ Poor | SaaS startup aesthetic, wrong signal |

### Design Formula

```
90% Weatherlight    →  Structure, tone, restraint, client list, single-page
 5% iA.net          →  Typography precision, Ghost White warmth
 5% THE TRANSITION  →  Logo treatment (black box + knockout text + Λ mark)
```

---

## Color System

### Background Colors Research

Alternatives to pure white (#FFFFFF) for warmer, more sophisticated backgrounds:

| Name | Hex | Temperature | Character |
|------|-----|-------------|-----------|
| Alabaster | `#FAFAFA` | Neutral | Pure, clean, no tint |
| Ivory | `#FFFFF0` | Warm | Subtle yellow undertone |
| **Ghost White** | `#F8F8FF` | Cool | Faint blue/lavender tint |
| Linen | `#FAF0E6` | Warm | Noticeable beige/cream |
| Platinum | `#E5E4E2` | Neutral | Darker gray, more contrast |
| Azure | `#F0FFFF` | Cool | Light cyan/mint tint |
| Cultured | `#F5F5F5` | Neutral | Classic light gray |
| Old Lace | `#FDF5E6` | Warm | Creamy, antique paper |

### Selected Palette

#### Primary Background
**Ghost White `#F8F8FF`**
- Subtle lavender/blue undertone adds sophistication
- Pairs beautifully with dark text (high contrast)
- Modern and slightly cool — aligns with tech positioning
- Works well with both light and dark mode strategies

#### Black Alternatives for Typography

| Name | Hex | Character |
|------|-----|-----------|
| Rich Black | `#0A0A0A` | Near-black, slightly warmer than pure |
| Eerie Black | `#1B1B1B` | Deep but not absolute |
| Charcoal | `#2D2D2D` | Softer, good for secondary text |

**Selected:** Rich Black `#0A0A0A` for logo/primary, Eerie Black `#1B1B1B` for body text

#### Accent Color
**Azure `#F0FFFF`**
- Subtle cool tint for highlights
- Can be used for links, accents, or logo variations
- Digital/screen-native feel

### CSS Variables

```css
:root {
  /* Backgrounds */
  --bg-primary: #F8F8FF;      /* Ghost White */
  --bg-dark: #0A0A0A;         /* Rich Black */
  
  /* Text */
  --text-primary: #0A0A0A;    /* Rich Black */
  --text-secondary: #1B1B1B;  /* Eerie Black */
  --text-muted: #666666;
  --text-inverse: #FFFFFF;
  
  /* Accents */
  --accent-azure: #F0FFFF;
  
  /* Borders */
  --border-light: rgba(0, 0, 0, 0.08);
  --border-dark: rgba(255, 255, 255, 0.1);
}
```

---

## Typography

### Font Selection

#### Primary: IBM Plex Mono
- **Role:** Logo, code, technical elements
- **Why:** Technical credibility, open-source, excellent readability
- **Weights:** 400 (regular), 500 (medium), 600 (semibold)

#### Alternative: JetBrains Mono
- **Role:** Alternative for tighter, more developer-focused contexts
- **Why:** The developer's font, ligatures, compact

#### Body/UI: IBM Plex Sans
- **Role:** Body text, navigation, UI elements
- **Why:** Pairs perfectly with IBM Plex Mono, humanist warmth

### Typography Scale

```css
:root {
  /* Font Families */
  --font-mono: 'IBM Plex Mono', monospace;
  --font-sans: 'IBM Plex Sans', sans-serif;
  
  /* Font Sizes */
  --text-xs: 0.75rem;    /* 12px - labels */
  --text-sm: 0.875rem;   /* 14px - small text */
  --text-base: 1rem;     /* 16px - body */
  --text-lg: 1.125rem;   /* 18px - large body */
  --text-xl: 1.25rem;    /* 20px - subheadings */
  --text-2xl: 1.5rem;    /* 24px - headings */
  
  /* Line Heights */
  --leading-tight: 1.25;
  --leading-normal: 1.5;
  --leading-relaxed: 1.7;
  
  /* Letter Spacing */
  --tracking-tight: -0.02em;
  --tracking-normal: 0;
  --tracking-wide: 0.08em;
  --tracking-wider: 0.15em;
}
```

---

## Logo Explorations

### Core Concept

Two-line stacked wordmark with:
- **Left-aligned text** (asymmetric padding: tight left, more space right)
- **Reversed "a" as Λ** (lambda) — physics/spacetime reference
- **Black rectangle container** — knockout text style inspired by THE TRANSITION

### The Λ (Lambda) Mark

The letter "a" in "timespace" is rendered as a rotated/reversed "a" resembling the Greek letter lambda (Λ). This creates:
- A visual hook that's subtle but distinctive
- Reference to physics notation (spacetime, wavelength)
- A memorable mark within the wordmark

### Logo Variations

#### Option A: Classic Box — Lowercase (Recommended)

```html
<style>
  .logo-box {
    background: #0A0A0A;
    padding: 1.25rem 2.5rem 1.25rem 1rem;
    display: inline-block;
  }
  .logo-box .line {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 1.1rem;
    font-weight: 500;
    letter-spacing: 0.08em;
    color: white;
    line-height: 1.5;
    text-align: left;
  }
  .reversed-a {
    display: inline-block;
    transform: rotate(180deg) translateY(0.1em);
    font-weight: 600;
  }
</style>

<div class="logo-box">
  <div class="line">finite</div>
  <div class="line">timesp<span class="reversed-a">a</span>ce</div>
</div>
```

**Visual:**
```
┌─────────────────────────┐
│ finite                  │
│ timespΛce               │
└─────────────────────────┘
```

#### Option B: Outlined Box — Lowercase

```html
<style>
  .logo-outlined {
    border: 2px solid #0A0A0A;
    padding: 1.25rem 2.5rem 1.25rem 1rem;
    display: inline-block;
    background: transparent;
  }
  .logo-outlined .line {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 1.1rem;
    font-weight: 500;
    letter-spacing: 0.08em;
    color: #0A0A0A;
    line-height: 1.5;
    text-align: left;
  }
  .reversed-a {
    display: inline-block;
    transform: rotate(180deg) translateY(0.1em);
    font-weight: 600;
  }
</style>

<div class="logo-outlined">
  <div class="line">finite</div>
  <div class="line">timesp<span class="reversed-a">a</span>ce</div>
</div>
```

**Visual:**
```
┏━━━━━━━━━━━━━━━━━━━━━━━━━┓
┃ finite                  ┃
┃ timespΛce               ┃
┗━━━━━━━━━━━━━━━━━━━━━━━━━┛
```

### Logo Usage Guidelines

| Context | Recommended Variation |
|---------|----------------------|
| Website header | Option B (Outlined) or no box |
| Dark backgrounds | Option A (Filled) inverted to white box |
| Favicon | Λ mark only |
| Social media | Option A (Filled) |
| Print / documents | Option B (Outlined) |

---

## Content Structure

### Recommended Layout (Weatherlight Model)

```
┌─────────────────────────────────────────────────────────┐
│                                                         │
│  ┌─────────────┐                                        │
│  │ finite      │                                        │
│  │ timespΛce   │                                        │
│  └─────────────┘                                        │
│                                                         │
│  Software Engineering                                   │
│  c/o Niki                                               │
│                                                         │
│  ───────────────────────────────────────────────────    │
│                                                         │
│  Services                                               │
│  iOS Development                                        │
│  macOS Development                                      │
│  Software Architecture                                  │
│  Technical Consulting                                   │
│                                                         │
│  ───────────────────────────────────────────────────    │
│                                                         │
│  Select Clients                                         │
│  Kensa Health (London, UK)                              │
│  [Other clients with locations]                         │
│                                                         │
│  ───────────────────────────────────────────────────    │
│                                                         │
│  Contact                                                │
│  hello@finitetimespace.com                              │
│                                                         │
│  ───────────────────────────────────────────────────    │
│                                                         │
│  © 2024–2026 Finite Timespace LLC                       │
│  Registered in Wyoming, USA                             │
│  Independently owned and operated                       │
│                                                         │
└─────────────────────────────────────────────────────────┘
```

### Content Principles

1. **Single page** — everything scannable in 10 seconds
2. **Text-first** — no images, videos, or animations
3. **Client list as proof** — with geographic locations
4. **Services as simple list** — no lengthy descriptions
5. **Contact is email only** — no forms
6. **Legal footer** — LLC registration, independence statement

---

## Implementation Notes

### Technical Stack (Recommended)

- **Framework:** Astro (static site generation)
- **Styling:** Tailwind CSS with custom design tokens
- **Fonts:** Self-hosted IBM Plex (Mono + Sans)
- **Hosting:** Vercel or Cloudflare Pages
- **Domain:** finitetimespace.com

### Accessibility Considerations

- Minimum contrast ratio 4.5:1 for all text
- Ghost White (#F8F8FF) with Rich Black (#0A0A0A) = 19.5:1 ✓
- Semantic HTML structure
- Focus states for keyboard navigation
- Prefers-reduced-motion support

### Performance Targets

- First Contentful Paint: < 1s
- Total page weight: < 100KB
- No JavaScript required for core content
- System font fallbacks defined

---

## Summary & Next Steps

### Design Direction Summary

Finite Timespace's landing page will follow the **Weatherlight model** — a text-first, single-page site that communicates expertise through restraint. The visual identity centers on:

1. **Ghost White (#F8F8FF)** background for subtle sophistication
2. **IBM Plex Mono** typography for technical credibility
3. **The Λ (lambda) mark** as a distinctive visual element
4. **Black box logo** with left-aligned, asymmetric padding
5. **Client list with locations** as primary social proof

### What to Avoid

- ❌ Video case studies
- ❌ Logo carousels
- ❌ Awards sections
- ❌ Team photos
- ❌ Complex navigation
- ❌ Animations/motion
- ❌ Multiple CTAs

### Next Steps

1. [ ] Finalize logo variation (Option A vs Option B)
2. [ ] Gather client list with locations
3. [ ] Write final copy for services section
4. [ ] Set up Astro project with design tokens
5. [ ] Implement responsive layout
6. [ ] Test typography at various viewport sizes
7. [ ] Deploy to staging for review

---

## Appendix

### Full Logo HTML (Copy-Ready)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Finite Timespace</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=IBM+Plex+Mono:wght@400;500;600&display=swap" rel="stylesheet">
  <style>
    :root {
      --bg-primary: #F8F8FF;
      --bg-dark: #0A0A0A;
      --text-inverse: #FFFFFF;
    }
    
    body {
      background: var(--bg-primary);
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      margin: 0;
      padding: 2rem;
    }
    
    /* Option A: Filled Box */
    .logo-filled {
      background: var(--bg-dark);
      padding: 1.25rem 2.5rem 1.25rem 1rem;
      display: inline-block;
    }
    
    .logo-filled .line {
      font-family: 'IBM Plex Mono', monospace;
      font-size: 1.1rem;
      font-weight: 500;
      letter-spacing: 0.08em;
      color: var(--text-inverse);
      line-height: 1.5;
      text-align: left;
    }
    
    /* Option B: Outlined Box */
    .logo-outlined {
      border: 2px solid var(--bg-dark);
      padding: 1.25rem 2.5rem 1.25rem 1rem;
      display: inline-block;
      background: transparent;
    }
    
    .logo-outlined .line {
      font-family: 'IBM Plex Mono', monospace;
      font-size: 1.1rem;
      font-weight: 500;
      letter-spacing: 0.08em;
      color: var(--bg-dark);
      line-height: 1.5;
      text-align: left;
    }
    
    /* Reversed A (Λ) */
    .reversed-a {
      display: inline-block;
      transform: rotate(180deg) translateY(0.1em);
      font-weight: 600;
    }
  </style>
</head>
<body>

  <!-- Option A: Filled Box -->
  <div class="logo-filled">
    <div class="line">finite</div>
    <div class="line">timesp<span class="reversed-a">a</span>ce</div>
  </div>

  <!-- Option B: Outlined Box (uncomment to use)
  <div class="logo-outlined">
    <div class="line">finite</div>
    <div class="line">timesp<span class="reversed-a">a</span>ce</div>
  </div>
  -->

</body>
</html>
```

---

**Document maintained by:** Niki  
**Last review:** March 14, 2026
