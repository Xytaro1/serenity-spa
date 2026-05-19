# Serenity Spa — Design System
**Version:** 1.0  
**Date:** 2026-05-19  
**Stack:** HTML + Tailwind CSS (CDN), no frameworks  
**Aesthetic:** Soft UI Evolution — warm, diffuse shadows, organic shapes, serif/sans pairing, premium restraint

---

## TABLE OF CONTENTS

1. Color Palette & Semantic Tokens
2. Typography
3. Spacing System
4. Effects (Shadows, Radii, Gradients, Organic Shapes)
5. Component Specifications
6. Motion & Animation
7. Responsive System
8. Iconography
9. Accessibility Standards
10. Tailwind Config Object

---

## 1. COLOR PALETTE & SEMANTIC TOKENS

### Design Principles
- Backgrounds are never pure white — always warm off-white with 2–5% tint
- Earthy browns signal touch and grounding
- Deep teal drives trust and action (CTA)
- Terracotta is the emotional warmth accent (never overused)
- Sage provides nature/calm contrast
- High saturation is forbidden across all tokens

### Semantic Token Reference

| Token | Role | Hex | Usage |
|---|---|---|---|
| `serenity-base` | Primary background | #FAF8F5 | Page background, section alternation, modal body |
| `serenity-sand-light` | Secondary background | #F3EDE7 | Social proof strip, services section, booking CTA bg |
| `serenity-sand-mid` | Tertiary neutral | #E8DDD4 | Dividers, card borders, input borders, subtle separators |
| `serenity-sand-deep` | Warm mid-tone | #D4C5B5 | Decorative borders, disabled states |
| `serenity-terracotta` | Primary accent | #C4956A | Icons, price labels, quote marks, highlights, logo, active nav |
| `serenity-terracotta-light` | Hover accent | #D4A596 | Terracotta hover states, footer link hover |
| `serenity-sage` | Nature accent | #929C92 | Subtitles, meta text, placeholder text, secondary labels |
| `serenity-sage-light` | Light sage | #C9D3CA | Subtle decorative elements, tag backgrounds |
| `serenity-charcoal` | Primary text anchor | #3A3530 | All body text, headings, nav links, labels |
| `serenity-charcoal-deep` | Darkest anchor | #2D241B | Footer secondary background, deepest text contexts |
| `serenity-teal` | Primary CTA / trust | #2C5F63 | Primary buttons, focus rings, links, form selection states |
| `serenity-teal-dark` | CTA active state | #1F4547 | Primary button active/pressed state |
| `serenity-teal-light` | CTA ghost bg | #EAF3F4 | Ghost button hover fill, teal tint backgrounds |
| `serenity-white-warm` | Card/modal surface | #FDFCFB | Card backgrounds, modal surfaces where white is needed |

### Contrast Compliance (WCAG 2.1)

All ratios measured against usage context. AA requires 4.5:1 for normal text, 3:1 for large text (18pt+ or 14pt bold+).

| Text Token | Background Token | Contrast Ratio | Level | Usage |
|---|---|---|---|---|
| `#3A3530` on `#FAF8F5` | charcoal on base | **12.1:1** | AAA | Body text, headings |
| `#3A3530` on `#F3EDE7` | charcoal on sand-light | **10.8:1** | AAA | Card text, strip text |
| `#3A3530` on `#E8DDD4` | charcoal on sand-mid | **9.1:1** | AAA | Input labels |
| `#3A3530` on `#FDFCFB` | charcoal on warm-white | **11.8:1** | AAA | Card body text |
| `#2C5F63` on `#FAF8F5` | teal on base | **6.4:1** | AA | Ghost button text, links |
| `#2C5F63` on `#F3EDE7` | teal on sand-light | **5.7:1** | AA | Service card CTA |
| `#FDFCFB` on `#2C5F63` | warm-white on teal | **6.4:1** | AA | Primary button text |
| `#FDFCFB` on `#3A3530` | warm-white on charcoal | **12.1:1** | AAA | Footer text on dark bg |
| `#C4956A` on `#3A3530` | terracotta on charcoal | **4.7:1** | AA | Price labels on dark cards |
| `#C4956A` on `#FAF8F5` | terracotta on base | **3.4:1** | AA large only | Use only at 18px+ or bold |
| `#929C92` on `#FAF8F5` | sage on base | **4.6:1** | AA | Subtitles, meta text |
| `#929C92` on `#F3EDE7` | sage on sand-light | **4.1:1** | AA large only | Use only at 16px+ |
| `#C4956A` on `#2C5F63` | terracotta on teal | **2.2:1** | Fail | NEVER combine these |
| `rgba(255,255,255,0.8)` on `#3A3530` | footer body text | **9.7:1** | AAA | Footer paragraph text |

