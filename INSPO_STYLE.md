# GlitchCAP Labs — True Design Reference
# Written from frame-by-frame video analysis. This is the ACTUAL style to replicate.

---

## ⚠️ WHAT WE BUILT WAS WRONG

The prototype (`site/index.html`) is trash. Delete or ignore it. Problems:
- Bebas Neue is not the right font — it's generic and not what those sites use
- The particle canvas is a cliché developer toy, not cinematic
- The orb/ring visual is AI-generated slop
- "Glitch" effect on the logo is a red herring — the sites have NO gimmick effects
- The layout has cards and containers — the reference sites have NONE
- The color palette (cyan + purple) is wrong — reference sites are near-monochrome

---

## THE CORN REVOLUTION — The North Star

**URL:** cornrevolution.resn.global (built by Resn studio)
**Analyzed:** 53 frames at 1fps from Matvey's screen recording

### How it actually works

The site is NOT a normal webpage. It is a **scroll-driven film**. Each frame of scroll
advances a single cinematic scene. There are no separate "sections" that slide in —
the entire page is one continuous moving image that your scroll position controls.

### Loading Screen
- Pure `#000000` black
- Centered Pioneer logo — drawn only as an **outline/stroke**, not filled. Barely visible.
- White counter: `26%` ... `100%` counting up
- Lowercase italic: `"Loading your experience."` — not uppercase, not a loading bar
- Nothing else. The restraint IS the design.

### Hero / Intro
- Background: Deep forest green `#0d2d10` — very dark, almost black-green
- Cinematic **close-up photography** of a corn cob (studio lit, shallow depth of field)
- The word `"CORN"` appears in **OUTLINE only** — `color: transparent`, `-webkit-text-stroke: 1px #f0f0fa`
- As scroll advances, the outline FILLS IN to become solid white — this is the key animation
- `"CORN. REVOLUTIONIZED."` — the period is intentional, it reads like a military designation
- Body copy underneath in thin white: `"From lab to field, it's corn seed development that will change farming."`
- **No nav visible at first** — it fades in after intro
- Scroll circle indicator bottom-left: small circle with chevron, stroked not filled

### Navigation (always visible after intro)
- Hamburger (3 lines) top LEFT — minimal, not a drawer by default
- Pioneer logo + wordmark centered at top
- That is the ENTIRE nav. Nothing else. No links in the nav bar.
- When hamburger opens: "EXPLORE THE STORY" + Chapter 1/2/3 listed by name, then CTAs

