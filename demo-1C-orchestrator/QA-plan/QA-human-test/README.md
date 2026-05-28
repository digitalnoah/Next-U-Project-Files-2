# Human QA (HTML)

When automated QA returns **pass_with_risks**, the orchestrator adds `phase-N-<slug>.html` here.

Open the file in a browser, complete every checkbox, then tell the orchestrator:

`Human test done for phase N`

Include per-step pass/fail and evidence (screenshots, notes). The orchestrator updates QA-results and closes the phase (or opens a fix round on failure).

Markdown human-validation files in `phase-plans/human-validation/` are planning reference; runtime checklists are **HTML only**.
