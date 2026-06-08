# Design Style Library: 20 Web Styles + 20 PPT Styles (HTML-Native First)

> **2026-06 Refactor**. Based on research reverse-engineered from the top 5 universally acknowledged best designs across the world's 10 major website types + 10 major presentation types (100 real cases total).
> The fatal flaw of the old 20-style "graphic/installation designer philosophy" library: bold styles were almost all AI-generation-only (particles/lighting/hand-drawn). **When users default to having no image-generation capability and default fully to HTML, the bold half collapses to zero, leaving only minimalism—this is the root cause of "default sameness."** Every style in this library is tagged with its **fidelity** under "pure HTML/CSS without image generation."
>
> ⚖️ **But remember the positioning**: This is **"ammunition to flip through when you have no ideas," not a "must-choose-from-here" checklist**. When the user provides content/brand/references, the design unfolds from there—don't force-fit the library. The skill's job is to help users avoid the worst, not to dictate what the design looks like—good design grows from the user's real needs.

## How to Use This Library

1. **First select the half-section by output type**: Building a webpage/landing page/official site → 20 Web Styles; building a PPT/deck/presentation → 20 PPT Styles.
2. **Temperature system**: Each style is tagged `bold / neutral / quiet`. **Bold styles intentionally make up the majority**—the model's certainty bias naturally leans toward quiet minimalism, so the library's ratio must push it toward bold.
   - Direction A (safe foundation) is chosen from quiet/neutral per the requirements; Direction B takes a different temperature to create contrast; **Direction C is force-injected with a bold style by the SKILL's "seconds roulette."**
   - ❌ Don't let all three directions land on "off-white + whitespace + one accent color"—that's the most common failure mode.
3. **Fidelity**: ≥90% can be done blindfolded; 70-90% main body achievable, individual details degraded; <70% (e.g. Memphis distressed textures) must **explicitly note which parts are degraded to solid color blocks** in the output, not pretend the original texture can be achieved.
4. **Fonts**: Each style gives open-source alternatives (Inter/Geist/Manrope/Space Grotesk/Fraunces/Playfair, etc.). Don't write paid fonts (Söhne/Circular, etc.).
5. Companion: The SKILL "Design Direction Advisor" Phases 3-5 use this library to propose 3 directions; `assets/showcases/` has a pre-built screenshot gallery.

---

## Web Style Library (20 Styles)

#### Bold Group

**Editorial Brutalism (giant Helvetica crushing tiny body text)** `bold · 98% fidelity`
- Reference: Bloomberg Businessweek (Richard Turley 2010-2014 redesign, executed by Code and Theory); the Neue Haas Grotesk lineage
- Suited for: media/content publishing, AI product launches, brand site heroes, research report covers, opinion-piece longform header images
- Visual DNA: Palette of pure black #000 + pure white #FFF + hyperlink blue #0000EE, accented with signal orange-red #FF433D / terminal green #00A33E. Font Helvetica/Neue Haas Grotesk, 120px+ giant headlines left-aligned with tight tracking directly crushing 14px small body text—extreme font-size contrast. Layout is a modular grid + 1px rule lines splitting columns, high information density deliberately leaving no whitespace. Signature elements: rule-line column splits, hyperlink-blue underlines, large black-and-white color blocks.
- HTML implementation: Pure CSS achieves a 1:1 reproduction. CSS Grid for the modular grid + border for rule-line column splits, clamp() for super-large responsive font sizes + tightened letter-spacing, system Helvetica/Arial stack or Inter fallback, hyperlinks directly #0000EE underlined. Zero asset dependency.
- Fonts: Inter (replacing Helvetica/Neue Haas Grotesk), code uses Geist Mono

**Neo-Brutalism clashing-color feed (thick black-stroked cards + high-saturation clashing colors)** `bold · 95% fidelity`
- Reference: The Verge 2022 redesign (in-house team, PolySans + Mānuka)
- Suited for: media/content sites, AI product aggregation pages, event landings, community ranking pages, Xiaohongshu-style info cards
- Visual DNA: Palette of electric purple #5200FF ~ magenta #E1306C high-saturation primary colors + bright yellow #F8E000 accent + pure black #08080D + white, large clashing color blocks deliberately not softened. Font contrast between geometric sans-serif large headings + serif body. Layout is card-based feed, 2-4px thick black strokes, hard color-block zoning, near-zero rounded corners. Signature elements: thick-stroked cards with hover clash-color flip, an unfinished-interface vibe.
- HTML implementation: A pure-CSS strength. border:3px solid #000 thick strokes + box-shadow hard offset shadow (4px 4px 0 #000) + grid/flex card feed + :hover toggling background clash-color flip. No 3D/lighting obstacles.
- Fonts: Space Grotesk (replacing PolySans) + any serif like Fraunces

**Memphis retro-collage maximalism (clashing blocks + offset stacking + retro fonts)** `bold · 72% fidelity`
- Reference: Gucci Vault concept store (Alessandro Michele); the Memphis design movement / Sagmeister's rebellious DNA
- Suited for: e-commerce concept stores, creative event pages, brand experimental campaigns, Y2K retro themes, holiday marketing pages
- Visual DNA: Palette of retro red / mustard yellow / royal blue / purple / olive green in large-area clashing juxtaposition + distressed beige warm base, intense and deliberately dissonant. Font mixing retro serif + decorative fonts, print texture, broken grid with offset stacking. Layout is anti-grid collage curation, modules of varying sizes scattered and overlapping, like wandering a digital room. Signature elements: clashing blocks, offset stacking, unconventional navigation easter eggs.
- HTML implementation: transform:rotate() for offset stacking + position:absolute overlap + high-saturation background clash-color blocks + retro Google Fonts. The genuine distressed texture cannot be reproduced in CSS—degrade to solid color blocks + mix-blend-mode/contrast filters to simulate texture; the geometric collage version holds up, the archival distressed version degrades.
- Fonts: DM Serif Display + Bungee (decorative) + Space Mono

**Candy-color raised 3D button gamification — Friendly Geometric Candy** `bold · 85% fidelity`
- Reference: Duolingo (Johnson Banks + Monotype, Feather Bold font); anti-Silicon-Valley minimalism
- Suited for: educational language learning, consumer app landings, gamified products, mass-market-friendly products, event registration pages
- Visual DNA: Palette of Duo green #58CC02 + duck yellow #FFC800 + sky blue #1CB0F6 candy high-saturation + white base, round and friendly. Font ultra-bold rounded (Feather Bold feel). Layout large rounded-corner cards, raised 3D buttons (hard bottom shadow = pressable feel), mascot slots + progress bubbles. Signature elements: 3px solid-bottom-shadow 3D buttons, press displacement animation, super-rounded corners.
- HTML implementation: Pure CSS. box-shadow:0 4px 0 hard bottom shadow for raised buttons + :active translateY(4px) removing shadow to simulate press, border-radius large rounding, solid colors. Mascot uses CSS geometric shapes or emoji placeholders when no image generation is available (slight degradation).
- Fonts: Baloo 2 / Nunito (ultra-bold rounded replacing Feather)

