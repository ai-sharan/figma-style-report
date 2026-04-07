# Extended Style Guide — Report Style

Reference file for CSS snippets, spacing tokens, and per-page-type implementation details.
Read this when building the actual HTML output.

---

## CSS Base Setup

```css
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: 'Inter', 'Helvetica Neue', Arial, sans-serif;
  background: #e0e0e0;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 24px;
  padding: 24px;
}

@page {
  size: A4;
  margin: 0;
}

@media print {
  html, body {
    width: 210mm;
    margin: 0;
    padding: 0;
    background: white;
    gap: 0;
  }
  .page {
    box-shadow: none !important;
    margin: 0 !important;
    width: 210mm !important;
    min-height: 297mm !important;
    max-height: 297mm !important;
    overflow: hidden !important;
    page-break-after: always !important;
    break-after: page !important;
  }
}

.page {
  width: 794px;
  min-height: 1123px;
  position: relative;
  background: white;
  box-shadow: 0 4px 24px rgba(0,0,0,0.15);
  overflow: hidden;
  page-break-after: always;
  break-after: page;
  /* Print-safe sizing */
  -webkit-print-color-adjust: exact;
  print-color-adjust: exact;
}
```

---

## Per-Page CSS Classes

### Cover Page
```css
.page.cover {
  background: #3D3DF5;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  padding: 64px 64px 56px;
}

.cover-title {
  font-size: 64px;
  font-weight: 700;
  color: white;
  line-height: 1.1;
  max-width: 80%;
  margin-top: 8px;
}

.cover-footer {
  display: flex;
  justify-content: space-between;
  align-items: flex-end;
}

.cover-year {
  font-size: 22px;
  color: white;
  font-weight: 400;
}

.cover-logo svg {
  width: 40px;
  height: 40px;
  fill: white;
}
```

### Table of Contents
```css
.page.toc {
  background: #111111;
  padding: 56px 64px 48px;
  display: flex;
  flex-direction: column;
}

.toc-entry {
  display: flex;
  align-items: flex-start;
  gap: 32px;
  padding: 28px 0;
  border-top: 1px solid rgba(255,255,255,0.15);
}

.toc-entry:last-child {
  border-bottom: 1px solid rgba(255,255,255,0.15);
}

.toc-page-num {
  font-size: 13px;
  color: rgba(255,255,255,0.6);
  min-width: 28px;
  padding-top: 8px;
  font-variant-numeric: tabular-nums;
}

.toc-title {
  font-size: 44px;
  font-weight: 400;
  color: white;
  line-height: 1.1;
}
```

### Introduction / Dark Body Pages
```css
.page.intro {
  background: #111111;
  padding: 72px 80px 56px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.intro-body {
  font-size: 24px;
  font-weight: 400;
  color: white;
  line-height: 1.65;
}

.intro-body p + p {
  margin-top: 32px;
}

.intro-body .method-label {
  font-weight: 700;
  margin-bottom: 8px;
}
```

### Section Divider Pages
```css
.page.divider {
  padding: 64px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.page.divider.green { background: #1DC55E; }
.page.divider.blue  { background: #3D3DF5; }

.divider-title {
  font-size: 72px;
  font-weight: 400;
  color: black;
  line-height: 1.05;
  max-width: 75%;
}

/* For blue dividers, make text white */
.page.divider.blue .divider-title { color: white; }
.page.divider.blue .page-footer { color: white; }
```

