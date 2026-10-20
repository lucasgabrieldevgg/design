# the-flow — spec first, directions, evidence, review

> Merged from: `xiaopu-ai/web-design` (MIT — the spec-first DESIGN.md workflow, flexible input handling), `oil-oil/oil-ui` (MIT — the three-direction exploration, text-before-pixels rule, evidence discipline, independent review protocol, subtraction pass), and `Nutlope/hallmark` (MIT — the study verb, design.md portable format, scope-safety rails). See ATTRIBUTION.md.

One loop serves all four modes. The phases compress for small tasks, but none is skipped — the pattern behind all AI-looking output is skipped decisions; the flow puts the decisions back in.

## Phase 0 — Scope check (what kind of change is this?)

| Request shape | Path |
| --- | --- |
| Named element, named change ("make the save button green", "delete this badge") | Just do it; deliver with a one-line note. Skip the flow — this is not a design task |
| New interface, or "explore", or "redesign" | Full flow: Phase 1–5 |
| Direction already chosen (or continuing an approved one) | Enter at Phase 2; check only affected areas |
| Single component to perfect | Flow scoped to the component: one visual protagonist, effort concentrated on the main action's moment |
| Existing app, professional pass | RESTYLE: inventory pages/tokens/components, keep a baseline screenshot, fix from the source (design variables, not per-page patches) |
| Screenshot/URL the user admires | STUDY path (below) |
| Review only | Deliver diagnosis + evidence; fix nothing |

**Safety rail:** a design pass is not a license to bulldoze. Never delete routes, component directories, or pages unless the user explicitly approves a file-level plan listing the deletions. Brand assets and established patterns survive a restyle; the restyle may re-decide *accidental* visual defaults only.

## Phase 1 — Understand, then spec (CREATE)

Accept flexible input — any mix works: a reference URL (extract tokens, structure, motion audit; *reference* means extract the language and build an independent page, *replicate* is a different explicit ask) · a screenshot (extract temperament, color temperature, density, type feel) · keywords ("dark restrained serif" → match to an archetype) · a brand name ("like Linear" → check `references/design-systems/` notes or fetch) · a PRD (read positioning, page structure, handoff section). When two inputs conflict ("this URL but warmer"), extract + override, stating what overrode what.

Ask at most **one batched round of questions**, and only what would change the core direction: who uses it, the main task, the device, what "done" delivers. Detail you can reverse gets decided and stated as your assumption.

Then write the spec — **a DESIGN.md before code**:

```markdown
# Design — <project/page>
1. One-line intent: what this page is for, who wakes up using it
2. Design Read: [artifact / audience / world / dials V-M-D / macrostructure family]
3. Tokens: palette (OKLCH anchors), type pairing + scale, spacing ladder, radii
4. Structure: macrostructure + the six-axis fingerprint picks
5. Content inventory: the real copy blocks and data the page must carry
6. Non-goals: what this page is deliberately NOT doing
```

Small work: the spec is 6–10 lines in chat. Real product: the spec is a file the user confirms before code exists. If a DESIGN.md already exists in the project, read it first and amend intentionally — the file is the rule.

## Phase 2 — Three directions, text before pixels

Before building the full page, write **three contrasting directions** — from categorically different macrostructure families ([structure.md](structure.md) domain trio), each 3–4 lines: the feeling, the above-the-fold shape, the type and color, what carries the hero. State your recommendation and why. Then ask: pick one from text, or see all three rendered?

- **User picks from text** → build only that one.
- **User wants to see** → three real above-the-fold screens: one HTML file each, one viewport, hero only, primary state only — no interactions, no responsive work, no polish. Same example copy and data across all three; structures and styles written independently (not one template with three skins — that fakes variety). Then the user picks.
- **User said "you decide" / unattended** → still build the three, screenshot them side by side at 480px, pick with the reason stated aloud, and keep going.

A direction card ends with the **difference check**: set beside the benchmark sites of the category, does it read as a sibling or a twin? A twin goes back to the drawing board.

## Phase 3 — Build on the chosen direction

- The most representative page or the key flow first, checked, then spread outward.
- Real content at real sizes: sample data written like a real product would ship it; mock data, generated images, and not-yet-wired actions go in the delivery note, never on the canvas ("示例", "button not wired" on screen is a shipped tell). No invented business results, testimonials, or metrics.
- Every interactive primitive gets the full 8-state treatment ([motion-states.md](references/motion-states.md)) as it is built, not "later".
- Existing project: reuse the effective design variables, components, and interaction habits; fix at the source (the token), not per-page; never mix an unrelated refactor into visual work.

## Phase 4 — Evidence and independent review

**Take evidence, don't remember vibes.** Screenshot the built page at the target viewport (desktop + mobile together in one pass); look at 100% and 200% zoom on key areas; a long page gets scrolled end to end — check the whole rhythm, not just the hero. Chinese/multi-line titles and narrow screens get an actual line-break read: text overlapping, clipped, or fitting only via tiny type is a content/layout problem, fixed there — not with scaling.

**Dispatch a fresh reviewer when available** (subagent with no session history): give it the screenshot, the spec, and the constraint — it sees only the current render and judges against the gates. No subagent capability: self-review, labeled as such, and the user decides if that's enough. Review findings enter ONE fix pass (Critical and Important), each fix verified in the next render; minors get noted, not endlessly polished.

**The subtraction pass** — run once before delivery: every screen keeps exactly one protagonist and the rest goes quiet; walk each block deleting repeated explanations; keep only sentences whose removal would damage understanding. Subtraction deletes decoration and repetition — object names, judgment basis, current state, and the primary action always survive.

## Phase 5 — Gate and deliver

Run [design-gates.md](design-gates.md) (7-axis score + slop-test sweep). Deliver with a short note: the chosen direction and why; what changed and what was deliberately not done; the motion authored; review rounds and scores; what the subtraction pass removed; where the evidence files live.

## The STUDY path (DNA extraction)

User pastes a screenshot or URL they admire. **Diagnose, never copy pixels.**

1. **Extract the DNA:** macrostructure + fingerprint axes · archetype/token structure (canvas/surface/rule/accent bands, exact values from CSS in URL mode, estimated from bands in image mode) · type pairing and scale · the motion stance · the copy voice. A URL routes to reading the page's HTML/CSS; an auth-walled or JS-shell page falls back to asking for a screenshot.
2. **Report the diagnosis:** what the DNA is, what it would cost to run (density, imagery appetite, type licensing), which parts transfer to the user's content and which don't.
3. **Three follow-ups, user picks:** rebuild the user's content in that DNA (handoff to the normal flow) · lock the DNA into a portable `design.md` · stop at the diagnosis.

**Refusals:** template-marketplace URLs get declined. Locking a `design.md` from a third-party site requires the user's attestation that it's their own design or a reference they have rights to. Never re-emit a protected identity as a "system".

## The portable design.md (lock the system)

After the user has iterated and is satisfied, "lock the system" freezes the working DNA into ~45 lines at the project root: System (world/macrostructure/dials), Tokens (the canonical CSS block), CTA voice, motion stance, Exports pointer. Once written: future runs read it first, pages *share* the system (the variety rule inverts), and changes amend the file rather than overriding per-page. Opt-in only — auto-emitting on every build would churn the file across iterations or lock a weak system before it settled.