**Pure-CSS geometric illustration + responsive morphing easter egg — Pure-CSS Art** `bold · 80% fidelity`
- Reference: Lynn Fisher (lynnandtonic.com, pure-CSS art legend, covered in a dedicated Adobe article)
- Suited for: personal homepages, creative 404/easter-egg pages, playful brand landings, tech blog headers, designer self-showcases
- Visual DNA: Palette of 2-4 high-contrast flat surfaces (each breakpoint swaps the palette). Font bold geometric sans-serif headings. Layout core is "image morphs with viewport"—a set of CSS shapes recompose into different scenes at different breakpoints (e.g. a building shifting floor count with screen width). Signature elements: pure-CSS-drawn geometric illustration, breakpoint-driven reflow easter egg, zero images.
- HTML implementation: A pure-CSS showmanship battleground, zero assets is an advantage. div + border-radius/clip-path/transform/box-shadow stacking geometric shapes, @media breakpoints changing shape size/position/location for the morph. The difficulty lies in design conception rather than technique, but each shape must be carefully hand-crafted.
- Fonts: Rubik / Archivo (bold geometric replacing custom fonts)

**Giant-type black-and-white high-contrast fashion broadsheet — Bold Big-Type Editorial** `bold · 88% fidelity`
- Reference: Jacquemus official site / Rik Oostenbroek / Domestika; fashion-magazine broadsheets
- Suited for: fashion e-commerce, portfolios, media features, brand manifesto pages, video course covers, big-type research report versions
- Visual DNA: Palette of minimalist black-and-white + a single restrained accent color (nude pink #E8C4C0 or scarlet). Font super-large Display sans-serif / high-contrast serif, headlines filling the entire screen. Layout full-width grid, giant type vs. negative space tension, image-text 1:1 split. Signature elements: screen-dominating giant headlines, luxury-grade whitespace, left-right positional typesetting.
- HTML implementation: Pure CSS reproduces perfectly. clamp() giant type + CSS Grid full-width split + abundant padding whitespace + vh units letting headlines fill the viewport. Without images, use solid color blocks / text blocks to stand in for fashion shots (slight degradation but the layout holds).
- Fonts: Archivo Expanded / Anton (Display) + Playfair Display (high-contrast serif)

**Retro-futurist space catalog — Cosmic Retro-Futurism** `bold · 75% fidelity`
- Reference: Perplexity Comet browser launch site (The Brand Identity: Black/Blue/Cream; a 2001: A Space Odyssey vibe)
- Suited for: AI product launch sites, tech brand manifesto pages, event countdown pages, futuristic landings, concept launch events
- Visual DNA: Palette of pure black #0A0A0A + cream paper white #F0EAD8 + a touch of cobalt-peacock blue #2B4F91, low saturation like an old astronomical catalog. Font high-contrast serif (classical astronomical atlas feel) + whitespace. Layout line-drawn orbits / parabola SVGs, planet dots, cream base crushing black type, antique typesetting. Signature elements: SVG celestial orbit lines, cream + blue + black tricolor, retro serif large type, astronomical-catalog texture.
- HTML implementation: Pure CSS + SVG reproduces 80% of the static-version vibe. SVG path drawing orbital parabolas + CSS radial positioning of planet dots + tricolor variables + high-contrast serif. The gap is the full-screen video transition of "space falling to Earth" (the soul part)—degrade to CSS scroll parallax + SVG orbit rotation as an approximation.
- Fonts: Cormorant Garamond / EB Garamond (high-contrast serif) + Space Mono

**Cinematic sound-wave visualization — Cinematic Sound-Viz Dark** `bold · 72% fidelity`
- Reference: ElevenLabs; cinematic title sequences (Saul Bass-style minimalist motion) × audio engineering interfaces
- Suited for: audio/voice AI products, music-tech sites, podcast platforms, media launch pages, cinema-grade brand heroes
- Visual DNA: Palette of pure black #000 base + pure white text + blue-purple gradient accent waveform. Font large sans-serif headings, Saul Bass-style minimalist. Layout full-width dark field, sound-wave/spectrum visualization running throughout, giant headlines crushing waveforms, card feature zones. Signature elements: colored audio-waveform bands, cinematic title-sequence minimalism, high-contrast black-and-white + single gradient, sound-visualization motif.
- HTML implementation: Pure CSS + SVG reproduces 70% of the vibe (skeleton perfect, waveform is the degradation point). SVG polyline drawing static waveforms or arrays of unequal-height divs + CSS animation for "fake waveform" pulsing approximation. Gap: real-time-pulsing Web Audio/Canvas spectrum cannot be reproduced in pure CSS—the static version looks right, the dynamic soul can't be reproduced.
- Fonts: Inter / Sora (large sans-serif)

**Pixel-game side-scroller narrative — Pixel-Game Side-Scroller** `bold · 70% fidelity`
- Reference: Robby Leonardi's interactive resume (8/16-bit platformer action-game narrative, an homage to Nintendo SNES)
- Suited for: creative resumes/portfolios, playful brand campaigns, gamified landings, event easter-egg pages, personal fun homepages
- Visual DNA: Palette of retro-game segmented zones—forest green #4CAF50 grassland + sky blue #5DADE2, transitioning to space purple #2C2A4A, volcanic orange-red #E8743B, undersea teal #1ABC9C, each "level" swaps a set of high-saturation cartoon palettes. Font pixel font (8-bit feel) + bold sans-serif. Layout side-scroll/vertical-scroll level scenes, parallax layering, scroll-triggered displacement. Signature elements: per-level color swap, pixel aesthetic, parallax scroll, game-HUD-style UI.
- HTML implementation: Pure CSS + a little JS reproduces the skeleton (the original was HTML+CSS+jQuery, no WebGL). Parallax layering position + scroll displacement, image-rendering:pixelated, CSS frame-by-frame background-position for sprite animation, segmented background colors. Gap: original character/scene hand-drawn pixel illustrations—without image generation, use CSS squares to assemble simple pixel icons as substitutes (art degraded, technique not).
- Fonts: Press Start 2P / VT323 (pixel fonts) + Inter


#### Neutral Group

**Bauhaus geometric logomark + flat illustration system — Bauhaus Geometric** `neutral · 90% fidelity`
- Reference: Khan Academy rebrand (hexagon + petal logomark + Wonder Blocks design system); Bauhaus geometric construction
- Suited for: education course sites, brand logo systems, infographics, child-friendly products, event key visuals
- Visual DNA: Palette of the primary-color spectrum—Bauhaus red #E63946 / yellow #FFB703 / blue #0077B6 + black-and-white, solid-color-block assembly. Font geometric sans-serif (round geometric feel). Layout circles/triangles/squares as basic geometric units building illustrations, aligned grid, modular puzzle. Signature elements: pure-geometric-form logomark, flat gradient-free illustration, primary-color-block composition.
- HTML implementation: Pure CSS geometry is fully capable. border-radius:50% for circles, clip-path/border triangles, square divs assembling geometric illustrations, CSS Grid for grid alignment, solid-color fill needs no assets. Illustrations are hand-crafted with CSS shapes or inline SVG geometric paths.
- Fonts: Poppins / Manrope (geometric round replacing Wonder Blocks)

**Dark two-tone sidebar developer portfolio — Dark Editorial (dark base + single neon accent + monospace font)** `neutral · 96% fidelity`
- Reference: Brittany Chiang (brittanychiang.com v4, the de-facto standard dev portfolio)
- Suited for: portfolio homepages, developer-facing products, tech brand sites, resume pages, AI tool landings
- Visual DNA: Palette of dark ink-green / navy base #0A192F + slate-gray text #8892B0 + a single neon cyan-green accent #64FFDA. Font sans-serif body + monospace (numbering/labels). Layout left-fixed sidebar nav + right-scrolling main area two-column, section numbers 01/02, link-hover underline slide-in. Signature elements: single accent color, monospace numbered labels, sidebar anchor highlighting.
- HTML implementation: Pure CSS reproduces fully. position:sticky for the fixed sidebar + CSS Grid two-column + single accent variable + monospace label fonts + :hover underline transform slide-in. Zero assets, pure layout and micro-interaction.
- Fonts: Inter + JetBrains Mono (monospace)

**Warm publication — Warm Editorial (cream paper base + terracotta orange + serif/sans-serif mixing)** `neutral · 97% fidelity`
- Reference: Anthropic / Claude (DBCo + Geist Studio, Styrene × Tiempos); Penguin/Pelican paperback typesetting
- Suited for: AI product sites, brand official sites, longform reading pages, orange-book e-books, research reports, training materials
- Visual DNA: Palette of cream paper base #F5F0E8 + terracotta orange #CC785C/#D97757 accent + near-black text #191919, warm and low-saturation. Font serif headings (Tiempos feel) × sans-serif body (Styrene feel) mixing. Layout book-style single-column reading flow, comfortable line-height, restrained dividers. Signature elements: paper-feel warm base, terracotta orange, publication-grade typesetting rhythm.
- HTML implementation: Pure CSS 100% reproduction, zero assets. Background-color variable + serif/sans-serif font-stack mixing + max-width limiting reading width + line-height 1.7 comfortable line-height. This is the safe home turf of Anthropic's terracotta-orange warm version.
- Fonts: Fraunces / Newsreader (replacing Tiempos serif) + Inter (replacing Styrene)

**Linear dark glow + Bento grid — Glassmorphism Bento** `neutral · 85% fidelity`
- Reference: Linear / Cursor ("The Linear Look" phenomenal genre, Frontend Horse has the code recipe)
- Suited for: SaaS/AI product sites, developer tools, tech brand heroes, product feature showcases, dark dashboard presentations
- Visual DNA: Palette of near-black base #08090A + desaturated blue-purple brand #5E6AD2 + low-saturation cyan-purple glow gradient #4EA7FC→#B59AFF. Font geometric sans-serif with negative tracking, compact. Layout bento-box grid blocking, hairline dividers, glassmorphism cards. Signature elements: dark-base glowing gradient borders, bento blocking, streamer light, frosted glass.
- HTML implementation: Pure CSS strong reproduction. box-shadow/filter blur + radial-gradient for the glow halo, backdrop-filter:blur for glassmorphism, conic/linear-gradient borders, CSS Grid assembling bento. The only gap is "real product UI screenshots"—use color blocks + text to assemble simplified fake UI substitutes (this part degrades).
- Fonts: Inter / Geist (negative tracking) + Geist Mono

**Angled fluid gradient band — Angled Fluid Gradient** `neutral · 92% fidelity`
- Reference: Stripe (signature angled gradient banner, Klim custom Söhne font)
- Suited for: SaaS/Fintech landing pages, brand site heroes, product launch pages, event banners, AI product marketing pages
- Visual DNA: Palette of multi-color fluid gradient (indigo #635BFF → cyan → pink → orange warm tones) as hero background + pure white content area + near-black text. Font refined sans-serif (Söhne feel). Layout angled-split color blocks (skew-cut zoning), gradient hero crushing structured-grid body. Signature elements: angled cut boundaries, multi-color fluid gradient, rational grid crushing expressive gradient.
- HTML implementation: Pure CSS. transform:skewY() or clip-path:polygon() for angled-split zoning, linear-gradient multi-color layering (can add CSS animation slow flow) for the fluid gradient band, Grid for the structured body below. Zero assets.
- Fonts: Inter / Hanken Grotesk (replacing Söhne)

**Utility-first rainbow-categorized docs — Utility-First Colorful Docs** `neutral · 98% fidelity`
- Reference: Tailwind CSS Docs (Sky/Cyan brand color + functional-category rainbow hue bars)
- Suited for: technical documentation, API references, design system sites, tutorial sites, developer knowledge bases, SaaS help centers
- Visual DNA: Palette of Sky blue #38BDF8 brand + teal→cyan→sky cyan-blue gradient + Slate grayscale #0F172A/#64748B/#F8FAFC, docs use rainbow hue bars to distinguish functional categories (pink #EC4899 / purple #A855F7 / green #10B981 / orange). Font crisp sans-serif + monospace code. Layout left sidebar nav + center body + right TOC three columns, colored highlighted code blocks, category color tags. Signature elements: cyan-blue gradient hero, rainbow category colors, three-column doc skeleton, syntax-highlighted code blocks.
- HTML implementation: Pure CSS 98% reproduction (it is itself a CSS framework's docs). Grid three columns + linear-gradient cyan-blue hero + category color variables + code blocks with syntax colors via span coloring. Inter is open-source, only dark-mode toggle / copy needs lightweight JS. Zero lighting/3D/hand-drawn.
- Fonts: Inter + JetBrains Mono / Fira Code (code)

**Terminal-core soft-futurism (monospace font + isometric cubes) — Terminal-Core Soft-Futurism** `neutral · 80% fidelity`
- Reference: Cursor (Anysphere); developer terminal aesthetic × Teenage Engineering industrial minimalism
- Suited for: AI coding tool sites, CLI product landings, developer infrastructure, tech brand heroes, terminal-type products
- Visual DNA: Palette of charcoal black #0B0D14 base + warm white text #F2F0EF + restrained blue-purple gradient accent dotting buttons and glow. Font monospace as the protagonist (command-line feel) + sans-serif support. Layout command-line/code blocks in the foreground, bento zoning, 2.5D isometric cube diagrams. Signature elements: monospace command-line, isometric-projection cubes, warm white × charcoal black, restrained gradient glow, industrial minimalism.
- HTML implementation: Pure CSS 80% reproduction. Monospace code blocks + dark bento + box-shadow glow; 2.5D isometric cubes hand-crafted via CSS 3D transform (rotateX/Y + skew) or SVG isometric projection. Gap: clickable multi-interface demos need JS + fake-UI assembly. No hard WebGL requirement.
- Fonts: Geist Mono / JetBrains Mono (protagonist) + Inter (support)


#### Quiet Group

**Functionalist grid community — Functional Brutalism (gray-line splits + system font + blue links)** `quiet · 98% fidelity`
- Reference: Are.na / Lobsters / Quartz; Müller-Brockmann grid digital landing + Tufte information density
- Suited for: community/UGC platforms, content aggregation sites, document knowledge bases, mobile-first content feeds, geek-facing products
- Visual DNA: Palette of near-white base #FBFBFB + black text + 1px gray divider lines #E0E0E0 + classic link blue #0000EE / visited purple. Font system font stack (-apple-system / undecorated). Layout high-density information lists, hairline gray column splits, minimal whitespace, compact line-spacing. Signature elements: hairline gray dividers, blue links, system font, information-density-first.
- HTML implementation: Pure CSS is the easiest to reproduce—this is the true colors of Brutalist Web. border-bottom:1px gray-line lists + system-ui font stack + compact padding + blue links. Almost no assets or JS needed, pure structure.
- Fonts: system-ui system font stack / IBM Plex Sans (fallback)

**Dark gallery framing — Gallery Dark (deep-black negative space + single-column large images + EXIF small text)** `quiet · 75% fidelity`
- Reference: Glass (glass.photo) / Bottega Veneta; museum darkroom + Apple Photos content-first
- Suited for: photography portfolios, luxury e-commerce, immersive visual content display, personal gallery pages, high-end product display
- Visual DNA: Palette of pure black base #0A0A0A + the work image itself providing the only color + very faint gray EXIF small text #666. Font ultra-thin sans-serif small text. Layout single-column centered large image, giant negative-space framing, metadata small text beneath the image. Signature elements: darkroom black base, content-first retreating UI, EXIF-style small-text annotations, large image dominating the viewport.
- HTML implementation: Pure CSS reproduces the layout skeleton. Pure black base + centered max-width single column + giant padding framing whitespace + small-text metadata. The gap is "real photographic works" themselves—using placeholder images / solid color blocks loses the soul, but the darkroom atmosphere and layout are 100% buildable.
- Fonts: Inter (thin weight 300) / Cormorant (serif luxury feel optional)

**Swiss extreme black-and-white — Swiss Monochrome (Vercel-style pure black-and-white + Geist + sharp corners)** `quiet · 98% fidelity`
- Reference: Vercel / Next.js Docs (self-developed Geist is open-sourced); Massimo Vignelli's less-is-more
- Suited for: developer tool documentation, tech brand official sites, AI product sites, SaaS landing pages, minimalist research reports
- Visual DNA: Palette of pure black #000 + pure white #FFF + grayscale #888, zero color or only a touch of link blue. Font Geist geometric sans-serif + Geist Mono. Layout sharp right angles (no rounding or minimal), high contrast, precise grid, restrained whitespace. Signature elements: pure black-and-white, sharp corners, Geist font, triangle/arrow geometric marks.
- HTML implementation: Pure CSS 100% reproduction, Geist open-source can be directly referenced. CSS Grid precise grid + pure black-and-white variables + border-radius:0 sharp corners + hairline borders. This is HTML's most comfortable minimalist home turf, zero asset dependency.
- Fonts: Geist + Geist Mono (Vercel open-source original)

**Japanese-whitespace white-box gallery — Kenya Hara White Gallery** `quiet · 80% fidelity`
- Reference: Cosmos (cosmos.so) / Aesop official site; Kenya Hara's emptiness of "white" + Swiss grid hybrid
- Suited for: high-end e-commerce, creative galleries, content curation platforms, designer portfolios, brand boutiques, moodboard sites
- Visual DNA: Palette of near-full-white #FAFAFA base + pure black text #0A0A0A + very faint gray dividers #EFEFEF, content images providing all the color, UI retreating to the background. Font minimalist system/geometric sans-serif small text, large letter-spacing. Layout masonry waterfall grid, extreme whitespace, faint gray hairline dividers, Eastern emptiness. Signature elements: white-box aesthetic, luxury whitespace, content-first UI retreat, waterfall-flow curation.
- HTML implementation: Pure CSS reproduces the static layout (distinguished from the dark gallery by the "white"). CSS columns or Grid for masonry + near-white variables + large padding whitespace + faint gray dividers. The gap is Lenis/GSAP smooth inertial scrolling and image-entrance easing (60% of the premium feel lies here), CSS only has basic transition, the motion layer degrades.
- Fonts: Inter (thin weight) / Cooper Hewitt (Aesop's same open-source font)


## PPT Style Library (20 Styles)

#### Bold Group

**Neo-Swiss Billboard Editorial** `bold · 98% fidelity`
- Reference: The Big-Number Editorial genre of AI/SaaS pitch decks like Scribe $75M, Flock Safety $47M; Bloomberg Businessweek infographics; Pentagram
- Suited for: fundraising pitches, QBR/business reviews, annual trend recaps, key product-launch pages
- Visual DNA: Palette = pure white (#FFFFFF) or near-black (#0A0A0A) base + a single high-saturation accent color (electric blue #2D5BFF / fluorescent green #00E676 / brand orange #FF6B2C) + neutral grid lines #E5E5E5. Font = ultra-large bold sans-serif, headlines occupying half the screen, numbers tabular-nums monospace with tightened tracking. Masters = ① large-color-block section page with one word ② giant number occupying half the screen (3.2x) + small note ③ left-right column comparison ④ full-width flat line/bar chart. Signature = billboarding big type, strict baseline grid, large-color-block section pages
- HTML implementation: Ultra-large numbers use clamp(); strict grid uses CSS Grid; large-color-block section pages use background-color; line/bar charts use pure div + CSS or inline SVG (sharper than image pasting); number alignment font-variant-numeric:tabular-nums. Zero illustration, zero 3D
- Fonts: Inter / Geist / Söhne replacing Neue Haas Grotesk; numbers paired with Geist Mono

**Black Big-Number Stage** `bold · 97% fidelity`
- Reference: Steve Jobs 2007 iPhone Keynote, Xiaomi SU7 Ultra Lei Jun launch event, Spotify Wrapped, Presentation Zen (Garr Reynolds)
- Suited for: product launch keynotes, thought presentations, all-hands town halls, emotional annual recaps
- Visual DNA: Palette = pure black #000000 base + pure white #FFFFFF text high-contrast, one page with only one brand accent color highlighted (Xiaomi orange #FF6900 / Spotify green #1ED760 / Apple blue #2997FF). Font = geometric sans-serif bold, one word per screen or one giant number filling the field of view, tracking tightened. Masters = ① title page black base centered one row of big type ② data-climax page giant number + unit + one row of note ③ left-right parameter comparison two columns (accent color vs gray) ④ slogan single page. Abundant negative space
- HTML implementation: Black base white text a few lines of CSS; giant number clamp() + flex centering; accent-color highlight separate span; left-right comparison CSS Grid two columns + bar highlighting; tabular-nums. Removing product photos for pure text actually gets closer to the essence of Zen
- Fonts: Geist / Inter / Source Han Sans replacing SF Pro

**High-saturation mono-brand clash-color poster — Mono-Brand Type-as-Hero** `bold · 96% fidelity`
- Reference: Spotify Wrapped visual system, Mailchimp Brand Book (Collins), Netflix red-black modern reimagining, COLLINS brand systems
- Suited for: brand/marketing strategy, campaign briefings, town-hall culture pages, event key visuals
- Visual DNA: Palette = a single brand primary color full-bleed (Spotify green #1ED760 / Mailchimp yellow #FFE01B / Netflix red #E50914) + black or white contrast text, two-layer clash. Font = ultra-large font as the main visual (type-as-hero) reaching ceiling to floor. Masters = ① full-color-block base + reversed-out giant type ② two-color-block top/bottom or left/right split ③ giant number filling the frame. Signature = mono-color full-bleed, type-as-image, high-contrast clash
- HTML implementation: Full-bleed background-color; ultra-large type clamp() filling; two colors using two 100vh color blocks; type-as-image relies on font-weight 900 + negative letter-spacing. Solid color blocks, zero assets, HTML-native is most comfortable
- Fonts: Inter / Manrope / Archivo (ultra-bold) replacing Circular/Cavendish

**Full-Bleed Gradient Manifesto** `bold · 82% fidelity`
- Reference: Zuora "Tell a Different Story" sales deck (analyzed by Andy Raskin), Nike "Just Do It" campaign, National Geographic spreads
- Suited for: sales proposal vision pages, brand manifestos, keynote turning-point pages, mission-vision single pages
- Visual DNA: Palette = full-bleed CSS gradient (warm orange → magenta / deep blue → cyan) or solid-color bleed + reversed-out manifesto big type + hashtag slogan (#shifthappens). Font = heavy sans-serif all-caps slogan running horizontally. Masters = ① full-frame gradient + centered reversed-out manifesto ② promised-land vision page ③ customer logo wall. Signature = full-bleed, reversed-out big slogans, hashtag slogans
- HTML implementation: linear-gradient/radial-gradient full-bleed (no particles/lighting, pure CSS gradient is allowed); reversed-out text position-centered; logo wall using grid grayscale SVG/text placeholders. The part originally relying on documentary large photos degrades to CSS gradient base + big type; with photos missing, this item's fidelity drops by ~15%
- Fonts: Archivo / Anton / Manrope (ultra-bold)

**CS50 single-concept candy stage — Candy-Color Lecture Stage** `bold · 94% fidelity`
- Reference: Harvard CS50 (David Malan), Lessig Method/Takahashi method, Presentation Zen
- Suited for: educational courseware, technical lectures, concept explanations, code teaching
- Visual DNA: Palette = deep black base #0A0A0A + high-saturation candy-color big type rotation (magenta #FF2D95 / cyan #00E5FF / bright yellow #FFD500 / green #39FF14). Font = sans-serif ultra-large type floating centered, one concept per screen, very little text. Masters = ① deep black base single candy-color big word ② monospace code block syntax highlighting ③ stage-spotlight-feel big type. Signature = deep-black floating candy-color big type, monospace code highlighting, strong stage spotlight, very little text
- HTML implementation: Deep black background + single-color ultra-large type clamp() centered; code blocks use pre + monospace font + span coloring for syntax highlighting; spotlight feel via very faint radial-gradient vignette (not particle light effects). High fidelity
- Fonts: Inter ultra-bold + JetBrains Mono (code)

**Playful Maximalist Editorial (Collins-style)** `bold · 75% fidelity`
- Reference: Mailchimp Brand Book (Collins 2018), New Yorker cartoon vibe, Cooper rounded serif, Cavendish fluorescent yellow
- Suited for: decks with attitude, creative agency proposals, culture-facing town halls, anti-SaaS-minimalist marketing pages
- Visual DNA: Palette = Cavendish fluorescent yellow #FFE01B large-area + black + a little clash color, anti-SaaS minimalism. Font = Cooper-style rounded serif big headlines (playful) + magazine-style whitespace composition. Masters = ① fluorescent-yellow full base + quirky headline ② magazine-style irregular-whitespace layout ③ big-type meme copy. Signature = fluorescent yellow, rounded serif, playful composition, quirky hand-drawn vibe (degraded to geometric color blocks / emoji replacing real illustration)
- HTML implementation: Fluorescent yellow background; rounded serif font-family; magazine whitespace via asymmetric Grid. The core element of hand-drawn gorillas/illustrations cannot be done without AI image generation—degrade to CSS geometric color blocks + large emoji + irregular transform-rotated text blocks; with illustration missing, fidelity drops by ~20%
- Fonts: Fraunces (adjustable roundness) / Bree Serif replacing Cooper; body Inter

**Irreverent Pop (Reddit-style)** `bold · 80% fidelity`
- Reference: Reddit Ads sales deck (listed by Dock as the most characterful), David Carson-style irreverent typesetting, 90s web retro, Memphis playfulness
- Suited for: Gen-Z brands, meme marketing decks, community/creator-facing, proposals daring to be improper
- Visual DNA: Palette = Reddit orange-red #FF4500 + clash colors, 90s web retro colors. Font = mixed/grid-breaking David Carson-style typesetting, meme colloquial copy. Masters = ① fun page meme big type ② facts page rhythm-shift serious data ③ colloquial headlines. Signature = grid-breaking mixing, orange-red, meme colloquial, fun→facts rhythm reversal, retro web texture
- HTML implementation: Deliberately break grid via transform rotation/overlap positioning/mixed font sizes; orange-red + clash blocks; retro texture via thick black border + hard shadow box-shadow (no blur). Custom meme illustrations degrade to emoji + geometric collage, but the mixed typesetting itself is HTML-reproducible
- Fonts: Archivo / Space Grotesk + mixing Inter to create contrast

**Y2K inflated big type — Maximalist 3D-Type (Wrapped-style)** `bold · 78% fidelity`
- Reference: Spotify Wrapped 2022/2023/2025, Memphis clash colors, Y2K/Maximalism, duotone portrait gradients
- Suited for: annual recaps (emotion-going-viral oriented), personalized data cards, social-share vertical cards, brand year-ends
- Visual DNA: Palette = high-saturation clash-color full-bleed background (magenta + cyan + orange) + Spotify green accent + duotone two-color gradient. Font = ceiling-to-floor giant numbers, years/numbers done with 3D inflation/metallic texture. Masters = ① clash-color full-bleed + giant inflated numbers ② duotone portrait/color-block base + reversed-out big type ③ vertical shareable card. Signature = giant inflated 3D numbers, clash-color full-bleed, duotone gradient, year metallic texture, vertical story card
- HTML implementation: Clash-color full-bleed background; 3D inflated numbers via CSS text-shadow multi-layer stacking + transform:perspective or SVG + stroke creating dimensionality (not true 3D rendering); duotone via mix-blend-mode + gradient layered over a grayscale image placeholder block. Metallic texture degrades to gradient-filled text background-clip:text, fidelity drops by ~15%
- Fonts: Archivo Black / Anton ultra-bold + numbers Clash Display


#### Neutral Group

**Bento Grid** `neutral · 95% fidelity`
- Reference: The Apple Keynote Bento Grid era, the new generation of MBB Bento/Big-Type decks (2024-2026), Stripe annual-report metric-card matrices, Pitch.com QBR templates
- Suited for: product feature summaries, consulting/QBR data reports, sales-results pages, town-hall metric pages
- Visual DNA: Palette = light gray/cream base (#F5F5F7/cream) or near-black base + brand primary color + 1-2 accent colors, cards with light-color zone base + rounded corners + micro-stroke/micro-shadow. Font = ultra-large display headline + regular body, strong weight contrast, KPI numbers tabular figures. Masters = ① title page giant single sentence + whitespace ② bento page 2×2/3-column unequal-height cards each with one insight (number/linear icon/sparkline) ③ one-insight giant number page. Signature = unequal-height card grid, rounded micro-stroke, breathing room
- HTML implementation: CSS Grid grid-template-areas for unequal-height bento; cards border-radius + box-shadow micro-shadow + 1px hairline; sparkline via inline SVG; linear icons via inline SVG stroke. Zero image pasting
- Fonts: Inter / Geist + numbers Geist Mono

**Neo-Swiss dark terminal aesthetic — Dark Hairline Terminal** `neutral · 94% fidelity`
- Reference: Linear pitch deck, Vercel design language, CS50 deep-black stage courseware; fonts Inter Tight + JetBrains Mono
- Suited for: developer tool/tech product launches, technical pitches, engineering-facing reports
- Visual DNA: Palette = near-black base (#0D0D0F/#111113) + hairline thin-line #262629 grid + single purple-blue accent (#5B5BD6/#7C7CFF). Font = Inter Tight big headline + JetBrains Mono for labels/data. Masters = ① minimalist title page one sentence + mono small heading ② hairline-divided data grid ③ mono-label feature list. Signature = 1px thin-line grid, mono monospace labels, extreme whitespace, near-black not pure black
- HTML implementation: Near-black background + border:1px solid hairline grid; mono labels via monospace font-family; glow via very faint box-shadow/border highlight rather than real light effects (degraded to avoid the cyber-neon forbidden zone). Note: avoid the #0D1117 deep-blue forbidden zone, use neutral near-black
- Fonts: Inter Tight + JetBrains Mono / IBM Plex Mono

**Two-font consulting style — Two-Font Consulting (Bower-style)** `neutral · 90% fidelity`
- Reference: McKinsey 2019 brand system (designed by Wolff Olins, Bower serif + sans-serif), BCG Executive Perspectives, deep-blue thin-line pattern
- Suited for: consulting reports, executive briefings, industry research, authoritative-institution proposals
- Visual DNA: Palette = deep blue (#051C2C/McKinsey deep blue) × white binary + single brand color highlight (BCG green #00805A), warm-gray base with breathing room. Font = characterful serif big headline (Bower-style) juxtaposed with sans-serif body in high contrast. Masters = ① top-left conclusion-style action-title ② blue thin-line pattern decoration ③ magazine-style left-right division of labor (conclusion text + visual) ④ big-number data-point card. Signature = serif × sans-serif high contrast, deep-blue thin-line pattern, action-title, warm-gray premium feel
- HTML implementation: Two fonts font-family juxtaposed (serif headline + sans-serif body); thin-line pattern via repeating-linear-gradient or SVG line; data-point card pure CSS; photo-grayscale treatment can be omitted with no photos. Blue-purple edge shimmer degrades to solid-color border
- Fonts: Playfair Display / Fraunces serif headline + Inter body (replacing Bower)

**Diagram-and-arrow enterprise style — Diagram-Driven Isotype** `neutral · 88% fidelity`
- Reference: Salesforce sales deck, the Isotype (Otto Neurath) lineage, Gene Zelazny's "Say It With Charts," Hans Rosling/Gapminder
- Suited for: platform/architecture explanations, customer journeys, process methodologies, ecosystem maps
- Visual DNA: Palette = enterprise blue color blocks + product-line color differentiation zones + iconized capability grid. Font = clear sans-serif. Masters = ① horizontal customer-journey arrow flow ② layered platform architecture diagram ③ iconized capability grid ④ 2×2/waterfall/pyramid structure diagram. Signature = arrow flows, layered architecture boxes, Isotype icon grid, process-as-narrative
- HTML implementation: Arrow flows via Flexbox + CSS clip-path triangles or SVG arrow; architecture layering via nested bordered divs; icons via inline SVG stroke with unified stroke; waterfall/pyramid via Grid + skew cut. Bubble charts can use CSS circles + positioning. Pure vector drawing
- Fonts: Inter / IBM Plex Sans (chart-friendly)

**Single mother-diagram concept illustration — Diagrammatic Minimalism** `neutral · 95% fidelity`
- Reference: Simon Sinek's Golden Circle TED, Bauhaus geometric abstraction, information architecture's "one diagram defines the whole show"
- Suited for: theoretical framework explanations, TED-style thought dissemination, model/methodology visualization, single-concept keynotes
- Visual DNA: Palette = minimalist white/light base + black + one accent color, geometric solid colors. Font = sans-serif, labels uppercase embedded in shapes. Masters = ① a single geometric mother-diagram (concentric circles/triangle/matrix) carrying all the concepts ② inside-out arrows ③ contrasting cases. Signature = single geometric mother-diagram, nested concentric circles/triangles, uppercase labels, one diagram carrying the concept
- HTML implementation: Concentric circles via border-radius:50% nested divs or SVG circle; triangle via clip-path/SVG polygon; arrows SVG marker; labels absolute-positioned attached to shapes. Pure geometry, HTML reproduces perfectly
- Fonts: Manrope / Futura-family (Jost open-source replacement) geometric feel

**Sparkline narrative waveform — Narrative Sparkline (Duarte-style)** `neutral · 91% fidelity`
- Reference: Nancy Duarte's "Resonate" Sparkline narrative diagram, Al Gore's "An Inconvenient Truth," Duarte Inc. data storytelling
- Suited for: speech structure design, change narratives, before/after comparisons, data story arcs
- Visual DNA: Palette = dark base or white base + brand orange highlighting turning points + grayed-out comparison. Font = sans-serif, annotation points. Masters = ① an oscillating waveform line running across the full screen ② text annotation points on the waveform ③ top-bottom juxtaposed comparison waveforms ④ all-black base with one lone data line ⑤ progressive reveal. Signature = running waveform line, waveform annotation points, orange turning points, comparison waveforms, the curve climbing out of the frame
- HTML implementation: Waveform line via inline SVG path (smooth Bézier); annotation points via SVG circle + text positioning; comparison waveforms two top-bottom paths; reveal via CSS animation stroke-dashoffset. Pure SVG drawing, no assets
- Fonts: Inter + numbers Geist Mono


#### Quiet Group

**Assertion-Evidence / Tufte information design** `quiet · 93% fidelity`
- Reference: Michael Alley Assertion-Evidence (Penn State empirical), McKinsey/BCG action-title, Edward Tufte data-ink ratio, Barbara Minto Pyramid Principle
- Suited for: academic/engineering reports, data-rigorous consulting pages, policy research reports, technical reviews
- Visual DNA: Palette = white/very light gray base + black body + a single restrained accent color (deep blue/brick red). Font = full-sentence title (not noun phrase), one image occupying space below the title, text annotations embedded in the image. Masters = ① full-sentence action-title ② single-image evidence below the title ③ zero bullets. Signature = full-sentence titles, single-image evidence, embedded annotations, zero chartjunk, high data-ink ratio
- HTML implementation: Full-sentence title relies on typography hierarchy; charts via pure CSS/inline SVG drawing minimalist line/scatter plots (remove gridlines, remove legend, annotations directly text-positioned next to data points); zero decoration. Tufte's restraint is precisely HTML's strength
- Fonts: Source Serif / Lora title + Inter body (two fonts reading-grade)

**Institutional Swiss Minimal** `quiet · 96% fidelity`
- Reference: Sequoia official 10-page pitch template, Airbnb 2009 seed-round deck, Müller-Brockmann grid, Massimo Vignelli
- Suited for: investment pitches, standard business proposals, problem-solution narratives, brand de-decoration proposals
- Visual DNA: Palette = pure white base + black-gray body + single brand accent color (Airbnb coral red #FF5A3C / neutral blue). Font = Helvetica-family sans-serif, headline medium-size bold one sentence, body short sentences with large spacing. Masters = ① centered logo + slogan ② top one-sentence title band + below 3-column parallelism (Problem/Solution three points) ③ TAM big number layered ④ 2×2 competitor matrix. Signature = top title band, three-column parallelism, single-color accent, 2×2 matrix
- HTML implementation: Flexbox three-column parallelism; 2×2 matrix pure CSS Grid + border drawing; TAM layering via nested divs or concentric squares; one page one message. Almost pure typography grid, an ideal HTML object
- Fonts: Inter / Helvetica Now replacing Helvetica; body Inter

**Magazine editorial longform flow — Editorial Longform** `quiet · 95% fidelity`
- Reference: Stripe Annual Letter ($1.9T), Amazon six-page narrative memo, Benedict Evans "X eats the world," Stripe Press
- Suited for: annual letters/recap narratives, deep thought longform, internal updates, research-report-style reading material
- Visual DNA: Palette = cream/off-white base (#FBFAF8) + deep ink text + brand color accent (Stripe purple #635BFF). Font = serif or high-quality sans-serif, prose paragraphs + inline data cards, giant display numbers interspersed. Masters = ① masthead big title ② multi-column prose + inline metric cards ③ giant-number paragraph anchors. Signature = publication reading rhythm, inline data cards, restrained whitespace, prose body rather than bullets
- HTML implementation: Multi-column column-count or Grid; inline data cards float/inline-block embedded in body; serif body max-width controlling line width 65ch; giant numbers interspersed. Pure typography, zero assets
- Fonts: Newsreader / Source Serif body + Inter support; numbers tabular

**Humanist rounded cards (Khan-style) — Humanist Rounded Cards** `quiet · 80% fidelity`
- Reference: Khan Academy Wonder Blocks design system, Source Serif Pro serif, forest-green brand, friendly humanism
- Suited for: education products, approachable courseware, nonprofit/charity decks, warm brand proposals
- Visual DNA: Palette = forest green #14BF96/#0A5C4B + off-white base + warm-color support, soft and not harsh. Font = Source Serif serif title (humanist feel) + sans-serif body. Masters = ① rounded-card component groups ② serif title + approachable body ③ real-photo slot (degraded to green-family geometric/rounded color blocks). Signature = forest green, serif title, large rounded cards, humanist warmth, imperfect approachable texture
- HTML implementation: Large rounded border-radius cards + soft box-shadow; serif title font-family; warm off-white base. Real teacher-student photography, this item, cannot be done without AI image generation—degrade to green-family geometric illustration blocks / large rounded solid-color placeholders + emoji figures; with photos missing, fidelity drops by ~18%
- Fonts: Source Serif 4 title + Nunito Sans / Inter body (Nunito's roundness echoes humanism)

**Dense research report (Meeker-style) — Dense Research Report** `quiet · 92% fidelity`
- Reference: Mary Meeker's "Internet Trends" (BOND), CB Insights "State of AI," McKinsey Global Institute "Year in Charts," FT/Bloomberg data journalism
- Suited for: trend research reports, industry data recaps, dense data reports, market maps
- Visual DNA: Palette = white base + brand color (BOND/CB Insights bright blue #0066FF) stepped mono-color highlighting with the rest grayed out, almost zero whitespace. Font = conclusion-style sentence titles, one image per page density, very small source footnotes. Masters = ① conclusion-sentence title + full-page single image ② logo grid market map ③ big-number KPI card ④ dense multi-image grid + footnotes. Signature = conclusion-sentence titles, zero-whitespace research-report feel, mono-color stepped highlighting, logo market map, source footnote conventions
- HTML implementation: Dense charts all via pure CSS/inline SVG drawing (bar/line/stacked/scatter); logo market map via Grid + text/SVG placeholder cells; KPI card CSS; footnotes small text. Extreme information density is precisely HTML's strength, zero assets
- Fonts: Inter + IBM Plex Sans + numbers tabular Geist Mono

**All-text manifesto memo (Netflix/Amazon-style) — All-Text Manifesto** `quiet · 97% fidelity`
- Reference: Netflix Culture Deck (2009, 125 pages), Amazon six-page narrative memo (Bezos), Tufte's anti-PowerPoint stance, Matthew Carter reading-grade typesetting
- Suited for: culture manifestos, values briefings, deep memos, anti-PPT pure-document presentations
- Visual DNA: Palette = pure white or pure black base + single accent color (Netflix red #E50914) as the sole highlight, extreme restraint. Font = reading-grade typesetting, one viewpoint per page with golden-sentence assertions / pure prose, zero bullets, zero images. Masters = ① full-bleed base + golden-sentence assertion ② colloquial candid paragraphs ③ institutional-noun highlighting (Keeper Test) ④ six-page prose + appendix table. Signature = pure-text one viewpoint per page, zero image zero bullet, single-color highlighted golden sentence, colloquial candor, silent-read document feel
- HTML implementation: Pure typography: golden sentences use big type clamp() left-aligned hierarchy; prose max-width controlling line width; sole accent color span highlighting key phrases; appendix uses minimalist table. Zero assets zero images, pure text is HTML's most stable reproduction
- Fonts: Newsreader / Source Serif (reading-grade) or Inter (manifesto-style); title can be Archivo ultra-bold


---

## ⚠️ AI-Image-Generation-Specific Styles (only recommend when the user is confirmed to have image-generation capability; not selectable in default)

The souls of the styles below lie in **dynamically generated visuals / 3D / particles / cinematic lighting / hand-drawn illustration**. Under pure HTML/CSS without image generation, only severely degraded mocks can be made, so they are **removed from the default recommendation pool**. They become candidates only when the user explicitly has image-generation capability (going through `huashu-gpt-image`):

| Style | Soul | Why HTML can't do it |
|------|------|------------------|
| Active Theory (WebGL particles) | 3D particle systems / real-time rendering | Pure CSS cannot |
| Field.io (generative art) | algorithmically generated graphics | Static SVG can only do a rigid simplified version |
| Resn (illustration interaction) | character illustration + gamification | Depends on hand-drawn assets |
| Zach Lieberman (real-time generation) | creative coding strokes | Depends on real-time generation |
| Raven Kwok (fractal parameters) | recursive fractals | CSS can't produce the complexity |
| Ash Thorp (cinematic lighting) | cinema-grade volumetric light / concept art | CSS lighting is degradation |
| Territory Studio (FUI hologram) | sci-fi holographic interfaces | Depends on heavy glowing layered assets |
| Neo Shen (ink wash) | organic ink-wash diffusion | CSS gradient ≠ ink wash |
| Sagmeister & Walsh (color burst) | handcrafted physical objects + experimental typesetting | Clash-color skeleton is doable (already merged into web "Memphis" and PPT "Mono-color clash poster"), but handcrafted texture can't be done |

> These styles aren't "bad," they're "wrong medium"—their native medium is AI direct-output images, not browser DOM.

---

## Default Aesthetic Forbidden Zones (users can override per their own brand)

- ❌ **GitHub-dark lazy solution**: uniform deep-blue base (#0D1117) + generic cyan/purple neon glow—only this one overused combination is banned, not "all dark colors banned"
- ✅ **Not in the forbidden zone**: cinema-grade dramatic lighting, warm cyberpunk (Ash Thorp orange/cyan), kinetic-poetics dark-field narrative—dark colors with authorial intent are retained (this library's "Linear dark glow," "Black big-number stage," "CS50 candy stage" are all legitimate dark colors)
- ❌ Aggressive purple-gradient universal formula, emoji as icons, rounded cards + left colored border accent (unless the brand itself uses it)
- ❌ Cover images with personal signature/watermark

---

## Prompt Philosophy When You Have Image-Generation Capability (Mood, Not Layout)

> Applies only when going through the AI-image-generation path; the HTML path directly writes code per the "HTML implementation" of each style above.

Short prompts > long prompts. Describing mood and content is more effective than piling on 30 lines of layout detail.

| Diversity-killing writing | Creativity-sparking writing |
|----------------|----------------|
| Specifying color ratios (60%/25%/15%) | Describing mood ("warm like Sunday morning") |
| Prescribing layout positions | Referencing specific aesthetics ("Pentagram editorial feel") |
| Listing all visual elements | Describing what the audience should feel |

Complete AI-image-generation methodology → `huashu-gpt-image` skill.

---

**Version**: v3.0 (2026-06 fully refactored into the HTML-native 40-style library)
**Applicable to**: the default HTML path for all visual design—webpages/PPT/PDF/infographics/covers/apps, etc.