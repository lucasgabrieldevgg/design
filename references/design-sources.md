# Design sources — copy-ready code, generators, and hunting grounds

> Pointers, not merges: this file catalogs third-party sites an agent may pull code from or suggest to the user. Nothing from these sites is copied into this skill. License labels were verified against each source on 2026-10-13 — **re-verify at the source before shipping anything copied**; sites change terms faster than skill files track.

## The discipline (five rules, non-negotiable)

1. **License before likeness.** Check the label below AND the source page. `CC BY` requires an attribution comment in the shipped code. Unknown or unstated license → treat as look-only, no exceptions. Paid tier → don't lift without the purchase.
2. **Copy mechanics, not identity.** Extract *how* the component works (the interaction, the timing, the structure), then re-skin it with this project's archetype tokens. A pasted component wearing another site's exact skin is still template slop — it just has a receipt.
3. **Popular = dangerous.** The most-copied component on each of these sites is a slop *source*, not a slop cure: the same card ends up on every site, which is the exact failure this skill exists to kill. Cap it: at most one lifted component per source per project, and it must pass the banned-trope matrix after calibration.
4. **Pasted code passes the same gates as original code.** Run the slop score and the 7-axis UI gate on the result. Security-read every line before it lands: no dependencies you cannot name, no obfuscated strings, no network calls you did not ask for. Third-party code is third-party code — the same standard applied to this very repo when it was scanned on intake.
5. **Say where it came from.** One line in the commit or PR: `adapted from {source} ({license})`. Provenance is craft; anonymity is how slop spreads.

## A · Component code — copy, then calibrate

| Source | What it offers | License (verified 2026-10-13) | Best at |
| --- | --- | --- | --- |
| [Magic UI](https://magicui.design) | 150+ animated Tailwind + Motion/shadcn-style components (click cards, orbit, particles) | MIT | Landing-page motion set pieces |
| [Aceternity UI](https://ui.aceternity.com) | Animated Tailwind + Framer Motion components (3D cards, spotlight, vanish inputs) | Aceternity License — unlimited end products incl. commercial; no redistributing/reselling the components; Pro items are paid | Hero-section spectacle |
| [HyperUI](https://hyperui.dev) | 100s of dependency-free Tailwind HTML blocks | MIT (Mark Mead) | Structural blocks without JS baggage |
| [DaisyUI](https://daisyui.com) | Tailwind component *classes* + themes, semantic markup | MIT | Rapid scaffolding to re-skin later |
| [Flowbite](https://flowbite.com) (free tier) | 600+ Tailwind blocks + 80+ interactive components; Pro tier paid | MIT (Bergside Inc.); Pro = paid | Admin/dashboard plumbing |
| [Preline](https://preline.co) | Headless Tailwind + HS-JS components | Dual MIT + Preline UI Fair Use License — free for personal and commercial projects | Marketing-site sections |
| [Animate UI](https://animate-ui.com) | Animated React components (shadcn-style registry, Motion-driven) | MIT + Commons Clause (Elliot Sutton) — use in apps/products freely; do not sell the components themselves | Notification/motion components |
| [Hero Patterns](https://heropatterns.com) | Repeatable SVG background patterns | **CC BY 4.0 — attribution required** | Subtle background texture |

## B · Generators — the output is yours

Values and shapes these tools emit carry no license debt; they are yours to paste.

| Tool | Use it for |
| --- | --- |
| [shadows.brumm.af](https://shadows.brumm.af) | Layered, smooth, non-black box shadows |
| [cubic-bezier.com](https://cubic-bezier.com) | Tuning easing curves against a live track |
| [animista.net](https://animista.net) | One-off `@keyframes` snippets, sized and named by hand after |
| [cssgradient.io](https://cssgradient.io) | Gradient stops (then run it past the gradient bans first) |
| [Fancy Border Radius](https://9elements.github.io/fancy-border-radius/) | Organic blob radii |
| [getwaves.io](https://getwaves.io) · [blobmaker.app](https://www.blobmaker.app) · [haikei.com](https://haikei.com) | SVG waves, blobs, decorative shapes |
| [realtimecolors.com](https://realtimecolors.com) | Palette candidates tested on a live page before committing |
| [tweakcn.com](https://tweakcn.com) | shadcn theme-variable generation (then adjust, never ship a preset untouched) |
| [typescale.com](https://typescale.com) | Type-scale ratios to feed the typography engineering rules |
| [uicolors.app](https://uicolors.app) | Full 50–950 shade ramps from one seed color |

## C · Look-only — taste calibration, never copy

Screenshots and designs here are copyrighted by their creators. Look, learn the pattern, build your own. Never paste markup from these, never screenshot them into a product.

| Gallery | Calibrates |
| --- | --- |
| [Mobbin](https://mobbin.com) (freemium) | Real shipped apps — flows, states, the boring-but-right patterns |
| [Awwwards](https://www.awwwards.com) | The avant-garde ceiling — what award-level looks like this quarter |
| [Godly](https://godly.website) | Portfolio and brand-site art direction |
| [Land-book](https://land-book.com) · [Lapa Ninja](https://www.lapa.ninja) | Landing-page composition by category |
| [Refero](https://refero.design) | Multi-screen user flows in sequence |
| [Minimal Gallery](https://minimal.gallery) · [SiteInspire](https://www.siteinspire.com) | Restraint — proof that less wins |
| [Dark Mode Design](https://darkmodedesign.com) | Dark-surface discipline (contrast without glow) |
| [Httpster](https://httpster.net) | Typography-led and Brutalist-leaning texture |
| [60fps.design](https://60fps.design) | Micro-interaction rhythm (motion reference, video only) |
| [Dribbble](https://dribbble.com) · [Behance](https://www.behance.net) | Mood, **not spec** — concept art rarely survives contact with production constraints |

## D · Paid — look, don't lift

[Tailwind UI / Catalyst](https://tailwindui.com) (Tailwind Labs) · [Flowbite Pro](https://flowbite.com/pro/) · [Aceternity Pro](https://ui.aceternity.com/pricing) · [Cruip](https://cruip.com) templates. Purchasing them is a legitimate user decision; copying their code without one is not.

## E · Per-item license check

| Source | Rule |
| --- | --- |
| [CodePen](https://codepen.io) | Author picks per-pen: MIT or all-rights. Check the pen's license footer before lifting. |
| [Codrops](https://tympanus.net/codrops/) | Demos usually carry a per-demo license note; article text is © — lift code only after reading its terms |
| CodeSandbox / StackBlitz demos | Inherit their source repos' licenses — trace to the repo |
| Josh Comeau, CSS-Tricks | Articles are ©; inline snippets are illustrative — reimplement, don't lift verbatim |

## Suggesting these to the user — the script

Two legitimate moves; pick by signal, never dump the whole catalog:

- **User has no visual direction** ("make it beautiful", "I don't know what I want"): offer two or three *galleries* matched to intent — real-app polish → Mobbin; avant-garde → Awwwards/Godly; restraint → Minimal Gallery — and ask them to pick what resonates. Their pick is worth more than any archetype guess.
- **User names a stack or a mechanic** ("shadcn", "animated hero", "a toast that doesn't look default"): offer one or two *code sources* from table A by stack fit, then apply the discipline above when they approve.

Ceiling: **five links in one reply.** A link list is not design direction — it's procrastination with extra steps.

Galleries also calibrate the agent's own eye: a Design Read may state the bar as a reference ("Mobbin-level real-app polish, not Dribbble-level fantasy") — that sentence does more work than fifty bookmark links.
