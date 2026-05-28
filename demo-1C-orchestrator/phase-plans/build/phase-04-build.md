# Phase 4: Email Signup Form and Success State

## Phase objective

Implement the **email capture experience** at `#signup`: validation, simulated submission, success UI with kit contents, and clear prototype disclaimer. No backend or real email delivery.

## Source files to reference

- `demo-1B/01-project-brief.md` (functional requirement)
- `demo-1B/03-brand-guidelines.html` (builder notes: distinguish simulated behavior)
- `demo-1C-orchestrator/phase-plans/00-planning-decisions.md`
- `demo-1B/prototype.html`

## Specific tasks

1. Markup at `#signup`:

   - `<form id="starterKitForm">` with `novalidate` if using custom JS validation
   - Email `<input type="email" id="email" name="email" required autocomplete="email">`
   - Associated `<label for="email">` (e.g. “Work email” or “Email address”)
   - Submit button: **Get the Prototype Starter Kit**
   - Helper text: requesting the free Prototype Starter Kit (not workshop payment)

2. Embed `<script>` at end of `body` in `prototype.html` (no external JS files).

3. On submit (prevent default):

   - Trim email; validate with reasonable regex or `type="email"` + checkValidity()
   - If invalid: show inline error near field (accessible, `role="alert"` or `aria-live="polite"`)
   - If valid: hide form (or disable inputs), show **success panel** containing:
     - Thank-you headline using submitted email
     - Bulleted list of kit deliverables (4 items from planning decisions)
     - **Simulated delivery notice** in plain language (e.g. “This prototype does not send email or store data.”)
     - Link/button: **Join the next workshop** → `#pricing`

4. Do not POST to a server; do not localStorage unless optional and documented — default is display-only success.

5. Style form, error, and success states to match Phase 2 brand (acid primary button, graphite panel for success).

6. Ensure signup section CTA in hero/nav still scrolls to `#signup`; after success, focus moves to success panel for screen readers.

## Expected output

- Working client-side form flow in `prototype.html`.
- Clear communication that user requested the starter kit and that submission is simulated.

## Constraints

- Simulated submission only unless product owner explicitly approves JSON/SQLite storage later.
- No third-party form services (Mailchimp, etc.).
- Accessible labels and error messages required.
- Do not claim “Check your inbox” as if email was sent — wording must reflect simulation.

## Files to edit or create

| File | Action |
|------|--------|
| `demo-1B/prototype.html` | Add/extend `<script>`, form styles |

## Stop condition

Stop when QA can: submit empty → error; submit `not-an-email` → error; submit valid email → success panel with kit list and simulation notice; no network requests on submit.

## Summary instructions

Build a **trustworthy prototype** form, not a fake production signup. The success state should educate what the kit contains and nudge toward paid workshops without being pushy.
