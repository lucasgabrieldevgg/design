# design-gates — score before shipping, sweep before claiming

> Merged from: `wwewtech/anti-slop-design` (MIT — 7-axis gate, 5-phase loop), `Nutlope/hallmark` references/slop-test.md (MIT — the gate-sweep discipline, the six-axis self-critique), `Gesso-Build/skills` anti-slop (MIT — deterministic-guard concept: objective detectors before judgment), and `pbakaus/impeccable` (Apache 2.0 — bounded verification). See ATTRIBUTION.md.

Everything here exists to catch slop before the user sees it. Two layers: a **self-critique** before building weakens into the record, then a **gate sweep** before delivery. Bounded verification throughout: build fully, inspect once with a batched pass, fix everything shown in one batch, confirm with at most one more round, stop — open-ended self-QA burns budget and degrades the result.

## Layer 1 — The pre-emit self-critique (six axes)

Score the *planned* output 1–5 before building it out, and again before the sweep. Anything **< 3 on any axis triggers a revision pass** — don't bring known weakness into a full gate review. Two revision passes is normal; three means the brief is wrong, not the design — re-read the brief.

| Axis | You are scoring |
| --- | --- |
| **Philosophy** | Is there a clear *why* — a position the page takes? Or is it just a layout? |
| **Hierarchy** | In 2 seconds, can a reader tell primary from secondary from tertiary? |
| **Execution** | Rule weights, accent footprint, focus rings, contrast — in spec, or sloppy bones under right-ish paint? |
| **Specificity** | Does this look like *this brief* — or a generic page that could be anyone's? |
| **Restraint** | Is everything that isn't earning its place already removed? |
| **Variety** | Does it share a structural fingerprint with the previous output in this project? Color-swaps don't count as variety. |

Record the six scores in one line (`critique: P5 H4 E5 S4 R5 V5`) in the delivery note — future runs can see the weakness history and not repeat it.

## Layer 2 — The 7-axis gate (every axis ≥ 4, score 1–5)

| Axis | Checks |
| --- | --- |
| **1. Anti-slop purity** | Zero gradient blobs / gradient text; zero emoji icons; zero one-word italic accents; zero vanity stats; zero dead placeholders; no badge riding the headline; no puffy halo shadows |
| **2. UX speed & 1-to-3** | One primary action per zone; ≤ 3 secondary; filters unified at page level; zero duplicated metrics; the 85% scenario is zero-click |
| **3. Typographic discipline** | ≤ 2 families (3 only in the monochrome-industrial exception); tabular-nums on all metrics; body ≤ 75ch; sentence case; obvious scale steps; negative tracking on display; three-layer hierarchy visible on squint |
| **4. Spacing geometry** | 8pt ladder values only; nested-radius formula holds; ≥ 16px card padding; optical icon alignment; more space above headings than below |
| **5. Motion & states** | Transitions < 200ms; 100+/day actions at 0ms; `:active` scale feedback; no `ease-in`; reduced-motion variant; all 8 states present |
| **6. Accessibility** | `:focus-visible` everywhere; no bare `outline: none`; `aria-label` on icon-only buttons; semantic elements; contrast 4.5:1 / 3:1 (UI components 3:1); touch targets ≥ 44px |
| **7. Structural variety** | Not the SaaS-hero skeleton; fingerprint differs from sibling pages on ≥ 3 axes; layout coherent with content; clean mobile stacking; zero horizontal overflow |

Any axis < 4 loops back to structure (Phase 3 of the flow), not to detail polish.

## The deterministic sweep (objective before judgment)

Before the scored gates, run the checks that are yes/no facts — a deterministic instrument, not an opinion. On HTML/CSS deliverables, grep-able checks: the display font is not Inter/Roboto/Open Sans/Poppins/Lato/system default · no `background-clip: text` anywhere · no `#000000`/`#ffffff` base surfaces (except deliberate paper-white editorial) · no `transition: all` · no bare `outline: none` · no `via.placeholder`/hotlinked Unsplash/lorem in shipped copy · every `<img>` has `alt` and explicit `aspect-ratio` (CLS is a craft failure). Structural facts: no card nested in a card · the hero is not centered-everything · a `<body>` with no max-width/grid is a layout bug. Where tooling exists (`npx @gessobuild/anti-slop check <file>`), run it: exit 0 clean, 1 slop found — report exactly what it found, apply the safe auto-fixes, then layer judgment on top, clearly labeled as judgment.

**The one-pass rule:** the sweep and the axis scores share one rendering pass — they all look at the same screenshot. Fix everything one batch shows in one batch, re-render once, stop.

## The render verify list (against the render, not the intention)

- **Contrast:** body and placeholder ≥ 4.5:1, large text ≥ 3:1; secondary text tinted from its surface hue, never gray-on-color.
- **Depth:** shadows carry offset + soft blur; surfaces step through the 4 levels; the accent appears exactly once per viewport.
- **Type:** real copy at every breakpoint; nothing overflows; measure capped; steps obvious; numbers tabular.
- **Motion:** one authored moment; high-frequency at 0ms; reduced-motion variant exists.
- **States:** all eight on primitives; keyboard order sane; focus rings visible on both light and dark surfaces.
- **Browser surfaces:** selection, caret, scrollbars, focus rings themed from tokens.
- **Copy:** the product's own language; controls name their action; errors name the problem and the recovery.
- **Coverage:** every brief requirement present and findable in seconds; mobile stacks linearly; 100% and 200% zoom checked on key areas.

## The final assertion

Before delivering anything under this skill, answer honestly:

> *Does this read as crafted by a disciplined professional with extreme respect for the user's attention — or does any part of it look like it was generated from a prompt?*

If any element feels like prompt-slop: eliminate it, do not soften it. Then ship, and stop polishing — the remaining 2% is not worth the user's patience, and over-polished work starts acquiring its own uniformity tells. Craft ends at *decided and verified*, not at *perfect*.
