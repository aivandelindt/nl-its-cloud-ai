---
name: design-direction-advisor
description: >
  Run the Design Direction Advisor to produce 3 differentiated HTML visual
  directions when design needs are vague. Uses the 40-style HTML-native library
  (20 Web + 20 PPT), seconds roulette, real-world references, and top-designer
  logic. Use when the user invokes /design-direction-advisor or explicitly
  requests design direction exploration with $output_type and $project_name.
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
  Bash(date:*)
  Bash(npx:*)
  Bash(python3:*)
---

# Design Direction Advisor

When a user has design content but no style reference, this skill runs a
structured advisor workflow that produces **3 real HTML visual directions** the
user can compare side-by-side. The style library is ammunition to break model
bias toward safe minimalism — not a mandatory checklist.

## Inputs

- `$output_type`: `web` or `ppt` — selects which half of the 40-style library
- `$project_name`: directory name for outputs (e.g. `parrot-history-site`)

## Goal

Deliver 3 differentiated HTML demos at
`$project_name/design-demos/[logic-name].html` plus screenshots, so the user can
pick a direction based on **what they see**, not text descriptions alone.

**Success artifact**: 3 HTML files + 3 screenshots presented together, each
labeled with its logic (roulette style / reference case / designer name).

## When to Run

**Invoke only** when the user explicitly calls `/design-direction-advisor`
or requests this workflow by name.

## When NOT to Run

- User already gave Figma, screenshots, or brand guidelines → design from that
- User specified an exact style ("Apple Silicon keynote style") → execute directly
- Small utility tasks (HTML→PDF, minor edits) → skip this skill

## Style Library Reference

Read `references/design-styles.md` when you need style details.

**How the library works** (read the file for full entries):

1. Pick half by `$output_type`: Web → Web Style Library; PPT → PPT Style Library
2. **Temperature**: `bold / neutral / quiet`. Bold styles are the majority —
   the model's certainty bias leans quiet; the library pushes toward bold.
3. **Fidelity**: ≥90% blind-build; 70–90% main body OK, some details degrade;
   <70% must annotate which parts degrade to solid color blocks
4. **Fonts**: Use open-source alternatives listed per style (Inter, Geist, etc.)
5. **Positioning**: Library is "ammunition when stuck," not a must-pick list.
   When user gives content/brand/references, design grows from there — don't
   force-fit the library.

## Default Aesthetic Forbidden Zones

Users can override per their brand. Do not use these by default:

