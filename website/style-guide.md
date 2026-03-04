# ClaimMentor Brand Style Guide

> Visual identity and design standards for ClaimMentor

---

## Brand Essence

**Tagline:** "Built For Insurance Adjusters"

**Value Proposition:** We automate and streamline recorded statements

**Proof Points:**
- 2.5 hours saved per day per adjuster
- $1,000/month cost savings per adjuster
- 75 insurance industry experts interviewed
- 25 adjusters validated problem and value
- 22 claim decision makers representing 20 companies

**Team Credibility:**
- "Experts on Insurance Claims & AI"
- Leadership from Guidewire, Socotra, Interactive Intelligence (Genesys)
- 2 patents in insurance automation
- Multiple successful exits

---

## Logo

### Primary Logo (Teal + Black)
- **"Claim"** — Teal `#16464F`
- **"Mentor"** — Near Black `#100F0D`
- Use on white/light backgrounds

### Alternate Logo (Navy + Black)
- **"Claim"** — Navy Blue `#003366`
- **"Mentor"** — Black `#000000`
- Use when teal doesn't work with context

### Monochrome Logo
- All black `#100F0D` or all white `#FFFFFF`
- Use for single-color applications (print, favicon, etc.)

### Logo Files
```
claimmentor logos/
├── claimmentor-green.svg    # Primary (teal + black)
├── claimmentor.svg          # Alternate (navy + black)
├── claimmentor.png          # Alternate raster
├── claimmentor 2.png        # Primary raster
└── Logo-options/            # Additional variations
```

### Logo Clear Space
- Minimum clear space: Height of the "M" on all sides
- Never place logo on busy backgrounds without container

---

## Color Palette

### Primary Colors

| Color | Hex | RGB | Use |
|-------|-----|-----|-----|
| **Teal** | `#16464F` | rgb(22, 70, 79) | Primary brand color, "Claim" in logo, CTAs, UI accents |
| **Near Black** | `#100F0D` | rgb(16, 15, 13) | Body text, "Mentor" in logo, headlines |
| **Navy** | `#003366` | rgb(0, 51, 102) | Alternate brand color, large headlines |

### Secondary Colors

| Color | Hex | RGB | Use |
|-------|-----|-----|-----|
| **White** | `#FFFFFF` | rgb(255, 255, 255) | Backgrounds, reverse text |
| **Light Blue** | `#E8EDF5` | rgb(232, 237, 245) | Slide/section backgrounds, cards |
| **Light Gray** | `#F5F5F5` | rgb(245, 245, 245) | Section backgrounds |
| **Mid Gray** | `#6B7280` | rgb(107, 114, 128) | Secondary text, captions |
| **Border Gray** | `#E5E7EB` | rgb(229, 231, 235) | Borders, dividers |

### Accent Colors

| Color | Hex | RGB | Use |
|-------|-----|-----|-----|
| **Gold/Mustard** | `#C9A227` | rgb(201, 162, 39) | Section labels, highlights, premium accents |
| **Success Green** | `#22C55E` | rgb(34, 197, 94) | Success states, checkmarks, positive indicators |
| **Alert Red** | `#DC2626` | rgb(220, 38, 38) | Errors, problem callouts, urgent items |
| **Soft Blue** | `#5B8FAF` | rgb(91, 143, 175) | Info states, secondary accents |

### Color Usage

```
┌─────────────────────────────────────────────────────────────┐
│  HEADER / HERO                                              │
│  Background: White or Light Gray                            │
│  Text: Near Black (#100F0D)                                 │
│  Accent: Teal (#16464F)                                     │
├─────────────────────────────────────────────────────────────┤
│  CTA BUTTONS                                                │
│  Primary: Teal (#16464F) bg, White text                     │
│  Secondary: White bg, Teal border, Teal text                │
│  Hover: Darken 10%                                          │
├─────────────────────────────────────────────────────────────┤
│  FOOTER                                                     │
│  Background: Near Black (#100F0D)                           │
│  Text: White / Light Gray                                   │
│  Links: Teal (#16464F) or lighter tint                      │
└─────────────────────────────────────────────────────────────┘
```

