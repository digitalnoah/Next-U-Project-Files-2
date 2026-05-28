# Phase 3: Page Sections, Conversion Content, and CTA Flow

## Phase objective

Complete and polish **all content sections** for conversion: problem, outcomes, process, starter kit, audience, examples, pricing, FAQ, and repeated CTAs. Ensure the page teaches the offer and drives toward `#signup`. Form behavior remains for Phase 4.

## Source files to reference

- All `demo-1B/0*.md` source files
- `demo-1B/03-brand-guidelines.html` (messaging specimen, builder notes)
- `demo-1C-orchestrator/phase-plans/00-planning-decisions.md`
- Phase 1–2 outputs in `demo-1B/prototype.html`

## Specific tasks

1. **Hero** — Refine if needed: kicker, H1 (“Turn your idea into a prototype you can show” or equivalent from persona doc), subcopy for mixed audience, 3 quick facts (format, duration, no degree required), dual CTAs to `#signup` and `#examples`.
2. **Problem** — Three pain cards: vague prompts, polished-but-shallow output, no testable artifact (from persona pain points).
3. **Outcomes** — What user leaves with: prototype artifact, clearer product explanation, feedback, next-step plan; emphasize **not** a finished software product.
4. **How it works** — Five steps with short descriptions; mention Cursor and project folder workflow.
5. **Starter kit** — Bulleted kit items + why planning prevents “build before you know what to prove.”
6. **Audience** — Four cards: student builder, marketing operator, early-stage founder, curious professional (from persona secondary personas).
7. **Examples** — Four project cards with title, one-line description, “good for” tag.
8. **Pricing** — Four tiers styled per brand; highlight **Free / Prototype Starter Kit** card; paid cards include “Join the next workshop” or “Book a team session” links to `#pricing` anchors or mailto placeholder.
9. **Mid-page CTA band** — Repeat primary CTA between major sections (at least after outcomes and before FAQ).
10. **FAQ** — Minimum questions:

    - Do I need to know how to code?
    - What will I actually build?
    - What tools will we use (Cursor)?
    - Is this a finished software product?
    - What happens after I sign up for the kit?
    - Who is the workshop best for?

11. **Footer** — Tagline “Craft / Code / Critique / Repeat”, copyright, optional mailto for team inquiries.
12. **Voice pass** — Replace any hype phrases with brand guide “Use this / Avoid this” table language.
13. Embed any **section-specific CSS** in the same `<style>` block; keep file under 800 lines — if approaching limit, extract repeated patterns to concise utility classes, not a second file (Phase 5 consolidates).

## Expected output

- Fully populated, on-brand landing page sections with repeated conversion path.
- `#signup` contains visible form UI (email + submit) styled consistently; submit may still be inert until Phase 4.

## Constraints

- Single HTML file target; embedded CSS only.
- No testimonials, video, payment, or backend.
- No lorem ipsum.
- Preserve section IDs from Phase 1.
- Primary CTA string exactly: **Get the Prototype Starter Kit**.

## Files to edit or create

| File | Action |
|------|--------|
| `demo-1B/prototype.html` | Primary edit target |

## Stop condition

Stop when every section listed in Phase 1 is **content-complete**, visually polished per Phase 2, and at least **two** in-page paths lead to `#signup` besides the header.

## Summary instructions

This phase is the **full landing page experience** minus working form JavaScript. Optimize for workshop demo teaching: clear structure, credible outcomes, obvious free first step.
