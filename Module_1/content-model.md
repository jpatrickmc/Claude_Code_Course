# Content Model: 3AM Datacenter — Static Landing Page

Derived from `PRD.md`. Scoped to what the Must-Have feature set requires — a single static page, no backend, all actions link out. Decorative-only elements (motion, glow, grid texture) are excluded since they carry no content field.

## 1. Site Meta (non-visible)

| Field | Description | Constraints |
|---|---|---|
| Page Title | Browser tab / bookmark text | ≤ 60 characters, required for valid HTML regardless of tier |
| Meta Description | Search/link-preview summary | ≤ 155 characters — *Should-Have per PRD, not required for launch* |

## 2. Header

| Field | Description | Constraints |
|---|---|---|
| Brand Mark | Site/product name, top-left | ≤ 20 characters, static text, monospace per Design Standard |
| Nav Links (optional) | In-page anchor links only | 2–4 items, anchor `#id` targets only — no external nav |

## 3. Hero

| Field | Description | Constraints |
|---|---|---|
| Eyebrow / Status Label | Short atmospheric flag above headline | ≤ 6 words, uppercase, monospace, sets "nominal/unattended" tone |
| Headline (H1) | Primary statement of the page's premise | ≤ 12 words, declarative, no exclamation points — matches "calm, confident" tone |
| Subheadline | 1–2 sentences expanding the headline | ≤ 40 words, plain sans-serif voice, no jargon |
| Primary CTA | Label + destination | Label ≤ 4 words; destination must be `mailto:`, external URL, or in-page anchor — **no form submission** (Must-Have constraint) |
| Secondary CTA (optional) | Lower-emphasis link | ≤ 6 words, text-link style |

## 4. Value / Proof Section

| Field | Description | Constraints |
|---|---|---|
| Section Heading | Names what the page is proving or offering | ≤ 8 words |
| Value Points (×3 recommended) | Title + short description per point | Title ≤ 4 words; description ≤ 25 words; fixed count, hard-coded — no dynamic list |

## 5. Closing CTA

| Field | Description | Constraints |
|---|---|---|
| Heading | Restates the core offer/message | ≤ 10 words |
| Supporting Line | One sentence of context | ≤ 25 words |
| CTA | Label + destination | Same constraint as Hero primary CTA — link-out only |

## 6. Footer

| Field | Description | Constraints |
|---|---|---|
| Brand / Copyright Line | Legal line + brand repeat | ≤ 15 words, static text (year hard-coded, not script-generated) |
| Footer Links (optional) | Secondary links | Anchor or external URL only, ≤ 4 items |

---

## Gaps Between PRD and Content Model

- **No defined product or business behind the site.** The Vision describes a feeling, not what's being offered — Hero copy, Value Points, and both CTAs can't be finalized until it's clear whether this is a portfolio, a product, or a pure mood piece.
- **The Mobile Skimmer persona requires "a single clear action," but the PRD never defines what that action is** (contact, subscribe, view work, etc.) or where it should point. CTA destinations are placeholders until this is resolved.
- **No copywriting/tone guideline beyond the Design Standard's visual description.** Word-count and tone constraints above are inferred, not sourced from an explicit voice guide in the PRD.
- **Design Standard references monospace treatment for "stats" and "logs,"** implying a status-feed or metrics display, but no such content is listed under Must-Have. This content model omits it; if that visual element is wanted at launch, it needs an explicit field (e.g., a fixed set of stat labels/values) added to the PRD.
- **Should-Have SEO fields (meta description, OG image) aren't required for launch**, but Page Title is unavoidable for valid HTML — flagged above as a tier inconsistency, not a gap in scope.
- **Nice-to-Have items (downloadable asset, analytics script) have no corresponding fields** here, since they're out of Must-Have scope; adding them later will require new content (a file to host, a tracking ID).
- **Success Criteria's qualitative goal** ("visitors describe the page as calm/quiet/controlled") isn't measurable from the content model itself — it depends on execution of tone and design, not on any single field.