### Data / Findings Pages
```css
.page.data {
  padding: 56px 64px 48px;
  display: flex;
  flex-direction: column;
}

.data-headline {
  font-size: 44px;
  font-weight: 400;
  color: black;
  line-height: 1.1;
  margin-bottom: 40px;
}

.data-body-row {
  display: flex;
  gap: 48px;
  flex: 1;
}

.data-body-left {
  flex: 1.1;
  font-size: 16px;
  line-height: 1.65;
  color: black;
}

.data-stats-right {
  flex: 0.9;
  display: flex;
  flex-direction: column;
  gap: 0;
}

.stat-block {
  padding: 20px 0;
  border-top: 1px solid #ddd;
}

.stat-block:first-child { border-top: none; }

.stat-number {
  font-size: 88px;
  font-weight: 700;
  color: black;
  line-height: 1;
  margin-bottom: 8px;
}

.stat-label {
  font-size: 13px;
  color: black;
  line-height: 1.5;
  max-width: 180px;
}

.data-footnotes {
  font-size: 12px;
  color: #555;
  margin-top: 16px;
  border-top: 1px solid #eee;
  padding-top: 8px;
}

/* Inline percentage lists */
.pct-row {
  display: flex;
  gap: 40px;
  margin: 20px 0;
}
.pct-item .pct-num {
  font-size: 36px;
  font-weight: 700;
}
.pct-item .pct-label {
  font-size: 13px;
  color: #333;
}

/* Illustration area placeholder */
.illustration-block {
  height: 220px;
  background: linear-gradient(135deg, #1DC55E 0%, #3D3DF5 50%, #FF6B6B 100%);
  border-radius: 0;
  margin-top: auto;
  display: flex;
  align-items: center;
  justify-content: center;
  overflow: hidden;
}
```

### Opportunity Pages
```css
.page.opportunity {
  padding: 56px 64px 48px;
  display: flex;
  flex-direction: column;
}

.opp-pill {
  display: inline-block;
  background: #D6F25A;
  color: black;
  font-weight: 700;
  font-size: 13px;
  padding: 6px 14px;
  border-radius: 4px;
  margin-bottom: 32px;
  width: fit-content;
}

.opp-headline {
  font-size: 40px;
  font-weight: 400;
  color: black;
  line-height: 1.15;
  margin-bottom: 24px;
  max-width: 72%;
}

.opp-body {
  font-size: 16px;
  line-height: 1.65;
  color: black;
  max-width: 68%;
  margin-bottom: 32px;
}

.in-practice-box {
  background: #E8F7A0;
  border-radius: 8px;
  padding: 24px 28px;
  max-width: 85%;
}

.in-practice-box .label {
  font-weight: 700;
  font-size: 15px;
  margin-bottom: 10px;
}

.in-practice-box p {
  font-size: 15px;
  line-height: 1.6;
  color: black;
}

/* Salmon variant (for quote pages) */
.in-practice-box.salmon {
  background: #F5C9BB;
}
```

### Quote / Testimonial Pages
```css
.page.quotes {
  background: #F9DDD5;
  padding: 56px 64px 48px;
  display: flex;
  flex-direction: column;
}

/* Top section same as opportunity page */

.quote-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 40px;
  margin-top: 40px;
}

.quote-card {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.quote-text {
  font-size: 18px;
  line-height: 1.6;
  color: black;
  margin-bottom: 40px;
}

.quote-author-name {
  font-size: 14px;
  font-weight: 700;
  text-decoration: underline;
  color: black;
}

.quote-author-title {
  font-size: 13px;
  text-decoration: underline;
  color: black;
}
```

### Key Takeaways Page
```css
.page.takeaways {
  padding: 56px 64px 48px;
  display: flex;
  flex-direction: column;
}

.takeaways-headline {
  font-size: 48px;
  font-weight: 400;
  color: black;
  line-height: 1.1;
  margin-bottom: 20px;
  max-width: 80%;
}

.takeaways-body {
  font-size: 16px;
  line-height: 1.65;
  color: black;
  max-width: 75%;
  margin-bottom: 36px;
}

.cards-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 16px;
  flex: 1;
}

.takeaway-card {
  background: #C4C0F0;
  border-radius: 8px;
  padding: 28px 28px 32px;
}

.card-title {
  font-size: 28px;
  font-weight: 400;
  color: black;
  line-height: 1.15;
  margin-bottom: 16px;
}

.card-body {
  font-size: 15px;
  line-height: 1.6;
  color: black;
}
```

