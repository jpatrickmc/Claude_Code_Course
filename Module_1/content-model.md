# Content Model: 3AM Datacenter — Static Landing Page

Derived from `PRD.md`. Trimmed to what the Must-Have feature set actually requires: a single static page, one clear action, everything hard-coded. The prior draft added a Value/Proof section and a duplicate closing CTA that the PRD never asked for — both are cut here.

## Site Meta *(non-visible, precedes all sections)*
- Page Title — appears in the browser tab; ≤ 60 characters; required for any valid HTML document regardless of feature tier

## Header
- Brand Mark — site/product name, top-left; ≤ 20 characters; static text, monospace, no logo image (Design Standard uses type and color, not imagery)

## Hero
- Headline — eight words maximum; carries the emotional core
- Subheadline — one sentence; expands without repeating
- Primary CTA — action-oriented label; links to the intended section; destination must be `mailto:`, an external URL, or an in-page anchor — never a form submission (Must-Have constraint)

## Footer
- Brand / Copyright Line — ≤ 15 words; static text, year hard-coded rather than script-generated; closes the page without introducing new claims

---

## Gaps Between PRD and Content Model

- **No defined product or business behind the site.** The Vision describes a feeling, not an offering — the Headline, Subheadline, and Primary CTA's destination stay placeholders until it's clear what the page is actually for.
- **The Primary CTA's target is still unresolved.** The Mobile Skimmer persona calls for "a single clear action," and this model gives it exactly one CTA — but the PRD never says what that action does (contact, subscribe, view something) or what "the intended section" is, since the page currently has no second section to point to.
- **This draft removes the prior Value/Proof section and second CTA.** Nothing in the Vision, personas, or Must-Have list calls for enumerated value points or a repeated call to action — a single Hero statement matches the "calm, confident, nothing loud" brief more directly, and better serves the Technical Evaluator persona's preference for restraint. If a body section turns out to be necessary, it isn't justified by the current PRD and would need its own rationale added first.
- **The Design Standard's mention of monospace "stats" and "logs" now has no home at all.** That implies a status-feed or metrics display, but no Must-Have content calls for one. Either that visual detail should be dropped from the Design Standard, or the PRD needs an explicit field for it (e.g., a fixed set of stat labels/values).
- **No copywriting/tone guideline exists beyond the Design Standard's visual description.** The tone implied above ("carries the emotional core," "expands without repeating") is inferred from Vision and Design Standard, not a stated voice guide.
- **Meta Description and other SEO fields are intentionally absent**, since the PRD marks them Should-Have, not Must-Have. They'll need to be added before launch, but don't belong in a Must-Have-only model.
- **Success Criteria's qualitative goal** ("visitors describe the page as calm/quiet/controlled") still isn't something any single field can guarantee — it depends on execution, not content structure.
