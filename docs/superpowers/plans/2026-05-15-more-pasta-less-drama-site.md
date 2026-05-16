# More Pasta, Less Drama — Brand Site Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Build a single-page cream-background brand site for More Pasta, Less Drama, hosted on GitHub Pages, featuring a structured snapback hat SVG and prominent TikTok/Instagram community CTAs.

**Architecture:** One `index.html` file containing all HTML, CSS, and inline SVG. Google Fonts (Lobster, Georgia) loaded via CDN. No JavaScript framework, no build step — browser opens the file directly. Shopify and social links are placeholders until Brian creates those accounts.

**Tech Stack:** HTML5, CSS3, Google Fonts (Lobster), GitHub Pages

---

## File Map

| File | Purpose |
|---|---|
| `index.html` | The entire site — all sections, styles, and SVG |
| `CLAUDE.md` | Project docs — how to update links, brand rules |
| `.gitignore` | Ignore `.superpowers/` brainstorm artifacts |

---

## Task 1: Project Scaffolding

**Files:**
- Create: `index.html`
- Create: `CLAUDE.md`
- Create: `.gitignore`

- [ ] **Step 1: Initialize git repo**

```bash
cd "C:\Users\Brian\Desktop\MPLD"
git init
```

Expected output: `Initialized empty Git repository in C:/Users/Brian/Desktop/MPLD/.git/`

- [ ] **Step 2: Create `.gitignore`**

Create `C:\Users\Brian\Desktop\MPLD\.gitignore` with this content:

```
.superpowers/
```

- [ ] **Step 3: Create the HTML shell**

Create `C:\Users\Brian\Desktop\MPLD\index.html` with this content:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>More Pasta, Less Drama</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Lobster&display=swap" rel="stylesheet">
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --cream: #f5f0e8;
      --brown: #1a0a00;
      --gold:  #c8a000;
      --muted: #9a7a5a;
      --light-border: #d4cfc7;
    }

    html { scroll-behavior: smooth; }

    body {
      background: var(--cream);
      color: var(--brown);
      font-family: Georgia, 'Times New Roman', serif;
    }
  </style>
</head>
<body>

  <!-- Sections go here -->

</body>
</html>
```

- [ ] **Step 4: Verify shell loads in browser**

Open `index.html` in a browser. Expected: blank cream page, no console errors.

- [ ] **Step 5: Create `CLAUDE.md`**

Create `C:\Users\Brian\Desktop\MPLD\CLAUDE.md` with this content:

```markdown
# More Pasta, Less Drama — Project Guide

## What This Is
Brand site for the More Pasta, Less Drama structured snapback hat. Single HTML file, hosted on GitHub Pages.