### Footer (used on all light-background pages)
```css
.page-footer {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-top: auto;
  padding-top: 16px;
}

.page-num-box {
  width: 30px;
  height: 30px;
  border: 1.5px solid black;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 12px;
  font-weight: 400;
}

.footer-title {
  font-size: 12px;
  color: #444;
  letter-spacing: 0.02em;
}

.footer-logo {
  font-size: 20px; /* or inline SVG */
}

/* Dark page footer variant */
.page-footer.dark .page-num-box {
  border-color: white;
  color: white;
}
.page-footer.dark .footer-title { color: rgba(255,255,255,0.5); }
.page-footer.dark .footer-logo { color: white; }

/* Green divider footer */
.page-footer.on-green .page-num-box {
  border-color: black;
  color: black;
}
```

---

## Shapes Library — 1300 Geometric Shapes

A bundled SVG library (`references/shapes-library.svg`) contains **1148 grouped geometric shape compositions**, each using exactly **4 colors**. This is the authoritative source for all illustrations in reports.

### Shape Library Color Palette (the only 4 colors used)
| Name | Hex | Visual |
|---|---|---|
| Golden Yellow | `#FFD313` | Warm, energetic |
| Red | `#F61710` | Bold accent |
| Navy Blue | `#0E448C` | Deep, anchoring |
| Teal/Emerald | `#08A887` | Fresh, forward |

These 4 colors rotate across shapes. Each shape group uses 2–4 of them. When applying shapes to report pages, **remap these colors to the report's palette** — see color mapping table below.

### How to use the shapes library

The SVG is a 1000×13080px canvas, grid-arranged. Each shape group occupies a ~100×100px cell. To use a shape in a report:

1. Open `references/shapes-library.svg`
2. Pick a `<g clip-path="url(#clipN)">` group by index
3. Copy its `<path>` elements into your illustration SVG
4. **Adjust the coordinates** — subtract the group's y-offset so it starts at y=0
5. Remap fill colors to match the current page's section palette

### Color remapping — library → report palette

When placing a shape on a report page, substitute colors as follows depending on the section:

| Section | `#FFD313` → | `#F61710` → | `#0E448C` → | `#08A887` → |
|---|---|---|---|---|
| Green section | `#D6F25A` | `#1DC55E` | `#111111` | `#1A5C32` |
| Blue section | `#D6F25A` | `#3D3DF5` | `#111111` | `#C4C0F0` |
| White/data page | `#FFD313` | `#FF00CC` | `#111111` | `#1DC55E` |
| Dark/intro page | `#D6F25A` | `#3D3DF5` | `white` | `#1DC55E` |
| Salmon/quote page | `#D6F25A` | `#FF00CC` | `#111111` | `#1DC55E` |

### Clipping shapes to fit illustration areas

Each shape must be clipped to the illustration container. Use a `<clipPath>` + `<g>` wrapper:

```html
<svg viewBox="0 0 666 160" xmlns="http://www.w3.org/2000/svg" width="100%" height="160">
  <defs>
    <clipPath id="illus-clip">
      <rect x="0" y="0" width="666" height="160"/>
    </clipPath>
  </defs>
  <!-- Background fill -->
  <rect x="0" y="0" width="666" height="160" fill="#F5F5F5"/>
  <!-- Shape group from library, scaled and repositioned, clipped to container -->
  <g clip-path="url(#illus-clip)" transform="translate(80, 10) scale(1.4)">
    <!-- paste path elements here with remapped colors -->
    <path d="M0 0V100L50 50L100 100V0H0Z" fill="#D6F25A"/>
    <path d="M33 33C33 23 41 15 50 15C59 15 67 23 67 33H50H33Z" fill="#1DC55E"/>
  </g>
</svg>
```

### Shape selection guide

The library has 1148 shapes. Here are recommended index ranges by visual character:

| Index range | Character |
|---|---|
| 0–100 | Simple 2-path compositions — triangles, arcs, chevrons |
| 100–300 | 4-path interlocking geometric combos |
| 300–500 | Curved/organic shapes — semicircles, teardrops, crescents |
| 500–700 | Complex layered compositions — nested shapes |
| 700–900 | Angular/sharp shapes — arrows, stars, diamonds |
| 900–1148 | Mixed organic + geometric combos |

### Quick sample shapes (ready to use, coordinates normalized to 0,0)

**Shape A — Arrow/chevron (from index 0)**
```html
<path d="M0 0V100L50 50L100 100V0H0Z" fill="#FFD313"/>
<path d="M33 33C33 23 41 15 50 15C59 15 67 23 67 33H50H33Z" fill="#F61710"/>
```

