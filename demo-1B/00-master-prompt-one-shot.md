Demo 1B Master Prompt — One Shot

Use this prompt in Cursor from inside the demo-1B project folder.

The goal is to ingest the planning files as source context, ask clarifying questions, then build the complete landing page in this session — not phase plans for an orchestrator. Deliver prototype.html (and optional supporting files only if you approve them in the interview).

For the phased planning workflow instead, use 00-master-prompt.md.

Master Prompt

You are helping me build a polished, single-page landing page for Vibe Code Academy in one session.

Before building, read and use the following project files as your source of truth:

01-project-brief.md

02-reference-sites.md

03-brand-guidelines.html

04-user-persona.md

05-value-prop.md

Logo assets (use directly in the page):

03-logo-full.png

03-logo-simple.jpg

Primary deliverable:

prototype.html — single HTML file in demo-1B/, with embedded CSS and JavaScript

Step 1: Read and Summarize Context

First, read all source files listed above.

Then summarize what you understand in this format:

Project Summary

Briefly explain what Vibe Code Academy is.

Target User

Summarize the primary user persona.

Core Value Proposition

Explain the main value the class provides.

Primary Conversion Goal

Explain the main action the landing page should drive.

Brand Direction

Summarize the visual and voice direction from the brand guidelines.

Reference Site Takeaways

Summarize the most important lessons from the reference sites.

Key Constraints

List what is in scope and out of scope.

Do not build the site yet.

Step 2: Build the Site in One Shot

After I answer the interview questions, build the full landing page in this session. Work in a logical order internally (architecture → visual system → HTML/CSS → form → polish), but do not create phase-plans/ files or stop between phases.

2A: Page architecture

Implement a single-page scroll layout with anchor-linked navigation. Default section order unless my answers suggest otherwise:

Order

Section

Suggested anchor ID

Purpose

1

Header / nav

—

Logo, anchor nav, primary CTA

2

Hero

#hero

Promise, audience hook, primary CTA

3

Problem

#problem

Why users get stuck with AI building

4

Outcomes

#outcomes

What they leave able to do / build

5

How it works

#how-it-works

Plan → Build → Test → Improve → Share

6

Example projects

#examples

Concrete project types they can build

7

Starter kit

#starter-kit

Free kit contents + primary CTA repeat

8

Pricing

#pricing

Free kit + paid workshop tier(s) per interview

9

Who it's for

#for-students or audience-appropriate ID

Primary audience positioning

10

Signup

#signup

Email form

11

FAQ

#faq

Reassurance for beginners

12

Footer

—

Class format, schedule, secondary CTAs

Primary CTA (default unless I change it): Get the Prototype Starter Kit → #signup

Secondary CTAs (default): same-page anchors only — e.g. See what you will build → #examples, Join the next workshop → #pricing

2B: Visual system

Apply 03-brand-guidelines.html in embedded CSS:

Dark editorial studio style

Strong typography, high contrast, generous spacing, modular sections

Logo used cleanly and sparingly (03-logo-simple.jpg and/or 03-logo-full.png)

Avoid generic SaaS gradients and AI hype visuals

Premium but beginner-friendly feel

Responsive layout (desktop and mobile; readable type; strong contrast)

2C: Create prototype.html

Requirements:

Single file: demo-1B/prototype.html

Embedded <style> and <script> — no external libraries unless I approve

No backend dependency unless I approve persistence in the interview

No placeholder lorem ipsum — real copy from project files and interview answers

Semantic HTML: <header>, <main>, <section>, <footer>, labeled form controls

The page must clearly explain:

What Vibe Code Academy is

Who it is for

What problem it solves

What the class helps the user build

Why planning matters

What the Prototype Starter Kit includes

What the class costs (per interview)

What the user should do next

2D: Signup form and interaction

In #signup:

Email field with accessible <label>

Client-side format validation

Inline error and success states (aria-live="polite" where helpful)

On valid submit: show success confirming the starter kit request

Default (simulated): no server round-trip; success UI after validation. Include a short visible note that delivery/storage is simulated for the demo unless I asked for persistence.

If I approved persistence: add minimal supporting files (e.g. api/submit-email.php + SQLite) and wire fetch from the form; keep paths relative to demo-1B/. Document what is real vs simulated.

Success copy should reflect my interview answer (default direction: confirmation that the kit will arrive within 24 hours).

2E: Polish pass (same session)

Before finishing, self-review against:

01-project-brief.md success criteria (60-second comprehension)

Persona and value prop alignment

Brand guide (no off-brand hype)

All interview decisions

Accessibility: labels, contrast, focus, semantic structure

Mobile responsiveness

Fix issues you find; do not defer polish to a follow-up session.

Step 3: Deliverables and Handoff

When the build is complete, provide:

Build Summary

What you built (files created/edited)

How interview answers shaped copy, sections, and form behavior

What is simulated vs functional

Self-QA Report

Short html file with checklist with pass/fail notes:

Content completeness (all required messages present)

CTA and anchor behavior

Brand and typography

Form validation and success flow

Accessibility and responsive checks

Human Validation Prompt

Give me 5–8 specific questions to review in the browser (conversion, tone, student focus, pricing clarity, form UX) and what “good” looks like vs what would need revision.

Important Behavior Rules

Do not ignore the source files.

Do not invent a different brand direction.

Do not build before asking clarifying questions.

Do not create phase-plans/ or orchestrator phase files in this workflow.

Do not add out-of-scope features (payments, accounts, real email delivery, CMS, production deploy) unless explicitly approved in the interview.

Prefer one complete prototype.html over splitting into many files unless persistence or my answers require helpers.

Keep the result teachable for a vibe coding workshop demo: clear structure, readable code, intentional comments only where they explain simulated vs real behavior.
