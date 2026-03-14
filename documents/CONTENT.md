# Finite Timespace — Landing Page Content

**Version:** 1.0
**Last Updated:** March 14, 2026
**Status:** Draft

**Related Documents:**
- [CONCEPT.md](./CONCEPT.md) — Design concept, colors, typography
- [LOGO.md](./LOGO.md) — Logo explorations and usage guidelines

---

## Table of Contents

1. [Page Structure](#page-structure)
2. [Header](#header)
3. [Main Sections](#main-sections)
4. [Contact Form](#contact-form)
5. [Footer](#footer)
6. [Technical Notes](#technical-notes)

---

## Page Structure

### Overview

Single-page layout following the Weatherlight model:

```
┌─────────────────────────────────────────────────────────┐
│  HEADER (Logo)                                          │
├─────────────────────────────────────────────────────────┤
│  INTRO (Tagline + Description)                          │
├─────────────────────────────────────────────────────────┤
│  SERVICES                                               │
├─────────────────────────────────────────────────────────┤
│  CLIENTS                                                │
├─────────────────────────────────────────────────────────┤
│  CONTACT                                                │
├─────────────────────────────────────────────────────────┤
│  FOOTER                                                 │
└─────────────────────────────────────────────────────────┘
```

### Content Width

- **Max-width:** 42rem (~672px) for optimal reading
- **Padding:** 1.5rem horizontal on mobile, 2rem on desktop

---

## Header

### Structure

```
┌─────────────────────────────────────────────────────────┐
│                                                         │
│  ┌─────────────────┐                                    │
│  │ finite          │                                    │
│  │ timespΛce       │                                    │
│  └─────────────────┘                                    │
│                                                         │
└─────────────────────────────────────────────────────────┘
```

### Content

- Logo only (Option B: Outlined, or Option C: Minimal)
- No navigation — single page scroll
- Sticky behavior: optional, subtle

---

## Main Sections

### Section 1: Intro

**Structure:**
```
FINITE TIMESPACE
Software Engineering
c/o Niki

[Brief description - 1-2 sentences]
```

**Draft Content:**
```markdown
**FINITE TIMESPACE**
Software Engineering
c/o Niki

Independent software engineering for Apple platforms. 
10+ years building iOS and macOS applications.
```

**Alternative (more Weatherlight):**
```markdown
**FINITE TIMESPACE**
Software Engineering Company
c/o Niki
Porto, Portugal
```

---

### Section 2: Services

**Structure:**
```
Services
────────────────────────

[Service list]
```

**Draft Content:**
```markdown
Services

iOS Development
macOS Development
Software Architecture
Technical Consulting
```

**Alternative (with context):**
```markdown
Bespoke Services

iOS Development
macOS Development
SwiftUI & UIKit
Software Architecture
Technical Consulting
Code Review & Audits
```

---

### Section 3: Clients

**Structure:**
```
Select Clients
────────────────────────

[Client list with locations]
```

**Draft Content:**
```markdown
Select Clients

Kensa Health (London, UK)
[Client Name] ([City], [Country])
[Client Name] ([City], [Country])
```

**Format Notes:**
- Client name followed by location in parentheses
- Alphabetical or by recency
- Only include clients with permission
- Geographic diversity signals reach

---

### Section 4: Contact

Two options based on design direction:

#### Option A: Email Only (Weatherlight Style)

```markdown
Contact

hello@finitetimespace.com
```

#### Option B: Contact Form (Hello Robo Inspired)

See [Contact Form](#contact-form) section below.

---

## Contact Form

### Reference

Based on Hello Robo contact form structure:
- **Source:** hellorobo.co
- **XPath:** `/html/body/div[2]/main/section[9]`
- **Webflow attribute:** `data-wf--contact-form--variant="base"`

### Simplified Structure for Solo Agency

```html
<section class="contact-form">
  <h2>Let's talk</h2>
  
  <form>
    <!-- Email (required) -->
    <div class="field">
      <label for="email">Email *</label>
      <input type="email" id="email" name="email" required>
    </div>
    
    <!-- Name (required) -->
    <div class="field">
      <label for="name">Name *</label>
      <input type="text" id="name" name="name" required>
    </div>
    
    <!-- Project Type (optional checkboxes) -->
    <div class="field">
      <label>What do you need?</label>
      <div class="checkboxes">
        <label>
          <input type="checkbox" name="service" value="ios">
          iOS Development
        </label>
        <label>
          <input type="checkbox" name="service" value="macos">
          macOS Development
        </label>
        <label>
          <input type="checkbox" name="service" value="consulting">
          Technical Consulting
        </label>
        <label>
          <input type="checkbox" name="service" value="other">
          Something else
        </label>
      </div>
    </div>
    
    <!-- Message (optional) -->
    <div class="field">
      <label for="message">Tell me about your project</label>
      <textarea id="message" name="message" rows="4"></textarea>
      <span class="hint">Optional</span>
    </div>
    
    <!-- Submit -->
    <button type="submit">Send</button>
  </form>
  
  <!-- Success State -->
  <div class="success" hidden>
    Thanks! I'll be in touch soon.
  </div>
  
  <!-- Error State -->
  <div class="error" hidden>
    Something went wrong. Please try again or email directly.
  </div>
</section>
```

### Form Fields Comparison

| Hello Robo | Finite Timespace | Notes |
|------------|------------------|-------|
| Email * | Email * | Keep |
| Full Name * | Name * | Simplify label |
| How can we help? * (checkboxes) | What do you need? (checkboxes) | Adapt services |
| How did you know about us? | — | Remove (unnecessary for solo) |
| — | Tell me about your project | Add optional message |

### Form Behavior

- **Submission:** Formspree, Netlify Forms, or custom endpoint
- **Validation:** HTML5 native + JavaScript enhancement
- **Success:** Show inline message, hide form
- **Error:** Show inline message, keep form visible

---

## Footer

### Structure

```
┌─────────────────────────────────────────────────────────┐
│                                                         │
│  © 2024–2026 Finite Timespace LLC                       │
│  Registered in Wyoming, USA                             │
│  Independently owned and operated                       │
│                                                         │
└─────────────────────────────────────────────────────────┘
```

### Draft Content

```markdown
© 2024–2026 Finite Timespace LLC
Registered in Wyoming, USA
Independently owned and operated
```

### Alternative (with links)

```markdown
© 2024–2026 Finite Timespace LLC
Registered in Wyoming, USA

[GitHub](https://github.com/...)
[LinkedIn](https://linkedin.com/in/...)
```

---

## Technical Notes

### Implementation Stack

| Layer | Technology |
|-------|------------|
| Framework | Astro |
| Styling | Tailwind CSS |
| Forms | Formspree / Netlify Forms |
| Hosting | Vercel / Cloudflare Pages |
| Analytics | Plausible (optional) |

### SEO Metadata

```html
<head>
  <title>Finite Timespace — iOS & macOS Software Engineering</title>
  <meta name="description" content="Independent software engineering for Apple platforms. 10+ years building iOS and macOS applications.">
  
  <!-- Open Graph -->
  <meta property="og:title" content="Finite Timespace">
  <meta property="og:description" content="Independent software engineering for Apple platforms.">
  <meta property="og:image" content="/og-image.png">
  <meta property="og:type" content="website">
  
  <!-- Twitter -->
  <meta name="twitter:card" content="summary_large_image">
  <meta name="twitter:title" content="Finite Timespace">
  <meta name="twitter:description" content="Independent software engineering for Apple platforms.">
</head>
```

### Structured Data (JSON-LD)

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Organization",
  "name": "Finite Timespace LLC",
  "url": "https://finitetimespace.com",
  "description": "Independent software engineering for Apple platforms",
  "address": {
    "@type": "PostalAddress",
    "addressRegion": "Wyoming",
    "addressCountry": "US"
  },
  "founder": {
    "@type": "Person",
    "name": "Niki"
  }
}
</script>
```

---

## Content Checklist

### Required
- [ ] Finalize tagline/intro copy
- [ ] Confirm services list
- [ ] Gather client names + locations (with permission)
- [ ] Decide on contact method (email only vs form)
- [ ] Write form success/error messages

### Optional
- [ ] Add brief bio
- [ ] Link to side projects/ventures
- [ ] Add social links to footer

---

**Document maintained by:** Nikita Khomitsevych
**Last review:** March 14, 2026
