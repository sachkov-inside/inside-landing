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

### Human communication

- Speak to the user in their language. In Russian, prefer ordinary Russian words over optional
  English terms. Keep code, commands, exact product or API names, and established project terms
  unchanged. Do not invent abbreviations.
- Lead with what happened or what must be decided and why it matters. Use short, natural sentences
  with one idea each. Remove filler, but keep normal grammar.
- Use an unfamiliar specialist term only when it is needed for the current decision. Explain it in
  plain words on first use.
- When offering a choice, name the decision directly. Give each option a short everyday label and
  one sentence explaining what it changes. Mark the recommendation and explain its reason plainly.

- For shared delivery rules and owner gates, read the repository-local `WORKFLOW.md` when the task
  touches issues, branches, pull requests, review, readiness, or merge.
- Native runtimes discover the selected skill profile through `.agents/skills` or `.claude/skills`.
  Fallback runtimes use `.inside-harness/skills/REGISTRY.md`: route by intent only to `Model` rows;
  open a `User` row only when the user names that skill.
- Managed skills and workflow files change in the canonical package and arrive through the harness
  lifecycle. Repository-specific skills stay local under unique names.
- Keep build, test, run, deploy, and agent work repository-local. Project-owned integrations may
  use native config; record them in `.inside-harness/integrations.json` without credentials.

### Pipeline stages

- The developer pipeline runs in owner-driven stages: sharpen the idea, then Specification, then
  Ticket breakdown, then Implementation. The owner starts each stage explicitly.
- Do not chain stages. Finish a stage with its outcome, the next stage you recommend, and any
  decision needed, then stop and wait. Start the next stage only after the owner asks for it. This
  holds even when a runtime does not honor a skill's user-only invocation marker.
- Start a development session in the repository that owns the outcome so its rules and skills load;
  a parent navigation directory does not carry the project pipeline.
<!-- inside-product-harness:end -->