**Shape B — Step blocks (from index 100)**
```html
<path d="M0 0H25L50 50H25L0 0Z" fill="#08A887"/>
<path d="M50 100H25L0 50H25L50 100Z" fill="#FFD313"/>
<path d="M100 0V25L50 50V25L100 0Z" fill="#F61710"/>
<path d="M100 50V75L50 100V75L100 50Z" fill="#0E448C"/>
```

**Shape C — L-shapes (from index 190)**
```html
<path d="M100 0V50L0 100V0H100Z" fill="#F61710"/>
<path d="M100 100H50L0 0H100V100Z" fill="#0E448C"/>
```

**Shape D — Interlocking arcs (from index 475)**
```html
<path d="M0 0H50V25L25 50L0 25V0Z" fill="#0E448C"/>
<path d="M0 100V50H25L50 75L25 100H0Z" fill="#08A887"/>
<path d="M100 0V50H75L50 25L75 0H100Z" fill="#FFD313"/>
<path d="M100 100H50V75L75 50L100 75V100Z" fill="#F61710"/>
```

When using these shapes, always:
1. Wrap in a `<clipPath>` to contain them in the illustration area
2. Use `transform="translate(x,y) scale(n)"` to position and size them
3. Remap colors per the section color table above

---

## Common Inline Data Patterns

There are **three chart types** used in this report style. Use the right one based on what the data shows.

---

### Chart Type 1 — Horizontal Bar Chart (% value = bar width, label right)

Used when showing a ranked list of items with a percentage each.
The colored bar fills left-to-right proportionally. The label sits in the gray area to the right.
% number is displayed INSIDE the bar on the right edge OR to the right of the bar depending on variant.

**Variant A — Number inside bar, label outside right** (Image 2 style: blue bars, number right of bar)
```html
<style>
.hbar-wrap { display:flex; flex-direction:column; gap:8px; margin:20px 0; }
.hbar-row { display:flex; align-items:center; background:#F0F0F0; height:56px; position:relative; }
.hbar-fill { height:100%; display:flex; align-items:center; padding-left:16px; font-size:15px; color:black; white-space:nowrap; overflow:hidden; }
.hbar-fill.blue { background:#00BFFF; }
.hbar-fill.green { background:#1DC55E; }
.hbar-num { font-size:36px; font-weight:400; color:black; padding:0 16px; min-width:90px; text-align:right; }
</style>

<div class="hbar-wrap">
  <div class="hbar-row">
    <div class="hbar-fill blue" style="width:61%">Save time on routine coding tasks</div>
    <div class="hbar-num">61%</div>
  </div>
  <div class="hbar-row">
    <div class="hbar-fill blue" style="width:59%">Improve code quality and reduce errors</div>
    <div class="hbar-num">59%</div>
  </div>
  <div class="hbar-row">
    <div class="hbar-fill blue" style="width:56%">Free up time for higher-value work</div>
    <div class="hbar-num">56%</div>
  </div>
  <div class="hbar-row">
    <div class="hbar-fill blue" style="width:55%">Learn new frameworks faster</div>
    <div class="hbar-num">55%</div>
  </div>
</div>
```

**Variant B — Number inside bar top-left, label in gray area right** (Image 1 style: tall blue bars)
```html
<div class="hbar-wrap">
  <div class="hbar-row" style="height:120px; align-items:flex-start;">
    <div class="hbar-fill blue" style="width:73%; height:100%; align-items:flex-start; padding-top:16px; font-size:88px; font-weight:400;">73%</div>
    <div style="flex:1; height:100%; display:flex; align-items:center; justify-content:flex-end; padding-right:20px; font-size:14px; text-align:right; color:black;">Individual workflows<br>and productivity</div>
  </div>
  <div class="hbar-row" style="height:120px; align-items:flex-start;">
    <div class="hbar-fill blue" style="width:72%; height:100%; align-items:flex-start; padding-top:16px; font-size:88px; font-weight:400;">72%</div>
    <div style="flex:1; height:100%; display:flex; align-items:center; justify-content:flex-end; padding-right:20px; font-size:14px; text-align:right; color:black;">Tools they use at work</div>
  </div>
  <div class="hbar-row" style="height:120px; align-items:flex-start;">
    <div class="hbar-fill blue" style="width:69%; height:100%; align-items:flex-start; padding-top:16px; font-size:88px; font-weight:400;">69%</div>
    <div style="flex:1; height:100%; display:flex; align-items:center; justify-content:flex-end; padding-right:20px; font-size:14px; text-align:right; color:black;">Capabilities of the<br>features they build</div>
  </div>
</div>
```

