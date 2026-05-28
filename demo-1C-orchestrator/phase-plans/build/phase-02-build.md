# Phase 2: Brand Design System and Layout Shell

## Phase objective

Apply the **Vibe Code Academy brand** to `prototype.html`: dark editorial studio look, typography, color tokens, spacing, cards, buttons, and header/footer chrome. Layout shell for all sections; do not change copy meaning from Phase 1.

## Source files to reference

- `demo-1B/03-brand-guidelines.html` (palette, typography, voice specimen, builder notes)
- `demo-1C-orchestrator/phase-plans/00-planning-decisions.md`
- `demo-1B/prototype.html` (Phase 1 output)

## Specific tasks

1. Embed all CSS in `prototype.html` inside a `<style>` block in `<head>` (start migration away from external `prototype.css` if present).
2. Implement CSS custom properties from brand guide:

   - `--black` #050505, `--white` #F7F4EC, `--paper` #EFE9DD, `--muted` #B7B0A3
   - `--graphite` #1D1D1D, `--soft-black` #151515
   - `--acid` #D7FF46, `--blue` #4F6DFF, `--coral` #FF6B4A
   - `--line` rgba(247, 244, 236, 0.18), `--radius` 28px

3. Typography: system UI stack (`Inter` if available via system, else ui-sans-serif). Large confident headings — uppercase hero title, tight letter-spacing per brand specimen.
4. Global layout: max-width container (~1260px), generous vertical rhythm, section borders (`border-top` on sections).
5. Components:

   - Site header with brand chip, dot accent, nav, primary CTA pill
   - `.card` panels on graphite/soft-black backgrounds
   - `.label-pill` acid badges
   - `.btn` primary (acid or black-on-bone per specimen) and secondary outline
   - Hero grid: logo panel (bone field) + content column
   - Kicker text (acid, uppercase, letter-spaced)

6. **Design rules:**

   - Dark editorial studio; high contrast; modular sections.
   - Logo used sparingly: icon in header, optional hero panel; full lockup only where space allows.
   - **Avoid** generic SaaS gradients, purple AI hype, glassmorphism clutter.
   - Premium but beginner-friendly — not childish, not MIT-academic.

7. Style all Phase 1 sections consistently; empty states should not look unstyled.
8. Mobile: header nav may collapse to a simple stacked layout or menu button (full behavior can finish in Phase 5).

## Expected output

- `demo-1B/prototype.html` with embedded brand CSS; page visually matches brand guide direction.
- External `prototype.css` either removed from `<link>` or deleted after styles migrated.

## Constraints

- No external CSS frameworks or font CDN unless user explicitly approves later.
- No JavaScript required in Phase 2 except what already exists (prefer none).
- Do not change section IDs or CTA labels from Phase 1.
- Secondary accents (blue, coral) used sparingly — acid is primary CTA accent.

## Files to edit or create

| File | Action |
|------|--------|
| `demo-1B/prototype.html` | Embed `<style>`, refine markup classes only as needed |
| `demo-1B/prototype.css` | Deprecate / migrate into HTML |

## Stop condition

Stop when the page at desktop width looks like one coherent **Vibe Code Academy** product — not a generic Tailwind landing page — and all sections share the same design language.

## Summary instructions

Translate `03-brand-guidelines.html` into production CSS on the landing page. Favor grid, type scale, and restraint over decoration. This phase is **look and feel**, not new content.
