# CLAUDE.md

> Instructions for Claude Code when working on the Finite Timespace landing page.

## Project Overview

**Finite Timespace** is a solo software engineering agency website. This is a minimal, text-first landing page following the Weatherlight design model — premium restraint, typography-focused, anti-portfolio.

**Repository:** https://github.com/FiniteTimespace/finitetimespace.com

## Current State

The project is in **early MVP stage**. The design documentation is complete, but the implementation has not yet adopted the full component architecture or design system.

### What Exists

- 3 standalone Astro pages with inline Tailwind classes
- Basic Tailwind CSS integration
- Design documentation in `/documents`

### What's Missing

- Component architecture (Logo, Header, Footer)
- Base Layout for shared HTML structure
- Design tokens/CSS variables
- Custom Tailwind theme configuration
- Google Fonts integration (IBM Plex Mono/Sans)
- Branded favicon (Λ mark)
- Linting/formatting configuration

## Tech Stack

| Layer | Technology | Version |
|-------|------------|---------|
| Framework | Astro | ^4.5.5 |
| Styling | Tailwind CSS | ^3.4.1 |
| Type Checking | TypeScript | ^5.4.2 |
| Fonts | IBM Plex Mono, IBM Plex Sans | Not yet integrated |
| Forms | TBD | Not yet implemented |
| Hosting | GitHub Pages | Via CNAME |

## Project Structure

### Current (Actual)

```
finitetimespace.com/
├── documents/                  # Design documentation (complete)
│   ├── CONCEPT.md              # Primary design doc (colors, typography, references)
│   ├── LOGO.md                 # Logo specs and implementation
│   └── CONTENT.md              # Landing page content structure
├── src/
│   ├── env.d.ts                # Astro TypeScript definitions
│   └── pages/
│       ├── index.astro         # Landing page (standalone HTML)
│       ├── 404.astro           # Error page (standalone HTML)
│       └── contact-us/
│           └── index.astro     # Contact page (standalone HTML)
├── public/
│   └── favicon.svg             # Default Astro favicon (not branded)
├── astro.config.mjs            # Minimal config with Tailwind
├── tailwind.config.mjs         # Basic content paths only
├── tsconfig.json               # Extends astro/tsconfigs/strict
├── package.json
├── CNAME                       # finitetimespace.com
└── CLAUDE.md                   # This file
```

### Target (Planned)

```
finitetimespace.com/
├── documents/                  # Design documentation
├── src/
│   ├── components/             # Reusable Astro components
│   │   ├── Logo.astro          # Logo component (see LOGO.md)
│   │   ├── Header.astro
│   │   └── Footer.astro
│   ├── layouts/
│   │   └── Layout.astro        # Base layout with shared HTML
│   ├── pages/
│   │   ├── index.astro         # Landing page (uses Layout)
│   │   └── 404.astro           # Error page (uses Layout)
│   └── styles/
│       └── global.css          # CSS variables, design tokens
├── public/
│   ├── favicon.svg             # Λ mark favicon
│   └── og-image.png            # Open Graph image
├── astro.config.mjs
├── tailwind.config.mjs         # Extended with custom theme
└── package.json
```

## Design Documents

Before making changes, read the relevant design document in `/documents`:

| Task | Read First |
|------|------------|
| Colors, typography, overall aesthetic | `documents/CONCEPT.md` |
| Logo implementation, Λ mark | `documents/LOGO.md` |
| Page structure, sections, copy | `documents/CONTENT.md` |

## Design Tokens (To Be Implemented)

These design tokens are defined in `documents/CONCEPT.md` but **not yet implemented** in code.

### Colors

```css
/* src/styles/global.css — NOT YET CREATED */
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
}
```

### Tailwind Config (Target)

The current `tailwind.config.mjs` is minimal. It should be extended to:

