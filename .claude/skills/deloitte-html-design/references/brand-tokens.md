# Deloitte Brand Tokens (HTML-native)

Official-adjacent tokens used across long pages and slide decks. Verify against
current Deloitte brand guidelines before client-facing delivery.

## Core palette

| Token | Hex | Usage |
|-------|-----|-------|
| Deloitte Green | `#86BC25` | Primary accent, CTAs, progress, phase icons, green dot |
| Green Dark | `#6B9619` | Hover states, pill text (light mode) |
| Green Soft | `#EEF6E0` | Accent backgrounds, pills, objectives (light) |
| Smoky Black | `#0F0B0B` | Ink, hero background, CTA bands |
| Body text | `#3D3D3D` | Paragraphs (light mode) |
| Muted | `#757575` | Secondary labels, counters |
| Border | `#E0E0E0` | Cards, dividers (light mode) |
| Warn | `#B45309` | Risk callouts |

Dark mode: invert surfaces to `#0F0B0B` / `#1A1818`; keep green accent unchanged;
set `--green-soft: #1E2A10` for tinted panels.

## Typography

- **Primary**: `system-ui, -apple-system, 'Segoe UI', Roboto, sans-serif` (Open Sans equivalent)
- **Mono**: `ui-monospace, 'SF Mono', Menlo, Consolas, monospace`
- No serif body copy — Deloitte digital uses clean sans throughout

## Signature elements

1. **Green dot** — after wordmark, as section label prefix, decorative hero/CTA accent
2. **Green underline** — 32–48px bar under `h2` headings
3. **Black hero band** — optional large circle motif at low opacity (12%), not gradients
4. **Sticky brand bar** — logo + session tag + theme toggle
5. **Phase icons** — filled green circles with white numerals (roadmap / phases)

## Logo (inline SVG)

```html
<svg class="logo" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 140 28" aria-label="Deloitte">
  <text x="0" y="22" font-family="system-ui,sans-serif" font-size="22" font-weight="700" fill="currentColor">Deloitte</text>
  <circle cx="132" cy="18" r="5" fill="#86BC25"/>
</svg>
```

Use `color: var(--logo-color)` on parent so dark mode inverts wordmark to white.

## Forbidden (unless user overrides)

- Generic GitHub-dark + cyan/purple neon
- Purple gradient hero formulas
- Emoji as icons
- Rounded cards with left colored border accent (Deloitte uses top/left green bar on callouts only)

## Theme toggle

- `data-theme="light"` (default) / `data-theme="dark"` on `<html>`
- Persist: `localStorage` key per file (e.g. `cloud-training-deloitte-theme`)
- Preview dark screenshots: append `?theme=dark` to `file://` URL

## CSS variable block (copy into `:root`)

See canonical implementation in `cloud-training/deloitte.html` lines 10–72.
