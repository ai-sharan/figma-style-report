---
name: figma-style-report
description: >
  Use this skill to create professional reports, research documents, or industry outlook documents
  styled exactly like the Figma India Developer Report 2026. Triggers whenever the user asks to
  "write a report", "create a research report", "make an industry report", "format a report",
  "generate an outlook report", "figma style report", or says anything like "create a report in
  my style" or "write a report like my reference". Always use this skill even if the user says
  "quick report" or gives only a topic — the skill handles the full formatting and structure automatically.
---

# Figma Style Report Skill

This skill produces professional reports matching the visual style and structure of the
**Figma India Developer Report 2026**. Always read this SKILL.md fully before generating
any report content or code. For typography and layout details, also read `references/style-guide.md`.

---

## Report Style Overview

The reference report is a **Figma-published industry research report**. It has a bold,
editorial design language with strong typographic hierarchy, vibrant color blocks, and
a clean white/black/accent color palette depending on page type. The output format is
an **HTML file** (single-file, self-contained, print-ready).

---

## Document Structure — Always Follow This Order

Every report must have these sections in this exact sequence:

1. **Cover Page** — Full-bleed colored background, large white title, year/edition label, logo
2. **Table of Contents** — Black background, white oversized section titles with page numbers left-aligned
3. **Introduction Pages** — Black background, large white body text, no header clutter
4. **Section Divider Pages** — Single bold color fill, black large section title, page number bottom-left
5. **Content Pages (Data/Findings)** — White background, black serif-weight headline, body text left column, big stat callouts right column, decorative illustration area
6. **Opportunity Pages** — White background, yellow-green label pill ("The opportunity"), large display headline, body text, yellow-green "In practice:" callout box
7. **Quote/Testimonial Pages** — White/salmon background, two-column quote layout, underlined attribution names
8. **Key Takeaways Page** — White background, display headline, 2×2 lavender card grid
9. **Closing/CTA Page** — White background, body text left, CTA button right

---

## Page Types — Detailed Specs

### 1. Cover Page
- Background: Bold electric blue (`#3D3DF5` or similar vivid blue)
- Title: White, very large (display size ~56–72px equivalent), Inter/sans-serif, bold weight
- Title sits top-left with generous padding
- Bottom-left: Company logo (use SVG placeholder or text)
- Bottom-right: Year label ("2026 report") in white, medium weight
- No body text on cover

### 2. Table of Contents
- Background: `#111111` (near-black)
- Each TOC entry = thin horizontal rule + page number (small, left) + section title (large, white)
- Section titles use display-scale type (~40–52px), normal weight
- Page numbers: small monospace or tabular numerals, top-left of each row
- Bottom footer: page number box (outlined square) + report title centered + logo right

### 3. Introduction / Body Text Pages
- Background: `#111111` (near-black)
- Text: White, large body (~22–26px), generous line-height (~1.6)
- Paragraphs separated by clear spacing (not ruled lines)
- No sidebars or columns — full-width text block with wide margins
- Footer: outlined page number box (bottom-left) + centered report title + logo (bottom-right)

### 4. Section Divider Pages
- Background: Solid vivid color — rotate through: Electric Green (`#1DC55E`), Electric Blue (`#3D3DF5`)
- Text: Black, display-scale (~64–80px), normal/light weight, top-left aligned
- No other content — pure typographic statement
- Footer: page number + logo (both colored for contrast on background)

### 5. Data / Findings Pages
- Background: White
- Layout: Two-column — left ~55% body, right ~45% stats
- Large black display headline at top (full width, ~40–52px)
- Left column: body text (~16–18px), black, with footnotes at bottom (small, numbered)
- Right column: Big percentage stats — number in ~80–96px bold, description below in small text (~13px), separated by thin horizontal rules
- Decorative illustration area (lower half, abstract geometric art block — can use SVG shapes or a colored block)
- Footer: outlined page number box + centered report title + logo

### 6. Opportunity Pages
- Background: White
- Top: Small pill/badge label — **"The opportunity"** — with yellow-green background (`#D6F25A`) and black bold text, rounded corners
- Headline: Large (~36–44px), normal weight, black, serif feel
- Body: Regular body text (~16px), black
- **"In practice:" callout box**: Yellow-green background (`#D6F25A` or `#E8F7A0`), rounded border (~8px), "In practice:" in bold, body text below — no border line, just filled box
- Optional: decorative illustration in lower half
- Footer: standard

