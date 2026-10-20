---
name: design
description: "The visual-craft skill for AI-built interfaces: make UI read as designed, not generated. Four modes cover the whole design surface. DE-SLOP: audit existing HTML/CSS/components against the banned-trope matrix and the structural-sameness fingerprint (the AI fingerprint is structural — hero, 3-feature row, CTA, footer — not just visual), returning a ranked punch list. CREATE: build new pages with a spec-first flow — a stated Design Read, three contrasting directions from different macrostructure families, one committed visual world (five archetypes with full tokens), then code. RESTYLE: the professional pass on an existing app — typography engineering, color and surface hierarchy, spacing geometry, motion physics, 8-state primitives — with behavior preservation as a hard contract. STUDY: extract the DNA (macrostructure, archetype, type pairing, color anchors) from a screenshot or URL the user admires, diagnose it, and optionally lock it into a portable design.md. Covers the banned tropes (gradient blobs, emoji icons, 3-card grids, screaming eyebrows, vanity stats, dead placeholders), typography and color discipline, layout patterns, accessibility floors, and the pre-emit gates. Use for ANY request about how an interface looks, reads, or feels — 'make it look professional', 'this looks AI-generated', 'fix the design', 'make it pop', 'give it personality', 'redesign this', 'audit my UI', 'de-slop my app' — and for choosing components or references to copy from the license-labeled catalog."
version: 1.0.0
license: MIT for the synthesis; upstream content keeps its own licenses - see ATTRIBUTION.md
---

# design — interfaces that read as designed, not generated

The test for everything this skill produces: a working designer opens the result and cannot tell the model made it. Not because AI assistance is hidden, but because the work carries what human design always carries — one committed visual world, structure that follows the content, hierarchy visible from across the room, and nothing decorative that is not also structural.

Generated UI fails that test in two predictable ways, and both must be attacked or nothing else matters. **Visually**: the same purple gradient glow, the same three identical cards, the same emoji icons, Inter-on-everything — assembled from defaults instead of chosen. **Structurally**: pages that look different but are the same shape — centered hero, three-feature row, CTA, footer, everything fades in. Structural sameness is the deeper AI fingerprint; a new color palette over the same skeleton still reads generated. This skill treats both: the trope matrix kills the visual defaults, the structural fingerprint kills the template shape.

**Load on demand.** This SKILL.md is the only always-load surface. References route by task — loading all nine at once burns context on rules the task never touches.

## The design contract

Four rules that explain every specific rule that follows.

1. **Decide, don't default.** Every element traceable to a choice — this palette, this skeleton, this rhythm — because the content and the use scene call for it. The statistical middle of the training data is exactly what "looks AI" means.
2. **Structure follows content.** The layout grows from what the page is actually for, not from a container library. Two pages for two different briefs should not share a skeleton.
3. **Restraint is a feature.** Deleting a card, a badge, a gradient, an animation is often the highest-value edit. Audit for what can be removed before adding anything.
4. **Verify the render, not the intention.** Every check runs against the actual output — the rendered page at real viewport sizes, the screenshot at 100% and 200%. "I meant to" does not count.

## The four modes

| Mode | Triggers | Flow |
| --- | --- | --- |
| **DE-SLOP** | "this looks AI-generated", "fix the design", audit an existing screen | Scan against [banned-tropes](references/banned-tropes.md) + [structure](references/structure.md) anti-patterns → ranked punch list by severity → smallest honest diff → gates |
| **CREATE** | New page, landing, dashboard, portfolio — "don't make it look generic" | Design Read → three contrasting directions (different macrostructure families) → user picks → archetype tokens + structural fingerprint → build → gates |
| **RESTYLE** | "make it look professional", professional pass on an existing app | Preserve behavior (hard contract) → typography, color, spacing, motion, states passes from the craft references → one batched verification render → gates |
| **STUDY** | User admires a screenshot/URL: "make it like this" | Extract the DNA — macrostructure, archetype, type pairing, color anchors → diagnosis report → optionally rebuild the user's content in that DNA or lock a portable `design.md` |

Most real work mixes modes: a restyle usually starts with a DE-SLOP scan; a create ends with the RESTYLE finish work. That is expected — run both, in that order.

## The Design Read (mandatory first line)

Before writing any HTML/CSS/component, one line pins the work and closes the escape route to the middle:

> **`Design Read: building [artifact] for [audience], in [visual world], dials [V=? / M=? / D=?], structure [macrostructure family].`**

- `Design Read: building a freight-dispatch dashboard for night-shift controllers, in a Technical Terminal world, dials [V=3 / M=2 / D=8], structure: workbench (high-density, table-led).`
- `Design Read: building an indie perfume brand landing page for gift shoppers, in an Editorial world, dials [V=7 / M=4 / D=3], structure: letter (document-led, asymmetric).`