### Typography — THE MOST IMPORTANT PART
- **Display font**: Custom condensed bold — closest free equivalent is **`Barlow Condensed`** at weight 700 or 800. NOT Bebas Neue (too thin, too geometric). The Corn Revolution font has wider letterforms, more weight.
- **All headlines ALL CAPS**
- **Letter spacing**: TIGHT — slightly negative or zero, NOT positive like SpaceX
- **Line height**: 0.88–0.95 — headlines are compressed vertically, lines almost touch
- **Body text**: Inter or similar — weight 300 (light), smallish (15–16px), NOT uppercase
- **Text color**: `#f0f0fa` (slightly blue-tinted white, not pure #ffffff)
- **Outline text trick**: Headlines transition from outline-only → filled solid white as section scrolls in
- **Ghost/outline text**: `-webkit-text-stroke: 1px rgba(240,240,250,0.4)` + `color: transparent`

### Color Palette — EXACT VALUES
```
#000000      — Pure black (hero background)
#0d2d10      — Deep forest green (section backgrounds)
#0a1f0a      — Darker forest variant
#f0f0fa      — Spectral white (all text — NOT #ffffff)
#00ffaa      — Teal/cyan (particle dots, accent nodes) — used SPARINGLY
#e8a020      — Warm amber/gold (3D corn kernel, 3D objects — not UI color)
rgba(0,0,0,0.5) — Dark overlay on photos for text legibility
```

### Scroll Behavior — THE KEY MECHANIC
- **GSAP ScrollTrigger pinning**: the section is PINNED (doesn't scroll away)
- Instead of the page moving down, the SCENE changes in place
- Each "chapter" is pinned at 100vh, and the content inside animates based on scrollY
- Text reveals: `opacity 0 → 1` + `y: 30px → 0` triggered by scroll position
- Outline text fill: achieved with a clip-path or SVG mask that reveals fill as scroll advances
- Camera "movements": CSS `scale` + `translate` on background images creates parallax/zoom

### DNA / Science Section
- Background: `#000000` pure black
- A **3D glowing strand** — two intertwined ropes of orange/gold light
- This is WebGL — probably Three.js with custom shader. The strands TWIST and GLOW.
- Floating teal dots scattered — small, 4–6px, random positions, slowly drifting
- Text FADES IN as you scroll: `"FIRST, A SOLID FOUNDATION."`
- Then body copy: white, thin weight, appears below
- Circle outline CTA: `"EXPLORE THE LIBRARY"` — white circle outline, text inside, NO fill

### Data Section
- Background: very dark teal `#071a0f`
- 3D corn kernels FLOATING in space — rendered in amber/gold, photorealistic-ish
- Teal and yellow DOTS connected by thin white lines (like a neural network / constellation)
- Dots have different sizes: some larger (hubs), some tiny (nodes)
- Text: `"COMPUTERS CUT DOWN THE CONTENDERS."` — massive, all caps, solid white
- Body paragraph below explaining data/simulations

### Seed / Final Section
- Background: transitions — top is aerial corn field (photo), below is dark with orange glow
- A single large 3D corn **SEED/KERNEL** — glowing warm amber, fills most of screen
- Data constellation around it (white dots + lines)
- Text: `"LESS THAN 0.01% OF SEEDS MAKE IT."` — the emotional payoff
- Circle CTA: `"SEE THE NEW CLASS"` — outline circle button

### Footer / End
- Forest green background
- Large ALL CAPS stacked links with right-arrow icons:
  - `SIGN UP FOR NEWS ›`
  - `CONTACT A TERRITORY MANAGER ›`
  - `VISIT CORN REVOLUTION PODCAST ↗`
  - `VISIT PIONEER.COM ↗`
- Small legal text bottom left
- Corteva Agriscience logo bottom right

### UI Components — EXACT SPECS
```css
/* The only button style */
.cta-circle {
  display: inline-flex;
  align-items: center; justify-content: center;
  width: 120px; height: 120px;
  border-radius: 50%;
  border: 1px solid rgba(240, 240, 250, 0.4);
  background: transparent;
  color: #f0f0fa;
  font-size: 11px;
  letter-spacing: 1.5px;
  text-transform: uppercase;
  text-align: center;
  padding: 16px;
}
/* NO other button shapes exist on the site */

/* Scroll indicator */
.scroll-indicator {
  width: 44px; height: 44px;
  border-radius: 50%;
  border: 1px solid rgba(240,240,250,0.3);
  background: transparent;
  /* contains a small chevron/triangle pointing down */
}

/* Outline headline text */
.headline-outline {
  -webkit-text-stroke: 1px rgba(240, 240, 250, 0.5);
  color: transparent;
  /* transitions to: */
}
.headline-solid {
  -webkit-text-stroke: 0px;
  color: #f0f0fa;
}
```

---

## NIKE "HUNGRY FOR MORE" SCROLLYTELLING
**Creator:** @karan.shares (Instagram)

### What it actually is
A scrollytelling site where the HERO IMAGE is a video of a cheetah running.
Scroll position controls the video playback — as you scroll, the cheetah runs.
The text builds letter by letter as scroll advances: `H` → `HU` → `HUN` → `HUNG` → `HUNGRY FOR MORE.`

### Key techniques
- `<video>` element, `currentTime` driven by scroll position (not play/pause)
- Text reveals character by character via JavaScript span wrapping
- Full-bleed video: `object-fit: cover; width: 100vw; height: 100vh`
- White bold sans-serif overlaid directly — no background, no shadow behind text
- Below the video section: clean white background, product grid

### Product Grid Style
- White `#ffffff` background
- Clean 3-column grid of shoe renders on white cards — NO shadows
- Price in small gray text (`₹13,995`) — small, unobtrusive
- Section label: `"Best of Air Max"` in small sans-serif
- Below: wide panoramic image with forest/nature + Nike swoosh floating in sky center
- `"STEP INTO WHAT FEELS GOOD"` centered, black, no background
- Dark pill button: `"Find Your Size"` — black, 9999px radius, white text

### Product Detail Page Style
- `"NIKE AIR MAX PULSE"` in large serif-ish display
- White background, wide body text
- Two dark pill CTAs side by side

---

## MICHELANGELO DAVID SITE (neuwebstudio 3D Slider)
**Creator:** @neuwebstudio

### What it is
A slider where you drag left/right to reveal different 3D "scenes" — each scene is a full-screen
image with a subject (statue, product, etc.) against a dramatic background.

### Visual style
- Background: Deep forest green with rolling hills — dark, moody
- Statue: White marble Michelangelo David, lit from the right
- Greek columns frame the left edge
- Nav at top: `Paintings | Collection | Sculpture` + pill CTA `Contact` (outline pill)
- Bottom right: editorial serif type — `"Michelangelo"` (small light italic) above `"David"` (large bold serif)
- Small pill CTA: `"Discover"` — dark background, tiny
- The NEXT scene (dragging to reveal): shows Nike branding

### Typography
- Mixed serif + sans: small label in light italic serif, main title in heavy serif
- NOT all caps — editorial, magazine-style
- Body: dark background so text is white

---

## GREEN EATS (neuwebstudio Exploding Objects)
**Creator:** @neuwebstudio

### What it is
A restaurant site. On the hero, a dark sphere sits in the center of a cream/sage background.
The sphere has food inside. When triggered (hover or click), the food EXPLODES outward —
each ingredient flies to a position around the sphere with a label and kcal count.

### Visual style
- Background: `#f0ede4` cream / sage green — very light, natural
- Site name: `"GREEN EATS"` in massive bold condensed green type — `#1a5c1a` dark green
- Nav: `ORDER | BEVERAGES | KITCHEN | GREENS | SALADS | SANDWICH | TEAM` — thin, uppercase
- Center: large black sphere (the "container" ingredient)
- After explode: ingredients arranged radially (avocado top-left, spinach top-right, etc.)
- Labels: ingredient name in bold green caps, kcal in gray below
- Very flat design — no shadows, cream bg, 2D feel despite the animation

---

## JERRYTHEWEBDEV LUXURY YACHT SITE
**Creator:** @jerrythewebdev (Instagram)

### Hero
- Full-bleed sunset ocean photography — ship silhouette approaching camera
- Text stack bottom-left:
  - Small label: `"WHERE BLUE WATER MEETS"` (thin, spaced)
  - Large bold: `"UNRIVALED LUXURY"` (bigger, cyan accent on "BLUE" and "UNRIVALED")
- Body text: `"CRAFTED FOR THOSE WHO DEMAND MORE FROM THE SEA"` — centered, spaced

### Interior scroll
- Close-up yacht hull photography (reflective white surface, dramatic angle)
- Category cards: `"Blue Deck Accents"` — small white cards with product image + name + arrow link
- Split layout: full-bleed photo LEFT, white product cards RIGHT
- Cards: white bg, clean, no heavy shadows, arrow-link navigation

---

## THE DIGITAL OASIS (filatov.design x Spline/Omma)

### What it looks like
- Pure `#000000` black background
- **Hero**: glowing, moving grass/fur texture — like a field of luminous grass, rendered in 3D, olive/yellow-green color
- Text overlay: `"The"` in clean sans, `"Digital"` in *italic serif* (mixed typefaces — key detail!), `"Oasis"` in clean sans
- This mixing of serif italic + sans is the editorial signature
- Tagline below: `"we believe the next era of technology won't be built in sterile offices — it will be grown, like a forest, from living [things]"` — lowercase, light weight, poetic
- CTA label: `"no code"` in monospace/code style

### Porsche 911 Turbo scene (also in this series)
- Pure `#000000` background
- Top left small text: `"TURBO 930 / ARCHIVE"` — tiny, monospace-ish, uppercase
- Center: 3D Porsche 911 side profile — silver/blue tint, beautifully lit
- Bottom left text stack: `"BORN TO\nDOMINATE"` in massive bold condensed white (2 lines)
- Stats row: `260 | 5.5s | 155` in large mono — horsepower, 0-60, top speed
- License plate detail: `S·KM930`
- Nav: tiny right-aligned: `OVERVIEW | SPECS | DESIGN | PRICE | ENQUIRE`

---

## WHAT THE GCAP SITE SHOULD ACTUALLY BE

### Structure
Each section is a PINNED full-viewport scene. Scroll advances the story INSIDE each scene.
Not sections that appear — ONE continuous experience that scrolls like a film.

### Hero
- Black background
- `"GLITCHCAP LABS"` in a heavy condensed font like **Barlow Condensed 800**
- Text appears as OUTLINE FIRST, then fills in on load
- Subtle particle field — NOT a constellation. More like the Corn Revolution's DNA glow effect.
- No gimmick glitch animation on the logo

### Font choices (correct)
```
Display: "Barlow Condensed", weight 700-800, ALL CAPS, letter-spacing -1px to 0px
Body: "Inter", weight 300-400, NOT uppercase, light and readable
Mono/Tech: "JetBrains Mono" for specs/data/code labels
```

### Colors (correct)
```
Background:      #000000 (pure black) or #050508 (near black)
Section tints:   #06060f, #07070d — very dark, barely different from black
Text primary:    #f0f0fa (spectral white — NOT #ffffff)
Text secondary:  #767d88 (cool slate gray)
Text muted:      #3a3a4a
Accent:          Use sparingly. Either teal #00e5cc or a very dark green like the Corn Revolution.
                 NOT bright cyan, NOT purple — too artificial
Outline text:    color: transparent; -webkit-text-stroke: 1px rgba(240,240,250,0.4)
```

### What makes these sites special
1. **Photography / 3D is the design** — not backgrounds, not colors. The visual is the content.
2. **Text lives on top of imagery** — no cards, no panels, no containers
3. **One circle button** — that's the ONLY CTA shape. No rectangles, no pills.
4. **Outline → solid text animation** — text starts as a ghost outline, fills in as scroll progresses
5. **Negative letter-spacing** on large display text — tight, compressed
6. **Zero shadows** — none anywhere. Not on buttons, not on cards.
7. **Zero cards** — text sits directly on the dark background or image
8. **Pinned sections** — scroll advances the SCENE, not the page

### For GlitchLand (pixel section)
Look at the pixel-agents repo screenshots — clean pixel art in a VS Code style panel.
Characters have defined sprites (different poses for typing/reading/idle).
This is not a grid of random colored cells — it needs actual pixel art character sprites.

---

## SESSION LOG — What we actually did

1. Extracted frames at 1fps from all 5 videos + cornvid (167 total frames)
2. Analyzed: Corn Revolution (53fr), 3abe video (15fr), sr1 jerrythewebdev (11fr),
   sr2 karan.shares Nike (15fr), sr3 neuwebstudio (10fr), sr4 filatov.design (63fr)
3. Fetched: terminal-industries.com, omma.build, neuwebstudio.com, igloo.inc, spline.design
4. Wrote BRIEF.md with all 7 sections
5. Loaded popular-web-designs skill, read SpaceX + ElevenLabs + RunwayML templates
6. Built prototype — **WRONG**. It used Bebas Neue, bright cyan/purple, particle gimmicks.
   Does not look like ANY of the reference sites. Scrap it.

## FILES IN THIS FOLDER
- BRIEF.md — project brief, 7 sections, all content
- NOTES.md — session notes, all inspo frame analysis
- INSPO_STYLE.md — THIS FILE. The actual visual DNA of the reference sites.
- frames/ — all 167 extracted frames from all videos
- site/index.html — THE BAD PROTOTYPE. Start fresh next session.
