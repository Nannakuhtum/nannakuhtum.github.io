---
name: Aakkagam Games
description: Warm, handmade landing page for free browser board games from ancient traditions
colors:
  ink: "#2b2320"
  paper: "#faf6f0"
  terracotta: "#8b3a2b"
  muted-clay: "#6b5f58"
  ink-dark: "#ece5df"
  paper-dark: "#1d1917"
  terracotta-dark: "#e0805f"
  muted-clay-dark: "#a3968e"
typography:
  display:
    fontFamily: "Georgia, 'Times New Roman', serif"
    fontSize: "2rem"
    fontWeight: 700
    lineHeight: 1.2
  headline:
    fontFamily: "Georgia, 'Times New Roman', serif"
    fontSize: "1.4rem"
    fontWeight: 700
  title:
    fontFamily: "Georgia, 'Times New Roman', serif"
    fontSize: "1.1rem"
    fontWeight: 700
  body:
    fontFamily: "Georgia, 'Times New Roman', serif"
    fontSize: "1rem"
    lineHeight: 1.6
rounded:
  button: "6px"
  card: "10px"
spacing:
  gutter: "1.25rem"
  card-pad: "1.25rem 1.5rem"
  section-gap: "2.5rem"
components:
  button-play:
    backgroundColor: "{colors.terracotta}"
    textColor: "{colors.paper}"
    rounded: "{rounded.button}"
    padding: "0.6rem 1.4rem"
  card-game:
    backgroundColor: "{colors.paper}"
    textColor: "{colors.ink}"
    rounded: "{rounded.card}"
    padding: "{spacing.card-pad}"
---

# Design System: Aakkagam Games

## 1. Overview

**Creative North Star: "The Sand Kattam"**

A board drawn in warm sand, played with pebbles and tamarind seeds. Everything on this page should feel handmade, warm, and tactile: paper the color of dry sand, ink the color of dark earth, one terracotta accent like fired clay. The page is a single quiet column of serif prose, the way a good museum postcard explains an artifact in a few honest sentences.

The system explicitly rejects the ad-heavy game portal (thumbnail grids, screaming CTAs), the generic SaaS landing template (hero + gradient + feature cards), the dark "gamer" aesthetic (neon on black), and the kids' cartoon site (bubble letters, mascots). Its lightness is literal: one static HTML file, system serif, no images required to render.

**Key Characteristics:**
- Warm tinted neutrals; nothing is pure black or pure white
- One terracotta accent doing all the color work (Restrained strategy)
- Single-column prose layout, capped at 42rem
- Serif throughout; hierarchy by size and weight, not font changes
- Flat surfaces, thin borders, no shadows, no motion

## 2. Colors

Tinted warm neutrals plus a single terracotta accent; the palette of sand, earth, and fired clay.

### Primary
- **Terracotta** (#8b3a2b light / #e0805f dark): the only accent. Links, section headings (h2), and the Play button background. It signals "this is where you act or navigate", nothing else.

### Neutral
- **Ink** (#2b2320 light / #ece5df dark): all body text and headings except h2. Dark earth, not black.
- **Paper** (#faf6f0 light / #1d1917 dark): the page background and the Play button's text color. Dry sand, not white.
- **Muted Clay** (#6b5f58 light / #a3968e dark): secondary text (tagline, footer) and 1px card borders.

### Named Rules
**The Fired Clay Rule.** Terracotta appears on at most 10% of the page: links, h2 headings, and Play buttons. If terracotta starts covering backgrounds or large panels, it has escaped the kiln.

**The No Pure Rule.** #000 and #fff are forbidden. Every neutral is tinted toward the warm brown hue.

## 3. Typography

**Display Font:** Georgia (with 'Times New Roman', serif)
**Body Font:** Georgia (same stack; one family throughout)

**Character:** A bookish system serif that reads like printed matter, not an app. Free, instant, and warm; the typographic equivalent of the games themselves.

### Hierarchy
- **Display / h1** (700, 2rem, 1.2): the page headline, once.
- **Headline / h2** (700, 1.4rem): section headings, set in Terracotta.
- **Title / h3** (700, 1.1rem): game names inside cards.
- **Body** (400, 1rem, 1.6): all prose; the 42rem main column keeps lines near 70ch.
- **Small** (400, 0.9rem): footer, in Muted Clay.

### Named Rules
**The One Family Rule.** Georgia carries everything. Hierarchy comes from size and weight only; introducing a second family needs a reason as strong as a new game launch.

## 4. Elevation

Flat and bordered. No box-shadows anywhere; depth is conveyed by 1px Muted Clay borders (game cards) and by color contrast (the solid terracotta Play button against paper). Buttons feel like stamped clay: solid, matter-of-fact, no lift or glow. If a surface needs separation, give it a thin border or nothing.

### Named Rules
**The Sand Is Flat Rule.** A board drawn in sand casts no shadows. Neither does this page.

## 5. Components

### Buttons (Play link)
- **Shape:** gently rounded (6px radius)
- **Primary:** solid Terracotta background, Paper text, bold, 0.6rem 1.4rem padding; rendered as an `<a>`, one per game card
- **Hover / Focus:** browser-default focus outline today; any added hover should be a slight darkening of the terracotta, never a lift or glow

### Cards / Containers (game card)
- **Corner Style:** 10px radius
- **Background:** Paper (no fill change from the page)
- **Border:** 1px solid Muted Clay
- **Shadow Strategy:** none (see Elevation)
- **Internal Padding:** 1.25rem 1.5rem
- One card per game; the card holds name, a short rules description, and the Play button. Cards differ in content length; they are not forced into a uniform grid.

### Navigation
- No nav bar. The page is a single column; the footer repeats the game links in plain text.

### FAQ list
- Semantic `<dl>`: bold `<dt>` questions, plain `<dd>` answers, no accordions or toggles.

## 6. Do's and Don'ts

### Do:
- **Do** keep the whole page one static HTML file with inline CSS; no build step, no external fonts or scripts.
- **Do** give every game exactly one terracotta Play link, with an honest label ("Play align3 free").
- **Do** support both schemes via `prefers-color-scheme`; every color has a light and dark value.
- **Do** hold AA contrast in both schemes, including Paper-on-Terracotta button text.
- **Do** let history do the persuading: specific, true detail over superlatives.

### Don't:
- **Don't** build an "ad-heavy game portal": no thumbnail grids, no screaming CTAs, no clutter.
- **Don't** use the "generic SaaS landing" template: no hero gradients, no feature-card triptychs, no testimonials.
- **Don't** go "dark gamer": no neon on black, no glow effects.
- **Don't** go "kids' cartoon": no bubble letters, no mascots, no primary-color overload.
- **Don't** use #000 or #fff, box-shadows, gradient text, or colored side-stripe borders.
- **Don't** add motion; if any is ever added, it must respect `prefers-reduced-motion`.
