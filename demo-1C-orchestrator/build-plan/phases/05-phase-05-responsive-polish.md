# Phase 5: Responsive layout, accessibility, and polish

**QA file:** `QA-plan/05-phase-05-responsive-polish.md`  
**Detail:** `phase-plans/build/phase-05-build.md`

## Objective

Ship-ready single-file landing page: responsive breakpoints, accessible interactions, mobile nav, performance hygiene, final fixes.

## In scope

- Responsive layout 320px–desktop
- Mobile nav pattern; touch targets
- Focus states, contrast, semantic HTML cleanup
- Single file: embedded CSS + JS; no required external assets except logos
- Fix issues from prior phase QA

## Out of scope

- New features (video, payments, libraries)
- Backend integration

## Tasks

- [ ] Test 320 / 768 / 1280 widths
- [ ] Consolidate stray CSS/JS into `prototype.html`
- [ ] Run accessibility pass (labels, focus, contrast, skip link)
- [ ] 60-second comprehension check per project brief

## Exit criteria

Phase 5 QA outcomes all pass; index shows phases 1–5 `pass`.

## Validation

- Browser resize + keyboard tab through header, form, CTAs
- Optional: Lighthouse or axe notes in QA-results (not required to pass)
