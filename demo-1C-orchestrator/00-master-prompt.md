# Demo 1C Master Prompt

Use this prompt in Cursor from inside the `demo-1B` project folder.

The goal is to produce a phase-based execution plan for a Vibe Code Academy landing page by using the planning files as source context, asking clarifying questions before planning, and then creating build, QA, and human validation markdown files for each phase. **Do not build the site or execute any phase in this session.**

---

## Master Prompt

You are helping me plan a polished, single-page landing page for **Vibe Code Academy**.

Before creating phase plans, read and use the following project files as your source of truth:

- `01-project-brief.md`
- `02-reference-sites.md`
- `03-brand-guidelines.html`
- `04-user-persona.md`
- `05-value-prop.md`

Also note these logo assets for future build phases:

- `03-logo-full.png`
- `03-logo-simple.jpg`

The eventual site target (for phase plans only — do not create it in this session) is a single HTML file called:

- `prototype.html`

---

# Step 1: Read and Summarize Context

First, read all source files listed above.

Then summarize what you understand in this format:

## Project Summary

Briefly explain what Vibe Code Academy is.

## Target User

Summarize the primary user persona.

## Core Value Proposition

Explain the main value the class provides.

## Primary Conversion Goal

Explain the main action the landing page should drive.

## Brand Direction

Summarize the visual and voice direction from the brand guidelines.

## Reference Site Takeaways

Summarize the most important lessons from the reference sites.

## Key Constraints

List what is in scope and out of scope.

Do not create phase plans yet.

---

# Step 2: Reverse Prompt Interview

After summarizing the context, ask me a focused set of clarifying questions before planning.

Ask only questions that would materially improve the site.

Organize the questions into these categories:

## Offer and CTA

Ask about the primary conversion action, lead magnet, pricing, and what happens after signup.

## Audience

Ask whether the page should prioritize students, marketers, founders, operators, or a mix.

## Tone and Positioning

Ask how bold, premium, beginner-friendly, or playful the page should feel.

## Content and Proof

Ask whether to include testimonials, instructor bio, outcomes, examples, schedule, pricing, FAQs, or trust markers.

## Functionality

Ask what the email form should actually do in this prototype.

## Constraints

Ask about anything that should not be included.

Important:

- Do not ask more than 12 questions total.
- Number the questions.
- After asking the questions, stop and wait for my answers.
- Do not create phase plans until I answer.

---

# Step 3: Create Phase-Based Planning Files

After I answer the interview questions, create a phase-based project plan.

Create a folder called:

- `phase-plans`

Inside that folder, create one build folder, one QA folder, and one human-validation folder for each phase.

Use this naming pattern:

- `build/phase-01-build.md`
- `QA/phase-01-qa.md`
- `human-validation/phase-01-human-validation.md`

Repeat for each phase.

---

# Step 4: What Each Phase File Should Contain

Each phase file should be specific enough that another AI agent, developer, or human could execute or review it in a **separate** build session.

## Build File Requirements

Each `phase-XX-build.md` file should include:

- Phase objective
- Source files to reference
- Specific tasks
- Expected output
- Constraints
- Files to edit or create
- Stop condition
- Summary instructions

The build file should tell the builder exactly what to do.

## QA File Requirements

Each `phase-XX-qa.md` file should include:

- What to inspect
- Acceptance criteria
- Common failure modes
- Edge cases
- Accessibility checks where relevant
- Responsive checks where relevant
- Questions to answer before approving the phase

The QA file should tell the reviewer how to evaluate the work.

## Human Validation File Requirements

Each `phase-XX-human-validation.md` file should include:

- What a human should look at
- Questions for the human reviewer
- What decisions need human judgment
- What “good” looks like
- What would require revision

The human validation file should make it easy for me to review the phase without reading all the code.

---

# Step 5: Embed Site Requirements in the Phase Plans

Do not build `prototype.html` or any other implementation files in this session. Instead, capture the following requirements inside the relevant phase build, QA, and human validation files so a future builder can follow them.

## General (Phase 3+)

- Single HTML file: `prototype.html`
- Embedded CSS and JavaScript
- Use local logo files directly: `03-logo-full.png`, `03-logo-simple.jpg`
- No external libraries unless approved
- No backend dependency
- No placeholder lorem ipsum
- Real page copy based on the project files

## Design (Phase 2+)

- Follow `03-brand-guidelines.html`
- Dark editorial studio style
- Strong typography, high contrast, generous spacing, modular sections
- Logo used cleanly and sparingly
- Avoid generic SaaS gradients and AI hype visuals
- Premium but beginner-friendly feel

## Content (Phase 1 and 3)

The page should clearly explain:

- What Vibe Code Academy is
- Who it is for
- What problem it solves
- What the class helps the user build
- Why planning matters
- What the Prototype Starter Kit includes
- What the class costs
- What the user should do next

## CTA (Phase 1 and 3)

Primary CTA:

**Get the Prototype Starter Kit**

Secondary CTAs may include:

- Join the next workshop
- See what you will build
- Book a team session

## Signup Form (Phase 4)

- Email address field
- Basic email format validation
- Success message after submission
- Clear communication that the starter kit is being requested
- Simulated submission only unless backend storage is approved

## Accessibility and Responsiveness (Phase 3 and 5)

- Works on desktop and mobile
- Readable font sizes
- Strong contrast
- Accessible labels for form inputs
- Semantic HTML where practical

---

# Step 6: Planning Complete — Stop Here

After all phase plan files are created:

1. Provide a short **Planning Summary** covering:

- How many phases were defined and why
- What each phase is responsible for
- Which source files informed the plan
- What the builder should do first in a follow-up session (read `phase-01-build.md` and execute Phase 1 only)

2. **Stop.** Do not:

- Create or edit `prototype.html`
- Execute any build file
- Run QA against built code
- Present human validation for completed work
- Move through phases in this session

Phase execution happens in separate sessions, one phase at a time, using the files in `phase-plans/`.

---

# Important Behavior Rules

- Do not ignore the source files.
- Do not invent a different brand direction.
- Do not create phase plans before asking clarifying questions.
- Do not build or edit implementation files in this session.
- Do not add out-of-scope features unless explicitly approved.
- Keep the phase plans practical, clear, and teachable for a vibe coding workshop demo.
