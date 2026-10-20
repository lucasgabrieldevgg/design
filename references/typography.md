# typography — the interface's voice

> Merged from: `shinewinsu/vibe-frontend-design` (typography engineering, scale), `wwewtech/anti-slop-design` (MIT — numbers, spacing interplay), and `dominikmartn/nothing-design-skill` (MIT — the three-layer rule, the font budget, the hierarchy-not-size principle). See ATTRIBUTION.md.

Typography is the interface's voice; most generated output uses one bored monotone. It is also the cheapest human signal: type decisions are visible in every screenshot.

## The three-layer rule (hierarchy's spine)

Every screen has exactly **three layers of importance** — not two, not five:

| Layer | What | How |
| --- | --- | --- |
| **Primary** | The ONE thing the user sees first: a number, a headline, a state | Display face at display size, 48–96px breathing room |
| **Secondary** | Supporting context: labels, descriptions, related data | Body face, grouped tight (8–16px) to the primary |
| **Tertiary** | Metadata, nav, system info | Caption/mono, pushed to edges or bottom |

The test: squint at the screen. Can you still tell what's most important? If two things compete, one needs to shrink, fade, or move. The common mistake is making everything "secondary" — evenly-sized elements with even spacing = visual flatness. Be brave: make the primary absurdly large and the tertiary absurdly small. The contrast IS the hierarchy.

## The font budget

Per screen, maximum: **2 font families** (display + body, or body + mono) · **3 font sizes** (one large, one medium, one small) · **2 font weights** (regular + one other). Every additional size or weight costs visual coherence. Before adding a distinction, ask the decision table:

| Decision | Size? | Weight? | Color? |
| --- | --- | --- | --- |
| Heading vs. body | Yes | No | No |
| Label vs. value | No | No | Yes |
| Active vs. inactive nav | No | No | Yes |
| Hero number vs. unit | Yes | No | No |

**Rule of thumb:** reaching for a new font-size is usually a spacing problem. Add distance instead.

## Pairing

Maximum two families: a display face with actual character + a body face built for reading. Characterful pairs that work: `Fraunces` + `Plus Jakarta Sans` (editorial warmth) · `Space Grotesk` + `Inter Tight` (Swiss precision) · `Playfair Display` + `Newsreader` (long-form elegance) · `JetBrains Mono` pairings for terminal-archetype surfaces · `Doto` + `Space Grotesk` + `Space Mono` (monochrome industrial — the one three-family exception, hero numbers only). Source and self-host the display face; shipping the platform default as the display voice is the closest-installed-font failure. Declare the font load (Google Fonts or self-hosted `@font-face`) before any design work — never assume faces are available.

## The scale

Proportional steps, not invented values:

| Role | Size | Line height | Tracking | Weight |
| --- | --- | --- | --- | --- |
| Display/Hero | 36–72px | 1.05–1.1 | −0.03em to −0.04em | 600–700 |
| H1 | 36–40px | 1.15 | −0.025em | 600–700 |
| H2 | 24–30px | 1.2 | −0.02em | 600 |
| H3 | 18–20px | 1.3 | −0.01em | 600 |
| Body | 14–16px | 1.6 (relaxed) | normal | 400 |
| Meta/caption | 12–13px | 1.4 | normal | 500 |

Every large sans heading gets negative tracking (`tracking-tight`); untracked large type is on the banned-trope list. Measure caps at 65–75ch for body (`max-w-prose`). Display max 6rem — past that, scale stops adding and starts shouting.

## Steps must be obvious

If H2 does not read clearly bigger than H3, the hierarchy does not exist. When torn, make the step larger, not smaller.

## Numbers

`font-variant-numeric: tabular-nums` on every metric, price, timestamp, and table column (Tailwind: `tabular-nums`). Proportional digits jittering in a live dashboard is an instant amateur tell. Typeset big figures like a designer would: `$1.84M` not `$1,842,000` raw; align units as smaller, muted suffixes on hero numbers (the hero-number-vs-unit row above).

## Optical alignment

Icon-text pairs: `gap-1.5` to `gap-2`, icon sized to the font's x-height (16px icon for 14px text). Pure mathematical centering of unlike shapes reads wrong; optical centering reads right. Underline offset on body links; `text-wrap: balance` on headings so a wrapped headline doesn't strand one word.

## Copy is typography's content

The product's own language: controls name their action ("Track a load", not "Transform your logistics"), errors name the problem and the recovery, and nothing ships as lorem. Headlines earn their scale with specifics — a 140px generic claim is worse than a 44px specific one.
