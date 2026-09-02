# inside-landing

Landing for **Sachkov Inside** — Kirill Sachkov's authorial engineering membership.

Write agent-facing documents in English. Preserve the original language of user-submitted content.

## Working agreements

- For coding and review rules, read `CODING_STANDARDS.md`.
- For product, copy, visual, reference or UI work, read `docs/agents/domain.md`; it routes to the
  relevant local source of truth.
- For GitHub issue routing, Project fields, or Wayfinder operations, read
  `docs/agents/issue-tracker.md`.
- For readiness-label triage, read `docs/agents/triage-labels.md`.

## Commands and completion

Run from the repository root:

```bash
npm ci --prefix app
npm run dev --prefix app
npm run build --prefix app
npm run verify --prefix app
```

`npm run verify --prefix app` is the full CI-equivalent check; there is no separate test script.
Deploy has no local command: Timeweb deploys `main` through its GitHub integration. Use the
production smoke commands in `README.md` after deployment.

For UI changes, the browser QA and evidence gates in `playbook/README.md` are the Definition of
Done. Record anything not tested in the pull request.

<!-- inside-product-harness:start -->
## Inside product harness

This repository uses the versioned Sachkov Inside product harness.

- For shared delivery rules and owner gates, read the repository-local `WORKFLOW.md` when the task
  touches issues, branches, pull requests, review, readiness, or merge.
- Native runtimes discover the selected skill profile through `.agents/skills` or `.claude/skills`.
  Fallback runtimes use `.inside-harness/skills/REGISTRY.md`: route by intent only to `Model` rows;
  open a `User` row only when the user names that skill.
- Managed skills and workflow files change in the canonical package and arrive through the harness
  lifecycle. Repository-specific skills stay local under unique names.
- Keep build, test, run, deploy, and agent work repository-local. Project-owned integrations may
  use native config; record them in `.inside-harness/integrations.json` without credentials.
<!-- inside-product-harness:end -->
