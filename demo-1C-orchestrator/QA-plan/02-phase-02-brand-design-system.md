# Phase 2 QA: Brand design system

**Build file:** `build-plan/phases/02-phase-02-brand-design-system.md`  
**Detail:** `phase-plans/QA/phase-02-qa.md`

## QA goals

Verify embedded brand CSS matches guidelines without breaking Phase 1 structure.

## Outcomes (check each)

- [ ] CSS embedded in `prototype.html` (no required external sheet for core layout)
- [ ] Palette: black / bone / acid with graphite cards
- [ ] Strong hero typography per brand guide
- [ ] Primary CTAs visually obvious (acid accent)
- [ ] No generic SaaS gradient / AI cliché hero
- [ ] Editorial section rhythm (spacing, borders)
- [ ] Logos load locally; wordmark readable if images fail
- [ ] Phase 1 copy meaning unchanged

## Pass criteria

All outcomes with evidence.

## Fail conditions

- Light-mode default contradicting brand
- Split styles via linked `prototype.css` breaking layout
- Illegible contrast on graphite panels

**Minor aesthetic disagreement** → `pass_with_risks`.
