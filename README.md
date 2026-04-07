# figma-style-report

A Claude skill that generates professional research reports styled after the **Figma India Developer Report 2026** — complete with bold typographic hierarchy, geometric illustrations, vibrant color blocks, and a full page system.

---

## What it does

Give Claude a topic and it generates a fully structured, print-ready HTML report that matches the visual language of Figma's editorial report style:

- **Cover page** — Electric blue full-bleed, bold white title, abstract 7 logo mark
- **Table of contents** — Near-black background, oversized white section entries
- **Introduction pages** — Dark background, large white body text
- **Section dividers** — Solid color pages (green/blue alternating), giant display title
- **Data pages** — Two-column layout: body text left, big % stat callouts right
- **Opportunity pages** — Yellow-green pill badge + "In practice:" callout box
- **Quote pages** — Salmon background, two-column quote grid, underlined attribution
- **Key takeaways** — 2×2 lavender card grid
- **Dark CTA page** — Full dark closing page with underlined CTA link

---

## Skill contents

```
figma-style-report/
├── SKILL.md                        # Core skill instructions + page specs
└── references/
    ├── style-guide.md              # Full CSS, color palette, chart patterns
    └── shapes-library.svg          # 1148 geometric shape compositions
```

---

## Design system

### Logo mark
An abstract deconstructed **7** — a horizontal bar + diagonal drop stroke. Color-adaptive per page background.

```svg
<!-- White version (dark pages) -->
<svg width="28" height="28" viewBox="0 0 36 36" fill="none">
  <line x1="6" y1="7" x2="28" y2="7" stroke="white" stroke-width="4.5" stroke-linecap="square"/>
  <line x1="26" y1="8" x2="11" y2="32" stroke="white" stroke-width="4.5" stroke-linecap="square"/>
</svg>
```

### Color palette

| Name | Hex | Used for |
|---|---|---|
| Electric Blue | `#3D3DF5` | Cover, blue section dividers |
| Electric Green | `#1DC55E` | Green section dividers, chart bars |
| Near-Black | `#111111` | TOC, intro, CTA pages |
| Yellow-Green | `#D6F25A` | Opportunity pill, In Practice box |
| Lavender | `#C4C0F0` | Key Takeaway cards |
| Soft Salmon | `#F9DDD5` | Quote page background |
| Dark Mustard | `#A07800` | 3-column stat cards |
| Sky Blue | `#00BFFF` | Horizontal bar chart fills |

### Shapes library
1148 geometric shape compositions using 4 colors (`#FFD313`, `#F61710`, `#0E448C`, `#08A887`). Colors are remapped to the report palette per section when used in illustrations.

### Chart types supported
- **Horizontal bar chart** — two variants (tall with big number, compact with label inside bar)
- **Stacked block / treemap** — proportional blocks with labels below
- **3-column stat cards** — equal-weight stats on mustard background
- **Inline stat grid** — number + label + ruled lines, no background

---

## How to install

1. Download `figma-style-report.skill`
2. Go to **Claude Settings → Skills**
3. Upload the `.skill` file

---

## How to use

Just ask Claude:

> "Write a report on [your topic]"
> "Create a research report in my style about [topic]"
> "Generate a figma style report on [topic]"

Claude will ask for:
- Report title / topic
- Author or organisation name
- Any real data/stats to include (optional)
- Number of sections (default: 3–4)

Output is a single self-contained `.html` file, print-ready via browser → Print → Save as PDF.

---

## Credits

Report style inspired by the **Figma India Developer Report 2026**.  
Shapes library from the [1300 Geometric Shapes Community pack](https://tool.graphics/shapes).  
Skill built by **Sharan Shivannanavar**.
