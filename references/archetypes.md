# archetypes — the five visual worlds

> Merged from: `wwewtech/anti-slop-design` (MIT — archetypes A–D with tokens), `shahrukh-hack/vibe-superkit` (aesthetic personalities), and `dominikmartn/nothing-design-skill` (MIT — archetype E, the Nothing discipline). See ATTRIBUTION.md.

Pick **one per project** and commit. Mixing archetypes mid-page is the fastest way back to slop. Each block is a complete token starter — adapt hues to the brand, keep the *structure* of the relationships: canvas darkest, surfaces stepping up, one accent, minimum two text steps.

## A — Quiet Luxury SaaS (B2B tools, dashboards, pro apps)

```css
:root {
  --bg-canvas: #09090b;
  --bg-surface: #121215;
  --bg-surface-elevated: #18181c;
  --border-subtle: rgba(255,255,255,0.08);
  --border-hover: rgba(255,255,255,0.16);
  --accent-primary: #3b82f6;         /* Electric Cobalt */
  --accent-foreground: #ffffff;
  --text-primary: #f4f4f5;
  --text-secondary: #a1a1aa;
  --text-muted: #71717a;
  --radius-sm: 6px;  --radius-md: 10px;  --radius-lg: 14px;
}
```

Reference feel: Linear. Restraint as luxury; the accent appears on exactly one primary action per viewport.

## B — Technical Dense Terminal (DevTools, FinTech, observability)

```css
:root {
  --bg-canvas: #0c0d0e;
  --bg-surface: #141618;
  --bg-surface-elevated: #1a1d20;
  --border-subtle: #24282c;
  --border-hover: #383e44;
  --accent-primary: #10b981;         /* Precision Emerald */
  --accent-secondary: #f59e0b;       /* Amber for alerts only */
  --text-primary: #e6edf3;
  --text-secondary: #8b949e;
  --font-mono: 'JetBrains Mono', monospace;
  --radius-sm: 2px;  --radius-md: 4px;
}
```

Reference feel: GitHub dark, Bloomberg. Density is the point; tabular numbers everywhere.

## C — Editorial & Refined (media, portfolios, long-form, landing pages with taste)

```css
:root {
  --bg-canvas: #faf8f5;
  --bg-surface: #ffffff;
  --border-subtle: #e8e4df;
  --border-hover: #d1ccc4;
  --accent-primary: #1a1a1a;         /* Ink is the accent */
  --text-primary: #1a1918;
  --text-secondary: #635f59;
  --font-display: 'Playfair Display', serif;   /* or Fraunces */
  --font-body: 'Newsreader', 'Inter', sans-serif;
  --radius-sm: 0px;  --radius-md: 2px;
}
```

Reference feel: Stripe Press, Kinfolk, high-end journals. Asymmetry, generous whitespace, ink and paper.

## D — Warm Tactile (consumer products, creator tools, physical goods)

```css
:root {
  --bg-canvas: #f4f4f0;
  --bg-surface: #ffffff;
  --border-subtle: #e2e1db;
  --border-hover: #cbcac4;
  --accent-primary: #d97706;         /* Warm Ochre */
  --text-primary: #1c1917;
  --text-secondary: #78716c;
  --radius-sm: 8px;  --radius-md: 16px;  --radius-lg: 24px;
}
```

Reference feel: Teenage Engineering, Apple Pro pages. Tactile radii, warm neutrals, photography-forward.

## E — Monochrome Industrial (tools, hardware, spec sheets, anything that wants Nothing-style rigor)

```css
:root {
  --bg-canvas: #0a0a0a;              /* dark: OLED black; light: warm off-white #f5f4f0 */
  --bg-surface: #111111;
  --border-subtle: #1f1f1f;
  --text-primary: #ececec;
  --text-secondary: #8f8f8f;
  --font-display: 'Doto', 'Space Grotesk', sans-serif;   /* Doto for hero moments only */
  --font-body: 'Space Grotesk', sans-serif;
  --font-mono: 'Space Mono', monospace;
  --radius-sm: 0px;  --radius-md: 2px;  /* near-zero: the box is the box */
}
```

Reference feel: Nothing OS, Braun, Teenage Engineering spec sheets. **Monochrome is the canvas — color is an event, not a default** (exception: color encoding data status, which is information, not decoration). Both dark and light mode are first-class; ask which to start with. Declare the Google Fonts load before any design work — never assume fonts are available.

## Typography personality mapping

Editorial pairs `Fraunces`/`Playfair` + `Plus Jakarta Sans` · Swiss Precision pairs `Space Grotesk` (tracking −0.04em) + `Inter Tight` · Tactile Luxe pairs a heavy geometric display + crisp mono tags · Monochrome Industrial pairs `Space Grotesk` + `Space Mono` (+ `Doto` for hero numbers). Default prohibition: unmodified Inter as the *entire* type system. Two families maximum, display + body (or display + mono for data-heavy surfaces). Full discipline in [typography.md](typography.md).

## Choosing when the user hasn't

Ask one question — *"what does this thing do, and who wakes up using it?"* — then map: operations/dispatch/fintech → B · B2B productivity → A · content/brand storytelling → C · consumer/physical goods → D · hardware/spec/utilitarian → E. When the user gives a reference ("like Linear"), run the STUDY path in [the-flow.md](the-flow.md) instead of guessing. When they give a vibe word only ("modern"), that is not a direction — ask for a reference or map the domain. State the pick aloud with the reason: *"Going Technical Terminal — night-shift dispatch data at arm's length wants density and emerald status, not luxury restraint."*
