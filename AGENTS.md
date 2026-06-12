# AGENTS.md

## Plugin Role

Beytron Startup provides an agile AI delivery system for Codex. It does not own product code directly; it guides how product repositories should be researched, designed, implemented, tested, released, and improved.

## Mandatory Execution Order

1. Identify the current stage: idea, discovery, PRD, design, architecture, backlog, development, QA, release, or growth.
2. Read `config/workflow-map.yaml` to route the request to the correct workflow.
3. Read `config/role-skill-map.yaml` to select the responsible role and skill.
4. Read `config/tool-access.yaml` before using GitHub, Jira, web search, Figma, or release systems.
5. Read the matching file under `workflows/`.
6. Read the responsible role from `roles/`.
7. Read the matching `skills/*/SKILL.md` file.
8. Use `templates/` for new artifacts.
9. Use `handoffs/` when responsibility moves between roles.
10. Use `checklists/` before moving an artifact to the next workflow stage.
11. Apply `governance/` before coding, QA sign-off, release, or risk acceptance.

## Routing Registries

- `config/workflow-map.yaml`: maps stages to workflows, approvals, roles, inputs, outputs, and next stages.
- `config/role-skill-map.yaml`: maps roles to primary skills, supporting skills, workflows, and outputs.
- `config/tool-access.yaml`: defines when external tools may be used and when side effects require approval.

If a registry marks a skill or integration as missing, do not pretend it exists. Use the current best available role/workflow, record the gap, and recommend the missing file as follow-up.

## Validation Checklists

Use checklists as workflow gates:

- `checklists/discovery-checklist.md` before PRD.
- `checklists/prd-checklist.md` before design, architecture, or backlog.
- `checklists/design-checklist.md` before architecture, backlog, or development.
- `checklists/architecture-checklist.md` before backlog or development.
- `checklists/ticket-ready-checklist.md` before development.
- `checklists/development-handoff-checklist.md` before QA.
- `checklists/qa-checklist.md` before release.
- `checklists/release-checklist.md` before release execution.

## Core Rules

- Never move directly from idea to code.
- Development requires PRD, architecture, approved ticket scope, explicit approval, and test impact.
- Do not create real Jira issues, GitHub repositories, branches, pull requests, or releases unless the user explicitly asks or the workflow approval permits it.
- When working inside a product repository, obey that repository's own `AGENTS.md` before this plugin's generic rules.
- Keep every output traceable to source artifacts: idea, discovery, PRD, design, architecture, tickets, tests, and approval.
- Stop instead of guessing when approval, scope, testability, security, or release risk is unclear.

## Role Selection

Use `config/role-skill-map.yaml` as the source of truth. If direct routing is impossible, fall back to this summary:

- Product work starts with `roles/product.md`.
- UX/UI work uses `roles/product-designer.md`.
- Technical system decisions use `roles/architect.md`.
- Web implementation uses `roles/web-developer.md`.
- Backend implementation uses `roles/backend-developer.md`.
- Cross-platform mobile uses `roles/flutter-developer.md` or `roles/mobile-lead.md`.
- Native iOS uses `roles/ios-developer.md`.
- Native Android uses `roles/android-developer.md`.
- QA strategy uses `roles/qa-developer.md`.
- Test automation uses `roles/automation-developer.md`.
- Release uses `roles/devops-release.md`.
- Growth and SEO use `roles/growth-seo.md`.
- Analytics uses `roles/data-analytics.md`.
- Security review uses `roles/security-reviewer.md`.

## Standard Output Discipline

Every substantive output should include:

- Source artifacts read
- Registry route used
- Role used
- Skill used
- Workflow used
- Checklist used
- Decisions made
- Open questions
- Risks and blockers
- Next role or next workflow

## Stop Conditions

Stop when required inputs are missing, approval is unclear, ticket scope is not documented, design or architecture is unresolved, checklist pass criteria are not met, tests cannot be defined, sensitive data risk is unknown, release risk cannot be accepted explicitly, or a required external tool side effect lacks approval.
