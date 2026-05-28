# Build order — Vibe Code Academy

Execute **one phase per orchestrator run**. Do not skip.

| Phase | Build file | QA file | Focus |
| --- | --- | --- | --- |
| 1 | `build-plan/phases/01-phase-01-content-architecture.md` | `QA-plan/01-phase-01-content-architecture.md` | Semantic HTML skeleton + real copy |
| 2 | `build-plan/phases/02-phase-02-brand-design-system.md` | `QA-plan/02-phase-02-brand-design-system.md` | Brand CSS tokens, layout shell |
| 3 | `build-plan/phases/03-phase-03-conversion-content.md` | `QA-plan/03-phase-03-conversion-content.md` | Sections, pricing, FAQ, CTA flow |
| 4 | `build-plan/phases/04-phase-04-signup-form.md` | `QA-plan/04-phase-04-signup-form.md` | Email form, validation, success state |
| 5 | `build-plan/phases/05-phase-05-responsive-polish.md` | `QA-plan/05-phase-05-responsive-polish.md` | Responsive, a11y, single-file polish |

**Start:** Phase 1 unless `QA-plan/QA-results/00-index.md` shows a later phase ready.

**Deliverable:** `demo-1B/prototype.html`

**Planning context:** `phase-plans/00-planning-decisions.md`, `demo-1B/01-project-brief.md` … `05-value-prop.md`
