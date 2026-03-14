# CLAUDE.md

> Instructions for Claude Code when working on the Finite Timespace landing page.

## Project Overview

**Finite Timespace** is a solo software engineering agency website. This is a minimal, text-first landing page following the Weatherlight design model — premium restraint, typography-focused, anti-portfolio.

**Repository:** https://github.com/FiniteTimespace/finitetimespace.com

## Tech Stack

| Layer | Technology |
|-------|------------|
| Framework | Astro |
| Styling | Tailwind CSS |
| Fonts | IBM Plex Mono, IBM Plex Sans (Google Fonts) |
| Forms | TBD (Formspree / Netlify Forms) |
| Hosting | Vercel / Cloudflare Pages |

## Project Structure

```
finitetimespace.com/
├── documents/                  # Design documentation
│   ├── CONCEPT.md              # Primary design doc (colors, typography, references)
│   ├── LOGO.md                 # Logo specs and implementation
│   └── CONTENT.md              # Landing page content structure
├── src/
│   ├── components/             # Astro components
│   │   ├── Logo.astro          # Logo component (see LOGO.md)
│   │   ├── Header.astro
│   │   ├── Footer.astro
│   │   └── ContactForm.astro   # Optional contact form
│   ├── layouts/
│   │   └── Layout.astro        # Base layout
│   ├── pages/
│   │   └── index.astro         # Landing page
│   └── styles/
│       └── global.css          # Global styles, CSS variables
├── public/
│   ├── favicon.svg             # Λ mark favicon
│   └── og-image.png            # Open Graph image
├── astro.config.mjs
├── tailwind.config.mjs
├── package.json
└── CLAUDE.md                   # This file
```

## Design Documents

Before making changes, read the relevant design document in `/documents`:

| Task | Read First |
|------|------------|
| Colors, typography, overall aesthetic | `documents/CONCEPT.md` |
| Logo implementation, Λ mark | `documents/LOGO.md` |
| Page structure, sections, copy | `documents/CONTENT.md` |

## Design Tokens

### Colors

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
}
```

### Tailwind Config

```js
// tailwind.config.mjs
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

## Logo Component

The logo uses a **reversed "a" (Λ)** as a distinctive mark. See `docs/LOGO.md` for full specs.

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

The landing page is a **single-page** layout with these sections:

1. **Header** — Logo only
2. **Intro** — Company name, tagline, brief description
3. **Services** — Simple list
4. **Clients** — Names with locations
5. **Contact** — Email or simple form
6. **Footer** — Legal, registration

See `docs/CONTENT.md` for detailed structure and copy.

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

## Content Updates

All content copy lives in `src/pages/index.astro`. When updating:

1. Check `documents/CONTENT.md` for approved structure
2. Keep copy minimal — Weatherlight style
3. Client names need explicit permission

## Deployment

The site deploys automatically on push to `main`:

- **Preview:** PR deployments for review
- **Production:** Merges to `main` deploy to production

## Questions?

If unclear about design decisions, check the documents in order:
1. `documents/CONCEPT.md` — overall direction
2. `documents/LOGO.md` — logo specifics
3. `documents/CONTENT.md` — content structure
