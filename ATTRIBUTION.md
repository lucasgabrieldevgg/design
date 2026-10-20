# Attribution & Sources

`design` is an original synthesis for this repo, created by carrying the design track out of `theskill/craftsmanship` (where it lived as references merged from four upstream sources) and merging five new upstream sources researched and license-verified on 2026-10-20. The synthesis, structure, and merged rule set are MIT (same as this repo). Upstream material retains its original license; each reference file credits its sources inline.

## Carried from the theskill design track (merged there 2026-10-13)

| Source | What was merged | License |
| --- | --- | --- |
| `wwewtech/anti-slop-design` | The banned-trope matrix, archetypes A–D with CSS tokens, UX axioms (1-to-3, 85% law), 8-state system, surface hierarchy, 7-axis gate | MIT |
| `shahrukh-hack/vibe-superkit` | Aesthetic personalities, slop-vs-craft contrasts, micro-interaction principles | As upstream |
| `shinewinsu/vibe-frontend-design` | Design Read protocol, Three Dials, typography engineering scale, layout patterns | As upstream |
| `pbakaus/impeccable` v4.5.2 | Craft-floor refuse list, browser-surfaces rule, bounded-verification principle, the refusal test | Apache 2.0 |
| Emil Kowalski (emilkowalski.dev) | Duration-by-frequency decision matrix, easing rules, tactile-feedback principles — his motion work, encountered via the two repos above | Credited |

## New upstream sources (merged 2026-10-20, licenses read from cloned LICENSE files)

| Source | What was merged | License |
| --- | --- | --- |
| `Nutlope/hallmark` (★30k) | The structural fingerprint (six axes), macrostructure families and domain trios, structural anti-patterns (SaaS hero, 3-feature row, carbon-copy footer), the slop-test discipline (condensed from 58 gates + six-axis self-critique), the study/DNA-extraction flow, the portable `design.md` format, hero-shape and badge rules, OKLCH color anchors | MIT — © 2026 Hallmark contributors |
| `oil-oil/oil-ui` (v0.23.8) | The three-direction exploration (text before pixels, same copy across directions), evidence discipline (screenshots at 100%/200%, whole-page scroll, line-break reads), the independent-review protocol, the subtraction pass, scope-check routing (small change vs design task) | MIT — © 2026 oil-oil |
| `xiaopu-ai/web-design` | The spec-first DESIGN.md workflow (spec confirmed before code, flexible input handling: URL/screenshot/keywords/PRD) | MIT — © 2026 KAOPU-XiaoPu |
| `dominikmartn/nothing-design-skill` (v3.0.0) | Archetype E (Monochrome Industrial), the three-layer hierarchy rule, the font budget (2 families/3 sizes/2 weights), color-as-event, both-modes-first-class, declare-fonts-first rule | MIT — © 2026 Dominik Martin |
| `Gesso-Build/skills` — anti-slop (v0.4.3) | The deterministic-guard concept (objective grep-able checks before judgment), additional tell categories (puffy shadows, edge-stripe rails, fake data furniture, two-tone headlines), the `npx @gessobuild/anti-slop check` tool reference | MIT — © 2026 Gesso Build, Inc. |

## Individual credits

- **Emil Kowalski** — the motion system in `references/motion-states.md` is his work.
- **Hallmark contributors** (via Nutlope) — the structural-variety thesis ("structural sameness is the AI fingerprint, not visual sameness") and the fingerprint/macrostructure instrument in `references/structure.md` are theirs.
- **Nothing Technology Society-inspired design language** — archetype E follows `dominikmartn/nothing-design-skill`'s system, itself inspired by Nothing's industrial design language.
- **Gesso** — the deterministic critique discipline in `references/design-gates.md`.
- The authors of every repo above. Any errors in the merged synthesis are this repo's, not theirs.

## Surveyed, documented, not merged (2026-10-20 ecosystem survey)

| Source | Why not merged | License |
| --- | --- | --- |
| `nextlevelbuilder/ui-ux-pro-max-skill` (★137k) | Brand-asset generator (logo/banner/CIP/social photos via external APIs) — different scope from visual craft | MIT |
| `ConardLi/garden-skills` — web-design-engineer (★13k) | Canvas-tool skill (verify-facts-first pattern noted; CLI-driven workflow not portable to this synthesis) | MIT |
| `JimLiu/baoyu-design` (★4.4k) | Design-artifact generator (decks/docs/3D/email) — overlaps the pptx domain, not anti-slop craft | MIT |
| `plugin87/ux-ui-agent-skills` (★2.4k) | 25-skill DTCG/WCAG system — too heavy to merge whole; DTCG token-format awareness noted for future versions | MIT |
| `superdesigndev/superdesign-skill` (★853) | Infinite-canvas CLI tool, not mergeable methodology | MIT |
| `h3nryprod01/design-taste` (★77) | Another merge of overlapping sources (emilkowalski et al.) — nothing beyond what hallmark covers | MIT |
| `wilwaldon/Claude-Code-Frontend-Design-Toolkit` (★1.2k) | No license file — excluded on principle | none |
| `edisonmbli/refactoring-ui-skill` (★109) | Derivative of the copyrighted Refactoring UI book without a license — excluded | none |
| `yzfly/awesome-design-html` (★163) | No license — look-only | none |
| `AThevon/genjutsu` (★590) | Already an upstream of the sibling `motion` repo; NOASSERTION license here | — |

## Pointed sources (cataloged, not merged)

`references/design-sources.md` catalogs third-party design sites — component libraries, generators, galleries — with license labels verified on 2026-10-13 (carried from theskill, re-verification rule intact). These are pointers the agent may pull from or suggest; **no content from those sites is merged into this skill**.

## Provenance note

This repo is the design half of what was, until v1.0.0 of this skill, the design track of `lucasgabrieldevgg/theskill` (craftsmanship sub-skill). The split happened so both disciplines could be complete: `theskill` kept code craft, prose craft, and the development process; this repo owns visual craft. Both credit the same four upstream design sources for the material they share lineage from.

If you redistribute `design`, keep this file and the per-file credits with it.
