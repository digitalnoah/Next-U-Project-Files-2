# Phase 4 QA: Email Signup Form

## What to inspect

- `#signup` form markup and embedded JavaScript in `demo-1B/prototype.html`
- Error and success states in browser DevTools (Network tab idle on submit)

## Acceptance criteria

- [ ] Email field has visible associated label.
- [ ] Empty submit shows validation error.
- [ ] Invalid email format shows error (does not show success).
- [ ] Valid email shows success state without page reload.
- [ ] Success copy lists starter kit items (≥ 3 bullets).
- [ ] Success copy states behavior is **simulated** / no real email sent.
- [ ] Submit button label matches **Get the Prototype Starter Kit**.
- [ ] No network requests on submit (verify DevTools Network).
- [ ] Focus management: success content reachable by keyboard; error announced.
- [ ] Form does not navigate away or clear URL hash unexpectedly.

## Common failure modes

- `alert()` for errors (poor UX/a11y) instead of inline message.
- Success message implies email was delivered.
- Form still visible under success panel causing double submit confusion.
- Missing `preventDefault()` causing query string `?email=`.
- Script throws if elements missing (breaks whole page).

## Edge cases

- Submit with spaces around email → trim and accept if valid.
- Double-click submit → should not duplicate success panels.
- User resizes after success — layout intact.

## Accessibility checks

- `aria-invalid="true"` on field when error shown (recommended).
- Error connected via `aria-describedby` to input.
- Success region has `tabindex="-1"` and receives focus on success.

## Responsive checks

- Form and success panel readable at 320px; button tappable (~44px min height).

## Questions to answer before approving

1. Would a beginner understand they requested the kit, not enrolled in a paid class?
2. Is simulated behavior obvious without reading source code?

**Gate:** All behavioral criteria met → **pass**. Misleading “email sent” copy → **fail**.