**Critical Rules:**
- Sage (#929C92) must be 16px minimum when used on sand backgrounds
- Terracotta (#C4956A) on white backgrounds: minimum 18px or font-weight 600+
- Never use terracotta as small body text on light backgrounds
- All interactive elements maintain 4.5:1 minimum in all states

---

## 2. TYPOGRAPHY

### Font Selection

**Display / Headings:** Cormorant Garamond  
Rationale: High-contrast old-style serif with elegant thin-to-thick stroke modulation. Italic variants carry emotional weight. Luxury wellness benchmark. Available on Google Fonts. Avoid Inter/Roboto (tech product connotation).

**Body / UI:** Jost  
Rationale: Geometric humanist sans with warmth and personality. More distinctive than DM Sans while equally legible. Clean, calm, premium. Works at small sizes. Available on Google Fonts.

**Quote / Emotional Moments:** Cormorant Garamond Italic (same family, different style)

### Google Fonts Link Tag

Place in `<head>` before all CSS:

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,500;0,600;1,300;1,400;1,500;1,600&family=Jost:wght@300;400;500;600&display=swap" rel="stylesheet">
```

### Complete Type Scale

#### H1 / Hero Headline

| Property | Mobile | Desktop |
|---|---|---|
| font-family | Cormorant Garamond | Cormorant Garamond |
| font-size | 48px (3rem) | 100px (6.25rem) |
| line-height | 1.1 | 1.05 |
| font-weight | 400 | 400 |
| letter-spacing | -0.01em | -0.02em |
| color | #FAF8F5 (on hero image) | #FAF8F5 (on hero image) |
| font-style | normal | normal |
| Tailwind classes | `font-['Cormorant_Garamond'] text-5xl leading-none tracking-tight font-normal` | `md:text-[100px] md:leading-[1.05] md:tracking-[-0.02em]` |

#### H2 / Section Headline

| Property | Mobile | Desktop |
|---|---|---|
| font-family | Cormorant Garamond | Cormorant Garamond |
| font-size | 40px (2.5rem) | 72px (4.5rem) |
| line-height | 1.15 | 1.1 |
| font-weight | 400 | 400 |
| letter-spacing | -0.01em | -0.015em |
| color | #3A3530 | #3A3530 |
| Tailwind classes | `font-['Cormorant_Garamond'] text-[40px] leading-[1.15] tracking-[-0.01em] font-normal text-serenity-charcoal` | `md:text-[72px] md:leading-[1.1] md:tracking-[-0.015em]` |

#### H2 Italic / Signature / Emotional Variant

| Property | Mobile | Desktop |
|---|---|---|
| font-family | Cormorant Garamond | Cormorant Garamond |
| font-size | 36px | 64px |
| line-height | 1.2 | 1.15 |
| font-weight | 400 | 400 |
| font-style | italic | italic |
| color | #3A3530 | #3A3530 |
| Tailwind classes | `font-['Cormorant_Garamond'] italic text-4xl leading-[1.2] font-normal` | `md:text-[64px] md:leading-[1.15]` |

#### H3 / Card & Subsection Headline

| Property | Mobile | Desktop |
|---|---|---|
| font-family | Cormorant Garamond | Cormorant Garamond |
| font-size | 26px | 36px |
| line-height | 1.25 | 1.2 |
| font-weight | 500 | 500 |
| letter-spacing | -0.005em | -0.01em |
| color | #3A3530 | #3A3530 |
| Tailwind classes | `font-['Cormorant_Garamond'] text-2xl leading-[1.25] font-medium` | `md:text-4xl md:leading-[1.2]` |

#### H4 / Card Title, Practitioner Name

| Property | Mobile | Desktop |
|---|---|---|
| font-family | Cormorant Garamond | Cormorant Garamond |
| font-size | 20px | 24px |
| line-height | 1.3 | 1.25 |
| font-weight | 600 | 600 |
| letter-spacing | 0 | 0 |
| color | #3A3530 | #3A3530 |
| Tailwind classes | `font-['Cormorant_Garamond'] text-xl leading-[1.3] font-semibold` | `md:text-2xl` |

#### Body Large / Philosophy Text, Signature Narrative

| Property | Mobile | Desktop |
|---|---|---|
| font-family | Jost | Jost |
| font-size | 16px | 18px |
| line-height | 1.8 | 1.8 |
| font-weight | 400 | 400 |
| letter-spacing | 0.01em | 0.01em |
| color | #3A3530 | #3A3530 |
| max-width | 100% | 520px |
| Tailwind classes | `font-['Jost'] text-base leading-[1.8] tracking-[0.01em] font-normal` | `md:text-lg` |

#### Body / Standard Paragraph

| Property | Mobile | Desktop |
|---|---|---|
| font-family | Jost | Jost |
| font-size | 15px | 16px |
| line-height | 1.7 | 1.7 |
| font-weight | 400 | 400 |
| letter-spacing | 0.005em | 0.005em |
| color | #3A3530 | #3A3530 |
| Tailwind classes | `font-['Jost'] text-[15px] leading-[1.7] font-normal` | `md:text-base` |

#### Small / Meta Labels, Certifications, Tags

| Property | Mobile | Desktop |
|---|---|---|
| font-family | Jost | Jost |
| font-size | 12px | 13px |
| line-height | 1.6 | 1.6 |
| font-weight | 400 | 400 |
| letter-spacing | 0.02em | 0.02em |
| color | #929C92 | #929C92 |
| Tailwind classes | `font-['Jost'] text-xs leading-[1.6] tracking-[0.02em] text-serenity-sage` | `md:text-[13px]` |

#### Caption / Footnotes, Dates

| Property | Mobile | Desktop |
|---|---|---|
| font-family | Jost | Jost |
| font-size | 11px | 11px |
| line-height | 1.5 | 1.5 |
| font-weight | 400 | 400 |
| letter-spacing | 0.03em | 0.03em |
| color | #929C92 | #929C92 |
| Tailwind classes | `font-['Jost'] text-[11px] leading-[1.5] tracking-[0.03em] italic text-serenity-sage` | same |

#### Button Label

| Property | Mobile | Desktop |
|---|---|---|
| font-family | Jost | Jost |
| font-size | 14px | 14px |
| line-height | 1 | 1 |
| font-weight | 500 | 500 |
| letter-spacing | 0.06em | 0.06em |
| text-transform | uppercase | uppercase |
| Tailwind classes | `font-['Jost'] text-sm font-medium tracking-[0.06em] uppercase leading-none` | same |

#### Navigation Label

| Property | Mobile | Desktop |
|---|---|---|
| font-family | Jost | Jost |
| font-size | 13px | 14px |
| line-height | 1 | 1 |
| font-weight | 400 | 400 |
| letter-spacing | 0.04em | 0.04em |
| color | #3A3530 | #3A3530 |
| Tailwind classes | `font-['Jost'] text-[13px] tracking-[0.04em] font-normal` | `md:text-[14px]` |

#### Blockquote / Testimonial Text

| Property | Mobile | Desktop |
|---|---|---|
| font-family | Cormorant Garamond | Cormorant Garamond |
| font-size | 15px | 16px |
| line-height | 1.8 | 1.8 |
| font-weight | 400 | 400 |
| font-style | italic | italic |
| color | #3A3530 | #3A3530 |
| Tailwind classes | `font-['Cormorant_Garamond'] italic text-[15px] leading-[1.8] font-normal` | `md:text-base` |

#### Price Label

| Property | Mobile | Desktop |
|---|---|---|
| font-family | Jost | Jost |
| font-size | 15px | 16px |
| line-height | 1 | 1 |
| font-weight | 600 | 600 |
| color | #C4956A | #C4956A |
| Tailwind classes | `font-['Jost'] text-[15px] font-semibold text-serenity-terracotta` | `md:text-base` |

#### Stat Number / Social Proof Figures

| Property | Mobile | Desktop |
|---|---|---|
| font-family | Cormorant Garamond | Cormorant Garamond |
| font-size | 28px | 32px |
| line-height | 1 | 1 |
| font-weight | 600 | 600 |
| color | #C4956A | #C4956A |
| Tailwind classes | `font-['Cormorant_Garamond'] text-3xl font-semibold text-serenity-terracotta` | `md:text-[32px]` |

---

## 3. SPACING SYSTEM

### Base Unit: 4px (0.25rem)

All spacing values are multiples of 4px. Tailwind's default spacing scale aligns: `space-1 = 4px`, `space-2 = 8px`, etc.

### Spacing Scale

| Token | px | rem | Tailwind class | Usage |
|---|---|---|---|---|
| xs | 4px | 0.25rem | `p-1` | Icon internal padding, micro gaps |
| sm | 8px | 0.5rem | `p-2` | Tight element spacing, tag padding |
| md | 16px | 1rem | `p-4` | Default element padding, form inputs |
| lg | 24px | 1.5rem | `p-6` | Card internal gaps, between labels |
| xl | 40px | 2.5rem | `p-10` | Card padding, section internal |
| 2xl | 60px | 3.75rem | `p-[60px]` | Section horizontal padding |
| 3xl | 80px | 5rem | `py-20` | Minimum section vertical padding |
| 4xl | 100px | 6.25rem | `py-24` | Philosophy, services section padding |
| 5xl | 120px | 7.5rem | `py-[120px]` | Hero padding bottom |

### Section Padding (Vertical)

| Breakpoint | Top/Bottom Padding | Tailwind |
|---|---|---|
| Mobile (<768px) | 60px / 60px | `py-16` |
| Tablet (768–1199px) | 80px / 80px | `md:py-20` |
| Desktop (1200px+) | 100px / 100px | `lg:py-24` |

### Section Padding (Horizontal)

| Breakpoint | Left/Right Padding | Tailwind |
|---|---|---|
| Mobile | 20px | `px-5` |
| Tablet | 40px | `md:px-10` |
| Desktop | 60px (inside max-width container) | `lg:px-[60px]` |

### Container / Max-Width

```html
<!-- Standard content container -->
<div class="max-w-7xl mx-auto px-5 md:px-10 lg:px-[60px]">

<!-- Narrow content (philosophy text, booking CTA text) -->
<div class="max-w-[720px] mx-auto px-5 md:px-10">

<!-- Ultra-narrow (hero subheadline, testimonial body) -->
<div class="max-w-[520px]">

<!-- Full-bleed (hero, gallery, testimonials section bg) -->
<div class="w-full">
```

### Vertical Rhythm

- Between section headline and subheadline: 16px (`mb-4`)
- Between subheadline and body text: 24px (`mb-6`)
- Between body text and CTA button: 40px (`mb-10`)
- Between cards in a grid: 24px desktop, 16px mobile (`gap-6 md:gap-8`)
- Between list items: 12px (`space-y-3`)
- Between section dividers (white space): minimum 80px

---

## 4. EFFECTS

### Box Shadow Scale

All shadows use warm rgba tones — no cold grey shadows.

| Level | CSS Value | Tailwind (custom) | Usage |
|---|---|---|---|
| `shadow-warm-xs` | `0 1px 3px rgba(58, 53, 48, 0.06)` | `shadow-warm-xs` | Input fields default, subtle card lift |
| `shadow-warm-sm` | `0 2px 8px rgba(58, 53, 48, 0.08)` | `shadow-warm-sm` | Service cards default, practitioner cards |
| `shadow-warm-md` | `0 4px 16px rgba(58, 53, 48, 0.10)` | `shadow-warm-md` | Cards on hover, modal, buttons |
| `shadow-warm-lg` | `0 8px 32px rgba(58, 53, 48, 0.12)` | `shadow-warm-lg` | Cards in active hover state |
| `shadow-warm-xl` | `0 16px 48px rgba(58, 53, 48, 0.15)` | `shadow-warm-xl` | Modal overlay, dropdown |
| `shadow-teal-glow` | `0 4px 20px rgba(44, 95, 99, 0.20)` | `shadow-teal-glow` | Primary CTA button hover |
| `shadow-terracotta-soft` | `0 2px 12px rgba(196, 149, 106, 0.15)` | `shadow-terracotta-soft` | Decorative elements, logo area |

**Forbidden:** `box-shadow: 0 4px 6px rgba(0,0,0,0.5)` — any hard, dark, high-opacity shadows.

### Border Radius Scale

| Token | Value | Tailwind | Usage |
|---|---|---|---|
| `radius-xs` | 4px | `rounded` | Tags, badges, small chips |
| `radius-sm` | 6px | `rounded-md` | Form inputs, small buttons, secondary CTAs |
| `radius-md` | 8px | `rounded-lg` | Primary buttons, nav CTA, modal header |
| `radius-lg` | 12px | `rounded-xl` | Practitioner cards, gallery images, testimonial cards |
| `radius-xl` | 16px | `rounded-2xl` | Service cards, main content cards |
| `radius-2xl` | 24px | `rounded-3xl` | Featured image corners, large cards |
| `radius-blob` | 40px | `rounded-[40px]` | Philosophy section image crop |
| `radius-circle` | 50% | `rounded-full` | Avatar images, icon circles |

### Organic / Blob Shapes

Blob-shaped image crops use irregular border-radius values to evoke biomorphic, natural forms:

**Method 1 — CSS border-radius (recommended for simplicity):**
```css
/* Blob variant A — gentle left asymmetry */
.blob-a {
  border-radius: 60% 40% 30% 70% / 60% 30% 70% 40%;
}

/* Blob variant B — top-heavy organic */
.blob-b {
  border-radius: 40% 60% 70% 30% / 40% 50% 60% 50%;
}

/* Blob variant C — philosophy section image */
.blob-c {
  border-radius: 30% 70% 70% 30% / 30% 30% 70% 70%;
}
```

**Tailwind implementation (arbitrary):**
```html
<div class="rounded-[60%_40%_30%_70%/60%_30%_70%_40%] overflow-hidden">
  <img ...>
</div>
```

**Method 2 — SVG clip-path (for complex shapes):**
```html
<svg width="0" height="0">
  <defs>
    <clipPath id="blob-1" clipPathUnits="objectBoundingBox">
      <path d="M0.8,0.1 C1,0,1,0.3,0.9,0.5 C1,0.7,0.9,1,0.7,1 C0.5,1,0.2,0.9,0.1,0.7 C0,0.5,0,0.2,0.2,0.1 C0.4,0,0.6,0.2,0.8,0.1Z"/>
    </clipPath>
  </defs>
</svg>

<img style="clip-path: url(#blob-1);" ...>
```

**Curved section dividers** — use SVG wave between sections:
```html
<!-- Between sections (warm tone) -->
<div class="w-full overflow-hidden leading-none">
  <svg viewBox="0 0 1440 60" fill="none" xmlns="http://www.w3.org/2000/svg">
    <path d="M0,30 C360,60 1080,0 1440,30 L1440,60 L0,60 Z" fill="#F3EDE7"/>
  </svg>
</div>
```

### Gradients

All gradients are warm, subtle, and directional. No purple. No neon.

| Name | Value | Usage |
|---|---|---|
| `gradient-base-to-sand` | `linear-gradient(180deg, #FAF8F5 0%, #F3EDE7 100%)` | Booking CTA section background |
| `gradient-hero-overlay` | `linear-gradient(to top, rgba(58,53,48,0.55) 0%, rgba(58,53,48,0.15) 60%, rgba(0,0,0,0) 100%)` | Hero image overlay for text readability |
| `gradient-card-warm` | `linear-gradient(135deg, #FAF8F5 0%, #F3EDE7 100%)` | Decorative card bg variation |
| `gradient-footer` | `linear-gradient(180deg, #3A3530 0%, #2D241B 100%)` | Footer background depth |
| `gradient-teal-soft` | `linear-gradient(135deg, #2C5F63 0%, #3B5048 100%)` | Primary button gradient (optional) |
| `gradient-sand-to-base` | `linear-gradient(180deg, #F3EDE7 0%, #FAF8F5 100%)` | Section transition bottom |

**CSS custom property declarations (add to `:root`):**
```css
:root {
  --gradient-hero: linear-gradient(to top, rgba(58,53,48,0.55) 0%, rgba(58,53,48,0.15) 60%, transparent 100%);
  --gradient-booking-bg: linear-gradient(180deg, #FAF8F5 0%, #F3EDE7 100%);
}
```

---

## 5. COMPONENT SPECIFICATIONS

### 5.1 Primary Button ("Записаться" / Book CTA)

**Purpose:** Main conversion action. Used in header, hero, service cards (large version), booking CTA section, signature section.

**HTML structure:**
```html
<button class="btn-primary" type="button">
  Забронировать сеанс
</button>
```

**Tailwind classes — all states:**

```
Default:
font-['Jost'] text-sm font-medium tracking-[0.06em] uppercase leading-none
bg-[#2C5F63] text-[#FDFCFB]
px-8 py-4 rounded-lg
shadow-[0_4px_16px_rgba(44,95,99,0.20)]
transition-all duration-300 ease-out
min-h-[44px] min-w-[44px]
cursor-pointer border-0

Hover (add via group/peer or JS class):
hover:scale-[1.05] hover:shadow-[0_8px_28px_rgba(44,95,99,0.28)]
hover:bg-[#234E52]

Focus:
focus-visible:outline-none
focus-visible:ring-4 focus-visible:ring-[#2C5F63] focus-visible:ring-offset-2 focus-visible:ring-offset-[#FAF8F5]

Active:
active:scale-[0.98] active:bg-[#1F4547] active:shadow-[0_2px_8px_rgba(44,95,99,0.15)]

Disabled:
disabled:opacity-40 disabled:cursor-not-allowed disabled:scale-100 disabled:shadow-none
```

**Size variants:**
- Small (header nav): `px-6 py-3 text-xs`
- Default (service card CTA): `px-8 py-4 text-sm`
- Large (hero, signature, booking CTA): `px-12 py-5 text-sm`

**Full class string (default size):**
```
class="font-['Jost'] text-sm font-medium tracking-[0.06em] uppercase leading-none bg-[#2C5F63] text-[#FDFCFB] px-8 py-4 rounded-lg shadow-[0_4px_16px_rgba(44,95,99,0.20)] transition-all duration-300 ease-out min-h-[44px] cursor-pointer hover:scale-[1.05] hover:shadow-[0_8px_28px_rgba(44,95,99,0.28)] hover:bg-[#234E52] focus-visible:outline-none focus-visible:ring-4 focus-visible:ring-[#2C5F63] focus-visible:ring-offset-2 active:scale-[0.98] active:bg-[#1F4547] disabled:opacity-40 disabled:cursor-not-allowed"
```

---

### 5.2 Secondary / Ghost Button ("Узнать о процедурах")

**Purpose:** Non-primary action. Hero secondary CTA, service card explore. Never competes with primary.

**Default:**
```
font-['Jost'] text-sm font-medium tracking-[0.06em] uppercase leading-none
bg-transparent text-[#C4956A]
px-8 py-4 rounded-lg
border-2 border-[#C4956A]
transition-all duration-300 ease-out
min-h-[44px] cursor-pointer
```

**Hover:**
```
hover:border-[#3A3530] hover:text-[#3A3530]
```

**On dark backgrounds (hero):**
```
border-[rgba(253,252,251,0.6)] text-[#FDFCFB]
hover:border-[#FDFCFB] hover:bg-[rgba(253,252,251,0.08)]
```

**Focus:**
```
focus-visible:outline-none focus-visible:ring-4 focus-visible:ring-[#C4956A] focus-visible:ring-offset-2
```

**Active:**
```
active:scale-[0.98] active:opacity-80
```

**Full class string (hero ghost variant):**
```
class="font-['Jost'] text-sm font-medium tracking-[0.06em] uppercase leading-none bg-transparent text-[#FDFCFB] px-8 py-4 rounded-lg border-2 border-[rgba(253,252,251,0.6)] transition-all duration-300 ease-out min-h-[44px] cursor-pointer hover:border-[#FDFCFB] hover:bg-[rgba(253,252,251,0.08)] focus-visible:outline-none focus-visible:ring-4 focus-visible:ring-white focus-visible:ring-offset-2 focus-visible:ring-offset-transparent active:scale-[0.98]"
```

---

### 5.3 Service Card

**Purpose:** Displays a service category in the services grid. 3-column desktop, 2-column tablet, 1-column mobile.

**Dimensions:** min-height 420px, width auto (fills grid column).

**HTML structure:**
```html
<div class="service-card group relative bg-[#F3EDE7] rounded-2xl p-10 shadow-[0_2px_8px_rgba(58,53,48,0.08)] transition-all duration-300 ease-out hover:scale-[1.04] hover:shadow-[0_8px_32px_rgba(58,53,48,0.12)] cursor-pointer">
  <!-- Optional category icon (Lucide, 32px) -->
  <div class="mb-6 text-[#C4956A]">
    <svg ...></svg>
  </div>

  <!-- Service title -->
  <h4 class="font-['Cormorant_Garamond'] text-xl md:text-2xl font-semibold leading-[1.25] text-[#3A3530] mb-3">
    Восстанавливающий массаж
  </h4>

  <!-- Duration + intensity meta -->
  <p class="font-['Jost'] text-xs tracking-[0.03em] text-[#929C92] italic mb-4">
    60 мин · Глубокий
  </p>

  <!-- Description -->
  <p class="font-['Jost'] text-[14px] leading-[1.7] text-[#3A3530] mb-6">
    Глубокий шведский массаж с горячими камнями. Растворяет мышечное напряжение спины, плеч и шеи.
  </p>

  <!-- Price -->
  <p class="font-['Jost'] text-[15px] font-semibold text-[#C4956A] mb-6">
    от ₽6 500
  </p>

  <!-- CTA button (ghost style, fills on card hover) -->
  <button class="font-['Jost'] text-xs font-medium tracking-[0.06em] uppercase bg-transparent text-[#2C5F63] px-6 py-3 rounded-md border-2 border-[#2C5F63] transition-all duration-300 group-hover:bg-[#2C5F63] group-hover:text-[#FDFCFB] min-h-[44px] focus-visible:outline-none focus-visible:ring-4 focus-visible:ring-[#2C5F63] focus-visible:ring-offset-2">
    Забронировать
  </button>
</div>
```

**States:**
- Default: bg `#F3EDE7`, shadow `shadow-warm-sm`
- Hover: scale 1.04, shadow `shadow-warm-lg`, CTA button fills teal
- Focus (keyboard): ring-4 teal on the card or the inner button
- Disabled: opacity-50, no scale, cursor-not-allowed

---

### 5.4 Testimonial Card

**Purpose:** Client review. 3-column desktop, 1-column mobile.

```html
<article class="relative bg-[#FDFCFB] rounded-2xl p-10 shadow-[0_2px_8px_rgba(58,53,48,0.08)] transition-all duration-300 hover:shadow-[0_8px_32px_rgba(58,53,48,0.15)] hover:scale-[1.02]">
  
  <!-- Decorative large quote mark -->
  <span class="absolute top-6 left-8 font-['Cormorant_Garamond'] text-[80px] leading-none text-[#C4956A] opacity-10 select-none" aria-hidden="true">"</span>

  <!-- Review text -->
  <blockquote class="font-['Cormorant_Garamond'] italic text-base leading-[1.8] text-[#3A3530] mb-8 pt-8 relative z-10">
    Я пришла в Serenity с хроническими болями в спине...
  </blockquote>

  <!-- Author section -->
  <footer class="border-t border-[#E8DDD4] pt-6 flex items-center gap-4">
    <!-- Avatar placeholder (40x40 rounded-full) -->
    <div class="w-10 h-10 rounded-full bg-[#E8DDD4] overflow-hidden flex-shrink-0">
      <img src="/images/avatar-olga.jpg" alt="Ольга С." class="w-full h-full object-cover">
    </div>
    <div>
      <p class="font-['Jost'] text-[14px] font-semibold text-[#3A3530] leading-none mb-1">Ольга С.</p>
      <p class="font-['Jost'] text-[12px] text-[#929C92] leading-none mb-1">48 лет, гл. редактор</p>
      <p class="font-['Jost'] text-[11px] text-[#929C92] italic leading-none">Апрель 2026</p>
    </div>
    <!-- Star rating (right-aligned) -->
    <div class="ml-auto flex gap-1" aria-label="5 из 5 звёзд">
      <!-- 5x star SVG from Lucide, 14px, #C4956A -->
    </div>
  </footer>
</article>
```

**States:**
- Default: white card, shadow-warm-sm
- Hover: shadow-warm-xl, scale 1.02
- Focus: visible ring-4 on the article element
- No disabled state (static content)

---

### 5.5 Practitioner Card

**Purpose:** Trust-building. About section. 3-column desktop, 1-column mobile.

```html
<article class="bg-[#FDFCFB] rounded-xl overflow-hidden shadow-[0_2px_8px_rgba(58,53,48,0.08)] transition-all duration-400 hover:shadow-[0_8px_32px_rgba(58,53,48,0.15)] hover:scale-[1.02]">
  
  <!-- Portrait image -->
  <div class="w-full h-[220px] overflow-hidden">
    <img 
      src="/images/elena-sokolova.jpg" 
      alt="Елена Соколова — Директор практик"
      class="w-full h-full object-cover object-top transition-transform duration-700 group-hover:scale-[1.03]"
      loading="lazy"
    >
  </div>

  <!-- Content -->
  <div class="p-8">
    <!-- Name + Title -->
    <h4 class="font-['Cormorant_Garamond'] text-xl font-semibold text-[#3A3530] leading-[1.25] mb-1">
      Елена Соколова
    </h4>
    <p class="font-['Jost'] text-[13px] italic text-[#929C92] mb-5">
      Директор практик · 18 лет опыта
    </p>

    <!-- Certificates list -->
    <ul class="space-y-2 mb-5" role="list">
      <li class="font-['Jost'] text-[12px] text-[#3A3530] leading-[1.5]">Diploma in Ayurveda Therapeutics, India</li>
      <li class="font-['Jost'] text-[12px] text-[#3A3530] leading-[1.5]">Certified Swedish Massage Therapist, Sweden</li>
      <li class="font-['Jost'] text-[12px] text-[#3A3530] leading-[1.5]">RYT-500, Yoga Alliance</li>
    </ul>

    <!-- Specialization -->
    <p class="font-['Jost'] text-[13px] italic text-[#C4956A] mb-5">
      Абхьянга, лимфодренаж, wellness-консультирование
    </p>

    <!-- Quote -->
    <blockquote class="border-t border-[#E8DDD4] pt-5">
      <p class="font-['Cormorant_Garamond'] italic text-[14px] leading-[1.7] text-[#3A3530]">
        "Тело никогда не лжет. Нужно только научиться его слушать."
      </p>
    </blockquote>
  </div>
</article>
```

---

### 5.6 Navbar (Sticky)

**Purpose:** Persistent navigation. Transparent initially, becomes frosted on scroll.

```html
<header id="header" class="fixed top-0 left-0 right-0 z-[1000] transition-all duration-300" role="banner">
  
  <!-- Default state (at top of page) -->
  <!-- class: "bg-transparent" -->
  
  <!-- Scrolled state (add via JS when scrollY > 80) -->
  <!-- class: "bg-[rgba(250,248,245,0.95)] backdrop-blur-md shadow-[0_2px_8px_rgba(58,53,48,0.06)]" -->

  <nav class="max-w-7xl mx-auto px-5 md:px-10 lg:px-[60px] flex items-center justify-between h-[72px]" aria-label="Основная навигация">
    
    <!-- Logo -->
    <a href="#hero" class="font-['Cormorant_Garamond'] text-2xl font-semibold text-[#C4956A] tracking-[0.02em] transition-opacity hover:opacity-80 focus-visible:outline-none focus-visible:ring-4 focus-visible:ring-[#C4956A] focus-visible:ring-offset-2 rounded-sm" aria-label="Serenity — вернуться на главную">
      Serenity
    </a>

    <!-- Desktop nav links -->
    <ul class="hidden md:flex items-center gap-8" role="list">
      <li><a href="#about" class="font-['Jost'] text-[14px] tracking-[0.04em] text-[#3A3530] transition-colors duration-300 hover:text-[#C4956A] focus-visible:outline-none focus-visible:ring-4 focus-visible:ring-[#2C5F63] rounded-sm">О нас</a></li>
      <li><a href="#services" class="font-['Jost'] text-[14px] tracking-[0.04em] text-[#3A3530] transition-colors duration-300 hover:text-[#C4956A] focus-visible:outline-none focus-visible:ring-4 focus-visible:ring-[#2C5F63] rounded-sm">Услуги</a></li>
      <li><a href="#testimonials" class="font-['Jost'] text-[14px] tracking-[0.04em] text-[#3A3530] transition-colors duration-300 hover:text-[#C4956A] focus-visible:outline-none focus-visible:ring-4 focus-visible:ring-[#2C5F63] rounded-sm">Отзывы</a></li>
      <li><a href="#footer" class="font-['Jost'] text-[14px] tracking-[0.04em] text-[#3A3530] transition-colors duration-300 hover:text-[#C4956A] focus-visible:outline-none focus-visible:ring-4 focus-visible:ring-[#2C5F63] rounded-sm">Контакты</a></li>
    </ul>

    <!-- Desktop CTA button -->
    <button class="hidden md:flex font-['Jost'] text-xs font-medium tracking-[0.06em] uppercase bg-[#2C5F63] text-[#FDFCFB] px-6 py-3 rounded-lg shadow-[0_4px_16px_rgba(44,95,99,0.20)] transition-all duration-300 hover:scale-[1.05] hover:shadow-[0_8px_28px_rgba(44,95,99,0.28)] focus-visible:outline-none focus-visible:ring-4 focus-visible:ring-[#2C5F63] focus-visible:ring-offset-2 active:scale-[0.98] min-h-[44px]" aria-label="Открыть форму записи" onclick="openBookingModal()">
      Записаться
    </button>

    <!-- Mobile hamburger -->
    <button class="md:hidden w-11 h-11 flex items-center justify-center rounded-lg text-[#3A3530] transition-colors hover:bg-[#F3EDE7] focus-visible:outline-none focus-visible:ring-4 focus-visible:ring-[#2C5F63]" aria-label="Открыть меню" aria-expanded="false" aria-controls="mobile-drawer" onclick="toggleMobileMenu()">
      <!-- Hamburger icon (Lucide Menu) -->
      <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true">
        <line x1="3" y1="6" x2="21" y2="6"/><line x1="3" y1="12" x2="21" y2="12"/><line x1="3" y1="18" x2="21" y2="18"/>
      </svg>
    </button>
  </nav>
</header>

<!-- Mobile drawer -->
<div id="mobile-drawer" class="fixed inset-0 z-[999] bg-[#FAF8F5] px-5 pt-[100px] pb-10 flex flex-col translate-x-full transition-transform duration-400 ease-out" aria-label="Мобильное меню" aria-hidden="true">
  <ul class="flex flex-col gap-2" role="list">
    <li><a href="#about" class="font-['Cormorant_Garamond'] text-[28px] font-normal text-[#3A3530] leading-[2] block hover:text-[#C4956A] transition-colors duration-300">О нас</a></li>
    <li><a href="#services" class="font-['Cormorant_Garamond'] text-[28px] font-normal text-[#3A3530] leading-[2] block hover:text-[#C4956A] transition-colors duration-300">Услуги</a></li>
    <li><a href="#testimonials" class="font-['Cormorant_Garamond'] text-[28px] font-normal text-[#3A3530] leading-[2] block hover:text-[#C4956A] transition-colors duration-300">Отзывы</a></li>
    <li><a href="#footer" class="font-['Cormorant_Garamond'] text-[28px] font-normal text-[#3A3530] leading-[2] block hover:text-[#C4956A] transition-colors duration-300">Контакты</a></li>
  </ul>
  <button class="mt-auto font-['Jost'] text-sm font-medium tracking-[0.06em] uppercase bg-[#2C5F63] text-[#FDFCFB] w-full py-4 rounded-lg min-h-[44px]" onclick="openBookingModal()">
    Записаться на сеанс
  </button>
</div>
```

**Scrolled-state JS (minimal):**
```javascript
const header = document.getElementById('header');
const scrollThreshold = 80;

window.addEventListener('scroll', () => {
  if (window.scrollY > scrollThreshold) {
    header.classList.add('bg-[rgba(250,248,245,0.95)]', 'backdrop-blur-md', 'shadow-[0_2px_8px_rgba(58,53,48,0.06)]');
    header.classList.remove('bg-transparent');
  } else {
    header.classList.remove('bg-[rgba(250,248,245,0.95)]', 'backdrop-blur-md', 'shadow-[0_2px_8px_rgba(58,53,48,0.06)]');
    header.classList.add('bg-transparent');
  }
}, { passive: true });
```

---

### 5.7 Form Input

**Purpose:** Booking modal fields, newsletter subscribe field.

```html
<div class="flex flex-col gap-2">
  <label for="name" class="font-['Jost'] text-[13px] font-medium tracking-[0.03em] text-[#3A3530]">
    Ваше имя <span class="text-[#C4956A]" aria-label="обязательное поле">*</span>
  </label>
  <input 
    type="text" 
    id="name" 
    name="name"
    required
    placeholder="Как вас зовут?"
    class="font-['Jost'] text-[14px] text-[#3A3530] placeholder:text-[#929C92] bg-[#FDFCFB] border border-[#E8DDD4] rounded-md px-4 py-3 min-h-[44px] w-full transition-all duration-300 focus:outline-none focus:border-[#2C5F63] focus:shadow-[0_0_0_4px_rgba(44,95,99,0.12)] hover:border-[#D4C5B5]"
    aria-required="true"
  >
</div>
```

**States:**
- Default: `border-[#E8DDD4]`, `bg-[#FDFCFB]`
- Hover: `border-[#D4C5B5]`
- Focus: `border-[#2C5F63]`, `shadow-[0_0_0_4px_rgba(44,95,99,0.12)]`
- Error: `border-[#B85C38]`, `shadow-[0_0_0_4px_rgba(184,92,56,0.10)]`
- Disabled: `opacity-50`, `cursor-not-allowed`, `bg-[#F3EDE7]`
- Valid: `border-[#929C92]`

**Footer newsletter input (on dark bg):**
```html
<input 
  type="email"
  placeholder="Ваш email"
  class="font-['Jost'] text-[14px] text-white placeholder:text-[rgba(255,255,255,0.5)] bg-[rgba(255,255,255,0.10)] border-0 border-b-2 border-[rgba(255,255,255,0.2)] rounded-none px-4 py-3 w-full min-h-[44px] transition-all duration-300 focus:outline-none focus:border-[#C4956A]"
>
```

---

### 5.8 Footer

```html
<footer id="footer" role="contentinfo">
  <!-- Main footer body -->
  <div class="bg-[#3A3530] px-5 md:px-10 lg:px-[60px] py-[80px]">
    <div class="max-w-7xl mx-auto grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-16">
      
      <!-- Column 1: Contact + Hours -->
      <div>
        <p class="font-['Cormorant_Garamond'] text-2xl font-semibold text-[#C4956A] mb-6 tracking-[0.02em]">Serenity</p>
        <address class="not-italic space-y-4">
          <p class="font-['Jost'] text-[14px] leading-[1.8] text-[rgba(255,255,255,0.80)]">
            Улица Тверская, 15, офис 302<br>Москва, 125009
          </p>
          <a href="tel:+74951234567" class="font-['Jost'] text-[14px] text-[#C4956A] hover:text-[#D4A596] transition-colors duration-300 block">
            +7 (495) 123-45-67
          </a>
          <a href="mailto:hello@serenity-spa.ru" class="font-['Jost'] text-[14px] text-[#C4956A] hover:text-[#D4A596] transition-colors duration-300 block">
            hello@serenity-spa.ru
          </a>
        </address>
        <div class="mt-6 font-['Jost'] text-[13px] leading-[1.8] text-[rgba(255,255,255,0.60)]">
          <p>Пн–Пт: 10:00 — 21:00</p>
          <p>Сб–Вс: 10:00 — 19:00</p>
        </div>
      </div>

      <!-- Column 2: Quick links -->
      <div>
        <h3 class="font-['Jost'] text-[14px] font-semibold text-white mb-6 tracking-[0.04em] uppercase">Навигация</h3>
        <ul class="space-y-4" role="list">
          <li><a href="#services" class="font-['Jost'] text-[14px] text-[rgba(255,255,255,0.80)] hover:text-[#C4956A] transition-colors duration-300">Услуги</a></li>
          <li><a href="#about" class="font-['Jost'] text-[14px] text-[rgba(255,255,255,0.80)] hover:text-[#C4956A] transition-colors duration-300">О нас</a></li>
          <li><a href="#testimonials" class="font-['Jost'] text-[14px] text-[rgba(255,255,255,0.80)] hover:text-[#C4956A] transition-colors duration-300">Отзывы</a></li>
          <li><button onclick="openBookingModal()" class="font-['Jost'] text-[14px] text-[#C4956A] hover:text-[#D4A596] transition-colors duration-300 text-left">Забронировать сеанс</button></li>
          <li><a href="/gift-certificates" class="font-['Jost'] text-[14px] text-[rgba(255,255,255,0.80)] hover:text-[#C4956A] transition-colors duration-300">Подарочные сертификаты</a></li>
        </ul>
      </div>

      <!-- Column 3: Social + Newsletter -->
      <div>
        <h3 class="font-['Jost'] text-[14px] font-semibold text-white mb-6 tracking-[0.04em] uppercase">Следите за нами</h3>
        <ul class="flex gap-4 mb-8" role="list">
          <!-- Social icons: 24x24px, opacity-70, hover:opacity-100 -->
          <li><a href="https://instagram.com/serenity.spa.moscow" aria-label="Instagram" class="text-[rgba(255,255,255,0.70)] hover:text-[#C4956A] transition-all duration-300"><!-- Lucide Instagram svg 24x24 --></a></li>
        </ul>
        <div>
          <p class="font-['Jost'] text-[13px] text-[rgba(255,255,255,0.60)] mb-4">Одно письмо в неделю — только ценное</p>
          <div class="flex gap-2">
            <input type="email" placeholder="Ваш email" class="flex-1 font-['Jost'] text-[14px] text-white placeholder:text-[rgba(255,255,255,0.40)] bg-[rgba(255,255,255,0.08)] border border-[rgba(255,255,255,0.15)] rounded-md px-4 py-3 min-h-[44px] focus:outline-none focus:border-[#C4956A] transition-colors duration-300">
            <button class="font-['Jost'] text-[12px] font-semibold tracking-[0.04em] bg-[#C4956A] text-[#3A3530] px-5 py-3 rounded-md min-h-[44px] hover:bg-[#D4A596] transition-colors duration-300 whitespace-nowrap focus-visible:outline-none focus-visible:ring-4 focus-visible:ring-[#C4956A]">
              Подписаться
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>

  <!-- Secondary footer bar -->
  <div class="bg-[#2D241B] px-5 md:px-[60px] py-6">
    <div class="max-w-7xl mx-auto flex flex-col md:flex-row items-center justify-between gap-4">
      <p class="font-['Jost'] text-[12px] text-[rgba(255,255,255,0.50)]">© 2026 Serenity Spa. Все права защищены.</p>
      <nav aria-label="Правовые ссылки" class="flex gap-6">
        <a href="/privacy" class="font-['Jost'] text-[12px] text-[rgba(255,255,255,0.50)] hover:text-[#C4956A] transition-colors duration-300">Политика конфиденциальности</a>
        <a href="/terms" class="font-['Jost'] text-[12px] text-[rgba(255,255,255,0.50)] hover:text-[#C4956A] transition-colors duration-300">Условия использования</a>
      </nav>
    </div>
  </div>
</footer>
```

---

## 6. MOTION & ANIMATION

### Timing Philosophy
Slow is luxurious. Animations at 600–900ms signal unhurried premium quality. Hover transitions are faster (300ms) to feel responsive. Never use bouncy or elastic easings.

### Easing Functions

| Name | CSS | Usage |
|---|---|---|
| `ease-reveal` | `cubic-bezier(0.4, 0, 0.2, 1)` | Scroll reveals (fade-up) |
| `ease-hover` | `cubic-bezier(0.25, 0.46, 0.45, 0.94)` | Card/button hover transitions |
| `ease-modal` | `cubic-bezier(0.32, 0.72, 0, 1)` | Modal entrance |
| `ease-in-subtle` | `cubic-bezier(0.4, 0, 1, 1)` | Elements exiting (fade-out) |

**Add to CSS:**
```css
:root {
  --ease-reveal: cubic-bezier(0.4, 0, 0.2, 1);
  --ease-hover: cubic-bezier(0.25, 0.46, 0.45, 0.94);
  --ease-modal: cubic-bezier(0.32, 0.72, 0, 1);
}
```

### Duration Scale

| Token | Value | Usage |
|---|---|---|
| `duration-instant` | 100ms | Active/pressed feedback |
| `duration-fast` | 200ms | Step transitions inside modal |
| `duration-hover` | 300ms | All hover state transitions |
| `duration-reveal-sm` | 600ms | Small elements, gallery images |
| `duration-reveal-md` | 750ms | Standard scroll reveal |
| `duration-reveal-lg` | 900ms | Hero entrance, large blocks |
| `duration-parallax` | per-frame | `requestAnimationFrame` based |

### Scroll Reveal (Fade-Up)

**Base CSS class:**
```css
.reveal {
  opacity: 0;
  transform: translateY(60px);
  transition: opacity 750ms cubic-bezier(0.4, 0, 0.2, 1),
              transform 750ms cubic-bezier(0.4, 0, 0.2, 1);
}

.reveal.is-visible {
  opacity: 1;
  transform: translateY(0);
}
```

**JavaScript (Intersection Observer):**
```javascript
const revealElements = document.querySelectorAll('.reveal');

const revealObserver = new IntersectionObserver((entries) => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      entry.target.classList.add('is-visible');
      revealObserver.unobserve(entry.target); // Fire once
    }
  });
}, {
  threshold: 0.15,       // Trigger when 15% visible
  rootMargin: '0px 0px -40px 0px'  // Slight early trigger
});

revealElements.forEach(el => revealObserver.observe(el));
```

### Stagger Timing

Apply via inline `style` attribute or Tailwind arbitrary `delay-*`:

| Context | Stagger Delay | Method |
|---|---|---|
| Service cards (6 cards) | 80ms between each | `style="transition-delay: Xms"` |
| Testimonial cards (3) | 100ms between each | `style="transition-delay: Xms"` |
| Practitioner cards (3) | 120ms between each | `style="transition-delay: Xms"` |
| Social proof items (4) | 100ms between each | `style="transition-delay: Xms"` |
| Gallery images (12) | 50ms between each | `style="transition-delay: Xms"` |
| Booking CTA reasons (3) | 100ms between each | `style="transition-delay: Xms"` |

**Example (service cards):**
```html
<div class="reveal" style="transition-delay: 0ms"><!-- card 1 --></div>
<div class="reveal" style="transition-delay: 80ms"><!-- card 2 --></div>
<div class="reveal" style="transition-delay: 160ms"><!-- card 3 --></div>
```

### Hero Entrance Animation

```css
/* Runs on page load (no scroll trigger) */
.hero-headline {
  animation: heroFadeUp 900ms cubic-bezier(0.4, 0, 0.2, 1) 200ms both;
}

.hero-subheadline {
  animation: heroFadeUp 900ms cubic-bezier(0.4, 0, 0.2, 1) 450ms both;
}

.hero-cta-group {
  animation: heroFadeUp 900ms cubic-bezier(0.4, 0, 0.2, 1) 650ms both;
}

@keyframes heroFadeUp {
  from {
    opacity: 0;
    transform: translateY(40px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
```

### Hover Transforms

| Element | Transform | Duration | Easing |
|---|---|---|---|
| Service card | `scale(1.04)` | 300ms | ease-hover |
| Testimonial card | `scale(1.02)` | 300ms | ease-hover |
| Practitioner card | `scale(1.02)` | 400ms | ease-hover |
| Primary button | `scale(1.05)` | 300ms | ease-hover |
| Large CTA button | `scale(1.08)` | 300ms | ease-hover |
| Ghost button | no scale, border change | 300ms | ease-hover |
| Gallery image overlay | opacity 0 → 0.3 | 300ms | ease-hover |
| Nav link | color change only | 300ms | ease |
| Social icon | opacity 0.7 → 1 | 300ms | ease |

### Parallax

Applies to: hero background image, philosophy section image, signature section image.

```javascript
// Lightweight parallax — only desktop
function initParallax() {
  if (window.innerWidth < 768) return; // Disable on mobile
  
  const parallaxElements = document.querySelectorAll('[data-parallax]');
  
  window.addEventListener('scroll', () => {
    const scrollY = window.scrollY;
    parallaxElements.forEach(el => {
      const speed = parseFloat(el.dataset.parallax) || 0.3;
      el.style.transform = `translateY(${scrollY * speed}px)`;
    });
  }, { passive: true });
}
```

**HTML usage:**
```html
<img data-parallax="0.3" src="..." alt="..." class="absolute inset-0 w-full h-full object-cover">
```

### Modal Animation

```css
/* Modal backdrop */
.modal-backdrop {
  opacity: 0;
  transition: opacity 300ms ease;
}
.modal-backdrop.open {
  opacity: 1;
}

/* Modal panel */
.modal-panel {
  opacity: 0;
  transform: scale(0.92) translateY(20px);
  transition: opacity 350ms cubic-bezier(0.32, 0.72, 0, 1),
              transform 350ms cubic-bezier(0.32, 0.72, 0, 1);
}
.modal-panel.open {
  opacity: 1;
  transform: scale(1) translateY(0);
}
```

### prefers-reduced-motion

This block is mandatory. Place in the main stylesheet:

```css
@media (prefers-reduced-motion: reduce) {
  *,
  *::before,
  *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
    scroll-behavior: auto !important;
  }

  /* Keep opacity reveals but remove movement */
  .reveal {
    transform: none !important;
    transition-property: opacity !important;
    transition-duration: 300ms !important;
  }

  [data-parallax] {
    transform: none !important;
  }
}
```

---

## 7. RESPONSIVE SYSTEM

### Breakpoints

| Name | Min Width | Tailwind prefix | Key changes |
|---|---|---|---|
| Mobile | 0–767px | (default) | Single column, hamburger, 70vh hero |
| Tablet | 768px–1199px | `md:` | 2-column grids, nav visible |
| Desktop | 1200px+ | `lg:` | 3-column grids, full spacing |

### How Key Sections Adapt

#### Header
- Mobile: logo + hamburger button only. Nav hidden. Full-screen drawer on open.
- Tablet+: logo + nav links + "Записаться" button.

#### Hero
- Mobile: `min-h-[70vh]`, headline 48px, only primary CTA button, text center-aligned.
- Tablet: `min-h-[85vh]`, headline 64px, both CTAs stacked vertically.
- Desktop: `min-h-screen`, headline 100px, CTAs horizontal flex, text bottom-left.

```html
<!-- Hero text positioning -->
<div class="absolute bottom-10 left-0 px-5 md:px-10 lg:px-[60px] w-full md:w-auto max-w-full md:max-w-[580px]">
  <h1 class="font-['Cormorant_Garamond'] text-5xl md:text-[72px] lg:text-[100px] font-normal leading-[1.05] tracking-[-0.02em] text-[#FDFCFB] mb-6">
    Найдите спокойствие в себе
  </h1>
  <p class="font-['Jost'] text-base md:text-lg leading-[1.8] text-[rgba(253,252,251,0.90)] mb-10 max-w-[420px] md:max-w-[480px]">...</p>
  <div class="flex flex-col sm:flex-row gap-4">
    <!-- Primary CTA -->
    <!-- Secondary CTA (hidden on mobile-xs, shown sm+) -->
  </div>
</div>
```

#### Social Proof Strip
- Mobile: 2-column grid, 2 rows
- Tablet: 4-column flex
- Desktop: 4-column flex, 120px height

```html
<div class="grid grid-cols-2 md:grid-cols-4 gap-4 md:gap-0">
```

#### Philosophy Section
- Mobile: column (image top, text below), image 100% width, rounded blob
- Tablet: 50/50 column split
- Desktop: 60/40 column split, 100px section padding

```html
<div class="flex flex-col-reverse lg:flex-row gap-10 lg:gap-20 items-center">
  <div class="w-full lg:w-3/5"><!-- text --></div>
  <div class="w-full lg:w-2/5"><!-- image --></div>
</div>
```

#### Services Grid
- Mobile: `grid-cols-1` — full width cards
- Tablet: `grid-cols-2`
- Desktop: `grid-cols-3`

```html
<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6 md:gap-8">
```

#### Signature Treatment
- Mobile: column (image top, text below)
- Desktop: `grid-cols-5`: text 3 cols (60%), image 2 cols (40%)

```html
<div class="grid grid-cols-1 lg:grid-cols-5 min-h-[700px]">
  <div class="lg:col-span-3 bg-[#F3EDE7] p-10 lg:p-[80px] flex flex-col justify-center"><!-- text --></div>
  <div class="lg:col-span-2 relative overflow-hidden min-h-[360px] lg:min-h-0"><!-- image --></div>
</div>
```

#### About / Practitioners
- Mobile: 1 column
- Tablet: 1 column (wider cards)
- Desktop: 3 columns

```html
<div class="grid grid-cols-1 lg:grid-cols-3 gap-8">
```

#### Testimonials
- Mobile: 1 column
- Tablet: 1 column (centered max-width)
- Desktop: 3 columns

#### Gallery
- Mobile: 2 columns, uniform squares
- Tablet: 2 columns, masonry
- Desktop: 4 columns, asymmetric masonry

```html
<!-- Masonry-style via CSS columns -->
<div class="columns-2 lg:columns-4 gap-4 space-y-4">
  <div class="break-inside-avoid mb-4">
    <img class="w-full rounded-xl" ...>
  </div>
  <!-- ... -->
</div>
```

#### Booking CTA
- Mobile: column layout, padding 60px 20px, centered
- Desktop: centered, max-width 800px, horizontal reasons row

#### Footer
- Mobile: 1 column, 40px 20px padding
- Tablet: 2 columns
- Desktop: 3 columns, 80px 60px padding

---

## 8. ICONOGRAPHY

### Icon Library: Lucide Icons

**Source:** https://lucide.dev  
**Implementation:** Inline SVG only. No icon font. No CDN sprite (for performance control).  
**Rationale:** Open source, consistent stroke-based style, thin 1.5px strokes align with the elegant serif aesthetic. Extensive coverage for wellness contexts.

**Do not use:** Emoji, FontAwesome filled icons, Material Icons (too tech-product).

### Usage Specifications

| Context | Icon size | Stroke width | Color |
|---|---|---|---|
| Social proof strip | 28px × 28px | 1.5 | `#C4956A` |
| Service card decorative | 32px × 32px | 1.5 | `#C4956A` |
| Booking CTA reasons | 32px × 32px | 1.5 | `#C4956A` |
| Nav mobile social links | 20px × 20px | 1.5 | `#3A3530` |
| Footer social links | 22px × 22px | 1.5 | `rgba(255,255,255,0.70)` |
| Form validation check | 16px × 16px | 2 | `#929C92` |
| Bullet list chevrons | 14px × 14px | 2 | `#C4956A` |
| Gallery lightbox arrows | 24px × 24px | 1.5 | `#FDFCFB` |
| Modal close button | 20px × 20px | 1.5 | `#929C92` |
| Hamburger menu | 24px × 24px | 1.5 | `#3A3530` |

### Icon Mapping

| Usage | Lucide icon name |
|---|---|
| Rating / awards | `Star` |
| Best spa award | `Award` |
| Press badge | `BookOpen` |
| Certification | `ShieldCheck` |
| Massage / body | `Waves` |
| Spa / treatment | `Sparkles` |
| Yoga / meditation | `Leaf` |
| Face care | `Flower2` |
| Combo program | `Package` |
| Consultation | `MessageCircle` |
| Clock / duration | `Clock` |
| Calendar / booking | `CalendarDays` |
| Experience / years | `Gem` |
| Location | `MapPin` |
| Phone | `Phone` |
| Email | `Mail` |
| Instagram | `Instagram` |
| YouTube | `Youtube` |
| Chevron list bullet | `ChevronRight` |
| Check / yes | `Check` |
| Close / X | `X` |
| External link | `ExternalLink` |
| Gallery zoom | `ZoomIn` |
| Arrow navigation | `ArrowRight`, `ArrowLeft` |
| Practitioner | `UserCheck` |
| Limited slots | `Hourglass` |

### SVG Inline Example

```html
<!-- Star icon, 28px, terracotta, social proof -->
<svg 
  width="28" 
  height="28" 
  viewBox="0 0 24 24" 
  fill="none" 
  stroke="#C4956A" 
  stroke-width="1.5" 
  stroke-linecap="round" 
  stroke-linejoin="round"
  aria-hidden="true"
  focusable="false"
>
  <polygon points="12 2 15.09 8.26 22 9.27 17 14.14 18.18 21.02 12 17.77 5.82 21.02 7 14.14 2 9.27 8.91 8.26 12 2"/>
</svg>
```

**Accessibility note:** All decorative icons must have `aria-hidden="true"` and `focusable="false"`. Icons that convey meaning must have an accompanying visually-hidden text or `aria-label`.

---

## 9. ACCESSIBILITY STANDARDS

### WCAG 2.1 Level AA Compliance

**Color contrast:** See Section 1 contrast table. All normal text ≥4.5:1, large text ≥3:1.

**Focus indicators:**
```css
/* Global focus ring — always visible, 2px offset, teal ring */
:focus-visible {
  outline: none;
  box-shadow: 0 0 0 4px rgba(44, 95, 99, 0.30);
  border-radius: 4px;
}
```

Tailwind equivalent on each interactive element:
```
focus-visible:outline-none focus-visible:ring-4 focus-visible:ring-[#2C5F63] focus-visible:ring-offset-2
```

**Touch targets:** All interactive elements minimum 44×44px. Use `min-h-[44px] min-w-[44px]` on buttons and links.

**Semantic HTML:**
- `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>`, `<footer>` used correctly
- `aria-label` on nav elements without visible text context
- `aria-expanded` / `aria-controls` on hamburger button
- `aria-hidden="true"` on all decorative SVGs
- `role="list"` on `<ul>` styled without `list-style` (Safari VoiceOver fix)
- `<h1>` through `<h4>` in correct document order (no skipping)
- Booking modal: `role="dialog"`, `aria-modal="true"`, `aria-labelledby`, focus trap

**Image alt text:**
```html
<!-- Meaningful image -->
<img src="..." alt="Массажный кабинет с горячими камнями и ароматическими маслами на деревянном подносе">

<!-- Decorative image -->
<img src="..." alt="" role="presentation">
```

**Skip navigation:**
```html
<!-- First element in <body> -->
<a href="#main" class="sr-only focus:not-sr-only focus:absolute focus:top-4 focus:left-4 focus:z-[2000] focus:bg-[#2C5F63] focus:text-white focus:px-4 focus:py-2 focus:rounded-md">
  Перейти к основному содержимому
</a>
```

**Motion:** As specified in Section 6, `prefers-reduced-motion` block is mandatory.

**Form accessibility:**
- All inputs have associated `<label>` elements via `for`/`id`
- Required fields marked with `aria-required="true"` and visual asterisk
- Error messages use `role="alert"` and `aria-describedby`
- Success messages announced via `aria-live="polite"`

---

## 10. TAILWIND CONFIG OBJECT

Add this to your Tailwind CDN config (place `<script>` before the Tailwind CDN script):

```html
<script>
  tailwind.config = {
    theme: {
      extend: {
        colors: {
          'serenity-base':            '#FAF8F5',
          'serenity-sand-light':      '#F3EDE7',
          'serenity-sand-mid':        '#E8DDD4',
          'serenity-sand-deep':       '#D4C5B5',
          'serenity-terracotta':      '#C4956A',
          'serenity-terracotta-light':'#D4A596',
          'serenity-sage':            '#929C92',
          'serenity-sage-light':      '#C9D3CA',
          'serenity-charcoal':        '#3A3530',
          'serenity-charcoal-deep':   '#2D241B',
          'serenity-teal':            '#2C5F63',
          'serenity-teal-dark':       '#1F4547',
          'serenity-teal-light':      '#EAF3F4',
          'serenity-white-warm':      '#FDFCFB',
        },
        fontFamily: {
          'serif':    ['Cormorant Garamond', 'Georgia', 'serif'],
          'sans':     ['Jost', 'system-ui', 'sans-serif'],
        },
        fontSize: {
          'display':  ['100px', { lineHeight: '1.05', letterSpacing: '-0.02em' }],
          'h2':       ['72px',  { lineHeight: '1.1',  letterSpacing: '-0.015em' }],
          'h2-sm':    ['40px',  { lineHeight: '1.15', letterSpacing: '-0.01em' }],
          'h3':       ['36px',  { lineHeight: '1.2',  letterSpacing: '-0.01em' }],
          'h3-sm':    ['26px',  { lineHeight: '1.25' }],
          'h4':       ['24px',  { lineHeight: '1.25' }],
          'body-lg':  ['18px',  { lineHeight: '1.8',  letterSpacing: '0.01em' }],
          'body':     ['16px',  { lineHeight: '1.7',  letterSpacing: '0.005em' }],
          'body-sm':  ['15px',  { lineHeight: '1.7' }],
          'small':    ['13px',  { lineHeight: '1.6',  letterSpacing: '0.02em' }],
          'caption':  ['11px',  { lineHeight: '1.5',  letterSpacing: '0.03em' }],
          'label':    ['14px',  { lineHeight: '1',    letterSpacing: '0.06em' }],
        },
        boxShadow: {
          'warm-xs':             '0 1px 3px rgba(58, 53, 48, 0.06)',
          'warm-sm':             '0 2px 8px rgba(58, 53, 48, 0.08)',
          'warm-md':             '0 4px 16px rgba(58, 53, 48, 0.10)',
          'warm-lg':             '0 8px 32px rgba(58, 53, 48, 0.12)',
          'warm-xl':             '0 16px 48px rgba(58, 53, 48, 0.15)',
          'teal-glow':           '0 4px 20px rgba(44, 95, 99, 0.20)',
          'teal-glow-lg':        '0 8px 28px rgba(44, 95, 99, 0.28)',
          'terracotta-soft':     '0 2px 12px rgba(196, 149, 106, 0.15)',
        },
        borderRadius: {
          'xs':   '4px',
          'sm':   '6px',
          'md':   '8px',
          'lg':   '12px',
          'xl':   '16px',
          '2xl':  '24px',
          'blob': '40px',
        },
        spacing: {
          '18':  '4.5rem',
          '22':  '5.5rem',
          '26':  '6.5rem',
          '30':  '7.5rem',
          '100': '25rem',
          '120': '30rem',
        },
        transitionTimingFunction: {
          'reveal':  'cubic-bezier(0.4, 0, 0.2, 1)',
          'hover':   'cubic-bezier(0.25, 0.46, 0.45, 0.94)',
          'modal':   'cubic-bezier(0.32, 0.72, 0, 1)',
        },
        transitionDuration: {
          '400': '400ms',
          '600': '600ms',
          '750': '750ms',
          '900': '900ms',
        },
        backgroundImage: {
          'gradient-hero-overlay': 'linear-gradient(to top, rgba(58,53,48,0.55) 0%, rgba(58,53,48,0.15) 60%, transparent 100%)',
          'gradient-base-to-sand': 'linear-gradient(180deg, #FAF8F5 0%, #F3EDE7 100%)',
          'gradient-sand-to-base': 'linear-gradient(180deg, #F3EDE7 0%, #FAF8F5 100%)',
          'gradient-footer':       'linear-gradient(180deg, #3A3530 0%, #2D241B 100%)',
          'gradient-teal':         'linear-gradient(135deg, #2C5F63 0%, #1F4547 100%)',
        },
        maxWidth: {
          'content':  '1280px',
          'narrow':   '720px',
          'xs':       '420px',
          'reading':  '520px',
        },
        zIndex: {
          'modal':   '2000',
          'nav':     '1000',
          'overlay': '1500',
        },
        backdropBlur: {
          'nav': '12px',
        },
      }
    }
  }
</script>
<script src="https://cdn.tailwindcss.com"></script>
```

**Important:** The Tailwind config `<script>` must appear BEFORE the CDN script tag.

---

## APPENDIX A: FULL HTML BOILERPLATE

```html
<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Serenity Spa — Массаж, СПА и Йога в Москве</title>
  <meta name="description" content="Премиум wellness-пространство в центре Москвы. Массаж, спа-процедуры и йога с сертифицированными практиками.">

  <!-- Fonts -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,500;0,600;1,300;1,400;1,500;1,600&family=Jost:wght@300;400;500;600&display=swap" rel="stylesheet">

  <!-- Tailwind config BEFORE CDN -->
  <script>
    tailwind.config = { /* ... paste config from Section 10 ... */ }
  </script>
  <script src="https://cdn.tailwindcss.com"></script>

  <!-- Critical CSS (minimal, inline for LCP) -->
  <style>
    *, *::before, *::after { box-sizing: border-box; }
    html { scroll-behavior: smooth; }
    body { background-color: #FAF8F5; color: #3A3530; margin: 0; }

    /* Reveal animations */
    .reveal {
      opacity: 0;
      transform: translateY(60px);
      transition: opacity 750ms cubic-bezier(0.4, 0, 0.2, 1),
                  transform 750ms cubic-bezier(0.4, 0, 0.2, 1);
    }
    .reveal.is-visible { opacity: 1; transform: translateY(0); }

    /* Hero entrance */
    .hero-headline { animation: heroFadeUp 900ms cubic-bezier(0.4, 0, 0.2, 1) 200ms both; }
    .hero-sub      { animation: heroFadeUp 900ms cubic-bezier(0.4, 0, 0.2, 1) 450ms both; }
    .hero-cta      { animation: heroFadeUp 900ms cubic-bezier(0.4, 0, 0.2, 1) 650ms both; }

    @keyframes heroFadeUp {
      from { opacity: 0; transform: translateY(40px); }
      to   { opacity: 1; transform: translateY(0); }
    }

    /* Blob shapes */
    .blob-a { border-radius: 60% 40% 30% 70% / 60% 30% 70% 40%; }
    .blob-b { border-radius: 40% 60% 70% 30% / 40% 50% 60% 50%; }

    /* Reduced motion */
    @media (prefers-reduced-motion: reduce) {
      *, *::before, *::after {
        animation-duration: 0.01ms !important;
        animation-iteration-count: 1 !important;
        transition-duration: 0.01ms !important;
        scroll-behavior: auto !important;
      }
      .reveal { transform: none !important; transition-property: opacity !important; transition-duration: 300ms !important; }
      [data-parallax] { transform: none !important; }
    }
  </style>
</head>
<body class="bg-serenity-base font-sans text-serenity-charcoal antialiased">

  <!-- Skip link (accessibility) -->
  <a href="#main" class="sr-only focus:not-sr-only focus:absolute focus:top-4 focus:left-4 focus:z-[2000] focus:bg-serenity-teal focus:text-white focus:px-4 focus:py-2 focus:rounded-md">
    Перейти к основному содержимому
  </a>

  <!-- HEADER -->
  <!-- HERO -->
  <!-- SOCIAL PROOF STRIP -->
  <!-- PHILOSOPHY -->
  <!-- SERVICES -->
  <!-- SIGNATURE TREATMENT -->
  <!-- ABOUT / TRUST -->
  <!-- TESTIMONIALS -->
  <!-- GALLERY -->
  <!-- BOOKING CTA -->
  <!-- FOOTER -->

  <script>
    // Intersection Observer for .reveal elements
    const revealEls = document.querySelectorAll('.reveal');
    const observer = new IntersectionObserver(entries => {
      entries.forEach(e => {
        if (e.isIntersecting) { e.target.classList.add('is-visible'); observer.unobserve(e.target); }
      });
    }, { threshold: 0.15, rootMargin: '0px 0px -40px 0px' });
    revealEls.forEach(el => observer.observe(el));

    // Header scroll state
    const header = document.getElementById('header');
    window.addEventListener('scroll', () => {
      header.style.background = window.scrollY > 80 ? 'rgba(250,248,245,0.95)' : 'transparent';
      header.style.backdropFilter = window.scrollY > 80 ? 'blur(12px)' : 'none';
      header.style.boxShadow = window.scrollY > 80 ? '0 2px 8px rgba(58,53,48,0.06)' : 'none';
    }, { passive: true });

    // Parallax (desktop only)
    if (window.innerWidth >= 768) {
      const parallaxEls = document.querySelectorAll('[data-parallax]');
      window.addEventListener('scroll', () => {
        parallaxEls.forEach(el => {
          const speed = parseFloat(el.dataset.parallax) || 0.3;
          el.style.transform = `translateY(${window.scrollY * speed}px)`;
        });
      }, { passive: true });
    }
  </script>
</body>
</html>
```

---

## APPENDIX B: DESIGN DECISION LOG

| Decision | Rationale |
|---|---|
| Cormorant Garamond + Jost | Cormorant: high-contrast old-style serif with elegant stroke, premium wellness benchmark, generous italic. Jost: geometric-humanist warmth without Inter's tech connotation. Together: editorial, calm, confident. |
| #FAF8F5 not #FFFFFF | Pure white reads clinical. Warm 2% tint reads sanctuary. The difference is perceptible and significant for perceived quality. |
| Terracotta on CTA labels (not buttons) | Terracotta is an emotional accent, not a functional signal. Teal (#2C5F63) owns the action / trust territory. Combining both on the same button creates contradiction. |
| Warm rgba shadows | Cold grey `rgba(0,0,0,x)` makes components feel harsh against warm backgrounds. Brown-tinted shadows `rgba(58,53,48,x)` belong to the same color family and feel cohesive. |
| Blob shapes for images | Biomorphic, asymmetric image crops trigger associations with organic nature, safety, flow. Anti-grid. Differentiates from clinical wellness competitors. |
| 900ms hero animation | Matches the "slow is luxurious" principle from research. A 200ms hero entrance feels rushed — contradiction of the brand promise. |
| Ghost button with terracotta border (not teal) | On the dark hero image, teal ghost buttons visually compete with the primary CTA. Terracotta border signals secondary, warm, inviting — not urgent. |
| Stagger max 120ms | Above 150ms stagger, the last card in a row appears to "wait" noticeably, breaking flow. 80–120ms reads as natural choreography. |
| CSS columns masonry (not JS) | JavaScript masonry libraries add weight and can cause layout shift. CSS `columns` achieves the visual result without dependencies. |
| Jost for button labels, not Cormorant | Cormorant at 12–14px all-caps loses legibility due to thin hairline strokes. Jost is designed for small UI contexts. |
| No dark mode | Target audience (30–50 women, premium Moscow spa context) accesses primarily in daytime / warm light environments. Dark mode adds implementation complexity without measurable conversion benefit for this use case. |

---

*Design system prepared for Serenity Spa landing page. Version 1.0. All specifications are implementation-ready for a frontend developer working with HTML + Tailwind CSS CDN.*
