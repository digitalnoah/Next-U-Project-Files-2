# Phase 5 QA: Responsive, Accessibility, and Release

## What to inspect

- `demo-1B/prototype.html` complete integration
- Viewports: 1280px, 768px, 375px, 320px
- Keyboard-only navigation path
- DevTools Lighthouse accessibility snapshot (optional but recommended)

## Acceptance criteria

- [ ] Single-file: CSS and JS embedded in `prototype.html`; no required external CSS/JS.
- [ ] File line count ≤ 800 OR justified comment at top if exception approved by owner.
- [ ] No horizontal scroll at 320px on iOS-sized viewport.
- [ ] Mobile nav works: toggle opens/closes; `aria-expanded` updates.
- [ ] Skip link works to `#main`.
- [ ] All phases 1–4 requirements still pass (regression).
- [ ] Primary CTA visible above fold on mobile (hero or sticky header CTA).
- [ ] Form flow from Phase 4 still works after responsive changes.
- [ ] Focus indicators visible on links, buttons, inputs.
- [ ] `prefers-reduced-motion` respected if animations exist.
- [ ] Page title and meta description present and accurate.
- [ ] Opens correctly via local static server and `file://` (note any `file://` limitations in QA results comment only).

## Common failure modes

- Mobile menu traps focus or cannot close with Escape.
- Acid button text contrast fails on acid background (#050505 on #D7FF46 usually OK — verify).
- Regressions: signup JS error after CSS refactor.
- Duplicate IDs after merge.
- External `prototype.css` still linked, causing missing styles in single-file deployment.

## Edge cases

- Very long email in success message — should wrap, not overflow.
- Zoom 200%: content still readable and scrollable.
- Print: optional; page need not be print-perfect.

## Accessibility checks (full pass)

- [ ] Tab order logical: header → main sections → footer → form
- [ ] FAQ keyboard operable
- [ ] Error/success states from Phase 4 still meet aria requirements
- [ ] No positive `tabindex` abuse
- [ ] Landmark regions present (`header`, `main`, `footer`)

## Responsive checks (full pass)

- [ ] Hero stacks; logo panel not oversized on phone
- [ ] Pricing and FAQ readable without pinch-zoom
- [ ] CTAs full-width or adequately sized on touch devices

## Questions to answer before approving

1. 60-second comprehension test on mobile — pass?
2. Would you ship this as a workshop demo artifact?
3. Any remaining “AI template” smell?

**Gate:** All criteria → **pass** and project brief success criteria met. Minor cosmetic issues → **pass_with_risks** with human validation.