---

## Typography

### Font Family

**Primary Font:** Avenir

```css
font-family: 'Avenir', 'Avenir Next', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
```

**Fallback Stack:** System fonts for performance

### Font Weights

| Weight | Name | Use |
|--------|------|-----|
| 400 | Regular | Body text |
| 500 | Medium | Subheadings, emphasis |
| 600 | Semibold | Buttons, labels |
| 700 | Bold | Headlines, CTAs |
| 900 | Black | Hero headlines (sparingly) |

### Type Scale

| Element | Size | Weight | Line Height | Letter Spacing |
|---------|------|--------|-------------|----------------|
| Hero H1 | 48-64px | 700 | 1.1 | -0.02em |
| H1 | 36-40px | 700 | 1.2 | -0.01em |
| H2 | 28-32px | 600 | 1.3 | 0 |
| H3 | 22-24px | 600 | 1.4 | 0 |
| H4 | 18-20px | 600 | 1.4 | 0 |
| Body Large | 18px | 400 | 1.6 | 0 |
| Body | 16px | 400 | 1.6 | 0 |
| Body Small | 14px | 400 | 1.5 | 0 |
| Caption | 12px | 400 | 1.4 | 0.02em |

### Typography Examples

```css
/* Hero Headline */
.hero-headline {
  font-size: 3.5rem;
  font-weight: 700;
  line-height: 1.1;
  color: #100F0D;
  letter-spacing: -0.02em;
}

/* Section Headline */
.section-headline {
  font-size: 2rem;
  font-weight: 600;
  line-height: 1.3;
  color: #100F0D;
}

/* Body Text */
.body-text {
  font-size: 1rem;
  font-weight: 400;
  line-height: 1.6;
  color: #100F0D;
}

/* Accent Text (for highlighting "Claim" in headlines) */
.accent-text {
  color: #16464F;
}
```

---

## Spacing System

Based on 4px base unit:

| Token | Value | Use |
|-------|-------|-----|
| `xs` | 4px | Tight spacing, icon gaps |
| `sm` | 8px | Small gaps, padding |
| `md` | 16px | Default spacing |
| `lg` | 24px | Section padding |
| `xl` | 32px | Large gaps |
| `2xl` | 48px | Section margins |
| `3xl` | 64px | Hero padding |
| `4xl` | 96px | Major sections |

---

## Components

### Buttons

**Primary Button**
```css
.btn-primary {
  background: #16464F;
  color: #FFFFFF;
  padding: 12px 24px;
  border-radius: 6px;
  font-weight: 600;
  font-size: 16px;
  border: none;
  cursor: pointer;
  transition: background 0.2s;
}

.btn-primary:hover {
  background: #0F3238; /* Darken 15% */
}
```

**Secondary Button**
```css
.btn-secondary {
  background: #FFFFFF;
  color: #16464F;
  padding: 12px 24px;
  border-radius: 6px;
  font-weight: 600;
  font-size: 16px;
  border: 2px solid #16464F;
  cursor: pointer;
  transition: all 0.2s;
}

.btn-secondary:hover {
  background: #16464F;
  color: #FFFFFF;
}
```

### Cards

```css
.card {
  background: #FFFFFF;
  border: 1px solid #E5E7EB;
  border-radius: 8px;
  padding: 24px;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
}

.card:hover {
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
}
```

### Form Inputs

```css
.input {
  width: 100%;
  padding: 12px 16px;
  border: 1px solid #E5E7EB;
  border-radius: 6px;
  font-size: 16px;
  color: #100F0D;
  transition: border-color 0.2s;
}

.input:focus {
  outline: none;
  border-color: #16464F;
  box-shadow: 0 0 0 3px rgba(22, 70, 79, 0.1);
}
```

---

## Imagery

### Photography Style
- **Professional but approachable** — real people in work settings
- **Insurance context** — adjusters at desks, video calls, claims scenarios
- **Diverse representation** — varied ages, backgrounds
- **Natural lighting** — avoid overly stock-photo feel

