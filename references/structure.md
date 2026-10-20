# structure — breaking the template skeleton

> Merged from: `Nutlope/hallmark` references/structure.md + macrostructures.md (MIT — the six axes, the fingerprint idea, domain trios, structural anti-patterns), with layout patterns carried from `shinewinsu/vibe-frontend-design` and `wwewtech/anti-slop-design`. See ATTRIBUTION.md.

Most generated UIs are visually distinct but structurally identical: hero → three features → CTA → footer. Same heading positions, same column counts, same component vocabulary. **Structural sameness is the AI fingerprint, not visual sameness** — a new palette over the same skeleton still reads generated. This file is the instrument that breaks it.

## The six axes of a structural fingerprint

A fingerprint = one choice per axis. 8 × 7 × 5 × 5 × 5 × 6 ≈ **42,000** fingerprints — you will never run out. Two pages for two different briefs should never share the same fingerprint.

### 1. Section-heading placement
Left-margin eyebrow column (⚠️ opt-in only — reads templated on SaaS/consumer/dev-tool pages, and the eyebrow-left/heading-right variant is banned) · **Hanging** above the section in negative space · **Centered display** (formal, static if everywhere) · **Bottom-aligned** (inverts hierarchy — Swiss editorial) · **Overlapping image** (demands contrast) · **Sticky/pinned** (orientation aid) · **Numbered display** (⚠️ opt-in only — ordinal/chaptered work, stacked variant preferred) · **Inline with body** (conversational, no section break).

Coherence rule: the head's alignment must cohere with the body it introduces. A narrow centred head stranded over full-width left-flush content (a `margin-inline:auto` head above a wide grid) is the tell.

### 2. Body composition
**Single column** (narrative default) · **Two-column asymmetric** (wide body + narrow margin for metadata/marginalia) · **Multi-column justified** (newspaper rhythm) · **Marginalia** (Tufte sidenotes in a generous outer margin) · **Three-column equal** (reference/data density) · **Full-bleed with margin reset** (65ch body, images bleed viewport-wide) · **Asymmetric spans** (2-1-3 ratios via CSS Grid).

### 3. Divider language
**Hairline rule** (0.5–1px, the modernist default) · **Ornament** (fleuron, centered dot) · **Negative space** (the gap *is* the divider) · **Bleed-color block** (background shift edge) · **Double rule** (masthead signal).

### 4. Button voice
**Outlined** (quiet primary, default) · **Unstyled link** (trust the typography) · **Oversized solid** (statement CTA) · **Typographic-only** (a headline that happens to be clickable) · **Form-as-CTA** (newsletter signup — the field *is* the action).

### 5. Image treatment
**Full-bleed** (image as architecture) · **Tightly cropped** (sized to grid) · **Inline with text** (flows in the paragraph rhythm) · **Margin-aligned** (in the outer margin) · **None** (typography carries everything).

### 6. Reveal pattern
**Fade-up stagger** (orchestrated once, exponential ease-out) · **Horizontal sweep** (clip-path or transform momentum) · **Type-unmask** (clip-path opens over text) · **Number-tick** (counters for stats/prices) · **None** (everything just there — some sites should not move).

Two rules govern the picks: **Coherence** — a newspaper page with a multi-column justified body gets a typographic CTA, not an oversized solid button; choices must belong to the same world. **Anti-repetition** — consecutive pages built in the same session should differ on at least three of the six axes.

## Macrostructure families (the page shapes)

Whole-page shapes, grouped by family. When the brief has no locked structure, offer **three from categorically different families** — a grid-led shape, a document-led shape, a poster-led shape. Picking three near-twins is the AI tell this file exists to defeat.

