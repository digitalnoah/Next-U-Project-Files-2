# Phase 1: Content Architecture and Semantic Structure

## Phase objective

Establish the full landing page **information architecture** and **real copy** in `prototype.html` using semantic HTML only. Visitors should be able to read the entire story without polished styling. No signup interactivity yet.

## Source files to reference

- `demo-1B/01-project-brief.md`
- `demo-1B/02-reference-sites.md` (suggested page structure)
- `demo-1B/04-user-persona.md`
- `demo-1B/05-value-prop.md`
- `demo-1C-orchestrator/phase-plans/00-planning-decisions.md`

## Specific tasks

1. Work in `demo-1B/`. Create or refactor `prototype.html` as the single deliverable file for this project.
2. Add a minimal `<style>` block **only** for readability during build (system font, max-width, basic spacing). No brand polish yet — that is Phase 2.
3. Implement document structure with landmarks: `<header>`, `<main>`, `<footer>`, skip link to `#main`.
4. Create sections in this order with stable `id` attributes:

  | Section ID      | Purpose                                                        |
  | --------------- | -------------------------------------------------------------- |
  | `#hero`         | Promise, mixed-audience subcopy, primary + secondary CTA links |
  | `#problem`      | Why people get stuck with AI-assisted building                 |
  | `#outcomes`     | What the learner leaves with (artifact, workflow, clarity)     |
  | `#how-it-works` | Plan → Build → Test → Improve → Share (5 steps)                |
  | `#starter-kit`  | Free kit contents and why planning matters                     |
  | `#audience`     | Who this is for (students, marketers, founders, operators)     |
  | `#examples`     | Four example project cards                                     |
  | `#pricing`      | Free / $149 / $299 / team tiers from value prop                |
  | `#signup`       | Email field + submit button (no JS behavior yet)               |
  | `#faq`          | Full FAQ (~6 questions per planning decisions)                 |

5. Write **original copy** drawn from source files. Required messages on the page:
  - What Vibe Code Academy is
  - Who it is for
  - What problem it solves
  - What the class helps the user build
  - Why planning matters
  - What the Prototype Starter Kit includes
  - What workshops cost (example pricing)
  - What to do next (primary CTA: **Get the Prototype Starter Kit**)
6. Primary CTA text: **Get the Prototype Starter Kit**. Secondary link labels: **See what you will build**, **Join the next workshop**, **Book a team session** (href targets per planning decisions).
7. Mention **Cursor** in hero subcopy and in how-it-works / FAQ — not in the H1.
8. Do **not** use lorem ipsum or placeholder paragraphs.
9. Do **not** add testimonials, instructor bio, or client logos.
10. Include logo `<img>` tags pointing to `03-logo-simple.jpg` and `03-logo-full.png` where appropriate (header/hero). Alt text required.

## Expected output

- `demo-1C/prototype.html` containing all sections, headings hierarchy (`h1` once, logical `h2`/`h3`), nav links to in-page anchors, and complete real copy.
- Form markup present at `#signup` but submission does nothing yet (or native submit prevented in Phase 4).

## Constraints

- No external CSS/JS libraries.
- No payment flows, accounts, or backend.
- No video embeds.
- Semantic HTML: `<section>`, `<article>`, `<nav>`, `<ul>`, `<form>`, `<label>`, `<button>`.
- If `prototype.css` exists from a prior build, leave it unlinked for now or add a comment that Phase 2/5 will embed styles.

## Files to edit or create


| File                         | Action                               |
| ---------------------------- | ------------------------------------ |
| `demo-1B/prototype.html`     | Create or refactor                   |
| `demo-1B/03-logo-simple.jpg` | Use if present; do not invent assets |
| `demo-1B/03-logo-full.png`   | Use if present                       |


## Stop condition

Stop when a reviewer can answer “yes” to all of the following without opening other files:

- Every section in the table exists with correct `id`.
- Copy reflects source truth (no invented brand direction).
- Primary conversion path is obvious from hero through signup.
- No lorem ipsum; no Phase 2 visual design beyond minimal readability CSS.

## Summary instructions

Read source files and planning decisions. Build the **skeleton story** of the page in HTML. Prioritize clarity and structure over aesthetics. Commit mentally to the section order — later phases must not reorder IDs without updating nav and CTAs.