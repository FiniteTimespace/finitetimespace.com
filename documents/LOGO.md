# Finite Timespace — Logo

**Version:** 1.0
**Last Updated:** March 14, 2026
**Status:** Draft

**Related Documents:**
- [CONCEPT.md](./CONCEPT.md) — Design concept, colors, typography
- [CONTENT.md](./CONTENT.md) — Landing page content structure

See also: [CLAUDE.md](../CLAUDE.md) — Project instructions for Claude Code

---

## Table of Contents

1. [Logo Concept](#logo-concept)
2. [Logo Inspiration](#logo-inspiration)
3. [The Λ (Lambda) Mark](#the-λ-lambda-mark)
4. [Logo Variations](#logo-variations)
5. [Usage Guidelines](#usage-guidelines)
6. [Implementation Code](#implementation-code)

---

## Logo Concept

### Core Elements

The Finite Timespace wordmark is built on three principles:

1. **Two-line stacked layout** — `finite` above `timespace`
2. **Left-aligned text with asymmetric padding** — tighter left (~16px), more space right (~40px)
3. **The Λ (lambda) mark** — reversed "a" in "timespace" as a distinctive visual element

### Typography

- **Font:** IBM Plex Mono (Medium 500 / Semibold 600)
- **Letter-spacing:** 0.08em
- **Line-height:** 1.5
- **Case:** lowercase

---

## Logo Inspiration

### THE TRANSITION. — Primary Reference

A visual identity from a music/video project featuring:

| Element | THE TRANSITION | Finite Timespace Adaptation |
|---------|---------------|----------------------------|
| Typography | Condensed bold sans, all-caps | IBM Plex Mono, lowercase |
| Container | Vibrant pink/magenta block | Rich Black (#0A0A0A) block |
| Text | White knockout | White knockout |
| Structure | Single line | Two lines, stacked |
| Punctuation | Period at end | Λ mark in "timespace" |

### Key Takeaways

- **High contrast** — works over any background
- **Knockout text** — creates strong visual mark
- **Period/punctuation as design** — finality, confidence
- **Color block** — instant brand recognition

---

## The Λ (Lambda) Mark

### Concept

The letter "a" in "timespace" is rendered as a rotated/reversed "a" resembling the Greek letter lambda (Λ).

```
Standard:    timespace
With mark:   timespΛce
```

### Significance

| Association | Meaning |
|-------------|---------|
| **Physics** | Spacetime notation, relativity |
| **Mathematics** | Lambda calculus, functional programming |
| **Wavelength** | λ symbol in physics |
| **Greek letter** | Academic/scientific credibility |

### Visual Treatment

```css
.reversed-a {
  display: inline-block;
  transform: rotate(180deg) translateY(0.1em);
  font-weight: 600;  /* Slightly heavier than surrounding text */
}

.reversed-a-caps {
  display: inline-block;
  transform: rotate(180deg) translateY(-0.05em);
  font-weight: 700;
}
```

### Standalone Mark (Favicon)

The Λ can be extracted as a standalone mark for:
- Favicon
- App icon
- Social media avatar
- Watermark

---

## Logo Variations

### Option A: Filled Box (Primary)

**Use for:** Social media, dark backgrounds, hero placement

```
┌─────────────────────────┐
│ finite                  │  ← White text
│ timespΛce               │  ← on Rich Black (#0A0A0A)
└─────────────────────────┘
     ↑
   Asymmetric padding:
   Left: 16px, Right: 40px
   Top/Bottom: 20px
```

**Characteristics:**
- Strong presence
- Works on any background
- Clear brand mark

### Option B: Outlined Box (Secondary)

**Use for:** Website header, light backgrounds, subtle contexts

```
┏━━━━━━━━━━━━━━━━━━━━━━━━━┓
┃ finite                  ┃  ← Rich Black text
┃ timespΛce               ┃  ← on transparent
┗━━━━━━━━━━━━━━━━━━━━━━━━━┛
     ↑
   2px Rich Black border
```

**Characteristics:**
- Lighter weight
- Refined, elegant
- Better for Ghost White backgrounds

### Option C: No Box (Minimal)

**Use for:** In-text references, footer, maximum restraint

```
finite
timespΛce
```

**Characteristics:**
- Pure typography
- iA.net territory
- Most understated

### Option D: Inverted (Dark Mode)

**Use for:** Dark backgrounds, inversions

```
┌─────────────────────────┐
│ finite                  │  ← Rich Black text
│ timespΛce               │  ← on White background
└─────────────────────────┘
```

---

## Usage Guidelines

### Recommended Usage

| Context | Recommended Option |
|---------|-------------------|
| Website header | Option B (Outlined) or Option C (No Box) |
| Dark backgrounds | Option A (Filled) |
| Light backgrounds | Option B (Outlined) |
| Favicon | Λ mark only |
| Social media profile | Option A (Filled) |
| Email signature | Option C (No Box) |
| Print / documents | Option B (Outlined) |
| Watermark | Option A (Filled) at reduced opacity |

### Clear Space

Maintain minimum clear space around the logo equal to the height of one line of text:

```
        ┌─ Clear space (1x line height)
        ▼
    ┌───────────────────────────┐
    │                           │
    │   ┌─────────────────┐     │
    │   │ finite          │     │
    │   │ timespΛce       │     │
    │   └─────────────────┘     │
    │                           │
    └───────────────────────────┘
```

### Minimum Size

- **Digital:** 120px width minimum
- **Print:** 25mm width minimum

### Don'ts

- ❌ Don't stretch or distort
- ❌ Don't change the font
- ❌ Don't remove the Λ mark
- ❌ Don't add effects (shadows, gradients)
- ❌ Don't rotate
- ❌ Don't change letter-spacing
- ❌ Don't use colors outside the palette

---

## Implementation Code

### HTML + CSS (Complete)

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
      --text-primary: #0A0A0A;
      --text-inverse: #FFFFFF;
    }
    
    /* ================================
       OPTION A: Filled Box
       ================================ */
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
    
    /* ================================
       OPTION B: Outlined Box
       ================================ */
    .logo-outlined {
      border: 2px solid var(--text-primary);
      padding: 1.25rem 2.5rem 1.25rem 1rem;
      display: inline-block;
      background: transparent;
    }
    
    .logo-outlined .line {
      font-family: 'IBM Plex Mono', monospace;
      font-size: 1.1rem;
      font-weight: 500;
      letter-spacing: 0.08em;
      color: var(--text-primary);
      line-height: 1.5;
      text-align: left;
    }
    
    /* ================================
       OPTION C: No Box
       ================================ */
    .logo-minimal .line {
      font-family: 'IBM Plex Mono', monospace;
      font-size: 1.2rem;
      font-weight: 500;
      letter-spacing: 0.06em;
      color: var(--text-primary);
      line-height: 1.5;
      text-align: left;
    }
    
    /* ================================
       OPTION D: Inverted (for dark bg)
       ================================ */
    .logo-inverted {
      background: var(--text-inverse);
      padding: 1.25rem 2.5rem 1.25rem 1rem;
      display: inline-block;
    }
    
    .logo-inverted .line {
      font-family: 'IBM Plex Mono', monospace;
      font-size: 1.1rem;
      font-weight: 500;
      letter-spacing: 0.08em;
      color: var(--text-primary);
      line-height: 1.5;
      text-align: left;
    }
    
    /* ================================
       Λ (Lambda) Mark
       ================================ */
    .reversed-a {
      display: inline-block;
      transform: rotate(180deg) translateY(0.1em);
      font-weight: 600;
    }
  </style>
</head>
<body>

  <!-- OPTION A: Filled Box -->
  <div class="logo-filled">
    <div class="line">finite</div>
    <div class="line">timesp<span class="reversed-a">a</span>ce</div>
  </div>

  <!-- OPTION B: Outlined Box -->
  <div class="logo-outlined">
    <div class="line">finite</div>
    <div class="line">timesp<span class="reversed-a">a</span>ce</div>
  </div>

  <!-- OPTION C: No Box -->
  <div class="logo-minimal">
    <div class="line">finite</div>
    <div class="line">timesp<span class="reversed-a">a</span>ce</div>
  </div>

  <!-- OPTION D: Inverted -->
  <div class="logo-inverted">
    <div class="line">finite</div>
    <div class="line">timesp<span class="reversed-a">a</span>ce</div>
  </div>

</body>
</html>
```

### React Component

```tsx
import React from 'react';

type LogoVariant = 'filled' | 'outlined' | 'minimal' | 'inverted';

interface LogoProps {
  variant?: LogoVariant;
  className?: string;
}

export const Logo: React.FC<LogoProps> = ({ 
  variant = 'filled',
  className = '' 
}) => {
  const baseStyles = {
    fontFamily: "'IBM Plex Mono', monospace",
    fontSize: '1.1rem',
    fontWeight: 500,
    letterSpacing: '0.08em',
    lineHeight: 1.5,
    textAlign: 'left' as const,
  };

  const variantStyles = {
    filled: {
      container: {
        background: '#0A0A0A',
        padding: '1.25rem 2.5rem 1.25rem 1rem',
        display: 'inline-block',
      },
      text: { color: '#FFFFFF' },
    },
    outlined: {
      container: {
        border: '2px solid #0A0A0A',
        padding: '1.25rem 2.5rem 1.25rem 1rem',
        display: 'inline-block',
        background: 'transparent',
      },
      text: { color: '#0A0A0A' },
    },
    minimal: {
      container: { display: 'inline-block' },
      text: { color: '#0A0A0A', fontSize: '1.2rem' },
    },
    inverted: {
      container: {
        background: '#FFFFFF',
        padding: '1.25rem 2.5rem 1.25rem 1rem',
        display: 'inline-block',
      },
      text: { color: '#0A0A0A' },
    },
  };

  const styles = variantStyles[variant];

  return (
    <div style={styles.container} className={className}>
      <div style={{ ...baseStyles, ...styles.text }}>finite</div>
      <div style={{ ...baseStyles, ...styles.text }}>
        timesp
        <span style={{ 
          display: 'inline-block',
          transform: 'rotate(180deg) translateY(0.1em)',
          fontWeight: 600,
        }}>
          a
        </span>
        ce
      </div>
    </div>
  );
};
```

---

## Assets Checklist

- [ ] SVG versions of all logo variants
- [ ] PNG exports at 1x, 2x, 3x
- [ ] Favicon (Λ mark only) — .ico, .png, .svg
- [ ] Open Graph image (1200x630)
- [ ] Apple Touch Icon (180x180)