**The Three Dials** calibrate what "good" means per context: **VARIANCE** V1–10 (1–3 regulated/enterprise strict symmetry → 7–8 consumer bento and dimensional whitespace → 9–10 studio-tier collisions); **MOTION** M1–10 (1–2 near-static admin, color transitions only → 5–7 parallax and magnetic buttons → 8–10 cinematic); **DENSITY** D1–10 (1–3 gallery whitespace → 4–5 landing golden middle → 9–10 trading terminals). A dispatch tool at V=9 is wrong; a studio portfolio at V=2 is wrong. The dials make taste explicit instead of vibes.

## The hard bans (binary, non-negotiable)

When a ban conflicts with an explicit user instruction, the user wins — note the override and proceed.

- Purple/indigo radial gradient blobs on dark backgrounds; gradient text (`background-clip: text`); glowing card borders.
- Raw emoji standing in for an icon system. Icons: one library, one stroke weight (Lucide/Phosphor/Heroicons).
- Three identical icon-heading-text cards as the page structure; nested cards.
- Uppercase tracked-out eyebrow labels above headings; centered-everything heroes (all of eyebrow/title/lede/CTA on one axis).
- Vanity metrics with no source ("99.9% uptime", "10x faster") decorating a layout.
- Placeholders that 404 in production (placeholder.com, hotlinked Unsplash, lorem ipsum in shipped copy).
- Unmodified Inter (or Roboto/Poppins/Open Sans/Lato) as the entire type system.
- `transition: all 0.3s ease` on everything; `ease-in` for UI; ignoring `prefers-reduced-motion`.

## The workflow spine

1. **Read before making** — the Design Read line, plus (CREATE) the domain→trio routing from [structure](references/structure.md): offer three macrostructures from *categorically different* families, never one default.
2. **Diagnose against the catalogs** — trope matrix + structural fingerprint, flagged with severity, whole field seen before fixing.
3. **Prescribe the smallest honest diff** — grouped batches (all renames together, one archetype everywhere at once). Never bundle restyle with behavior changes; a bug found mid-restyle is flagged for a separate change.
4. **Verify behavior survived** (RESTYLE) — interactive logic, form state, and data handlers from the original survive; visual refactors never discard function.
5. **Run the gate before delivery** — [design-gates](references/design-gates.md): the 7-axis score, the slop-test sweep, the render pass at 100% and 200%.

## Reference routing

| The work | Reference |
| --- | --- |
| Auditing or restyling any screen — what to flag | [references/banned-tropes.md](references/banned-tropes.md) |
| Page shape, layout, breaking the template skeleton | [references/structure.md](references/structure.md) |
| Choosing the visual world + full token starters | [references/archetypes.md](references/archetypes.md) |
| Type pairing, scale, hierarchy discipline | [references/typography.md](references/typography.md) |
| Color tokens, contrast, surface hierarchy | [references/color-surfaces.md](references/color-surfaces.md) |
| Motion physics and the 8-state interactive system | [references/motion-states.md](references/motion-states.md) |
| The full create flow: spec, directions, evidence, review | [references/the-flow.md](references/the-flow.md) |
| Pre-emit gates and the slop-test | [references/design-gates.md](references/design-gates.md) |
| Copyable component code, generators, look-only galleries | [references/design-sources.md](references/design-sources.md) |

Typical combinations: "Build a dashboard" → structure (pick the family) → archetypes (tokens) → typography + color (foundation) → motion-states (primitives) → the-flow (evidence) → design-gates. "De-slop this page" → banned-tropes → structure → gates. "Make it like Linear" → the-flow's STUDY path → archetypes → gates.

## Calibration, not uniformity

The failure mode to avoid: producing a new template. Perfectly uniform spacing, identical rhythm everywhere, one radius on everything — that is also a machine signature. Human design has deliberate asymmetry, one section that breaks the grid on purpose. The gates ask *was this decided?* — a documented inconsistency passes; an accidental one fails. Break a rule loudly and once, not timidly and everywhere.

## Relationship to the sibling skills

Code tells, prose tells, and development process belong to the sibling `theskill` repo (craftsmanship: anti-vibe-code, prose-git, and the execution process). Security belongs to `security`. This repo is the visual discipline alone — use them together on any real product; this skill routes code-quality findings it finds mid-restyle instead of fixing them here.

## Attribution

Original synthesis for this repo, merging nine upstream sources (five new: `Nutlope/hallmark`, `oil-oil/oil-ui`, `xiaopu-ai/web-design`, `dominikmartn/nothing-design-skill`, `Gesso-Build/skills`; four carried from the theskill design track: `wwewtech/anti-slop-design`, `shahrukh-hack/vibe-superkit`, `shinewinsu/vibe-frontend-design`, `pbakaus/impeccable` + Emil Kowalski's motion principles). See [ATTRIBUTION.md](ATTRIBUTION.md); upstream licenses apply to their material.
