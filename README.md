# Beytron Startup

Beytron Startup is a Codex plugin blueprint for running an agile AI delivery organization across product repositories.

It defines reusable roles, workflows, skills, routing registries, handoffs, templates, checklists, examples, playbooks, validation scenarios, security hardening, release discipline, and governance rules so Codex can move a project from idea to delivery with traceable decisions, explicit approvals, and quality gates.

## Purpose

- Model a startup delivery organization as AI-readable roles.
- Standardize product, design, architecture, development, QA, automation, release, growth, analytics, and security responsibilities.
- Make handoffs between roles explicit and reviewable.
- Keep implementation tied to PRD, architecture, Jira tickets, GitHub changes, approval, tests, and release notes.
- Allow different implementation systems such as web, Flutter, iOS, Android, backend, automation, and QA to plug into the same operating model.

## Structure

```text
.codex-plugin/plugin.json
AGENTS.md
README.md
INSTALL.md
USAGE.md
CHANGELOG.md
CONTRIBUTING.md
RELEASE_POLICY.md
config/
roles/
workflows/
skills/
handoffs/
templates/
checklists/
examples/
playbooks/
repo-bootstrap/
validation/
security/
governance/
roadmap/
```

## Core Flow

```text
Idea -> Discovery -> PRD -> Design -> Architecture -> Backlog -> Development -> QA -> Release -> Growth
```

## Routing Layer

Version `0.4.0` uses these routing files first:

- `config/workflow-map.yaml` maps stages to workflows, approvals, roles, inputs, outputs, and next stages.
- `config/role-skill-map.yaml` maps roles to primary skills, supporting skills, workflows, and expected outputs.
- `config/tool-access.yaml` defines when GitHub, Jira, web search, Figma, and release systems may be used.

## Usage Layer

- `INSTALL.md` explains plugin installation and verification.
- `USAGE.md` provides practical prompts for idea, PRD, Jira, development, repo bootstrap, release, and artifact revision flows.

## Validation Layer

The `checklists/` directory turns governance into practical gates:

- Discovery must pass before PRD.
- PRD must pass before design, architecture, or backlog.
- Architecture and ticket readiness must pass before development.
- Development handoff must pass before QA.
- QA and release checklists must pass before release execution.
- Repo bootstrap checklist must pass before repository creation.

The `validation/` directory adds prompt-based behavior tests for common scenarios.

## Example Layer

The `examples/` directory provides golden paths Codex can imitate for common delivery situations:

- Idea to release
- Jira ticket to pull request
- Mobile feature delivery
- Backend API delivery
- Growth experiment planning

Examples do not replace governance. They show the expected order of routing, role selection, skill usage, checklist validation, outputs, and stop conditions.

## Execution Playbook Layer

The `playbooks/` directory defines operational sequences for external systems:

- Jira issue reading, creation, updates, and transitions
- GitHub repository inspection, branches, commits, pull requests, and release actions
- Jira-to-GitHub delivery from approved tickets to QA handoff

Side effects require explicit approval or workflow permission.

## Repo Bootstrap Layer

The `repo-bootstrap/` directory defines how an approved idea becomes a product repository.

Repository creation requires:

```text
Approval Status = APPROVED_FOR_REPO_CREATION
```

Development still requires:

```text
Approval Status = APPROVED_FOR_DEVELOPMENT
```

## Security Hardening Layer

The `security/` directory defines deeper guidance for:

- Data classification
- Secret handling
- Threat modeling
- Compliance checks
- Mobile privacy

Security uncertainty is treated as a blocker.

## Release Discipline Layer

The root release files define how this plugin evolves:

- `CHANGELOG.md` records user-visible changes by version.
- `RELEASE_POLICY.md` defines semantic versioning, release gates, approval, release notes, and rollback rules.
- `CONTRIBUTING.md` defines how to safely add or change roles, skills, workflows, integrations, templates, checklists, examples, and governance.

Publishing a plugin release requires:

```text
Approval Status = APPROVED_FOR_RELEASE
```

## How To Use

1. Start with the current stage or user intent.
2. Read `AGENTS.md`, `INSTALL.md`, and `USAGE.md` when setting up or explaining usage.
3. Read `config/workflow-map.yaml` to route the request.
4. Read `config/role-skill-map.yaml` to select role and skill.
5. Read `config/tool-access.yaml` before using external tools.
6. Read the selected workflow, role, and skill files.
7. Read a matching golden path under `examples/` when the request matches a known scenario.
8. Read a matching playbook under `playbooks/` before Jira or GitHub side effects.
9. Use templates for produced artifacts.
10. Use handoff files when responsibility moves between roles.
11. Use checklists before moving to the next workflow stage.
12. Apply `security/` and `governance/` before development, QA, release, or risk acceptance.
13. Apply `RELEASE_POLICY.md` and update `CHANGELOG.md` when changing the plugin itself.

## Required Operating Rules

- Do not code directly from an idea.
- Development requires approved scope, PRD, architecture, ticket reference, target repository, and test impact.
- Jira issue creation requires explicit approval unless the user asks for it directly and approval gates permit it.
- GitHub branches, PRs, and repo changes must preserve the target repository's own `AGENTS.md` instructions.
- Repository creation requires `APPROVED_FOR_REPO_CREATION`.
- Release publishing requires `APPROVED_FOR_RELEASE`.
- Sensitive data uncertainty blocks architecture, development, or release until resolved.
- Plugin changes require changelog and version impact review.

## Role Model

Each role defines mission, ownership, required inputs, workflow protocol, artifact contracts, collaboration points, stop conditions, quality gates, and example prompts.

## Plugin Status

Version `0.4.0` includes routing, core skills, integration contracts, validation checklists, stack deep dives, golden path examples, installation and usage guides, Jira/GitHub execution playbooks, repo bootstrap, validation scenarios, security hardening, changelog, contribution guide, and release policy.