**Key rules for horizontal bar charts:**
- Background of the full row: `#F0F0F0` (light gray)
- Bar colors: Electric Blue `#00BFFF` or Electric Green `#1DC55E` depending on section
- Bar width = the actual percentage value as a CSS width %
- Bars decrease in width going down (always sorted descending)
- No border, no border-radius — clean rectangular edges
- Gap between rows: 6–10px (white gap, not a line)
- Label text: 13–15px, black, right-aligned in the gray remainder area

---

### Chart Type 2 — Stacked Block / Treemap Chart

Used when showing how a whole breaks into proportional parts (e.g. "At what stage do developers collaborate?").
Blocks are proportional rectangles stacked/nested. Each block has its % number top-left inside the block.
Labels appear **below** each column, separated by thin vertical rules.

```html
<style>
.treemap-wrap { display:flex; flex-direction:column; background:#F0F0F0; position:relative; margin:20px 0; }
.treemap-blocks { display:flex; align-items:flex-end; width:100%; height:380px; }
.treemap-block { display:flex; align-items:flex-start; padding:16px; font-size:72px; font-weight:400; }
.treemap-block.green-bright { background:#1DC55E; color:black; }
.treemap-block.green-dark   { background:#145A32; color:white; }
.treemap-block.green-light  { background:#D6F25A; color:black; }
.treemap-block.gray-bg      { background:#F0F0F0; color:black; font-size:14px; align-items:flex-start; padding-top:12px; }
.treemap-labels { display:flex; border-top:1px solid #ccc; }
.treemap-label  { flex:1; padding:16px 12px 8px; font-size:13px; color:#333; text-align:center; border-right:1px solid #ccc; }
.treemap-label:last-child { border-right:none; }
</style>

<div class="treemap-wrap">
  <div class="treemap-blocks">
    <!-- Column widths represent proportion of respondents -->
    <div style="display:flex;flex-direction:column;width:45%;height:100%;">
      <div class="treemap-block green-bright" style="height:55%;width:100%;">43%</div>
      <div class="treemap-block green-dark" style="height:30%;width:100%;font-size:52px;">28%</div>
      <div class="treemap-block green-light" style="height:15%;width:60%;font-size:40px;">18%</div>
    </div>
    <div class="treemap-block gray-bg" style="width:55%;height:100%;font-size:14px;">11%</div>
  </div>
  <div class="treemap-labels">
    <div class="treemap-label">At problem<br>definition</div>
    <div class="treemap-label">After problem<br>is defined</div>
    <div class="treemap-label">After requirements<br>are final</div>
    <div class="treemap-label">Other</div>
  </div>
</div>
```

**Key rules for stacked block charts:**
- Overall container bg: `#F0F0F0`
- Use 2–3 shades of the section's accent color (bright → dark → light/yellow-green)
- % number sits top-left inside each block, large font (proportional to block size)
- When a block is very small, reduce font size accordingly
- Labels below separated by thin `1px #ccc` vertical rules
- Smallest/lowest % block may use yellow-green `#D6F25A` as contrast

---

### Chart Type 3 — Simple Styled List (text + bold %)

Used for brief ranked findings inline with body text. No bars, just bold numbers leading each line.

```html
<ul style="list-style:none;padding:0;margin:16px 0;">
  <li style="padding:10px 0;border-bottom:1px solid #eee;font-size:16px;">
    <strong>32%</strong> Balancing technical feasibility with design expectations
  </li>
  <li style="padding:10px 0;border-bottom:1px solid #eee;font-size:16px;">
    <strong>25%</strong> Designers' limited understanding of development workflows
  </li>
  <li style="padding:10px 0;font-size:16px;">
    <strong>22%</strong> Issues with handoff artifacts like design files or specs
  </li>
</ul>
```

