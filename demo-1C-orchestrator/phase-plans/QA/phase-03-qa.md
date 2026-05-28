# Phase 3 QA: Page Sections and Conversion Content

## What to inspect

- Full scroll of `demo-1B/prototype.html`
- CTA placement, pricing hierarchy, FAQ completeness, example cards
- Copy accuracy vs `01-project-brief.md` and `05-value-prop.md`

## Acceptance criteria

- [ ] All sections content-complete with real copy (no stubs).
- [ ] Workflow **Plan → Build → Test → Improve → Share** visible in how-it-works.
- [ ] Starter kit lists: planning template, build prompt template, project file structure, example brief.
- [ ] Four example projects present with distinct descriptions.
- [ ] Pricing: $0 kit featured; $149, $299, team $2,500+ visible.
- [ ] At least 2 mid-page CTAs to `#signup` besides header/nav.
- [ ] Secondary CTAs work: `#examples`, `#pricing`, mailto for team (placeholder domain acceptable).
- [ ] FAQ ≥ 6 items; includes simulated vs real product distinction.
- [ ] Page states workshop outcome is a **prototype**, not production software.
- [ ] No testimonials/instructor/video sections added.
- [ ] `prototype.html` ≤ 800 lines OR documented comment explains split (prefer single file).

## Common failure modes

- Paid workshop overshadows free kit visually.
- Missing “why planning matters” in starter kit section.
- FAQ omits “what happens after signup.”
- Broken anchor links after nav edits.
- AI hype phrases (“unlock transformation”, “agentic”, etc.).

## Edge cases

- Long FAQ answers wrapping awkwardly on mobile — acceptable if readable.
- Team pricing “starting at” without exact quote — acceptable per value prop doc.

## Accessibility checks

- FAQ uses `<details>`/`<summary>` or headings + paragraphs — must be keyboard accessible.
- Pricing cards: headings describe each tier; lists use `<ul>` where appropriate.
- Decorative example icons marked `aria-hidden` if used.

## Responsive checks

- Pricing grid stacks on narrow screens without horizontal scroll.
- Example cards stack; CTA buttons full-width on mobile if needed.

## Questions to answer before approving

1. Would Alex feel reassured about not being “technical enough”?
2. Is the free kit the obvious first step?
3. Could you explain Vibe Code Academy to a friend after one scroll?

**Gate:** Content + conversion structure complete → **pass**. Missing required section → **fail**.
