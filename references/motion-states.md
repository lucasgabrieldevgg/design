# motion-states — motion physics and the interaction layer

> Merged from: `wwewtech/anti-slop-design` (MIT — 8-state system), motion principles by **Emil Kowalski** (emilkowalski.dev, via anti-slop-design and vibe-superkit — duration-by-frequency matrix, easing, tactile feedback), `pbakaus/impeccable` (Apache 2.0 — verify list), and `Nutlope/hallmark` references/motion.md + interaction-and-states.md (MIT — reveal patterns, motion stance). See ATTRIBUTION.md.

This is the finish work: the layout is decided, the tokens are in place — this is what separates "looks fine in a screenshot" from "feels crafted under the cursor". The default generated motion is `transition: all 0.3s ease` on everything, which feels like wet cardboard. The replacement system:

## Duration by frequency (the decision matrix)

- Actions triggered 100+ times a day (command palette, row selection, keyboard shortcuts): **0ms. Never animate.** Speed is the feature.
- Standard interactions (tooltips, dropdowns, popovers): **120–180ms**.
- Modals and full-screen drawers: **200–250ms**.

## Easing

- `ease-in` is banned for UI — it starts slow and feels laggy.
- Tense ease-out: `cubic-bezier(0.23, 1, 0.32, 1)` (or the tighter `0.16, 1, 0.3, 1`).
- Popovers scale from their trigger point (`transform-origin: top left`), never from screen center.
- Where spring physics are available, prefer them over linear timing: `{ type: "spring", stiffness: 400, damping: 28, mass: 0.6 }` — weight and resistance instead of a curve.

**Tactile feedback:** on press, scale down 2–3% — `transform: scale(0.97); transition: transform 60ms ease-out`. Elements that do not respond to the cursor feel dead.

## Motion stance (pick one per project, say it in the Design Read)

- **Silent:** no entrances; color and state transitions only. Admin tools, dispatch screens, anything M ≤ 2.
- **1–2 reveal primitives:** one authored moment — a lead element, then children staggered 50–80ms apart, exponential ease-out from an already-visible default state. The golden middle.
- **Motion-cut / cinematic:** horizontal sweeps, type-unmask, scrollytelling — only for V ≥ 7 worlds that earn it (see [structure.md](structure.md) axis 6).

Entrances are one authored moment, not the same fade on every section. Beyond `transform` and `opacity`, the palette includes blur, `backdrop-filter`, `clip-path`, `mask`, and shadow — when they stay smooth (each on its own compositor-friendly property; never `transition: all`).

**`prefers-reduced-motion` is not optional.** Every motion rule needs a reduced variant; usually "no entrance, states still change color". Ignoring it is a shipped accessibility bug.

## The 8-state interactive system

Every interactive primitive ships all eight states or it ships broken:

```
Default → Hover → Focus-visible → Active/press
                Disabled ← Loading ← Error ← Success
```

The production button standard (adapt tokens to the chosen archetype):

```css
.btn-primary {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: 0.5rem;
  padding: 0.5rem 1rem;
  font-size: 0.875rem;
  font-weight: 500;
  line-height: 1.25rem;
  border-radius: var(--radius-sm, 6px);
  background: var(--accent-primary);
  color: var(--accent-foreground);
  border: 1px solid transparent;
  cursor: pointer;
  user-select: none;
  transition: background-color 140ms ease-out,
              transform 80ms ease-out,
              border-color 140ms ease-out;
}
.btn-primary:hover { filter: brightness(1.08); }
.btn-primary:focus-visible {
  outline: 2px solid var(--accent-primary);
  outline-offset: 2px;
}
.btn-primary:active { transform: scale(0.97); }
.btn-primary:disabled {
  opacity: 0.5;
  cursor: not-allowed;
  pointer-events: none;
}
```

Inputs need the same treatment: real `<label>`s, `:focus-visible` rings (`ring-2 ring-primary/20`), error states that name the problem and the recovery, disabled states that block and explain. Loading states: skeletons with a shimmer highlight, or preserved content — never a blank flash. Empty states are designed surfaces (what this space becomes when the user does the first thing), not blank voids.

## Keyboard and focus

Keyboard focus travels the page in a sane order; `tabindex` is not a minefield; no bare `outline: none` anywhere; icon-only buttons carry `aria-label`; semantic elements (`button`, `nav`, `main`) do structural work. Focus-visible styling differs from hover (mouse users never see rings they don't need; keyboard users always do).

## The motion verify list (against the render, not the intention)

- One authored entrance moment; high-frequency actions at 0ms.
- No `ease-in`; no `transition: all`; durations inside the matrix.
- Reduced-motion variant exists and works.
- All eight states present on primitives; focus ring visible on dark and light surfaces.
- Motion respects the M dial from the Design Read — a dispatch tool with parallax is a gate failure, not a flourish.