---

## Complete Color Palette — All Pages

Every color observed across all 25 pages of the reference PDF:

### Page Backgrounds
| Name | Hex | Page |
|---|---|---|
| Electric Blue | `#3D3DF5` | Cover, blue section dividers |
| Electric Green | `#1DC55E` | Green section dividers, green bar charts |
| Near-Black | `#111111` | TOC, intro pages, CTA closing page |
| White | `#FFFFFF` | Data pages, opportunity pages, takeaways |
| Soft Salmon | `#F9DDD5` | Quote/testimonial page background |

### Text Colors
| Name | Hex | Used for |
|---|---|---|
| Black | `#000000` | All body text on light pages |
| White | `#FFFFFF` | All text on dark/colored pages |

### Chart & Data Visualization Colors
| Name | Hex | Used for |
|---|---|---|
| Sky Blue (chart bars) | `#00BFFF` | Horizontal bar charts — AI/productivity sections |
| Electric Green (chart bars) | `#1DC55E` | Horizontal bar charts — collaboration sections |
| Dark Forest Green | `#1A5C32` | Stacked block chart, secondary/darker shade |
| Yellow-Green (small block) | `#D6F25A` | Stacked block chart, smallest block accent |
| Dark Mustard/Gold | `#A07800` | 3-column stat cards (page 19 — skills section) |
| Light Gray (chart bg) | `#F0F0F0` | Background of all bar chart rows, treemap container |

### Callout & UI Component Colors
| Name | Hex | Used for |
|---|---|---|
| Yellow-Green (pill) | `#D6F25A` | "The opportunity" pill badge |
| Yellow-Green (box) | `#E8F7A0` | "In practice" box — green/AI sections |
| Light Cyan (box) | `#C8F0F0` | "In practice" box — blue/AI workflow section (page 17) |
| Pale Cream (box) | `#F5F0C8` | "In practice" box — beige/warm sections (page 21) |
| Light Salmon (box) | `#F5C9BB` | "In practice" box — quote/salmon pages |
| Lavender (cards) | `#C4C0F0` | Key Takeaway 2×2 grid cards |
| Light Gray (quote card) | `#F0F0F0` | Single-quote card background (page 17) |

### Illustration Colors (abstract art blocks)
| Name | Hex | Used for |
|---|---|---|
| Electric Blue | `#3D3DF5` | Illustration blocks — blue accent |
| Electric Green | `#1DC55E` | Illustration blocks — dominant green |
| Magenta/Hot Pink | `#FF00CC` | Illustration blocks — vivid contrast |
| Orange | `#FF6B35` | Illustration blocks — warm accent |
| Purple/Violet | `#9B8FD4` | Illustration blocks — soft purple shapes |
| Dark Maroon | `#6B1A2A` | Illustration blocks — dark contrast |
| Yellow-Green | `#D6F25A` | Illustration blocks — accent |
| Black | `#111111` | Illustration blocks — anchor shapes |
| Lavender (light) | `#C4C0F0` | Illustration blocks — soft layer |
| Olive/Dark Gold | `#8B7320` | Illustration blocks — warm earth |

### Missing Page Type — Dark CTA Page (Page 24)
The closing/CTA page uses `#111111` dark background (same as intro pages), NOT white.
Large white display text, white body text, white underlined CTA link (no button pill).

```css
.page.cta-dark {
  background: #111111;
  padding: 64px 72px 56px;
  justify-content: space-between;
}
.cta-dark-headline {
  font-size: 56px;
  font-weight: 700;
  color: white;
  line-height: 1.08;
  margin-bottom: 40px;
}
.cta-dark-body {
  font-size: 22px;
  line-height: 1.65;
  color: white;
}
.cta-dark-link {
  font-size: 22px;
  color: white;
  text-decoration: underline;
  display: block;
  margin-top: 32px;
}
.cta-dark-footnote {
  font-size: 13px;
  color: rgba(255,255,255,0.5);
  margin-top: auto;
}
```