- **Grid-led:** Bento Grid (hero tile 2×2 + supporting tiles) · Portfolio Grid (work tiles with hover reveal) · Catalogue (dense product grid with filters) · Index-First (the page *is* an index/table of contents).
- **Document-led:** Long Document (reading-led, marginalia, footnotes) · Letter (personal, closes with a signature block) · Specimen (type-led, the faces are the content) · Docs/Workbench (sidebar + content + code).
- **Poster-led:** Manifesto (full-bleed statements, aggressive scale) · Marquee Hero (oversized display type as the page) · Quote-Led (one pull-quote opens, sections answer it) · Split Studio (50/50 screen + statement).
- **Data-led:** Stat-Led (numbers carry the narrative) · High-density dashboard (control bar → KPI strip → 70/30 split → table) · Component Playground (live interactive demos as content).
- **Narrative-led:** Photographic (imagery carries, text rides) · Scrollytelling (sections reveal a story on scroll) · Timeline/Card flow (connecting rail, single column).

### Domain → trio routing

Read the brief for a domain word and offer the matching trio — never default:

| Domain words | Trio to offer |
| --- | --- |
| podcast, audio, music, playlist | Photographic · Quote-Led · Letter |
| shop, store, product, merch, commerce | Catalogue · Photographic · Bento Grid |
| docs, CLI, SDK, API, library, open source | Workbench · Long Document · Component Playground |
| platform, infra, B2B tool, dashboard SaaS | Bento Grid · Workbench · Stat-Led |
| agency, studio, case studies, portfolio | Portfolio Grid · Split Studio · Index-First |
| personal one-pager, about-me, resume | Long Document · Letter · Index-First |
| restaurant, café, food, menu | Photographic · Long Document · Catalogue |
| fashion, apparel, lookbook | Photographic · Catalogue · Marquee Hero |
| fintech, banking, payments, trading | Stat-Led · Workbench · Long Document |
| manifesto, campaign, cause | Manifesto · Quote-Led · Stat-Led |
| editorial, magazine, type, foundry | Specimen · Long Document · Index-First |
| conference, event, keynote | Marquee Hero · Manifesto · Photographic |

Splits on intent: developer-tool *docs* wants a Workbench walkthrough; developer-tool *marketing* wants Bento + Stat-Led. A one-pager about-me and a multi-project portfolio are different briefs. If ambiguous, ask one question ("docs walkthrough or marketing landing?"). If the user answers a vague tone word ("modern", "clean"), that is not a feeling — re-ask with the domain trio.

## The structural anti-patterns (reject on sight)

- **The SaaS hero.** Centred display heading, centred subhead, centred pill CTA, full-viewport hero, fade-up. The single most-recognized AI structural fingerprint.
- **The 3-feature row.** Three equal columns of icon-above-heading-above-two-line-body, gapped 24px, identical card padding.
- **The benefits-then-CTA.** Feature bullet list followed by a "Sign up" block. Predictable rhythm.
- **The everything-fades-in.** Every section gets the same scroll-triggered fade-up. The page becomes a presentation.
- **The carbon-copy footer.** Logo, four columns of links, social row, copyright — identical on every site ever generated.

## Layout patterns that read as designed (parameter quick-reference)

Anchor a view to one of these instead of free-form boxes: **Bento grid** `grid grid-cols-1 md:grid-cols-3 gap-4 lg:grid-cols-4` with one `col-span-2 row-span-2` hero tile · **Split-screen** `grid lg:grid-cols-12` at 5/7 or 7/5 · **Asymmetric 12-col** 7:5 and 8:4 splits with occasional `translate-y-8` overlap · **Masonry** `columns-1 sm:columns-2 lg:columns-3` for testimonial walls/galleries · **Card flow/timeline** `relative border-l pl-6 space-y-8` for changelogs/step flows · **SaaS shell** fixed sidebar (240px, 64px icon-rail collapsed) + page header + scrollable `max-w-7xl mx-auto px-6 py-8` · **Conversion landing** crisp nav → hero (one offer, one CTA, one dominant visual) → social proof strip → bento benefits → interactive preview → pricing matrix → footer.

When a `design.md` exists in the project (see [the-flow.md](the-flow.md)), the diversification rule inverts: pages must *share* the locked system. Until then, no two pages share more than three of the six axes.
