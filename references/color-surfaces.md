# color-surfaces — tokens, depth, and contrast

> Merged from: `wwewtech/anti-slop-design` (MIT — surface hierarchy levels), `shinewinsu/vibe-frontend-design` (token discipline), `Nutlope/hallmark` references/color.md (MIT — OKLCH anchors, band logic), and `oil-oil/oil-ui` (MIT — evidence-based color decisions from real screenshots). See ATTRIBUTION.md.

Generated color fails two ways: the default palette nobody chose (`bg-slate-900 text-indigo-400` — the most recognizable color fingerprint in AI UI), and flat single-plane layouts where everything sits on one surface. Both are fixed with the same discipline: tokens with a chosen temperature, and a surface stack with steps you can see.

## Building the palette (OKLCH anchors)

Define the palette in OKLCH, where lightness, chroma, and hue are separable — then keep relationships, swap the hue:

- **Paper band.** Pick canvas lightness first (dark worlds: L ≈ 0.14–0.20; light worlds: L ≈ 0.96–0.99). Surfaces step up in lightness, never sideways in hue.
- **Ink steps.** Two text steps minimum on any surface (`ink` and `ink-2`), plus a muted third. On dark canvases, `#ececec`-level ink, never pure `#fff` bodies; on light canvases, near-black with warmth, never pure `#000`.
- **One accent.** Chroma high enough to carry a focus ring (C ≥ 0.15), hue chosen against the domain (emerald for status/ops, cobalt for productivity, ochre for warmth, ink for editorial). Amber exists for alerts only. A second accent requires a reason stated aloud.
- **Rule color.** Borders are low-chroma paper-shifted tones (`rgba(255,255,255,0.08)` dark / `#e8e4df` light) — visible on inspection, invisible at reading distance. Hover brightens the border one step, not the whole surface.
- **Focus.** The accent *is* the focus color — never the browser default blue unless the accent is blue.

The token starter sets in [archetypes.md](archetypes.md) encode these relationships per world; adapt hue, keep the structure.

## The surface hierarchy (four levels, never one plane)

- **Level 0 — canvas:** the page base, darkest (or lightest) value in the system.
- **Level 1 — surface:** large containers, sidebar, cards. One step up from canvas, hairline border.
- **Level 2 — overlay/interactive:** hovered rows, list cards, popovers anchored to content. Second step; hover brightens border to `--border-hover`.
- **Level 3 — elevated:** modals, menus, floating panels. `shadow-2xl`-class depth, own focus ring.

Blur (`backdrop-filter`) belongs to Level 2–3 floating chrome only — sticky navs and overlays. Surfaces elsewhere stay solid; glassmorphism everywhere is a banned trope.

## Spacing geometry (depth's sibling)

**The 8pt ladder.** All padding and gaps from: `4` (hairline) → `8` (compact) → `12` (standard control pad) → `16` (card pad) → `24` (section gutter) → `32`/`48`/`64` (macro whitespace). A `13px` and a `15px` in the same component is an accidental inconsistency; fix to the ladder. Cards need ≥ 16px padding; tight groups stay tight; **more space above a heading than below it** — the heading belongs to the section it introduces.

**Nested radius formula.** `radius_inner = max(0, radius_outer − padding)`. A 16px-radius card with 8px padding takes an 8px-radius button inside — not 16, not 0. One of the most reliable "a person was here" signals in UI.

**Grouping.** Tight groups, generous separation between groups. Read the *computed* values in devtools, not the intention.

## Shadows

Shadows carry an offset and a soft blur (`0 1px 2px rgba(0,0,0,.4), 0 8px 24px rgba(0,0,0,.35)`-class composites on elevated surfaces). A zero-offset colored halo around a card is decoration — remove it or make it a border. Level-1 surfaces usually want a hairline border, not a shadow at all.

## Contrast (the floor, not the ceiling)

Body and placeholder text ≥ **4.5:1**; large text (≥ 24px or 19px bold) ≥ **3:1**; UI components and focus indicators ≥ **3:1** against adjacent colors. On colored surfaces, tint secondary text from that hue — never gray-on-color. Placeholder text is content: it gets contrast too, and copy that names what belongs in the field ("you@company.com", never "Enter text here"). Check focus rings on both light and dark surfaces — a ring that only reads on one is half-done.

## Browser surfaces — the cheapest human signal

The parts you did not draw still carry the design, and the browser ships them with defaults that belong to no system. Theming these is what human teams do and generated UI skips most reliably: **text selection** (`::selection` from the palette) · **the caret** (`caret-color`) · **custom scrollbars** (`::-webkit-scrollbar`, `scrollbar-width`/`scrollbar-color`) · **focus rings** (outline color and offset from tokens) · **underline offset** on body links · **tabular numerals in data**. Ten lines of CSS, and the page reads *built* rather than *assembled*.

## Verifying color decisions

Judge color on evidence, not on the code: screenshot the built page at the target viewport and look — do the surfaces step? Does the accent appear exactly once per viewport? Does the ink hold contrast on every surface it touches? Reading hex values in a diff is where "it should look fine" gets born.
