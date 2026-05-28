# Phase 1 QA: Content architecture

**Build file:** `build-plan/phases/01-phase-01-content-architecture.md`  
**Detail:** `phase-plans/QA/phase-01-qa.md`

## QA goals

Verify semantic structure, section IDs, copy accuracy, and conversion clarity before visual design.

## Outcomes (check each)

- [ ] Single `h1` in hero; clear `h2` per major section
- [ ] All section IDs exist: hero, problem, outcomes, how-it-works, starter-kit, audience, examples, pricing, signup, faq
- [ ] 60-second scan answers: who, what they get, why it matters, what to do next
- [ ] Primary CTA **Get the Prototype Starter Kit** in hero and signup
- [ ] Four example project types in `#examples`
- [ ] Pricing: free kit, $149, $299, team starting price
- [ ] FAQ ≥ 6 questions (coding, tools/Cursor, prototype vs product, after signup)
- [ ] No lorem ipsum; no testimonials/instructor sections
- [ ] Cursor in subcopy/process, not H1
- [ ] Local logo paths + meaningful alt; email field has `<label>`

## Pass criteria

All outcomes met with evidence (file paths, grep, or browser check notes).

## Fail conditions

- Missing required section or wrong anchor IDs
- Placeholder copy or invented brand direction
- Form without accessible label

**Subjective voice only** → `pass_with_risks` + human HTML checklist.
