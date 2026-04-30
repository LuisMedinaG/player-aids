# Agent Instructions for player-aids

## Project Purpose
This repository contains printable player aids for board games, built with HTML + CSS.
The primary file is `river-of-gold-en-color.html` — a single-page letter-size (21.59 × 27cm)
player aid for the board game **River of Gold**.

## Tech Stack
- **HTML + CSS** only — no build tools, no JavaScript
- Fonts loaded from Google Fonts: `Cinzel` (headers) and `Noto Serif` (body)
- Print target: letter portrait, `@page { size: letter portrait; margin: 0; }`
- All dimensions in `cm` to match print output exactly

## File Structure
- `river-of-gold-en-color.html` — main player aid HTML
- `style.css` — all styles; shared by the HTML file
- `icons/` — PNG icons used inline in the HTML (`class="ic-sm"` or `class="ic"`)
- `assets/` — background texture image (`background.png`)
- `rules/` — rulebook PDFs and reference images for River of Gold
- `reference/` — additional reference materials (other games, card images)

## Design System
| Token | Value | Usage |
|---|---|---|
| `--crimson` | `#7A1525` | Section headers, numbered circles, borders |
| `--navy` | `#1B3A6B` | Keyword emphasis |
| `--forest` | `#1a4029` | Imperial Market references |
| `--gold` | `#C8922A` | Borders, dividers, table accents |
| `--sail` | `#1B5C6B` | Sail action header + Journey sub-section |
| `--sand` | `#EAD99A` | VP table top row background |
| `--ink` | `#2A1508` | Default body text |
| `--dim` | `#7A5A3C` | Notes, italic secondary text |

## Key CSS Classes
- `.sec` — section title (Cinzel 9pt, crimson, gold underline)
- `.setup-steps` — tighter-spaced steps for Setup section (7pt, gap 0.05cm)
- `.limit-bar` — prominent crimson-bordered constraints + anytime actions bar
- `.action-box / .action-head / .action-body` — action card structure
- `.ah-build / .ah-sail / .ah-deliver` — colored action headers
- `.btype-row / .btype` — building visitor-reward legend inside BUILD
- `.journey-sub / .journey-sub-head` — Completing Your Journey section inside SAIL
- `.emperor-note` — Emperor's Visit callout below action columns
- `.turn-box / .turn-col` — Your Turn 2-column box
- `.pct` — player-count table (Setup)
- `.vp-table / .vp-cell / .vp-top / .vp-bot` — Customers → VP scoring table
- `.ic-sm / .ic` — inline icon sizing

## Layout Structure (top to bottom)
1. **Setup** — two-col: board setup (steps 1–5 with tile-count table) | player setup (steps 6–10)
2. **Your Turn** — two-col turn-box: steps 1–2 | steps 3–4
3. **Actions** — sec + limit-bar + three-col (BUILD | SAIL | DELIVER) + emperor-note
   - BUILD includes building visitor-rewards legend (`.btype-row`)
   - SAIL includes Completing Your Journey (`.journey-sub`)
   - Emperor's Visit is a full-width callout below the three columns
4. **End Game & Final Scoring** — two-col: trigger + scoring steps | customers VP table

## Printing
Open `river-of-gold-en-color.html` in Chrome and use **Print → Save as PDF**.
- Set paper to **Letter**, margins **None**, **Background graphics ON**
- The page is sized exactly to letter at 27cm height (slightly shorter than full letter to avoid
  browser footer clipping)

## Rules Source
- `rules/River_of_Gold_Rulebook_English.pdf` — official English rulebook
- `rules/-_River_Of_Gold_Complete_Compact_Rules_V1.pdf` — compact rules reference

## Agent Guidelines
- Do NOT change page dimensions without confirming with the user
- Preserve all icon paths — icons live in `./icons/` and all referenced files exist
- When editing content, verify rules against the rulebook PDFs in `rules/`
- Prefer `cm` units for all sizing to stay print-accurate
- Do not add JavaScript or external dependencies
