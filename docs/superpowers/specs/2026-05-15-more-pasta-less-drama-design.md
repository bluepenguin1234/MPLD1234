# More Pasta, Less Drama — Brand Site Design Spec

**Date:** 2026-05-15
**Project:** More Pasta, Less Drama hat brand
**Location:** `C:\Users\Brian\Desktop\MPLD`

---

## Overview

A single-page brand site for More Pasta, Less Drama — a structured snapback hat brand built around a pasta lifestyle community. The site's primary job is to represent the brand and drive visitors to follow on TikTok and Instagram. A Shopify link will be wired in once the store is set up.

**GTM strategy:** Build the TikTok/Instagram pasta community first, then use that audience to drive hat sales through this site.

---

## Stack

- Single HTML file (`index.html`)
- Hosted on GitHub Pages
- No frameworks, no build step
- Google Fonts loaded via CDN (Lobster, Georgia)
- Shopify link: placeholder until store is live

---

## Visual Design

| Element | Value |
|---|---|
| Background | Cream/off-white `#f5f0e8` throughout |
| Primary text | Dark brown `#1a0a00` |
| Accent | Gold `#c8a000` |
| Body font | Georgia, serif, italic |
| Hat embroidery font | Lobster (Google Fonts) |
| Hat | Structured snapback — white crown, black flat brim, black Lobster "More Pasta, Less Drama" embroidery |

No logo image. Brand name "More Pasta, Less Drama" used as text treatment only. "MPLD" does not appear anywhere on the site — it is only the folder name.

---

## Page Structure

### 1. Nav
- Sticky top bar
- No wordmark or logo
- Links: About · The Hat · Shop · Follow Us
- "Shop" links to Shopify (placeholder `#` until live)

### 2. Hero
- Full-viewport section
- Centered structured snapback hat (SVG — white crown, black flat brim, black Lobster script embroidery)
- Large italic slogan: *More Pasta, Less Drama.*
- Subtext: short brand line (e.g. "The hat for people with priorities.")
- Gold "Shop Now" CTA button (placeholder until Shopify is live)

### 3. About
- Brand story section
- Copy connects the hat to the pasta community angle
- Ornamental dividers (✦ ✦ ✦), serif italic type
- Tone: warm, irreverent, confident

### 4. The Hat
- Product spotlight
- Hat SVG (same asset as hero, can be reused)
- Specs listed: structured snapback, white crown, black brim, black script embroidery, adjustable snap closure
- "Get Yours" CTA (same Shopify placeholder link)

### 5. Community
- TikTok + Instagram prominently featured
- "Join the pasta gang" energy
- Large social link buttons — not tucked in a footer, front and center
- This is the primary conversion goal while the Shopify store is being set up

### 6. Footer
- Minimal: copyright, social icon links, Shopify placeholder link

---

## Hat SVG Spec

The hat is rendered as an inline SVG:
- **Crown:** off-white/cream panels with subtle seam lines, structured (not floppy)
- **Brim:** flat, black, snapback style with a small snap closure tab at the back
- **Button:** small circle at crown top
- **Text:** "More Pasta," on line 1, "Less Drama" on line 2, centered on front panel, Lobster font, black fill

---

## Social Links

Placeholders to be filled in by Brian once accounts are created:
- TikTok: `https://tiktok.com/@[handle]`
- Instagram: `https://instagram.com/[handle]`

---

## CLAUDE.md

A `CLAUDE.md` file will be created in the project root documenting:
- Project purpose and brand rules
- File structure
- How to update the Shopify link
- How to update social handles

---

## Out of Scope

- Location/restaurant hat editions (future drop, not on this site yet)
- E-commerce checkout flow (Shopify handles this)
- Blog or content pages
- Any backend or server-side code
