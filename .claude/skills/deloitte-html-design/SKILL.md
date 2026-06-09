---
name: deloitte-html-design
description: >
  Apply Deloitte corporate branding to local-only HTML deliverables — long-form
  single pages and keyboard-navigable slide decks. Uses official-adjacent tokens
  (green #86BC25, black #0F0B0B, sans-serif), dark/light mode, green-dot motif,
  and patterns from cloud-training/deloitte.html and slides-deloitte.html. Use when
  the user asks for Deloitte styling, /deloitte-html-design, Deloitte-branded
  training pages, Deloitte slide decks, or converting index.html / slides.html
  content into Deloitte-branded HTML.
license: MIT
metadata:
  author: itcloud-training
  version: "1.0.0"
allowed-tools:
  Read
  Write
  Edit
  Grep
  Glob
  WebSearch
  Bash(npx:*)
---

# Deloitte HTML Design

Apply Deloitte corporate visual identity to **long-form single pages** and
**slide decks** as self-contained HTML files. No CDN, no React in output — vanilla
HTML/CSS/JS with system fonts and relative asset paths.

This skill executes a **known brand direction**. For open-ended style exploration
when no brand is specified, use `design-direction-advisor` instead.

## Inputs

- `$output_format`: `long-page` | `slide-deck` — required
- `$content_source`: path to existing HTML with the real content (e.g. `index.html`, `slides.html`)
- `$output_path`: destination file (e.g. `cloud-training/my-deck-deloitte.html`)
- `$title`: page/deck title shown in header and `<title>`
- `$deck_type`: `training` | `roadmap` | `custom` — required when `$output_format=slide-deck`
- `$session_tag`: optional eyebrow text (default: `IT Cloud · Enablement`)

## Goal

Deliver a production-ready Deloitte-branded HTML file plus light/dark PNG
screenshots. The output must be presentable to the IT Cloud Team without further
styling passes.

**Success artifacts**:
- One `.html` file at `$output_path`
- `$output_path` sibling or `design-demos/` PNG previews (light + dark)
- Dark/light toggle works in browser; theme persists via `localStorage`

## Reference files

Read before building:

| File | Purpose |
|------|---------|
| `references/brand-tokens.md` | Colors, typography, logo SVG, forbidden zones |
| `references/long-page.md` | Long-form layout anatomy and components |
| `references/slide-deck.md` | Deck chrome, primitives, navigation JS |
| `cloud-training/deloitte.html` | Canonical long-page implementation |
| `cloud-training/slides-deloitte.html` | Canonical full training deck |
| `cloud-training/ai-roadmap-deloitte.html` | Canonical focused roadmap deck |

## When to run

**Invoke when**:
- User specifies Deloitte branding, colors, or corporate style
- User asks to convert existing content to Deloitte HTML
- User wants a slide deck matching Deloitte long-page styling

**Do NOT invoke when**:
- User wants 3 competing visual directions → use `design-direction-advisor`
- User already supplied complete Figma/CSS spec → implement from spec directly
- Trivial CSS tweak on an existing Deloitte file → edit in place

## Steps

### 1. Detect scope and read source

Confirm `$output_format`, `$content_source`, and `$output_path`. If
`$output_format=slide-deck`, confirm `$deck_type`.

Read `$content_source` fully. Extract **real content** (headings, body copy, code
samples, phase data) — never replace with placeholder text when source exists.

Read `references/brand-tokens.md` for the token set.

**Rules**:
- Named tool logos (GitHub, Azure, VSCode, etc.) use existing SVGs under
  `cloud-training/assets/logos/` with paths adjusted for output location
- Deloitte wordmark: inline SVG from `brand-tokens.md` (not a fetched asset)

**Success criteria**: Output format, paths, and full content inventory are known.

### 2. Choose base pattern

| `$output_format` | Start from |
|------------------|------------|
| `long-page` | `cloud-training/deloitte.html` structure |
| `slide-deck` + `training` | `cloud-training/slides-deloitte.html` chrome |
| `slide-deck` + `roadmap` | `cloud-training/ai-roadmap-deloitte.html` chrome |
| `slide-deck` + `custom` | `slides-deloitte.html` chrome + user outline |

Read the matching reference file (`long-page.md` or `slide-deck.md`).

**Success criteria**: Base pattern selected; canonical file read for CSS/JS patterns.

### 3a. Build long-form page

**Execution**: Direct

1. Copy Deloitte `:root` / `[data-theme="dark"]` tokens from canonical file
2. Implement: sticky brand bar, black hero (eyebrow + green accent line + h1),
   chapter nav, sections, CTA, footer
3. Migrate all sections from `$content_source` preserving IDs, code blocks,
   phase accordions, and interactive JS
4. Apply Deloitte typography (sans only), green underlines on `h2`, green phase icons
5. Fix relative paths to logos and assets
6. Wire theme toggle with a **unique** `localStorage` key per output file
7. Support `?theme=dark` URL param for screenshot automation

**Success criteria**: Long page renders all source sections in Deloitte style with
working nav, accordion (if present), and theme toggle.

### 3b. Build slide deck

**Execution**: Direct

1. Implement deck chrome: header (logo, title, section tabs, counter, theme toggle),
   slide area, progress bar, footer nav
2. Create one `<section class="slide">` per slide with `data-section` for tab jumping
3. Map content from source:
   - **training**: 1:1 from `slides.html` SLIDES (20 slides typical)
   - **roadmap**: title + timeline + one slide per phase + wrap-up
   - **custom**: per user outline
4. Use deck primitives: `.card`, `.card-accent`, `.bullets`, `.code`, `.pill`,
   `.step-row`, `.timeline`, `.phase-badge`, `.exit-box`
5. Include navigation JS: `go()`, keyboard handlers, dots, progress fill
6. Unique `localStorage` theme key per deck file

**Rules**:
- Do not ship React or CDN dependencies in output
- Keep slides scrollable internally; body stays `overflow: hidden`
- Section tabs hidden on narrow viewports (`@media` breakpoint)

**Success criteria**: All slides navigable via keyboard, tabs, and prev/next;
content matches source; Deloitte styling consistent with long-page tokens.

### 4. Capture screenshots

**Execution**: Direct

```bash
cd "$(dirname "$output_path")"
npx playwright screenshot "file://$(pwd)/$(basename "$output_path")" \
  "$(basename "$output_path" .html)-light.png" \
  --viewport-size=1440,900

npx playwright screenshot "file://$(pwd)/$(basename "$output_path")?theme=dark" \
  "$(basename "$output_path" .html)-dark.png" \
  --viewport-size=1440,900
```

For slide decks prefer `1440,900`. For explicit PPT ratio use `1920,1080`.

If Playwright unavailable, tell user to open the file locally and note screenshots
are pending.

**Success criteria**: Light and dark PNG files exist beside the HTML output.

### 5. Present deliverable

Summarize for the user:
- Output file path and slide/section count
- How to open and navigate (← → Space for decks)
- Light/dark toggle location
- Relationship to canonical examples in `cloud-training/`

**Success criteria**: User can open, navigate, and switch themes without instructions
beyond the summary.

## Edge cases

| Situation | Action |
|-----------|--------|
| Content only in markdown/IDEA.md | Extract sections into HTML structure first |
| Output in `design-demos/` | Logo paths use `../assets/logos/` |
| User wants both page + deck | Run 3a and 3b as separate outputs |
| Conflicts with design-direction-advisor | This skill = known Deloitte brand; advisor = explore 3 directions |
| Official Deloitte assets unavailable | Use inline SVG wordmark + documented tokens; label if client needs official assets |

## Cross-platform notes

- `npx playwright screenshot` works macOS/Linux; use `file://` absolute paths
- `date` commands not required for this skill
- Theme preview via `?theme=dark` avoids needing Node Playwright API for dark shots
