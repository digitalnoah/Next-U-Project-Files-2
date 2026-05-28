# Phase 5: Responsive Layout, Accessibility, and Final Polish

## Phase objective

Ship-ready **single-file** landing page: responsive across breakpoints, accessible interactions, mobile nav, performance hygiene, and final QA fixes. Consolidate any remaining external assets into `prototype.html` per project requirements.

## Source files to reference

- `demo-1B/03-brand-guidelines.html` (responsive patterns in brand guide)
- `demo-1B/01-project-brief.md` (success criteria: 60-second comprehension)
- All prior phase QA files
- `demo-1B/prototype.html`

## Specific tasks

1. **Single file compliance**

   - All CSS in `<style>` in `prototype.html`.
   - All JS in `<script>` before `</body>`.
   - Remove `<link rel="stylesheet" href="prototype.css">` if still present.
   - Keep total file ≤ 800 lines; if over, refactor CSS (group selectors, remove duplication) without splitting files.

2. **Responsive**

   - Breakpoints ~850px and ~480px (align with brand guide media queries).
   - Header: mobile menu toggle if nav does not fit; `aria-expanded` on button; nav links focusable when open.
   - Grids (`hero`, cards, pricing, examples) stack to single column.
   - No horizontal overflow at 320px width.
   - Touch targets ≥ 44px for buttons and nav.

3. **Accessibility**

   - One `h1`; logical heading order.
   - Skip link visible on focus.
   - All images: correct `alt` (decorative vs informative).
   - Form labels, errors, success from Phase 4 verified on keyboard-only pass.
   - `:focus-visible` styles on interactive elements.
   - `prefers-reduced-motion`: disable or minimize transitions if any were added.
   - Color contrast recheck on muted text and acid buttons.

4. **Polish**

   - Smooth scroll for anchor links (`scroll-behavior: smooth` with reduced-motion override).
   - Consistent section padding; fix any orphaned widows in hero at common widths.
   - Favicon optional: link to `03-logo-simple.jpg` if appropriate.
   - Meta description and `<title>` accurate.

5. **Final content sweep**

   - No lorem; CTAs consistent; simulation disclaimer still visible post Phase 4.
   - Confirm logos exist or graceful degradation documented in HTML comment.

6. **Self-QA checklist** — Run through `QA/phase-05-qa.md` before marking phase done.

## Expected output

- `demo-1B/prototype.html` — production-ready for static hosting (MAMP, file://, or simple static server).
- Optional: `demo-1B/prototype.css` deleted or empty with comment “deprecated — styles in prototype.html”.

## Constraints

- No new features (payments, video, analytics, libraries).
- Do not change business copy meaning unless fixing errors found in QA.
- Do not add real email capture backend.

## Files to edit or create

| File | Action |
|------|--------|
| `demo-1B/prototype.html` | Final integration |
| `demo-1B/prototype.css` | Remove dependency / delete if safe |

## Stop condition

Stop when Phase 5 QA acceptance criteria all pass and the page meets project brief success criteria: visitor understands who it is for, what they get, why it is useful, and what to do — within 60 seconds on mobile and desktop.

## Summary instructions

This is the **release polish** phase. Fix rough edges, do not redesign from scratch. The deliverable is one teachable, demo-ready HTML file for Vibe Code Academy workshops.