## Brand Rules
- Brand name is always "More Pasta, Less Drama" — never abbreviated to "MPLD" on the site
- Background is cream (#f5f0e8) throughout — do not change to red or dark backgrounds
- Hat embroidery font is Lobster (Google Fonts), black, on a white crown with a black brim
- Accent color is gold (#c8a000), body font is Georgia italic

## File Structure
- `index.html` — the entire site (HTML + CSS, no JS framework)
- `CLAUDE.md` — this file
- `.gitignore` — ignores .superpowers/ brainstorm artifacts
- `docs/superpowers/` — design spec and implementation plan

## How to Update the Shopify Link
Search for `SHOPIFY_LINK_PLACEHOLDER` in index.html and replace with the real Shopify URL.

## How to Update Social Handles
Search for `TIKTOK_HANDLE_PLACEHOLDER` and `INSTAGRAM_HANDLE_PLACEHOLDER` in index.html and replace with real URLs.

## Hosting
GitHub Pages. Push to main branch, enable Pages in repo settings, source = root.
```

- [ ] **Step 6: Commit scaffolding**

```bash
git add index.html CLAUDE.md .gitignore
git commit -m "feat: project scaffolding — HTML shell, CLAUDE.md, gitignore"
```

---

## Task 2: Sticky Nav

**Files:**
- Modify: `index.html` — add nav HTML inside `<body>`, add nav CSS inside `<style>`

- [ ] **Step 1: Add nav CSS** inside the `<style>` block, after the `body` rule:

```css
/* ── NAV ── */
nav {
  position: sticky;
  top: 0;
  z-index: 100;
  display: flex;
  justify-content: flex-end;
  align-items: center;
  padding: 18px 48px;
  background: var(--cream);
  border-bottom: 1px solid var(--light-border);
}

nav ul {
  list-style: none;
  display: flex;
  gap: 32px;
}

nav a {
  color: var(--muted);
  text-decoration: none;
  font-size: 12px;
  letter-spacing: 2px;
  text-transform: uppercase;
  font-style: normal;
  transition: color .2s;
}

nav a:hover { color: var(--brown); }
```

- [ ] **Step 2: Add nav HTML** inside `<body>`, replacing the `<!-- Sections go here -->` comment:

```html
  <nav>
    <ul>
      <li><a href="#about">About</a></li>
      <li><a href="#the-hat">The Hat</a></li>
      <li><a href="#shop">Shop</a></li>
      <li><a href="#community">Follow Us</a></li>
    </ul>
  </nav>

  <!-- Sections go here -->
```

- [ ] **Step 3: Verify nav in browser**

Open `index.html`. Expected: cream sticky nav bar at top-right with 4 links, no wordmark.

- [ ] **Step 4: Commit**

```bash
git add index.html
git commit -m "feat: sticky nav with About, The Hat, Shop, Follow Us links"
```

---

## Task 3: Hat SVG Component

**Files:**
- Modify: `index.html` — add the reusable hat SVG as an inline `<template>` and a CSS helper

This task defines the hat once. Later tasks reference it.

- [ ] **Step 1: Add hat SVG template** inside `<body>`, after the closing `</nav>` tag:

```html
  <!-- Reusable hat SVG — referenced by hero and product sections -->
  <template id="hat-svg-template">
    <svg viewBox="0 0 260 155" xmlns="http://www.w3.org/2000/svg" aria-label="More Pasta, Less Drama structured snapback hat">
      <!-- Crown: structured, 5-panel, white/off-white -->
      <path d="M20 105 Q28 52 76 24 Q130 5 184 24 Q220 45 238 90 Q240 103 238 108 Q184 118 130 120 Q68 118 22 108 Z" fill="#f0ebe2"/>
      <!-- Panel seam lines -->
      <line x1="130" y1="7"  x2="130" y2="120" stroke="#ddd" stroke-width="0.8" opacity="0.55"/>
      <line x1="76"  y1="22" x2="72"  y2="118" stroke="#ddd" stroke-width="0.6" opacity="0.45"/>
      <line x1="184" y1="22" x2="188" y2="118" stroke="#ddd" stroke-width="0.6" opacity="0.45"/>
      <!-- Sweatband -->
      <path d="M22 108 Q130 122 238 108 Q238 114 236 118 Q130 132 24 118 Q22 114 22 108Z" fill="#d8d0c4"/>
      <!-- Crown button/eyelet -->
      <circle cx="130" cy="9" r="5.5" fill="#b0a898" stroke="#a09888" stroke-width="1"/>
      <!-- Embroidered text: Lobster, black -->
      <text x="130" y="72"  text-anchor="middle" font-family="'Lobster', cursive" font-size="17" fill="#1a0a00">More Pasta,</text>
      <text x="130" y="96" text-anchor="middle" font-family="'Lobster', cursive" font-size="17" fill="#1a0a00">Less Drama</text>
      <!-- Flat black brim (snapback style) -->
      <path d="M22 116 Q0 121 2 131 Q4 140 24 139 Q80 143 130 143 Q180 143 236 139 Q256 140 258 131 Q260 121 238 116 Q184 126 130 127 Q72 126 22 116Z" fill="#111"/>
      <!-- Brim top edge -->
      <path d="M22 116 Q130 127 238 116" stroke="#2a2a2a" stroke-width="1" fill="none"/>
      <!-- Snap closure tab -->
      <rect x="116" y="139" width="28" height="6" rx="2" fill="#2a2a2a"/>
      <line x1="122" y1="142" x2="138" y2="142" stroke="#444" stroke-width="1"/>
    </svg>
  </template>
```

- [ ] **Step 2: Add hat clone helper script** just before `</body>`:

```html
  <script>
    function cloneHat(containerId, width) {
      var template = document.getElementById('hat-svg-template');
      var container = document.getElementById(containerId);
      var clone = template.content.cloneNode(true);
      var svg = clone.querySelector('svg');
      svg.style.width = width;
      svg.style.height = 'auto';
      container.appendChild(clone);
    }
    document.addEventListener('DOMContentLoaded', function() {
      cloneHat('hero-hat', '320px');
      cloneHat('product-hat', '280px');
    });
  </script>
```

- [ ] **Step 3: Verify no console errors**

Open `index.html` in browser. Expected: no errors in DevTools console. Hat is not visible yet (no container divs) — that's fine.

- [ ] **Step 4: Commit**

```bash
git add index.html
git commit -m "feat: hat SVG template and clone helper"
```

---

## Task 4: Hero Section

**Files:**
- Modify: `index.html` — add hero HTML after `</nav>` comment, add hero CSS

- [ ] **Step 1: Add hero CSS** inside `<style>`, after the nav rules:

```css
/* ── HERO ── */
.hero {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  padding: 80px 24px 60px;
  border-bottom: 1px solid var(--light-border);
}

.hero-hat {
  margin-bottom: 36px;
  filter: drop-shadow(0 16px 32px rgba(0,0,0,0.12));
}

.hero-slogan {
  font-size: clamp(36px, 6vw, 64px);
  font-style: italic;
  line-height: 1.1;
  margin-bottom: 14px;
  color: var(--brown);
}

.hero-sub {
  font-size: 16px;
  font-style: italic;
  color: var(--muted);
  margin-bottom: 36px;
  letter-spacing: 0.5px;
}

.btn-primary {
  display: inline-block;
  background: var(--brown);
  color: var(--cream);
  font-family: Georgia, serif;
  font-style: italic;
  font-size: 14px;
  letter-spacing: 2px;
  padding: 14px 42px;
  text-decoration: none;
  transition: background .2s;
}

.btn-primary:hover { background: #3a1800; }
```

- [ ] **Step 2: Add hero HTML** inside `<body>`, replacing `<!-- Sections go here -->`:

```html
  <section class="hero">
    <div id="hero-hat" class="hero-hat"></div>
    <h1 class="hero-slogan">More Pasta,<br>Less Drama.</h1>
    <p class="hero-sub">The hat for people with priorities.</p>
    <a class="btn-primary" href="SHOPIFY_LINK_PLACEHOLDER">Shop Now</a>
  </section>

  <!-- Sections go here -->
```

- [ ] **Step 3: Verify hero in browser**

Open `index.html`. Expected: full-viewport cream section with the snapback hat SVG centered above the slogan, dark brown "Shop Now" button below. Hat should show Lobster script text on white crown with black flat brim.

- [ ] **Step 4: Commit**

```bash
git add index.html
git commit -m "feat: hero section with hat SVG, slogan, and Shop Now CTA"
```

---

## Task 5: About Section

**Files:**
- Modify: `index.html` — add about HTML and CSS

- [ ] **Step 1: Add about CSS** inside `<style>`, after hero rules:

```css
/* ── SHARED SECTION STYLES ── */
.section {
  padding: 90px 24px;
  border-bottom: 1px solid var(--light-border);
}

.section-inner {
  max-width: 640px;
  margin: 0 auto;
  text-align: center;
}

.section-label {
  font-size: 10px;
  letter-spacing: 5px;
  text-transform: uppercase;
  color: var(--gold);
  font-style: normal;
  margin-bottom: 20px;
  display: block;
}

.section-title {
  font-size: clamp(24px, 4vw, 36px);
  font-style: italic;
  line-height: 1.2;
  margin-bottom: 20px;
}

.ornament {
  color: var(--gold);
  font-size: 14px;
  letter-spacing: 10px;
  margin: 24px 0;
  display: block;
}

.section-body {
  color: var(--muted);
  font-size: 16px;
  font-style: italic;
  line-height: 1.85;
}
```

- [ ] **Step 2: Add about HTML** replacing `<!-- Sections go here -->`:

```html
  <section class="section" id="about">
    <div class="section-inner">
      <span class="section-label">The Story</span>
      <h2 class="section-title">Born in a booth.<br>Worn everywhere else.</h2>
      <span class="ornament">✦ ✦ ✦</span>
      <p class="section-body">
        Some people stress over the menu. We don't. More Pasta, Less Drama is a state of mind —
        white hat, black brim, pasta in front of you, drama behind you.
        Wear it to dinner. Wear it to the game. Wear it anywhere life gets too complicated.
        We're building a community of people who have their priorities straight.
        Join us on TikTok and Instagram.
      </p>
    </div>
  </section>

  <!-- Sections go here -->
```

- [ ] **Step 3: Verify about section in browser**

Scroll past the hero. Expected: centered text section with gold "The Story" label, italic headline, gold ornament divider, muted body copy.

- [ ] **Step 4: Commit**

```bash
git add index.html
git commit -m "feat: about section with brand story copy"
```

---

## Task 6: The Hat Section

**Files:**
- Modify: `index.html` — add product section HTML and CSS

- [ ] **Step 1: Add product section CSS** inside `<style>`, after the shared section styles:

```css
/* ── THE HAT ── */
.product-layout {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 60px;
  flex-wrap: wrap;
}

.product-hat {
  flex-shrink: 0;
  filter: drop-shadow(0 12px 24px rgba(0,0,0,0.10));
}

.product-details {
  max-width: 300px;
  text-align: left;
}

.product-details .section-label { text-align: left; }
.product-details .section-title { text-align: left; font-size: 24px; }

.product-specs {
  list-style: none;
  margin: 20px 0 28px;
  color: var(--muted);
  font-style: italic;
  font-size: 15px;
  line-height: 2;
}

.product-specs li::before {
  content: '✦  ';
  color: var(--gold);
  font-size: 10px;
  font-style: normal;
}
```

- [ ] **Step 2: Add product section HTML** replacing `<!-- Sections go here -->`:

```html
  <section class="section" id="the-hat">
    <div class="section-inner" style="max-width: 860px;">
      <div class="product-layout">
        <div id="product-hat" class="product-hat"></div>
        <div class="product-details">
          <span class="section-label">The Hat</span>
          <h2 class="section-title">More Pasta,<br>Less Drama</h2>
          <ul class="product-specs">
            <li>Structured snapback</li>
            <li>White crown</li>
            <li>Black flat brim</li>
            <li>Black script embroidery</li>
            <li>Adjustable snap closure</li>
            <li>One size fits most</li>
          </ul>
          <a class="btn-primary" href="SHOPIFY_LINK_PLACEHOLDER">Get Yours</a>
        </div>
      </div>
    </div>
  </section>

  <!-- Sections go here -->
```

- [ ] **Step 3: Verify product section in browser**

Scroll to The Hat section. Expected: hat SVG on the left, specs list on the right, "Get Yours" CTA. On narrow screens the layout should stack vertically.

- [ ] **Step 4: Commit**

```bash
git add index.html
git commit -m "feat: product section with hat specs and Get Yours CTA"
```

---

## Task 7: Community Section

**Files:**
- Modify: `index.html` — add community section HTML and CSS

- [ ] **Step 1: Add community CSS** inside `<style>`, after product styles:

```css
/* ── COMMUNITY ── */
.community-section {
  background: var(--brown);
  color: var(--cream);
  border-bottom: none;
}

.community-section .section-label { color: var(--gold); }
.community-section .section-title { color: var(--cream); }
.community-section .ornament { color: var(--gold); }

.social-buttons {
  display: flex;
  gap: 16px;
  justify-content: center;
  flex-wrap: wrap;
  margin-top: 8px;
}

.btn-social {
  display: inline-flex;
  align-items: center;
  gap: 10px;
  border: 1px solid var(--gold);
  color: var(--gold);
  text-decoration: none;
  font-family: Georgia, serif;
  font-style: italic;
  font-size: 14px;
  letter-spacing: 1px;
  padding: 14px 32px;
  transition: background .2s, color .2s;
}

.btn-social:hover {
  background: var(--gold);
  color: var(--brown);
}

.community-sub {
  color: #9a8a7a;
  font-style: italic;
  font-size: 14px;
  margin-top: 24px;
}
```

- [ ] **Step 2: Add community HTML** replacing `<!-- Sections go here -->`:

```html
  <section class="section community-section" id="community">
    <div class="section-inner">
      <span class="section-label">The Pasta Gang</span>
      <h2 class="section-title">Join the community.</h2>
      <span class="ornament">✦ ✦ ✦</span>
      <p class="section-body" style="color: #9a8a7a; margin-bottom: 32px;">
        We're building something on TikTok and Instagram. Pasta content,
        hat drops, and people who get it. Follow along.
      </p>
      <div class="social-buttons">
        <a class="btn-social" href="TIKTOK_HANDLE_PLACEHOLDER" target="_blank" rel="noopener">
          TikTok
        </a>
        <a class="btn-social" href="INSTAGRAM_HANDLE_PLACEHOLDER" target="_blank" rel="noopener">
          Instagram
        </a>
      </div>
      <p class="community-sub">More drops coming. Don't miss it.</p>
    </div>
  </section>

  <!-- Footer goes here -->
```

- [ ] **Step 3: Verify community section in browser**

Scroll to bottom. Expected: dark brown background section (inverted), gold-bordered TikTok and Instagram buttons, gold ornaments. Buttons hover to gold fill.

- [ ] **Step 4: Commit**

```bash
git add index.html
git commit -m "feat: community section with TikTok and Instagram CTAs"
```

---

## Task 8: Footer

**Files:**
- Modify: `index.html` — add footer HTML and CSS

- [ ] **Step 1: Add footer CSS** inside `<style>`:

```css
/* ── FOOTER ── */
footer {
  padding: 24px;
  text-align: center;
  background: var(--brown);
  color: #4a3a2a;
  font-size: 12px;
  font-style: italic;
  letter-spacing: 1px;
  border-top: 1px solid #2a1a0a;
}

footer a {
  color: #6a5a4a;
  text-decoration: none;
}

footer a:hover { color: var(--muted); }
```

- [ ] **Step 2: Add footer HTML** replacing `<!-- Footer goes here -->`:

```html
  <footer>
    <p>© 2024 More Pasta, Less Drama &nbsp;·&nbsp;
      <a href="TIKTOK_HANDLE_PLACEHOLDER" target="_blank" rel="noopener">TikTok</a>
      &nbsp;·&nbsp;
      <a href="INSTAGRAM_HANDLE_PLACEHOLDER" target="_blank" rel="noopener">Instagram</a>
      &nbsp;·&nbsp;
      <a href="SHOPIFY_LINK_PLACEHOLDER">Shop</a>
    </p>
  </footer>
```

- [ ] **Step 3: Verify full page in browser**

Scroll the entire page top to bottom. Expected:
1. Cream sticky nav (no wordmark)
2. Full-viewport hero with hat, slogan, Shop Now
3. About section with story copy
4. The Hat section with specs
5. Dark community section with social buttons
6. Dark footer with links

- [ ] **Step 4: Commit**

```bash
git add index.html
git commit -m "feat: footer with social and shop links"
```

---

## Task 9: Mobile Responsiveness & Polish

**Files:**
- Modify: `index.html` — add responsive CSS and smooth-scroll meta

- [ ] **Step 1: Add responsive CSS** inside `<style>`, at the bottom:

```css
/* ── RESPONSIVE ── */
@media (max-width: 640px) {
  nav { padding: 16px 20px; }
  nav ul { gap: 18px; }
  nav a { font-size: 11px; letter-spacing: 1px; }

  .hero { padding: 60px 20px 48px; }

  .section { padding: 60px 20px; }

  .product-layout { flex-direction: column; text-align: center; }
  .product-details { text-align: center; }
  .product-details .section-label,
  .product-details .section-title { text-align: center; }
  .product-specs li { text-align: center; }

  .social-buttons { flex-direction: column; align-items: center; }
  .btn-social { width: 100%; max-width: 280px; justify-content: center; }
}
```

- [ ] **Step 2: Verify on mobile viewport**

In browser DevTools, toggle device toolbar and set to iPhone SE (375px wide). Expected: nav links fit on one line, hat and product details stack vertically, social buttons stack full-width.

- [ ] **Step 3: Check all placeholder links are present**

Search `index.html` for all 3 placeholders — each should appear in the file:
- `SHOPIFY_LINK_PLACEHOLDER` (appears in hero CTA, product CTA, footer)
- `TIKTOK_HANDLE_PLACEHOLDER` (appears in community section, footer)
- `INSTAGRAM_HANDLE_PLACEHOLDER` (appears in community section, footer)

- [ ] **Step 4: Final visual check — desktop**

Open `index.html` on desktop. Scroll the full page. Verify:
- Lobster font loads (hat text appears in script style)
- No layout breaks
- Gold accent (#c8a000) appears on labels, ornaments, social button borders
- Community section is dark brown, all other sections are cream

- [ ] **Step 5: Commit**

```bash
git add index.html
git commit -m "feat: mobile responsive styles and final polish"
```

---

## Task 10: GitHub Pages Deploy

**Files:**
- No file changes — this is a configuration and deploy task

- [ ] **Step 1: Create GitHub repo**

Go to github.com → New repository → name it `more-pasta-less-drama` (or whatever Brian prefers) → public → no README (we have one).

- [ ] **Step 2: Push to GitHub**

```bash
git remote add origin https://github.com/[YOUR_USERNAME]/[REPO_NAME].git
git branch -M main
git push -u origin main
```

- [ ] **Step 3: Enable GitHub Pages**

In the GitHub repo → Settings → Pages → Source: Deploy from branch → Branch: main → Folder: / (root) → Save.

- [ ] **Step 4: Verify live site**

After ~60 seconds, visit `https://[YOUR_USERNAME].github.io/[REPO_NAME]/`. Expected: the full cream site loads with the hat SVG and all sections.

- [ ] **Step 5: Note placeholder update instructions for Brian**

When Brian has his Shopify store and social handles, he needs to:
1. Open `index.html`
2. Find and replace `SHOPIFY_LINK_PLACEHOLDER` with his Shopify store URL
3. Find and replace `TIKTOK_HANDLE_PLACEHOLDER` with his TikTok URL (e.g. `https://tiktok.com/@morepastalesdrama`)
4. Find and replace `INSTAGRAM_HANDLE_PLACEHOLDER` with his Instagram URL
5. Commit and push — site updates automatically

---

## Self-Review

**Spec coverage check:**

| Spec requirement | Covered by |
|---|---|
| Single HTML file, GitHub Pages | Tasks 1, 10 |
| Cream background throughout | Task 1 (CSS vars), Task 9 (verified) |
| Sticky nav, no wordmark, 4 links | Task 2 |
| Hero: hat SVG, slogan, Shop Now | Tasks 3, 4 |
| Structured snapback, white crown, black brim, Lobster black embroidery | Task 3 |
| About: brand story, pasta community angle | Task 5 |
| The Hat: product specs, CTA | Task 6 |
| Community: TikTok + Instagram prominent | Task 7 |
| Footer: minimal, social + shop links | Task 8 |
| Mobile responsive | Task 9 |
| CLAUDE.md | Task 1 |
| Shopify placeholder | Tasks 4, 6, 8, 9 |
| Social handle placeholders | Tasks 7, 8, 9 |
| No "MPLD" on site | All tasks — never used |

All spec requirements covered. No TBDs or placeholders in the plan itself.
