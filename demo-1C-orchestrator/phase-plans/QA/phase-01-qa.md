# Phase 1 QA: Content Architecture and Semantic Structure

## What to inspect

- `demo-1B/prototype.html` structure, heading hierarchy, anchor IDs, and copy accuracy against source files.
- Navigation links vs section IDs.
- Form markup at `#signup` (structure only).
- Logo references and alt text.

## Acceptance criteria

- [ ] Single `h1` in hero; each major section has one clear `h2`.
- [ ] All required section IDs exist: `hero`, `problem`, `outcomes`, `how-it-works`, `starter-kit`, `audience`, `examples`, `pricing`, `signup`, `faq`.
- [ ] Page answers within 60 seconds of scanning: who it is for, what they get, why it matters, what to do next.
- [ ] Primary CTA label is **Get the Prototype Starter Kit** in hero and signup.
- [ ] All four example project types appear in `#examples`.
- [ ] Pricing shows free kit + $149 + $299 + team starting price.
- [ ] FAQ has at least 6 questions including coding required, tools/Cursor, prototype vs finished product, after signup.
- [ ] No lorem ipsum; no testimonials/instructor sections.
- [ ] Cursor mentioned in subcopy/process, not in H1.
- [ ] Logos use local paths with meaningful `alt` text.

## Common failure modes

- Missing section (especially `starter-kit` or `audience`).
- Duplicate or skipped heading levels (`h1` → `h4`).
- Nav `href` typos (`#how-it-works` vs `#howitworks`).
- Generic AI hype copy contradicting brand voice.
- Placeholder “TBD” pricing or empty FAQ.
- Form without `<label>` associated to email input.

## Edge cases

- Pre-existing `prototype.html` with different section IDs — either migrate nav/CTAs to standard IDs or document a mapping table in an HTML comment at top of file.
- Missing logo files: page should still render; images may 404 but alt/wordmark text must remain understandable.

## Accessibility checks

- Skip link targets `#main`.
- Form email field has visible `<label>` (or `aria-label` if design requires — prefer `<label>`).
- Images have non-empty `alt` (decorative logo in header may use `alt=""` only if wordmark text is adjacent).

## Responsive checks

- Not required for Phase 1 pass; content must be readable at 320px without horizontal scroll from unbroken strings.

## Questions to answer before approving

1. Could Alex (persona doc) self-identify in the first screen?
2. Is the free kit clearly the easiest first step vs paid workshops?
3. Does the page explain why **planning** matters before building?
4. Are secondary CTAs pointing to the correct anchors?

**Gate:** All acceptance criteria met → **pass**. Structural gaps → **fail**. Subjective voice concerns only → **pass_with_risks** (human validation required).
