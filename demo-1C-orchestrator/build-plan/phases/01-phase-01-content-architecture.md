# Phase 1: Content architecture and semantic structure

**QA file:** `QA-plan/01-phase-01-content-architecture.md`  
**Detail:** `phase-plans/build/phase-01-build.md`

## Objective

Establish full information architecture and real copy in `demo-1B/prototype.html` using semantic HTML. Minimal readability CSS only — no brand polish.

## In scope

- Landmarks: `<header>`, `<main>`, `<footer>`, skip link → `#main`
- Sections with stable IDs: `hero`, `problem`, `outcomes`, `how-it-works`, `starter-kit`, `audience`, `examples`, `pricing`, `signup`, `faq`
- Real copy from `demo-1B/0*.md` and `phase-plans/00-planning-decisions.md`
- Primary CTA: **Get the Prototype Starter Kit**; secondary CTAs per planning decisions
- Logo `<img>` → `03-logo-simple.jpg`, `03-logo-full.png` with alt text
- Form markup at `#signup` (no JS behavior yet)
- Cursor in subcopy / how-it-works / FAQ — not H1

## Out of scope

- Brand design system (Phase 2)
- Form validation / success (Phase 4)
- External libraries, backend, lorem ipsum, testimonials

## Tasks

- [x] Create or refactor `demo-1B/prototype.html`
- [x] Implement all sections and nav anchor links
- [x] Write original copy covering offer, audience, problem, kit, pricing, next step
- [x] Single `h1`; logical `h2`/`h3` hierarchy

## Exit criteria

Reviewer can confirm section IDs, copy truth, and conversion path without other files.

## Validation

- Open `demo-1B/prototype.html` in browser — all sections present, readable at 320px
- Grep: no `lorem` / `TBD` placeholders in body copy
