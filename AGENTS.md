# AGENTS.md

## Plugin Role

Beytron Startup provides an agile AI delivery system for Codex. It does not own product code directly; it guides how product repositories should be researched, designed, implemented, tested, released, and improved.

## Mandatory Execution Order

1. Identify the current stage: idea, discovery, PRD, design, architecture, backlog, development, QA, release, or growth.
2. Read the matching file under `workflows/`.
3. Select the responsible role from `roles/`.
4. Read the matching `skills/*/SKILL.md` file.
5. Use `templates/` for new artifacts.
6. Use `handoffs/` when responsibility moves between roles.
7. Apply `governance/` before coding, QA sign-off, release, or risk acceptance.

## Core Rules

- Never move directly from idea to code.
- Development requires PRD, architecture, approved ticket scope, explicit approval, and test impact.
- Do not create real Jira issues, GitHub repositories, branches, pull requests, or releases unless the user explicitly asks or the workflow approval permits it.
- When working inside a product repository, obey that repository's own `AGENTS.md` before this plugin's generic rules.
- Keep every output traceable to source artifacts: idea, discovery, PRD, design, architecture, tickets, tests, and approval.
- Stop instead of guessing when approval, scope, testability, security, or release risk is unclear.

## Role Selection

- Product work starts with `roles/product.md`.
- UX/UI work uses `roles/product-designer.md`.
- Technical system decisions use `roles/architect.md`.
- Web implementation uses `roles/web-developer.md`.
- Cross-platform mobile uses `roles/flutter-developer.md` or `roles/mobile-lead.md`.
- Native iOS uses `roles/ios-developer.md`.
- Native Android uses `roles/android-developer.md`.
- Backend implementation uses `roles/backend-developer.md`.
- QA strategy uses `roles/qa-developer.md`.
- Test automation uses `roles/automation-developer.md`.
- Release uses `roles/devops-release.md`.
- Growth and SEO use `roles/growth-seo.md`.
- Analytics uses `roles/data-analytics.md`.
- Security review uses `roles/security-reviewer.md`.

## Standard Output Discipline

Every substantive output should include:

- Source artifacts read
- Role used
- Workflow used
- Decisions made
- Open questions
- Risks and blockers
- Next role or next workflow

## Stop Conditions

Stop when required inputs are missing, approval is unclear, ticket scope is not documented, design or architecture is unresolved, tests cannot be defined, sensitive data risk is unknown, or release risk cannot be accepted explicitly.
