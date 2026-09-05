# Design Standard: 3AM Datacenter

Reference document for any visual decision on this site. If a choice isn't covered here, default to the most restrained option — this world is defined by what it withholds, not what it adds.

## 1. Colour Palette

**Backgrounds** (darkest to slightly raised — use to imply depth, never a hard shadow)
| Token | Hex | Use |
|---|---|---|
| `void` | `#05070a` | Page base. The default background everywhere. |
| `floor` | `#090d12` | Bottom-of-gradient tone the void fades into; never used as a flat fill on its own. |
| `panel` | `#0d1218` | Cards, the terminal/log panel, any content block raised one step off the page. |
| `panel-2` | `#10161d` | Hover/active state for a panel — one step brighter than `panel`, never more. |

**Text**
| Token | Hex | Use |
|---|---|---|
| `ink` | `#dfe8ee` | Primary text — headlines, body copy, anything the reader must read. |
| `ink-dim` | `#8fa2ad` | Secondary text — subheadlines, card descriptions, supporting copy. |
| `ink-faint` | `#566772` | Tertiary text — timestamps, meta labels, footer fine print. Never used for anything the reader must read to understand the page. |

**Accent**
| Token | Hex | Use |
|---|---|---|
| `cyan` | `#5eead4` | Primary accent — CTA fills, active link colour, headline emphasis (gradient text), the default "status LED" colour. This is the one colour allowed to feel alive. |
| `blue-glow` | `#3fb6e0` | Secondary accent — paired with cyan in gradients and ambient glow only; never used alone for text or UI. |
| `green` | `#4ade80` | Status-nominal indicator only (a pulsing dot, an "OK" tag). Never decorative. |
| `amber` | `#f2b155` | Status-watching/warn indicator only, used at roughly 1/10th the frequency of green. Never decorative, never a CTA colour. |

**Structure**
| Token | Value | Use |
|---|---|---|
| `hairline` | `rgba(140,170,190,0.10)` | Default dividing line — section borders, card grids, table rules. |
| `hairline-strong` | `rgba(140,170,190,0.18)` | Emphasis divider — under a CTA link, around a focused/hovered panel. |

**Rule of use:** every screen should read as almost entirely `void`/`ink`/`ink-dim`, with `cyan` appearing in no more than a handful of places at once (one CTA, one active indicator, one headline emphasis). If a design has more than 3 distinct accent colours visible at the same time, it has drifted off-brief.

## 2. Typography

**Families**
- **Inter** — body copy, headlines, paragraph text. Carries the human, readable voice of the page.
- **JetBrains Mono** — anything technical or data-flavoured: eyebrows/status labels, stat values, log lines, CTA labels, nav labels, timestamps. Carries the "system" voice.

Never mix the two within a single text element. A component is either speaking as Inter (prose) or JetBrains Mono (system readout).

**Weights**
- Inter: 300 (body default), 400 (emphasis within body), 500 (card/subsection headings), 600 (rare — top-level nav or brand mark only if not monospace).
- JetBrains Mono: 400 (log lines, meta text), 500 (stat values, CTA labels), 600 (brand mark, section eyebrows).

Headlines are set *lighter* than most UI conventions (300, not 600–800) — weight is not how this system signals importance; scale and colour do that instead.