### Missing Stat Card Layout (Page 19 — 3-column gold cards)
Used when showing exactly 3 equal-weight stats side by side. Cards use dark mustard/gold background.

```html
<div style="display:grid;grid-template-columns:1fr 1fr 1fr;gap:10px;margin:24px 0;">
  <div style="background:#A07800;padding:24px 20px 28px;">
    <div style="font-size:56px;font-weight:400;color:black;line-height:1;margin-bottom:20px;">49%</div>
    <div style="font-size:14px;color:black;line-height:1.5;">Keeping up with emerging tech</div>
  </div>
  <div style="background:#A07800;padding:24px 20px 28px;">
    <div style="font-size:56px;font-weight:400;color:black;line-height:1;margin-bottom:20px;">49%</div>
    <div style="font-size:14px;color:black;line-height:1.5;">Developing communication and collaboration skills</div>
  </div>
  <div style="background:#A07800;padding:24px 20px 28px;">
    <div style="font-size:56px;font-weight:400;color:black;line-height:1;margin-bottom:20px;">48%</div>
    <div style="font-size:14px;color:black;line-height:1.5;">Mastering AI tools</div>
  </div>
</div>
```

### Missing Inline Stat Grid (Page 8 — no bars, ruled lines)
Used for tool usage stats — big number top, label below, thin top rule, no background color.

```html
<div style="display:grid;grid-template-columns:1fr 1fr 1fr;gap:0;margin:24px 0;">
  <div style="border-top:1px solid #ccc;padding:16px 0 24px;">
    <div style="font-size:48px;font-weight:400;color:black;line-height:1;margin-bottom:8px;">73%</div>
    <div style="font-size:13px;color:black;">Google Docs / Slides</div>
  </div>
  <div style="border-top:1px solid #ccc;padding:16px 0 24px;">
    <div style="font-size:48px;font-weight:400;color:black;line-height:1;margin-bottom:8px;">61%</div>
    <div style="font-size:13px;color:black;">Slack / Microsoft Teams</div>
  </div>
  <div style="border-top:1px solid #ccc;padding:16px 0 24px;">
    <div style="font-size:48px;font-weight:400;color:black;line-height:1;margin-bottom:8px;">45%</div>
    <div style="font-size:13px;color:black;">Figma</div>
  </div>
</div>
```

---

## Section Color Rotation

Chapters should alternate section divider colors:
- Chapter 1: Electric Green (`#1DC55E`)
- Chapter 2: Electric Blue (`#3D3DF5`)
- Chapter 3: Electric Green
- Chapter 4: Electric Blue
- ...and so on

---

## Logo — Abstract 7 Mark

The logo is a **deconstructed 7**: one horizontal bar across the top + one diagonal stroke dropping down-left. Always use this mark. Color adapts to the page background.

```html
<!-- White version — dark pages (TOC, intro, blue divider, cover) -->
<svg width="28" height="28" viewBox="0 0 36 36" fill="none" xmlns="http://www.w3.org/2000/svg">
  <line x1="6" y1="7" x2="28" y2="7" stroke="white" stroke-width="4.5" stroke-linecap="square"/>
  <line x1="26" y1="8" x2="11" y2="32" stroke="white" stroke-width="4.5" stroke-linecap="square"/>
</svg>

<!-- Black version — light pages (white bg, salmon, green divider) -->
<svg width="28" height="28" viewBox="0 0 36 36" fill="none" xmlns="http://www.w3.org/2000/svg">
  <line x1="6" y1="7" x2="28" y2="7" stroke="black" stroke-width="4.5" stroke-linecap="square"/>
  <line x1="26" y1="8" x2="11" y2="32" stroke="black" stroke-width="4.5" stroke-linecap="square"/>
</svg>
```

**Color rule by page type:**
| Page type | Logo stroke color |
|---|---|
| Cover (blue bg) | white |
| TOC (dark bg) | white |
| Intro (dark bg) | white |
| Section divider green | black |
| Section divider blue | white |
| Data page (white bg) | black |
| Opportunity (white bg) | black |
| Quotes (salmon bg) | black |
| Takeaways (white bg) | black |
| CTA (white bg) | black |
