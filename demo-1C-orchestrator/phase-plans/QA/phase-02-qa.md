# Phase 2 QA: Brand Design System

## What to inspect

- Embedded CSS in `demo-1B/prototype.html`
- Color contrast, typography scale, button styles, cards, header/footer
- Logo presentation on dark backgrounds

## Acceptance criteria

- [ ] CSS is embedded in `prototype.html` (no required external stylesheet for core layout).
- [ ] Primary palette is black / bone / acid with graphite cards.
- [ ] Hero uses strong typographic hierarchy consistent with brand guide.
- [ ] CTAs are visually obvious (acid accent on primary actions).
- [ ] No generic SaaS gradient hero or “AI startup” cliché visuals.
- [ ] Section spacing and borders create clear editorial rhythm.
- [ ] Logo images load from local paths; wordmark readable if images fail.
- [ ] Copy from Phase 1 unchanged in meaning (typos OK to fix).

## Common failure modes

- Light-mode default contradicting dark studio brand.
- Acid overused on every element (noise).
- Tiny body text on mobile.
- Low contrast muted text on graphite (#B7B0A3 on #1D1D1D — verify readability).
- Leaving `prototype.css` linked causing split-brain styles.

## Edge cases

- `onerror` handlers on logos — acceptable if wordmark fallback exists.
- Print styles optional; not required for pass.

## Accessibility checks

- Body text contrast ≥ 4.5:1 for normal text (bone on black, muted on graphite).
- Focus styles visible on links and buttons (`:focus-visible` outline).
- Do not rely on color alone for primary CTA (use weight, size, label).

## Responsive checks

- Page usable at 375px width: no overlapping header, text not clipped, cards stack.

## Questions to answer before approving

1. Does it feel “serious enough to trust, weird enough to remember”?
2. Would this pass as a workshop brand, not a crypto SaaS?
3. Are primary and secondary buttons distinguishable?

**Gate:** Visual brand alignment + embedded CSS → **pass**. Major brand drift → **fail**.