**Type scale** (desktop; scale down ~15–20% at the mobile breakpoint via `clamp()`, don't jump between fixed sizes)
| Level | Size | Line height | Letter spacing | Weight |
|---|---|---|---|---|
| H1 (hero headline) | 44–72px (`clamp(2.75rem, 6vw, 4.5rem)`) | 1.08 | -0.02em | 300 |
| H2 (section heading) | 26–36px | 1.3 | -0.01em | 300 |
| H3 (card/subsection) | 17px | 1.4 | -0.005em | 500 |
| Body | 15–17px | 1.7–1.75 | normal | 300 |
| Small / label / mono meta | 11–13px | 1.5–2.0 | 0.05–0.14em | 400–600, uppercase for eyebrows only |

**Governing ratio:** each heading level should feel like a clear, confident step down from the one above it (roughly 1.4–1.6× the level below), while body text stays generously spaced (line-height ≥1.7) so paragraphs read as calm rather than dense. Mono/label text always tracks wider (positive letter-spacing) than prose, which stays at normal tracking.

## 3. Spacing

**Base unit: 4px.** Every spacing value on the site is a multiple of 4, expressed in the scale below — no arbitrary one-off values (e.g. no 13px or 22px paddings).

| Step | Value | Typical use |
|---|---|---|
| xs | 4px | Icon-to-label gaps, tight inline spacing |
| sm | 8px | Space between a label and its value |
| md | 16px | Space between related elements (headline → subhead) |
| lg | 24px | Card internal padding, gap between grid items |
| xl | 32px | Page horizontal margin (mobile), gap between hero elements |
| 2xl | 48px | Space between a section's heading block and its content |
| 3xl | 64px | Vertical gap between minor sections |
| 4xl | 96px | Section vertical padding (desktop) |
| 5xl | 128px | Hero top padding, largest gap on the page |

**Philosophy:** generous, not tight. This is a quiet room, not a dashboard — err toward the next step up in the scale rather than the one below whenever a spacing decision is ambiguous. Horizontal page margin is 32px (`xl`) on mobile, growing to a centred 1180px max-width container on desktop (no fixed max-width padding beyond that — the void simply extends). Section vertical rhythm defaults to 96–120px of padding (`4xl`–~3×`3xl`) on desktop, compressing to 56–64px (`3xl`–ish) on mobile — never below 48px (`2xl`) even on the smallest screens.

## 4. Texture and Atmosphere

- **Ambient glow:** 2–3 large radial-gradient "orbs" (320–420px diameter) in `cyan`/`blue-glow` at 6–16% opacity, `blur(90px)`, positioned off-axis (never centred) and drifting slowly (see §5). This is the only "light source" texture on the page — it stands in for the server-rack glow.
- **Floor grid:** a faint linear-gradient grid (64px cells, `hairline`-strength lines at ~4.5% opacity) evoking raised floor tiles, masked to fade out toward the bottom of the viewport (`radial-gradient` mask) rather than tiling edge-to-edge indefinitely.
- **Scanlines:** an optional 1–3px repeating horizontal line texture at low opacity (~0.3–0.4), blended with `mix-blend-mode: overlay`, used sparingly (typically only behind the hero) — this is seasoning, not a dominant texture.
- **Depth:** depth is communicated by background token step (`void` → `floor` → `panel` → `panel-2`) and hairline borders, never by drop shadows. If a shadow is unavoidable (e.g. a CTA's glow), use a soft, colour-matched glow (`box-shadow` in `cyan` at low opacity/large blur) rather than a black/grey shadow — nothing here casts an ordinary shadow, because nothing here is lit from above.
- **No photography, no skeuomorphism, no visible noise/grain filter.** Texture comes from geometry (grid, hairlines) and light (glow, gradient), not from surface material effects.

## 5. Interactions

**Timing**
| Interaction | Duration | Easing |
|---|---|---|
| Hover/focus state (colour, opacity, border) | 150–200ms | `ease` |
| Section/element entrance (fade/slide-in) | 300–400ms | `ease-out` |
| Ambient motion (background drift, status pulse) | 18–24s (drift), 2–2.5s (pulse) | `ease-in-out`, looping |

**Hover behaviour**
- Colour and opacity only. No scale transforms, no bounce, no shadow "pop," no layout shift on hover.
- Interactive elements (CTA, links) get a `cursor: pointer` and a clear but understated colour shift — never a dramatic inversion.
- Status indicators (the pulsing dot) animate continuously and are not hover-triggered; they represent a system state, not a UI affordance.

**Emotional quality of movement:** everything moves the way a datacenter does at 3AM — slow, rhythmic, and unbothered. Ambient effects (glow drift, status pulse) run on long, looping timers with no acceleration or emphasis. Interactive feedback (hover, entrance) is quick enough to feel responsive but never energetic — no easing curve should overshoot or bounce. If an animation would read as "excited," it's wrong for this system.

**Accessibility default:** every non-essential animation (entrance transitions, ambient drift, smooth-scroll) is disabled or reduced to an instant state under `prefers-reduced-motion: reduce`. Only functional feedback (colour-based hover/focus states) remains — the room stays legible even when it isn't allowed to move.
