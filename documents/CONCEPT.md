# Finite Timespace — Design Concept

**Version:** 1.0
**Last Updated:** March 14, 2026
**Status:** Draft

**Related Documents:**
- [LOGO.md](./LOGO.md) — Logo explorations and usage guidelines
- [CONTENT.md](./CONTENT.md) — Landing page content structure

---

## Table of Contents

1. [Overview](#overview)
2. [Inspiration References](#inspiration-references)
3. [Design Spectrum Analysis](#design-spectrum-analysis)
4. [Color System](#color-system)
5. [Typography](#typography)
6. [Design Principles](#design-principles)

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
| 1 | **Weatherlight** | weatherlight.com | Agency | Text-only, client list as proof, anti-portfolio, premium restraint |
| 2 | **iA (Information Architects)** | ia.net | Agency/Product | Typography-first, "design is invisible", Swiss-Japanese precision |
| 3 | **Josh Horowitz** | joshuahhh.com | Personal | Plain HTML, academic minimalism, living document |
| 4 | **Conduit (Psiphon)** | conduit.psiphon.ca | Product | Extreme simplicity, single accent, trust through restraint |
| 5 | **Dia Browser (Release Notes)** | diabrowser.com/release-notes/latest | Product | Warm pastels, editorial typography, grainy gradients |
| 6 | **Dia Browser (Homepage)** | diabrowser.com | Product | Video-first, use-case sections, testimonials |
| 7 | **Seena Labs** | getseena.io | SaaS | Dark mode, multi-accent, product mockups |
| 8 | **Hello Robo** | hellorobo.co | Agency | Enterprise polish, video case studies, awards, contact form |

### Detailed Reference Notes

#### Weatherlight (weatherlight.com) ⭐ Primary Reference

**Structure:**
- Single-page, text-only
- No images, no animations
- Client list with geographic locations
- Links to ventures/side projects

**What to adopt:**
- Single-page structure
- Client list format with locations
- Minimal copy, services as simple list
- Email-only contact
- Legal footer (LLC registration, independence)

#### iA.net ⭐ Typography Reference

**Typography:**
- Custom iA Writer fonts (Mono, Duo, Quattro) — FREE, open-source
- Based on IBM Plex
- Single column ~700-800px width
- Generous line-height (1.7)

**Philosophy:**
- "Good design is invisible"
- "95% of web design is typography"
- Minimum input, maximum output

**What to adopt:**
- Typography precision
- Narrow content column
- Ghost White background warmth

#### Hello Robo (hellorobo.co) — Form Reference

**Contact form structure:**
- Email (required)
- Full Name (required)
- "How can we help?" — checkbox options
- "How did you know about us?" — optional text field
- Submit button with hover animation

**What to adapt:**
- Simplified version for solo agency
- Fewer checkbox options
- Same field structure

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

Alternatives to pure white (#FFFFFF) analyzed:

| Name | Hex | Temperature | Character |
|------|-----|-------------|-----------|
| Alabaster | `#FAFAFA` | Neutral | Pure, clean, no tint |
| Ivory | `#FFFFF0` | Warm | Subtle yellow undertone |
| **Ghost White** | `#F8F8FF` | Cool | Faint blue/lavender tint ⭐ Selected |
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

| Name | Hex | Usage |
|------|-----|-------|
| **Rich Black** | `#0A0A0A` | Logo, primary headings ⭐ |
| **Eerie Black** | `#1B1B1B` | Body text |
| Charcoal | `#2D2D2D` | Secondary/muted text |

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

### Contrast Ratios

| Combination | Ratio | WCAG |
|-------------|-------|------|
| Rich Black on Ghost White | 19.5:1 | AAA ✓ |
| Eerie Black on Ghost White | 17.2:1 | AAA ✓ |
| White on Rich Black | 19.5:1 | AAA ✓ |

---

## Typography

### Font Selection

#### Primary: IBM Plex Mono
- **Role:** Logo, code, technical elements
- **Why:** Technical credibility, open-source, excellent readability
- **Weights:** 400 (regular), 500 (medium), 600 (semibold)
- **Source:** Google Fonts or self-hosted

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

### Font Loading Strategy

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=IBM+Plex+Mono:wght@400;500;600&family=IBM+Plex+Sans:wght@400;500;600&display=swap" rel="stylesheet">
```

---

## Design Principles

### What to Do

- ✓ Single page — everything scannable in 10 seconds
- ✓ Text-first — typography carries the design
- ✓ Client list as proof — with geographic locations
- ✓ Services as simple list — no lengthy descriptions
- ✓ Email-only contact — or minimal form
- ✓ Legal footer — LLC registration, independence statement
- ✓ Maximum restraint — let whitespace breathe

### What to Avoid

- ❌ Video case studies
- ❌ Logo carousels
- ❌ Awards sections
- ❌ Team photos
- ❌ Complex navigation
- ❌ Animations/motion (beyond subtle hover states)
- ❌ Multiple CTAs
- ❌ Generic stock imagery

---

**Document maintained by:** Niki
**Last review:** March 14, 2026
