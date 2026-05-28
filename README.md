# Next-U — Vibe Code Academy Workshop

Phase-orchestrated landing page workshop materials for **Vibe Code Academy**: planning docs, build/QA plans, and a single-file HTML prototype.

## Structure

| Folder | Purpose |
|--------|---------|
| `demo-1B/` | Source briefs, brand guidelines, and `prototype.html` deliverable |
| `demo-1C-orchestrator/` | Phase orchestrator: `build-plan/`, `QA-plan/`, Cursor rules, agent workflow |
| `demo-1A/` | Earlier demo starter assets |

## Quick start

1. Read `demo-1C-orchestrator/project-plan/09-build-order.md`
2. Run one phase at a time: `demo-1C-orchestrator/build-plan/phases/01-phase-01-content-architecture.md`
3. Open the built page: `demo-1B/prototype.html` (local server or MAMP recommended)

## Orchestrator commands

See `demo-1C-orchestrator/AGENTS.md` — e.g. **Build phase 1 with the orchestrator**, **QA test phase 1 with the orchestrator**.

## GitHub

This folder is its own git repository (separate from the parent `a10x_2025` monorepo).

After [GitHub CLI](https://cli.github.com/) login (`gh auth login`), create and push the remote:

```bash
cd /Applications/MAMP/htdocs/a10x_2025/docs/client-work/Next-U
gh repo create vibe-code-academy-next-u --private --source=. --remote=origin --description "Vibe Code Academy workshop: phase orchestrator and landing prototype" --push
```

Use a different repo name if you prefer; `--public` instead of `--private` if it should be open.

## License

Client workshop materials — private unless otherwise agreed.
