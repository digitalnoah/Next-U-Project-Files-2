# Planning Decisions (Assumed)

These answers stand in for the Step 2 interview. Phase plans embed them where relevant.

## Offer and CTA

| # | Decision |
|---|----------|
| 1 | **Primary CTA:** Keep **Get the Prototype Starter Kit** everywhere it matters (hero, nav, signup, repeated mid-page). |
| 2 | **Pricing:** Show all tiers on the page — Free kit ($0), Intro ($149), Full workshop ($299), Team (from $2,500). Free kit is visually dominant; paid tiers are “next step” cards. |
| 3 | **Post-signup success:** Thank the user by name/email snippet, list what the starter kit includes, state clearly that **delivery is simulated in this prototype** (no real email), and offer one secondary link: **Join the next workshop** → `#pricing`. |

## Audience

| # | Decision |
|---|----------|
| 4 | **Hero audience:** Speak to a **mixed audience** (“students, marketers, founders, and operators with product ideas”). Use persona language: smart beginners, not engineers. |

## Tone and Positioning

| # | Decision |
|---|----------|
| 5 | **Tone:** **Editorial-bold, premium, beginner-friendly** — confident and slightly sharp, not playful or academic. No guru / hype voice. |
| 6 | **Cursor:** Mention **Cursor in hero subcopy** and again in “How it works” and FAQ; do not put Cursor in the H1. |

## Content and Proof

| # | Decision |
|---|----------|
| 7 | **Proof:** **No testimonials, instructor bio, or client logos** in v1. Use outcomes, workflow, and kit contents as trust instead. |
| 8 | **Examples:** Feature **all four** example project cards: startup landing page, dashboard/report mockup, portfolio site, simple AI-assisted workflow prototype. |
| 9 | **FAQ:** **Full FAQ** (~6 questions) covering coding required, tools, finished product vs prototype, after signup, workshop fit, and simulated form behavior. |

## Functionality

| # | Decision |
|---|----------|
| 10 | **Form success:** Show **success message plus inline list** of starter kit items (planning template, build prompt template, project file structure, example brief). |
| 11 | **Secondary CTAs:** **Join the next workshop** → `#pricing`; **See what you will build** → `#examples`; **Book a team session** → `#pricing` (team card) with `mailto:hello@vibecodeacademy.example` placeholder. Nav mirrors these anchors. |
| 12 | **Off limits for v1:** No video embeds, no payment/checkout, no real workshop dates, no external JS/CSS libraries, no lorem ipsum, no heavy animation, no third-party fonts (use system UI stack matching brand guide). |

## Build workspace

- **Source context:** `demo-1B/` (`01-project-brief.md` through `05-value-prop.md`, brand HTML, logos).
- **Deliverable:** `demo-1B/prototype.html` with **embedded CSS and JavaScript** (migrate off `prototype.css` if split files exist).
- **Logos:** `03-logo-full.png`, `03-logo-simple.jpg` in `demo-1B/` (copy from project assets if missing).
