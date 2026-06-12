# AGENTS.md

## Plugin Role

Beytron Startup provides an agile AI delivery system for Codex. It does not own product code directly; it guides how product repositories should be researched, designed, implemented, tested, released, and improved.

## Mandatory Execution Order

1. Identify the current stage: idea, discovery, PRD, design, architecture, backlog, repo-bootstrap, development, QA, release, growth, or plugin-change.
2. Read `governance/approval-statuses.md` and `config/approval-statuses.yaml` to validate the approval status and allowed actions.
3. Read `config/workflow-map.yaml` to route the request to the correct workflow.
4. Read `config/role-skill-map.yaml` to select the responsible role and skill.
5. Read `config/tool-access.yaml` before using GitHub, Jira, web search, Figma, or release systems.
6. Read the matching file under `workflows/`.
7. Read the responsible role from `roles/`.
8. Read the matching `skills/*/SKILL.md` file.
9. Use `templates/` for new artifacts.
10. Use `handoffs/` when responsibility moves between roles.
11. Use `checklists/` before moving an artifact to the next workflow stage.
12. Use `examples/` when the request matches a known golden path.
13. Use `playbooks/` before Jira or GitHub execution side effects.
14. Use `repo-bootstrap/` before proposing or creating product repositories.
15. Use `security/` for sensitive data, secrets, auth, compliance, mobile privacy, or release risk.
16. Apply `governance/` before coding, QA sign-off, release, or risk acceptance.
17. When changing this plugin, read `CONTRIBUTING.md`, `RELEASE_POLICY.md`, and `CHANGELOG.md` before editing release-impacting files.
18. When adding or materially changing a role, read `governance/role-creation-rules.md`, use `templates/ROLE.template.md`, and validate with `checklists/role-creation-checklist.md`.

## Approval Status Source of Truth

- `governance/approval-statuses.md` is the human-readable canonical policy.
- `config/approval-statuses.yaml` is the machine-readable registry.
- If another file conflicts with these approval definitions, the centralized approval status files win.
- Every approval-sensitive response must state the approval status, allowed actions, blocked actions, required artifacts, and next valid statuses.

## Setup and Usage Guidance

- Use `INSTALL.md` when the user asks how to install, connect, or verify this plugin.
- Use `USAGE.md` when the user asks what command or prompt to use.
- Use `validation/` when checking whether the plugin behavior works as expected.

## Routing Registries

- `config/approval-statuses.yaml`: maps approval statuses to allowed actions, blocked actions, required artifacts, and next statuses.
- `config/workflow-map.yaml`: maps stages to workflows, approvals, roles, inputs, outputs, and next stages.
- `config/role-skill-map.yaml`: maps roles to primary skills, supporting skills, workflows, and outputs.
- `config/tool-access.yaml`: defines when external tools may be used and when side effects require approval.

If a registry marks a skill or integration as missing, do not pretend it exists. Use the current best available role/workflow, record the gap, and recommend the missing file as follow-up.

## Role Creation Rules

When adding a new role, follow `governance/role-creation-rules.md`.

A new role must normally include or update:

- `roles/{role-slug}.md`
- `skills/{skill-slug}/SKILL.md` or documented reuse of an existing skill
- `config/role-skill-map.yaml`
- relevant workflow files when workflow ownership changes
- relevant handoff files when responsibility crosses role boundaries
- relevant checklist files when the role owns a gate
- relevant example files when user-facing behavior changes
- relevant validation scenarios when routing, approval, tool use, development, release, or security behavior changes
- `CHANGELOG.md`

Use `templates/ROLE.template.md` for the role file and `checklists/role-creation-checklist.md` before completion.

## Validation Checklists

Use checklists as workflow gates:

- `checklists/discovery-checklist.md` before PRD.
- `checklists/prd-checklist.md` before design, architecture, or backlog.
- `checklists/design-checklist.md` before architecture, backlog, or development.
- `checklists/architecture-checklist.md` before backlog or development.
- `checklists/ticket-ready-checklist.md` before development.
- `checklists/repo-bootstrap-checklist.md` before product repository creation.
- `checklists/role-creation-checklist.md` before completing a role addition or material role update.
- `checklists/development-handoff-checklist.md` before QA.
- `checklists/qa-checklist.md` before release.
- `checklists/release-checklist.md` before release execution.

## Execution Playbooks

Before Jira or GitHub side effects, read the matching playbook:

- Jira issue work: `playbooks/jira-execution.md`.
- GitHub repository, branch, commit, PR, or release work: `playbooks/github-execution.md`.
- Jira ticket to GitHub implementation: `playbooks/jira-github-delivery.md`.

Side effects require explicit approval or workflow permission. If approval is missing, produce a draft or plan instead of executing.

## Repo Bootstrap

Use `repo-bootstrap/` only after `governance/approval-statuses.md` confirms:

```text
Approval Status = APPROVED_FOR_REPO_CREATION
```

Repository bootstrap may propose or create a product repository, but it must not start product development. Development still requires:

```text
Approval Status = APPROVED_FOR_DEVELOPMENT
```

## Security and Compliance

Use `security/` when a request involves:

- Personal data
- Financial data
- Health data
- Authentication or authorization
- Secrets or credentials
- Payments
- Mobile permissions
- Third-party integrations
- Logging, analytics, or retention
- Release risk

Security uncertainty is a blocker. Do not mark architecture, development, QA, or release as safe until required security facts are known or residual risk is explicitly accepted.

## Release Discipline

When changing Beytron Startup itself:

- Read `CONTRIBUTING.md` before adding or changing roles, skills, workflows, integrations, templates, checklists, examples, playbooks, validation scenarios, security files, or governance.
- Read `RELEASE_POLICY.md` before changing version, release process, release gates, or publishing behavior.
- Update `CHANGELOG.md` for user-visible changes.
- Identify version impact as major, minor, or patch.
- Verify registries reference existing files.
- Verify examples do not bypass approval, checklists, governance, security, or target repository `AGENTS.md` instructions.
- Do not publish tags, GitHub releases, packages, or marketplace submissions without `Approval Status = APPROVED_FOR_RELEASE`.

## Core Rules

- Never move directly from idea to code.
- Development requires PRD, architecture, approved ticket scope, explicit approval, and test impact.
- Do not create real Jira issues, GitHub repositories, branches, pull requests, or releases unless the user explicitly asks and the centralized approval status policy permits it.
- When working inside a product repository, obey that repository's own `AGENTS.md` before this plugin's generic rules.
- Keep every output traceable to source artifacts: idea, discovery, PRD, design, architecture, tickets, tests, approval, security review, and release evidence.
- Stop instead of guessing when approval, scope, testability, security, compliance, or release risk is unclear.

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
- Approval status used
- Allowed and blocked actions
- Registry route used
- Role used
- Skill used
- Workflow used
- Checklist used
- Playbook used, if any
- Security files used, if any
- Decisions made
- Open questions
- Risks and blockers
- Next role or next workflow

When changing the plugin itself, also include:

- Version impact
- Changelog status
- Release policy impact

## Stop Conditions

Stop when required inputs are missing, approval is unclear, approval status is unknown to `config/approval-statuses.yaml`, ticket scope is not documented, design or architecture is unresolved, checklist pass criteria are not met, tests cannot be defined, sensitive data risk is unknown, compliance requirements are unknown, release risk cannot be accepted explicitly, a required external tool side effect lacks approval, a plugin release action lacks `Approval Status = APPROVED_FOR_RELEASE`, or a role addition fails `checklists/role-creation-checklist.md`.
