# Slide Deck Pattern (Deloitte)

Canonical examples:
- Full training deck: `cloud-training/slides-deloitte.html` (20 slides, mirrors `slides.html`)
- Focused roadmap deck: `cloud-training/ai-roadmap-deloitte.html` (9 slides)

## Deck chrome (shared)

```
┌─ deck-header ─ logo | title | section-tabs | counter | theme toggle ─┐
├─ deck-main ─ absolute-positioned .slide sections (one .active) ──────┤
├─ progress-track ─ green fill ────────────────────────────────────────┤
└─ deck-footer ─ Prev | dot indicators | Next ───────────────────────┘
```

Viewport: full `100vh`, `overflow: hidden` on body. Each slide scrolls internally if needed.

## Slide structure

```html
<section class="slide" data-section="Phase 1">
  <div class="slide-inner">
    <div class="slide-label">Phase 1 · ~2 weeks</div>
    <h2>Slide title</h2>
    <div class="slide-body">…</div>
  </div>
</section>
```

First slide: add `active` class + `title-slide` on inner.

## Primitives

| Primitive | Usage |
|-----------|--------|
| `.card` | Bordered content block |
| `.card-accent` | Green left border + soft fill — objectives, takeaways |
| `.card-warn` | Amber left border — risks |
| `.pill` | Topic tags on title slide |
| `ul.bullets` | Checklists (green ✓) |
| `ul.bullets.risks` | Warnings (amber ⚠) |
| `.tag` | Monospace deliverable chips |
| `.step-row` + `.step-num` | Numbered flow steps |
| `.timeline` + `.tl-phase` | Roadmap overview (numbered circles) |
| `.phase-badge` | Large green circle with phase number |
| `.exit-box` | Exit criteria highlight |
| `.code` | Same as long-page code blocks |

## Navigation JS (required)

- `go(n)` toggles `.active` on slides
- Keyboard: `ArrowRight`, `Space` → next; `ArrowLeft` → prev
- Section tabs jump via `firstIndexOf(section)` on `data-section`
- Progress bar width = `(current+1) / total * 100%`
- Theme: separate `localStorage` key per deck file

## Deck types

### Full training deck (`$deck_type=training`)

- Map 1:1 from React/source slide list (`slides.html` SLIDES array)
- ~20 slides, 6 section tabs
- Preserve all code blocks, ladders, MCP diagrams

### Focused roadmap deck (`$deck_type=roadmap`)

- Extract adoption roadmap (Chapter VII / phase cards)
- Title + timeline overview + one slide per phase + wrap-up
- Each phase slide: objective, owners, deliverables, checklist, exit criteria, risks

### Custom deck (`$deck_type=custom`)

- User supplies slide outline; apply same chrome + primitives

## Screenshots

```bash
npx playwright screenshot "file://$(pwd)/$output.html" "$output-light.png" --viewport-size=1440,900
npx playwright screenshot "file://$(pwd)/$output.html?theme=dark" "$output-dark.png" --viewport-size=1440,900
```

For PPT-style 16:9: `--viewport-size=1920,1080`

## Rules

- **No CDN** — vanilla HTML/CSS/JS only (matches project constraint)
- **No React** in output — translate compiled slides to static HTML
- One `localStorage` theme key per file to avoid clashes between decks
- Section tab labels: shorten "Phase N" → "PN" when space is tight