### 7. Quote / Testimonial Pages
- Background: White OR soft salmon/peach (`#F9DDD5`)
- Top section: "The opportunity" pill + headline + body + salmon "In practice:" box
- Lower section: Two-column quote layout
  - Each column: opening curly quote + quote text (~18–20px, normal weight)
  - Attribution: Name in **bold + underlined**, Title below in regular, underlined
  - Light gray vertical divider between columns (optional)
- Footer: standard

### 8. Key Takeaways Page
- Background: White
- Display headline: ~44–52px, normal weight, black, top section
- Body paragraph below headline
- **2×2 card grid**: Each card has lavender/periwinkle background (`#C4C0F0`), card title in ~28–34px normal weight, body text in ~15px
- Cards use generous padding, no border radius or subtle border radius (~8px)
- Footer: standard

### 9. Closing / CTA Page
- Background: `#111111` dark (same as intro pages) — NOT white
- Large bold white display headline (~56px, bold)
- White body text (~22px), generous line-height
- CTA = white underlined text link (no pill button) at ~22px
- Footnotes at bottom in faded white (~13px, opacity 0.5)
- Footer: white page num box + white footer title + white 7 logo

---

## Typography Rules

| Element | Size | Weight | Color | Notes |
|---|---|---|---|---|
| Cover title | 56–72px | Bold | White | Display, sans-serif |
| TOC entries | 40–52px | Normal | White | On black bg |
| Section divider title | 64–80px | Normal/Light | Black | On colored bg |
| Page headline | 36–52px | Normal | Black | On white bg |
| Body text (dark bg) | 22–26px | Normal | White | Generous line-height |
| Body text (light bg) | 15–18px | Normal | Black | — |
| Stat number | 80–96px | Bold | Black | Right column |
| Stat label | 13–14px | Normal | Black | Below stat |
| Callout box text | 15–16px | Normal | Black | On yellow-green bg |
| Quote text | 18–20px | Normal | Black | — |
| Attribution name | 14–15px | Bold | Black | Underlined |
| Footnote | 12–13px | Normal | Black/Gray | Numbered |
| Footer center text | 12–13px | Normal | Black/Gray | Report title |
| Page number | 12–13px | Normal | — | Outlined box |

**Font stack**: `'Inter', 'Helvetica Neue', Arial, sans-serif`

---

## Color Palette

| Name | Hex | Used For |
|---|---|---|
| Electric Blue | `#3D3DF5` | Cover background, accent |
| Electric Green | `#1DC55E` | Section divider background |
| Near-Black | `#111111` | TOC/intro page backgrounds |
| White | `#FFFFFF` | Text on dark, content page bg |
| Black | `#000000` | Text on light pages |
| Yellow-Green | `#D6F25A` | Opportunity pill, In Practice box |
| Soft Salmon | `#F9DDD5` | Quote page bg, In Practice variant |
| Lavender | `#C4C0F0` | Key Takeaway cards |
| Light Salmon | `#F5C9BB` | In Practice box on quote pages |

---

## Layout & Spacing Rules

- **Page size**: A4 portrait — `794px × 1123px` at screen, or use `@page { size: A4; }` in CSS for print
- **Margins**: 56–72px on all sides for content pages; cover has no margin (full bleed)
- **Footer**: Always present. Contains: `[page num box]` (bottom-left) · `Report Title` (centered, small caps or regular) · `[Logo]` (bottom-right)
- **Page number box**: Small outlined rectangle (~28×28px), page number inside, bottom-left
- **Logo**: Bottom-right corner, small (~24px height)
- **Horizontal rules**: Used sparingly — thin (1px), black or dark gray — in TOC and stat pages only

---

## Output Format

**Single self-contained HTML file. User prints via `cmd+P` in Chrome → Save as PDF.**

### Base CSS — always use exactly this

```css
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;700&display=swap');

*{box-sizing:border-box;margin:0;padding:0;}
body{font-family:'Inter','Helvetica Neue',Arial,sans-serif;background:#e0e0e0;display:flex;flex-direction:column;align-items:center;gap:24px;padding:24px;}

@page{size:A4;margin:0;}

@media print{
  body{display:block;background:white;padding:0;margin:0;
    -webkit-print-color-adjust:exact!important;
    print-color-adjust:exact!important;
    color-adjust:exact!important;}
  .page{box-shadow:none!important;width:210mm;height:296mm;margin:0;
    page-break-after:always;page-break-inside:avoid;break-inside:avoid;overflow:hidden!important;}
  .data-body-row,.cover-footer,.hbar-row{display:flex!important;flex-wrap:nowrap!important;}
}

.page{width:210mm;height:297mm;position:relative;background:white;
  box-shadow:0 4px 24px rgba(0,0,0,0.15);overflow:hidden;
  page-break-after:always;break-after:page;
  display:flex;flex-direction:column;}
```