```js
// tailwind.config.mjs — TARGET STATE
export default {
  content: ['./src/**/*.{astro,html,js,jsx,md,mdx,svelte,ts,tsx,vue}'],
  theme: {
    extend: {
      colors: {
        'ghost-white': '#F8F8FF',
        'rich-black': '#0A0A0A',
        'eerie-black': '#1B1B1B',
        'azure': '#F0FFFF',
      },
      fontFamily: {
        mono: ['IBM Plex Mono', 'monospace'],
        sans: ['IBM Plex Sans', 'sans-serif'],
      },
      maxWidth: {
        'prose': '42rem',
      },
    },
  },
}
```

### Typography

- **Logo:** IBM Plex Mono, 500 weight, 0.08em letter-spacing
- **Body:** IBM Plex Sans, 400/500 weight
- **Headings:** IBM Plex Sans, 500/600 weight
- **Code/technical:** IBM Plex Mono

### Font Loading (To Be Added)

Add to Layout.astro `<head>`:

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=IBM+Plex+Mono:wght@400;500;600&family=IBM+Plex+Sans:wght@400;500;600&display=swap" rel="stylesheet">
```

## Logo Component

The logo uses a **reversed "a" (Λ)** as a distinctive mark. See `documents/LOGO.md` for full specs.

### Quick Reference

```astro
<!-- src/components/Logo.astro -->
---
interface Props {
  variant?: 'filled' | 'outlined' | 'minimal';
}

const { variant = 'outlined' } = Astro.props;
---

<div class:list={[
  'logo',
  { 'logo--filled': variant === 'filled' },
  { 'logo--outlined': variant === 'outlined' },
  { 'logo--minimal': variant === 'minimal' },
]}>
  <div class="logo__line">finite</div>
  <div class="logo__line">timesp<span class="logo__lambda">a</span>ce</div>
</div>

<style>
  .logo {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 1.1rem;
    font-weight: 500;
    letter-spacing: 0.08em;
    line-height: 1.5;
    text-align: left;
  }
  
  .logo--filled {
    background: var(--bg-dark);
    color: var(--text-inverse);
    padding: 1.25rem 2.5rem 1.25rem 1rem;
  }
  
  .logo--outlined {
    border: 2px solid var(--text-primary);
    color: var(--text-primary);
    padding: 1.25rem 2.5rem 1.25rem 1rem;
  }
  
  .logo--minimal {
    color: var(--text-primary);
  }
  
  .logo__lambda {
    display: inline-block;
    transform: rotate(180deg) translateY(0.1em);
    font-weight: 600;
  }
</style>
```

## Page Structure

### Current Pages

| Page | Path | Status |
|------|------|--------|
| Landing | `/` | Basic structure, needs redesign |
| Contact | `/contact-us/` | Basic, needs to merge into landing |
| 404 | `/404` | Functional, needs styling |

### Target Structure (Single Page)

The landing page should be a **single-page** layout with these sections:

1. **Header** — Logo only
2. **Intro** — Company name, tagline, brief description
3. **Services** — Simple list
4. **Clients** — Names with locations
5. **Contact** — Email or simple form
6. **Footer** — Legal, registration

See `documents/CONTENT.md` for detailed structure and copy.

## Commands

```bash
# Development
npm run dev

# Build
npm run build

# Preview production build
npm run preview