### Icons
- **Style:** Line icons, 1.5-2px stroke
- **Size:** 24px default, 16px small, 32px large
- **Color:** Inherit from text or use Teal for emphasis

### Illustrations (if used)
- Simple, geometric style
- Use brand colors (Teal, Navy, grays)
- Avoid overly playful — maintain professional tone

---

## Voice & Tone

### Brand Voice
- **Confident** — We know insurance claims
- **Clear** — No jargon, direct communication
- **Helpful** — We're here to solve problems
- **Professional** — Serious about security and compliance

### Writing Guidelines

| Do | Don't |
|----|-------|
| "Video recorded statements" | "Video recording solution" |
| "Catch fraud" | "Enhance outcomes" |
| "See who you're paying" | "Improve visibility" |
| "$100/month per adjuster" | "Contact for pricing" |
| "Built by insurance veterans" | "Experienced team" |

### Headlines
- Lead with outcomes, not features
- Use active voice
- Keep under 10 words

**Good:** "Video Statements That Catch Fraud"
**Bad:** "Our Platform Helps Automate Your Recording Process"

---

## CSS Variables

```css
:root {
  /* Colors */
  --color-teal: #16464F;
  --color-teal-dark: #0F3238;
  --color-teal-light: #1E5A66;
  --color-navy: #003366;
  --color-black: #100F0D;
  --color-white: #FFFFFF;
  --color-gray-50: #F9FAFB;
  --color-gray-100: #F5F5F5;
  --color-gray-200: #E5E7EB;
  --color-gray-500: #6B7280;
  --color-gray-900: #111827;
  --color-success: #22C55E;
  --color-warning: #F59E0B;
  --color-error: #EF4444;

  /* Typography */
  --font-family: 'Avenir', 'Avenir Next', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
  --font-size-xs: 0.75rem;
  --font-size-sm: 0.875rem;
  --font-size-base: 1rem;
  --font-size-lg: 1.125rem;
  --font-size-xl: 1.25rem;
  --font-size-2xl: 1.5rem;
  --font-size-3xl: 2rem;
  --font-size-4xl: 2.5rem;
  --font-size-5xl: 3.5rem;

  /* Spacing */
  --space-1: 4px;
  --space-2: 8px;
  --space-3: 12px;
  --space-4: 16px;
  --space-6: 24px;
  --space-8: 32px;
  --space-12: 48px;
  --space-16: 64px;
  --space-24: 96px;

  /* Border Radius */
  --radius-sm: 4px;
  --radius-md: 6px;
  --radius-lg: 8px;
  --radius-xl: 12px;
  --radius-full: 9999px;

  /* Shadows */
  --shadow-sm: 0 1px 2px rgba(0, 0, 0, 0.05);
  --shadow-md: 0 1px 3px rgba(0, 0, 0, 0.1);
  --shadow-lg: 0 4px 12px rgba(0, 0, 0, 0.1);
  --shadow-xl: 0 10px 25px rgba(0, 0, 0, 0.1);
}
```

---

## Tailwind Config (if using Tailwind CSS)

```javascript
// tailwind.config.js
module.exports = {
  theme: {
    extend: {
      colors: {
        teal: {
          DEFAULT: '#16464F',
          dark: '#0F3238',
          light: '#1E5A66',
        },
        navy: '#003366',
        brand: {
          black: '#100F0D',
        },
      },
      fontFamily: {
        sans: ['Avenir', 'Avenir Next', '-apple-system', 'BlinkMacSystemFont', 'Segoe UI', 'Roboto', 'sans-serif'],
      },
    },
  },
}
```

---

## Quick Reference

### Primary Brand Colors
| | Teal | Black |
|---|------|-------|
| **Hex** | `#16464F` | `#100F0D` |
| **Use** | CTAs, accents, "Claim" | Body text, "Mentor" |

### Font
**Avenir** — clean, professional, modern sans-serif

### Key Principles
1. **Professional** — We're B2B insurance tech
2. **Clear** — No clutter, direct messaging
3. **Trustworthy** — Consistent, reliable appearance
4. **Modern** — Clean lines, generous whitespace

---

*Last updated: March 2026*
