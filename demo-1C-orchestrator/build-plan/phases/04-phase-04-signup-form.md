# Phase 4: Email signup form and success state

**QA file:** `QA-plan/04-phase-04-signup-form.md`  
**Detail:** `phase-plans/build/phase-04-build.md`

## Objective

Email capture at `#signup`: format validation, simulated submission, success UI with kit contents and prototype disclaimer. No backend.

## In scope

- Embedded JS in `prototype.html`
- Email validation; prevent real submit
- Success message: thank user, list kit items, state **simulated delivery**
- Secondary link after success: **Join the next workshop** → `#pricing`

## Out of scope

- Real email / CRM / backend
- Payment or account creation

## Tasks

- [ ] Wire form submit handler (prevent default)
- [ ] Show inline errors for invalid email
- [ ] Show success panel with kit bullet list per planning decisions
- [ ] Visible prototype disclaimer on success

## Exit criteria

Happy path and invalid email path both demonstrable in browser.

## Validation

- Submit empty / invalid / valid email in browser
- Confirm no network call to real API