# Type check
npm run astro check
```

## Code Style

- Use Astro components for everything
- Keep JavaScript minimal (progressive enhancement)
- Prefer CSS over JavaScript for interactions
- Use semantic HTML
- Follow accessibility best practices (WCAG AA)

## Key Constraints

### Do
- ✓ Keep it minimal — single page, text-first
- ✓ Use the defined color palette only
- ✓ Maintain generous whitespace
- ✓ Ensure high contrast (WCAG AAA)
- ✓ Make the Λ mark consistent across all logo uses
- ✓ Test on mobile first

### Don't
- ❌ Add animations beyond subtle hover states
- ❌ Use images (except favicon/OG)
- ❌ Add JavaScript carousels or effects
- ❌ Use colors outside the palette
- ❌ Break the single-column layout
- ❌ Over-engineer — this is a simple static site

---

## Recommended Improvements

### Priority 1: Foundation (Do First)

1. **Create `src/layouts/Layout.astro`**
   - Eliminates duplicate HTML boilerplate across pages
   - Centralizes `<head>` meta tags, fonts, and styles
   - Single source of truth for page structure

2. **Create `src/styles/global.css`**
   - Define CSS custom properties (design tokens)
   - Import via Layout.astro
   - Enables consistent theming

3. **Extend `tailwind.config.mjs`**
   - Add custom colors from design spec
   - Add IBM Plex font families
   - Add prose max-width

4. **Add Google Fonts**
   - IBM Plex Mono and IBM Plex Sans
   - Use preconnect for performance

### Priority 2: Components

5. **Create `src/components/Logo.astro`**
   - Implement Λ mark (reversed "a")
   - Support variants: filled, outlined, minimal
   - Follow `documents/LOGO.md` spec

6. **Create `src/components/Footer.astro`**
   - Extract common footer
   - Update copyright year
   - Add legal/registration info

7. **Update `public/favicon.svg`**
   - Replace default Astro favicon
   - Create Λ mark SVG

### Priority 3: Code Quality

8. **Add ESLint + Prettier**
   ```bash
   npm install -D eslint prettier eslint-plugin-astro prettier-plugin-astro
   ```
   - Consistent code formatting
   - Catch errors early

9. **Update dependencies**
   - Astro 5.x has View Transitions, improved performance
   - Tailwind CSS 4.x when stable (currently in beta)
   - Review changelog before major updates

10. **Add proper meta tags**
    - Description for SEO
    - Open Graph tags for social sharing
    - Twitter card meta tags
    - Create `public/og-image.png`

### Priority 4: Nice-to-Have

11. **Consider Astro View Transitions**
    - Native page transitions (Astro 3+)
    - Smooth navigation without JavaScript
    - Opt-in per page or global

12. **Add sitemap integration**
    ```bash
    npx astro add sitemap
    ```

13. **Remove `/contact-us/` page**
    - Merge into landing page per Weatherlight model
    - Single-page architecture

### Current Issues to Fix

| Issue | Location | Fix |
|-------|----------|-----|
| Emoji in code | `index.astro:37` | Remove 👈 |
| Hardcoded colors | `404.astro:20` | Use Tailwind theme colors |
| Duplicate footer | All pages | Extract to component |
| Missing viewport meta | `404.astro` | Add via Layout |
| Outdated copyright | All pages | Use dynamic year |
| Inconsistent styling | All pages | Apply design system |

---

## Content Updates

All content copy lives in `src/pages/index.astro`. When updating:

1. Check `documents/CONTENT.md` for approved structure
2. Keep copy minimal — Weatherlight style
3. Client names need explicit permission

## Deployment

- **Domain:** finitetimespace.com (via CNAME)
- **Hosting:** GitHub Pages (inferred from CNAME)
- **Deploy:** Automatic on push to `main`

## Dependencies

```json
{
  "@astrojs/check": "^0.5.9",
  "@astrojs/tailwind": "^5.1.0",
  "astro": "^4.5.5",
  "tailwindcss": "^3.4.1",
  "typescript": "^5.4.2"
}
```

**Note:** Dependencies were last updated around March 2024. Consider updating to latest stable versions:
- Astro 5.x introduces stable View Transitions and performance improvements
- Check [Astro changelog](https://github.com/withastro/astro/blob/main/packages/astro/CHANGELOG.md) before upgrading

## Questions?

If unclear about design decisions, check the documents in order:
1. `documents/CONCEPT.md` — overall direction
2. `documents/LOGO.md` — logo specifics
3. `documents/CONTENT.md` — content structure
