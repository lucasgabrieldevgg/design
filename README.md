# design

A big skill for **visual craft in AI-built interfaces** — born by carrying the design track out of `theskill` (where it shared a repo with the code track) and merging the best design skills found on GitHub, with `Nutlope/hallmark` (★30k, MIT) as the structural backbone. One discipline: interfaces that read as *designed*, not *generated* — visually and structurally.

```
The AI fingerprint is structural, not just visual: hero → 3-feature → CTA → footer.
Color-swapping the same skeleton still reads generated.
42,000 structural fingerprints exist; zero excuses for reusing one.
```

## Why it split from theskill

Until this repo, visual craft lived inside `theskill/craftsmanship` as one track beside code craft and prose craft. Both halves were compromises: the design track could not carry its full workflow (spec-first, direction exploration, DNA extraction, evidence discipline) inside a router that also had to serve code review and process, and the code track diluted its routing with design references. The split lets both be complete: `theskill` v2.0.0 owns code tells, prose tells, and the development process (now merged with `obra/superpowers`); this repo owns the visual discipline alone. They route to each other as siblings.

## What's inside

| Piece | What it does |
| --- | --- |
| **Banned tropes** (`references/banned-tropes.md`) | The visual-tell matrix — 22 tropes with replacements (gradient blobs, emoji icons, 3-card grids, screaming eyebrows, vanity stats, badge-over-hero, puffy halos, fake data furniture, two-tone headlines), the impeccable craft-floor, severity guide, the refusal test |
| **Structure** (`references/structure.md`) | The anti-template instrument: six fingerprint axes (heading placement, body composition, dividers, button voice, image treatment, reveal), macrostructure families (grid/document/poster/data/narrative-led), domain→trio routing, the five structural anti-patterns (SaaS hero, 3-feature row, carbon-copy footer) |
| **Archetypes** (`references/archetypes.md`) | Five committed visual worlds with full CSS token starters: Quiet Luxury SaaS, Technical Dense Terminal, Editorial Refined, Warm Tactile, Monochrome Industrial (from nothing-design) + typography personality mapping |
| **Typography** (`references/typography.md`) | The three-layer hierarchy rule, the font budget (2 families/3 sizes/2 weights), pairing catalog, the scale table, tabular numbers, optical alignment |
| **Color & surfaces** (`references/color-surfaces.md`) | OKLCH palette construction (paper band, one accent, rule color), the four-level surface hierarchy, 8pt spacing ladder + nested-radius formula, contrast floors, browser surfaces (selection/caret/scrollbars/focus) |
| **Motion & states** (`references/motion-states.md`) | Emil Kowalski's duration-by-frequency matrix (100+/day = 0ms), easing rules, the 8-state interactive system with the production button standard, motion stance, reduced-motion |
| **The flow** (`references/the-flow.md`) | The four-mode workflow: spec-first DESIGN.md, three contrasting directions (text before pixels), evidence at 100%/200%, independent review, subtraction pass, the STUDY path (DNA extraction from screenshot/URL), the portable design.md lock |
| **Gates** (`references/design-gates.md`) | Six-axis self-critique, deterministic sweep (objective before judgment), the 7-axis gate, the render verify list, the final assertion |
| **Design sources** (`references/design-sources.md`) | License-labeled catalog of copyable component code (Magic UI, HyperUI...), generators, look-only galleries, paid tiers + the five-rule copying discipline |

Plus a Cursor rules export at `exports/design.mdc`.

## The four modes

| Mode | Trigger |
| --- | --- |
| **DE-SLOP** | "this looks AI-generated" / "fix the design" — trope + structure scan, ranked punch list |
| **CREATE** | New page — Design Read, three directions from different macrostructure families, one committed world, then code |
| **RESTYLE** | "make it look professional" — behavior preserved as a hard contract, craft passes, one batched verify |
| **STUDY** | "make it like this" — extract the DNA from a screenshot/URL, diagnose, optionally lock a portable design.md |

## Install

**Claude Code / GLM / any SKILL.md host:**
```bash
git clone https://github.com/lucasgabrieldevgg/design.git ~/.claude/skills/design
```

**Cursor:** copy `exports/design.mdc` to `.cursor/rules/design.mdc`.

**ClawHub / skills.sh:** the folder is standard skill layout — publish as-is.

## The method (why structure is the other 70%)

Killing the purple gradients is the easy half — the matrix catches those on sight. The hard half is structural: models reach for the same page skeleton every time because nothing in the prompt forces a different *shape*. The fingerprint instrument (six axes, one pick each, coherence within a world, anti-repetition across siblings) plus macrostructure families turns "different" from a color-swap into a genuinely different page. Around it: spec-first flow (a DESIGN.md the user confirms before code), three contrasting directions in text before any pixels, evidence taken from renders at real zoom levels rather than remembered vibes, and gates that score before anything ships. The copying discipline exists because pasted components are how slop re-enters a calibrated page — one lift per source, re-skinned to the project's tokens, provenance in the commit.

## Verification

License labels in `references/design-sources.md` were verified 2026-10-13 (re-verify at the source before copying). Upstream licenses for the nine merged sources were read from cloned LICENSE files on 2026-10-20: hallmark MIT (© 2026 Hallmark contributors), oil-ui MIT (© 2026 oil-oil), web-design MIT (© 2026 KAOPU-XiaoPu), nothing-design-skill MIT (© 2026 Dominik Martin), Gesso anti-slop MIT (© 2026 Gesso Build, Inc.) — plus the four carried sources from theskill's original 2026-10-13 merge. The ecosystem survey (10 more candidates, including ui-ux-pro-max ★137k and garden-skills ★13k) is documented in ATTRIBUTION.md with merge decisions.

## Attribution

`design` is an original synthesis (MIT) merging upstream material from `Nutlope/hallmark` (MIT — the structural backbone), `wwewtech/anti-slop-design` (MIT), `shinewinsu/vibe-frontend-design`, `shahrukh-hack/vibe-superkit`, `oil-oil/oil-ui` (MIT), `xiaopu-ai/web-design` (MIT), `dominikmartn/nothing-design-skill` (MIT), `Gesso-Build/skills` anti-slop (MIT), and `pbakaus/impeccable` (Apache 2.0), with motion principles by Emil Kowalski (emilkowalski.dev). See [`ATTRIBUTION.md`](ATTRIBUTION.md) for per-source credits, the surveyed-not-merged list, and the theskill provenance note.

## License

MIT for this repo's original content. Upstream material retains its own licenses — see ATTRIBUTION.md.
