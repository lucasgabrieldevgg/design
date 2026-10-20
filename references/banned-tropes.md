# banned-tropes — the visual tells of generated UI

> Merged from: `wwewtech/anti-slop-design` (MIT — the core matrix), `shahrukh-hack/vibe-superkit` (trope/craft contrasts), `Gesso-Build/skills` anti-slop guards (MIT — deterministic tell categories), `Nutlope/hallmark` anti-patterns (MIT — hero-shape and badge rules), and `pbakaus/impeccable` (Apache 2.0 — the craft-floor). See ATTRIBUTION.md.

These are the assembled-not-designed tells. Each row: the trope, how it shows up, and the replacement that carries the same job with actual craft. Scan any UI against this list before doing anything else. Structural sameness (the hero → 3-feature → CTA → footer skeleton) lives in [structure.md](structure.md) — scan both; visual tropes and structural tropes are different diseases.

## The trope matrix

| Trope | How it shows up | Replace with |
| --- | --- | --- |
| **AI dark-mode blob** | `radial-gradient` from indigo-600/purple-900 blurred into corners of a dark background | Deliberate monochrome surfaces (`#09090b`, `#121214`) with 1px hairline borders `rgba(255,255,255,0.08)` |
| **Slate/indigo default** | `bg-slate-900 text-slate-400 bg-indigo-600` everywhere | A curated token set with a chosen temperature (OKLCH/HSL) — see [archetypes.md](archetypes.md) |
| **Gradient-clip headline** | `background-clip: text` gradient on words, "Make it *pop* tonight" | Uniform weight; emphasis from size or weight, never gradient. No genre allows gradient text |
| **Three-identical-card grid** | Three same-size icon-heading-text cards with hover glow | Content-driven layout: asymmetric bento (one hero tile 2×2), split panels, workflow rows |
| **Emoji as icons** | `🚀 🔥 💡 📊` in buttons, sidebars, cards | One icon library (Lucide, Phosphor, Heroicons), single stroke weight 1.5–2px |
| **Vanity stats** | "+99.9% uptime", "10x faster", "50k+ users" with no source; raw unformatted `$1,842,000` | Real telemetry, or delete the card. Zero invented metrics; typeset numbers (abbreviations, tabular figures) |
| **Screaming eyebrows** | Tracked-out uppercase `FEATURES` / `OVERVIEW` above every heading | Sentence case, or nothing — a heading that needs a label is a weak heading |
| **Centered-everything hero** | `min-height: 100vh` with eyebrow, title, lede, AND CTA stacked on one centred axis | At most two centred elements; eyebrow or CTA sits off-axis (margin-aligned, right-flush, numeral-anchored) |
| **Badge floated over hero** | "New: v2.0" pill riding the headline's kerning | Badge inline with the eyebrow row or in the nav; never overlapping display type |
| **Metric duplication** | The same KPI in header, sidebar, and three cards | One source of truth per viewport; drill-downs below the single primary KPI banner |
| **Filter pollution** | Date picker repeated inside every card | One page-level control bar that syncs all views |
| **Space-wasting hero widget** | Giant 3D globe / world map at 60% of viewport with no actionable data | Compact bar comparisons, sparklines, or delta tables with tabular numbers |
| **Missing states** | Buttons with hover only — no focus-visible, active, loading, disabled | The full 8-state system (see [motion-states.md](motion-states.md)) |
| **Dead placeholders** | via.placeholder.com, hotlinked Unsplash, lorem ipsum in shipped copy | Inline SVG, CSS shapes, local verified assets, real copy |
| **Glassmorphism everywhere** | `backdrop-blur` on every surface | Blur reserved for floating chrome (sticky nav, overlays) — surfaces elsewhere stay solid |
| **Puffy shadows** | Triple-layer drop-shadow halo on cards | One shadow with a real offset and soft blur, or a hairline border; a zero-offset colored halo is decoration |
| **Mono-as-costume** | Monospace font to feel "technical" on non-technical text | Monospace only for code, data, measurements |
| **Pure black on pure white** | `#000000` / `#ffffff` bases with flat gray text | Tinted charcoal (`#090a0f`, `#0d0e12`), multi-step text (`zinc-100 → zinc-400`) |
| **Same-fade-everything** | Every element fades in with identical rhythm | One lead element, then staggered cascade (50–80ms steps) — or no entrance at all |
| **Fake data furniture** | Decorative dot-charts, ticks sprayed on gauges, fake magazine mastheads | Real charts from real data, or no chart — decoration pretending to be information is the worst tell |
| **Colored edge-stripe rails** | Thick `border-left` accent bars on every card/section | 1px hairline at most; if the accent must mark the card, mark it in one place, not every card |
| **Two-tone headline** | Half the headline in accent color mid-sentence | One voice per statement; contrast comes from scale, not from coloring nouns |

## The craft-floor (from impeccable — banned outright)

Nested cards; a colored `border-left` above 1px on cards/alerts; hard offset shadows (`4px 4px 0`) outside a genuinely neobrutalist world; section numbers (`01 / 02`) unless sequence carries information; a modal for a task needing neither interruption nor protected focus; display faces that ship as the platform default (source a real face whose character matches — the closest installed font is a failure, not a fallback); a boxless `<body>` (content with no max-width and no grid — a genuine layout bug, not taste); a 1px divider stranded in a huge grid track.

## Severity guide

- **HIGH** (strong AI signal, fix always): gradient text, emoji icons, 3-card grid as page structure, dead placeholders, vanity stats, centered-everything hero.
- **MEDIUM** (common slop, context-dependent): glassmorphism everywhere, mono-as-costume, same-fade-everything, badge-over-hero, edge-stripe rails.
- **LOW** (minor signal): pure-black-on-white with good typography elsewhere, single puffy shadow, one duplicated metric.

A punch list ranks HIGH first, then MEDIUM, then LOW — fix in batches by type (all icon swaps together, all color-token changes together), never one-off mixed edits.

## The refusal test

Before shipping any interface: *does this feel crafted by someone with extreme respect for the user's attention and time, or does it look like it was generated from a prompt?* If any element feels like prompt-slop, eliminate that element — not soften it. Then run the gates in [design-gates.md](design-gates.md).
