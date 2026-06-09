# Long-Form Single Page Pattern

Canonical example: `cloud-training/deloitte.html` (derived from `cloud-training/index.html` content).

## Layout anatomy

```
┌─ brand-bar (sticky) ─ logo | session tag | theme toggle ─┐
├─ hero-band (black) ─ eyebrow · accent line · h1 · lead ─┤
├─ container ──────────────────────────────────────────────┤
│  ├─ chapters nav (sticky) — horizontal section tabs      │
│  ├─ logos row (tool SVGs, relative paths)                │
│  ├─ sections (id=ch1…chN) — chapter num + h2 + content   │
│  └─ optional phase cards (accordion roadmap)             │
├─ cta band (black + green dot)                          │
└─ footer ─────────────────────────────────────────────────┘
```

## Content components

| Component | Class / pattern |
|-----------|-----------------|
| Chapter number | `.chapter-num` — large muted numeral |
| Section title | `h2` with green `::after` underline |
| Prose | `p.prose` — slightly larger body |
| Pull quote | `.pullquote` — green left border |
| Metrics | `.metric-row` / `.metric` |
| Code | `.code` > `.bar` + `pre` |
| Bento grid | `.bento` / `.cell` |
| Phase roadmap | `.phase-card` accordion with `.phase-icon` circles |
| Callout | `.callout` or `.card-accent` |

## Rules

- **Local-only assets**: system fonts, relative `../assets/logos/*.svg` from `design-demos/`
- **Real content only** — never Lorem ipsum when source exists
- **Preserve interactivity**: chapter nav IntersectionObserver, phase accordion, theme toggle
- **Dark mode**: invert surfaces; GitHub/Copilot logos may need `filter: brightness(0) invert(1)` in dark

## Workflow

1. Read source content file (e.g. `index.html`) — extract sections, not just CSS
2. Copy structure; replace `:root` tokens with Deloitte palette
3. Add brand bar + hero treatment; remove non-Deloitte gradients (e.g. green-teal hero)
4. Fix asset paths for output location
5. Screenshot: `npx playwright screenshot "file://$(pwd)/path.html" out.png --viewport-size=1440,900`

## Success artifact

One self-contained `.html` file + light/dark PNG previews.