- ❌ **GitHub-dark lazy solution**: uniform deep-blue base (#0D1117) + generic
  cyan/purple neon glow — only this overused combo is banned, not all dark colors
- ✅ **Allowed dark styles**: cinema-grade dramatic lighting, warm cyberpunk
  (Ash Thorp orange/cyan), intentional dark palettes (Linear glow, black stage,
  CS50 candy stage)
- ❌ Aggressive purple-gradient universal formula
- ❌ Emoji as icons
- ❌ Rounded cards + left colored border accent (unless the brand uses it)
- ❌ Cover images with personal signature/watermark

AI-image-only styles (WebGL particles, hand-drawn illustration, cinematic
lighting) are **not in the default pool**. Use only when user confirms
image-generation capability.

## Steps

### 1. Detect Scope and Validate Inputs

Confirm `$output_type` (`web` | `ppt`) and `$project_name` are set. If missing,
ask once. Infer content topic from the user's message.

**Rules**:
- Theme names (coffee, parrots, history) are **content topics**, not brands —
  do not hunt for topic logos
- Named products/brands (Stripe, DJI, Claude) trigger logo requirements in Step 5

**Success criteria**: `$output_type` and `$project_name` are known; content
topic is understood.

### 2. Clarify Requirements [human]

Ask at most **3 questions** in one message:

- Target audience / core message / emotional tone / output format
- Project name, logo, brand colors, VI, fonts?
- Reference URLs, screenshots, or "just pick for me"?

**Rules**:
- If user does not respond → proceed with labeled assumptions; do not wait
- If user gives a specific brand with findable assets → note for Step 5, but
  continue this advisor workflow unless they also gave a complete style reference

**Success criteria**: Enough context to write a design spec, or assumptions are
explicitly labeled and workflow continues.

### 3. Advisor Restatement

Write ≥200 words restating: essence of the need, audience, scenario, emotional
tone, and unstated expectations. End with "Based on this, I'll build 3 different
real versions for you to compare" — **not** "which direction do you want?"

**Success criteria**: Restatement is ≥200 words and sets up visual comparison.

### 4. Write Design Spec

Write a **≥500-word design spec** — the single shared input for all 3 direction
passes. Must cover:

- What the product/project is
- Target audience and use scenario
- Core information and content sections (bulleted)
- Emotional tone and personality keywords
- **Output format and dimensions** (required — all 3 passes use the same size)
- Known constraints (brand colors, taboos, required elements)
- Image requirements (from Step 5 assessment)

Each pass works independently from this spec only — a thin spec makes all 3
directions drift.

**Success criteria**: Spec is ≥500 words and includes unified output dimensions.

### 5. Image and Logo Pre-fetch [human]

**Execution**: Direct — complete before direction passes.

Before generating visuals, answer: **Are images essential to the content?**

| Content type | Images needed? |
|---|---|
| Topics (animals, history, places, people, products) | Yes — almost always |
| Tools, data, docs, pure opinion | Maybe — judge and skip if not |
| Uncertain | Treat as content-required |

**If images required**, fetch real images first:

| Content type | Source priority |
|---|---|
| Museum / history / art / nature | Wikimedia Commons, Met Open Access, BHL |
| General lifestyle / scenes | Unsplash, Pexels |
| User's own product / brand | Official press kit, brand site |
| Named products in comparisons | Official logo per product (svgl → simpleicons → favicon) |

**Named product logo gate**: List every product/brand name appearing in the
design. Each must have an official logo embedded (base64 or local path) before
direction passes begin. One missing logo = stop and fetch. If truly unavailable,
use an honest placeholder labeled "logo pending."

**Image fetch fallback** (do not block the workflow):
1. Public domain miss → try Unsplash/Pexels
2. Still nothing → ask if user has image-generation capability
3. Still nothing → honest placeholder, label "image pending," continue

Embed fetched images as base64 or local paths for reuse across all 3 passes.
Content-required images must not be replaced with CSS color blocks.

**Human checkpoint**: Present fetched images/logos (or placeholders with
labels) and **wait for user confirmation** before Step 6.

**Success criteria**: User confirmed image set, or confirmed placeholders are
acceptable to proceed.

### 6a. Direction Pass 1 — Seconds Roulette

**Execution**: Direct (serial pass 1 of 3)

Run the roulette to force a non-minimal style:

```bash
# macOS / Linux
SECONDS=$(date +%S)
STYLE_NUM=$(( 10#$SECONDS % 20 + 1 ))
echo "Style #$STYLE_NUM"
```

**Rules**:
- Must run `date +%S` — no mental random picking
- `$output_type=web` → count styles in **Web Style Library** section (1–20, document order)
- `$output_type=ppt` → count styles in **PPT Style Library** section (1–20, document order)
- Read `references/design-styles.md` for the selected style's Visual DNA,
  HTML implementation, and fonts
- Fidelity <70% → annotate in output which parts degrade to solid color blocks

Build one complete HTML file using the user's **real content** (not Lorem ipsum).

Save to: `$project_name/design-demos/roulette.html`

Screenshot (cross-platform):

```bash
npx playwright screenshot "file://$(pwd)/$project_name/design-demos/roulette.html" \
  "$project_name/design-demos/roulette.png" \
  --viewport-size=1440,900
```

For PPT output type, use `--viewport-size=1920,1080`.

**Success criteria**: `roulette.html` exists, screenshot captured, style number
and name documented.

### 6b. Direction Pass 2 — Real-World Reference

**Execution**: Direct (serial pass 2 of 3)

**Memory isolation**: Do not reference Pass 1 output. Read only the design spec.

1. Pick 1 real site/deck known for exceptional design in this domain
   (Awwwards, CSS Design Awards, FWA, Apple Design Award winners)
2. `WebSearch` to verify the case exists and understand its design language
3. Extract: palette, typography, layout, signature elements
4. Migrate that language onto the user's content

Save to: `$project_name/design-demos/reference.html`

Capture screenshot with same viewport rules as 6a.

**Success criteria**: `reference.html` exists, reference case named and verified
via search, screenshot captured.

### 6c. Direction Pass 3 — Best Designer

**Execution**: Direct (serial pass 3 of 3)

**Memory isolation**: Do not reference Pass 1 or 2. Read only the design spec.

Ask: "If budget were unlimited, which studio/designer is best suited for this
user and product?" (e.g. Pentagram, Collins, IDEO, Kenya Hara, Stripe design
team — match to product tone). Embody that designer's philosophy and design from
scratch for this user.

Save to: `$project_name/design-demos/designer.html`

Capture screenshot with same viewport rules as 6a.

**Success criteria**: `designer.html` exists, named designer/studio documented,
screenshot captured.

### 7. Present Three Directions

**Self-check before presenting**: Confirm exactly **3** `.html` files exist in
`$project_name/design-demos/`. Fewer than 3 = incomplete — finish missing
passes first.

Present all 3 screenshots together. For each, label:
- Which logic was used
- Specific style / reference case / designer name
- One sentence on why it fits the brief

**Success criteria**: User sees 3 labeled screenshots side-by-side.

### 8. User Selection [human]

User picks one direction, requests a hybrid ("roulette palette + designer
layout"), asks for tweaks, or requests a full re-run.

**Success criteria**: User has made a selection or given revision instructions.

### 9. Deepen Chosen Direction

Take the selected (or hybrid) direction into full production: polish HTML/CSS,
fill remaining content, replace any pending placeholders.

If user confirms image-generation capability, AI-image-only styles from
`design-styles.md` may be used — otherwise stay HTML-native.

**Success criteria**: Production-ready HTML deliverable based on user's choice.

## Serial Execution Notes

This skill runs all 3 direction passes **serially** in the same conversation.
Between passes:

- Re-read only the design spec — not prior HTML outputs
- Use distinct anchors: roulette style number / reference case name / designer name
- Never merge passes into one "safe average" direction

## Edge Cases

| Situation | Action |
|---|---|
| No subagent spawn available | Already serial by default — use memory isolation rules above |
| Image fetch fails | Degrade with labeled placeholder; do not block workflow |
| Named products in design | Logo gate in Step 5 is mandatory before passes |
| User gives brand assets mid-flow | Incorporate into spec; re-run affected passes if visuals already exist |
| All 3 directions look too similar | Re-run roulette (new `date +%S`) and reference pass with stricter temperature contrast |

## Cross-Platform Notes

- `date +%S` works on macOS and Linux. On Windows Git Bash, same command applies.
  Fallback: `echo $(( RANDOM % 20 + 1 ))` only if `date` fails.
- Playwright screenshots require `npx playwright` installed. If unavailable,
  ask user to open HTML files locally or install playwright.
- Use `file://` absolute paths for local screenshot commands.