### Footer — every page must have this

```css
.page-footer{display:flex;align-items:center;justify-content:space-between;padding:0 64px 40px;margin-top:auto;}
.pg-box{width:28px;height:28px;border:1.5px solid black;display:flex;align-items:center;justify-content:center;font-size:12px;}
.pg-box.white-box{border-color:white;color:white;}
.footer-title{font-size:12px;color:#555;letter-spacing:0.02em;}
.footer-title.white-text{color:rgba(255,255,255,0.6);}
```

```html
<div class="page-footer">
  <div class="pg-box [white-box]">01</div>
  <div class="footer-title [white-text]">Report Title</div>
  <svg width="28" height="28" viewBox="0 0 36 36" fill="none">
    <line x1="6" y1="7" x2="28" y2="7" stroke="[white|black]" stroke-width="4.5" stroke-linecap="square"/>
    <line x1="26" y1="8" x2="11" y2="32" stroke="[white|black]" stroke-width="4.5" stroke-linecap="square"/>
  </svg>
</div>
```

### Data page

```css
.page.data{padding:56px 64px 0;}
.data-headline{font-size:42px;font-weight:400;color:black;line-height:1.1;margin-bottom:36px;}
.data-body-row{display:flex;gap:48px;flex:1;}
.data-body-left{flex:1.1;font-size:16px;line-height:1.7;color:black;}
.data-body-left p+p{margin-top:18px;}
.data-stats-right{flex:0.85;display:flex;flex-direction:column;}
.stat-block{padding:20px 0;border-top:1px solid #ddd;}
.stat-block:first-child{border-top:none;}
.stat-number{font-size:86px;font-weight:700;color:black;line-height:1;margin-bottom:6px;}
.stat-label{font-size:13px;color:#333;line-height:1.5;max-width:180px;}
.illus-block{height:180px;margin-top:auto;display:flex;}
```

### How to print

Chrome → `cmd+P` → Destination: Save as PDF → Paper: A4 → Margins: None → ✅ Background graphics.

**Full working example:** `references/sample-report.html`

---

## Content Generation Rules

When the user gives a topic, Claude must:

1. **Infer the report sections** from the topic (3–5 content chapters + intro + takeaways)
2. **Write all report copy** — headlines, body paragraphs, stat callouts, opportunity framing, quotes (use realistic placeholder quotes if none provided)
3. **Create stat callouts** — extract or invent plausible quantitative findings (clearly marked as illustrative if not from real data)
4. **Write "In practice:" action items** — concrete, actionable, 2–3 sentences
5. **Write key takeaways** — 4 cards in 2×2 grid, each with a title and 2–3 sentence description
6. **Apply color rotation** for section dividers (blue → green → blue...)

---

## Step-by-Step Generation Process

When asked to make a report:

**Step 1**: Ask the user for:
- Report title / topic
- Organization or author name (for footer)
- Any real statistics or data to include (optional)
- Preferred accent color (or use defaults)
- Number of chapters/sections (default: 3–4)

**Step 2**: Plan the page sequence (list all pages with their type)

**Step 3**: Write the full HTML, section by section, following the page type specs above

**Step 4**: Validate — check every page has a footer, every section divider uses the right color, the TOC matches actual sections

**Step 5**: Save as `.html` and present to user

---

## Quality Checklist

Before finishing, verify:
- [ ] Cover has full-bleed background, white title, year label, logo
- [ ] TOC is on black background with oversized white entries
- [ ] Intro pages are on black background with large white text
- [ ] Every chapter opens with a full-color section divider page
- [ ] Data pages have the two-column layout (body left, stats right)
- [ ] Every "Opportunity" page has the yellow-green pill and In Practice box
- [ ] Key Takeaways page has the 2×2 lavender card grid
- [ ] Every page has a footer with page number box + report title + logo
- [ ] Single self-contained HTML file, no broken external links

---

## Reference Files

- `references/style-guide.md` — Extended typography, spacing tokens, CSS snippets for each page type
- `references/shapes-library.svg` — 1148 geometric shape compositions for illustrations
- `references/sample-report.html` — Complete working example of all 16 page types, use as template
