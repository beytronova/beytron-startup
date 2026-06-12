# Beytron Startup

Beytron Startup is a Codex plugin blueprint for running an agile AI delivery organization across product repositories.

It defines reusable roles, workflows, skills, routing registries, handoffs, templates, checklists, examples, release discipline, and governance rules so Codex can move a project from idea to delivery with traceable decisions, explicit approvals, and quality gates.

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
governance/
```

## Core Flow

```text
Idea -> Discovery -> PRD -> Design -> Architecture -> Backlog -> Development -> QA -> Release -> Growth
```

## Routing Layer

Version `0.3.0` introduces the first routing foundation:

- `config/workflow-map.yaml` maps stages to workflows, approvals, roles, inputs, outputs, and next stages.
- `config/role-skill-map.yaml` maps roles to primary skills, supporting skills, workflows, and expected outputs.
- `config/tool-access.yaml` defines when GitHub, Jira, web search, Figma, and release systems may be used.

These files are the first place Codex should look when deciding what to do next.

## Validation Layer

The `checklists/` directory turns governance into practical gates:

- Discovery must pass before PRD.
- PRD must pass before design, architecture, or backlog.
- Architecture and ticket readiness must pass before development.
- Development handoff must pass before QA.
- QA and release checklists must pass before release execution.

## Example Layer

The `examples/` directory provides golden paths Codex can imitate for common delivery situations:

- Idea to release
- Jira ticket to pull request
- Mobile feature delivery
- Backend API delivery
- Growth experiment planning

Examples do not replace governance. They show the expected order of routing, role selection, skill usage, checklist validation, outputs, and stop conditions.

## Release Discipline Layer

The root release files define how this plugin evolves:

- `CHANGELOG.md` records user-visible changes by version.
- `RELEASE_POLICY.md` defines semantic versioning, release gates, approval, release notes, and rollback rules.
- `CONTRIBUTING.md` defines how to safely add or change roles, skills, workflows, integrations, templates, checklists, examples, and governance.

Publishing a plugin release requires:

```text
Approval Status = APPROVED_FOR_RELEASE
```

Without release approval, Codex may prepare release artifacts but must not publish tags, GitHub releases, packages, or marketplace submissions.

## How To Use

1. Start with the current stage or user intent.
2. Read `config/workflow-map.yaml` to route the request.
3. Read `config/role-skill-map.yaml` to select role and skill.
4. Read `config/tool-access.yaml` before using external tools.
5. Read the selected workflow, role, and skill files.
6. Read a matching golden path under `examples/` when the request matches a known scenario.
7. Use templates for produced artifacts.
8. Use handoff files when responsibility moves between roles.
9. Use checklists before moving to the next workflow stage.
10. Apply governance files before development, QA, release, or risk acceptance.
11. Apply `RELEASE_POLICY.md` and update `CHANGELOG.md` when changing the plugin itself.

## Required Operating Rules

- Do not code directly from an idea.
- Development requires approved scope, PRD, architecture, ticket reference, target repository, and test impact.
- Jira issue creation requires explicit approval unless the user asks for it directly.
- GitHub branches, PRs, and repo changes must preserve the target repository's own `AGENTS.md` instructions.
- Release requires QA evidence, known-risk review, rollback plan, and release approval.
- Plugin changes require changelog and version impact review.

## Role Model

Each role defines mission, ownership, required inputs, workflow protocol, artifact contracts, collaboration points, stop conditions, quality gates, and example prompts.

## Plugin Status

Version `0.3.0` now includes routing, core skills, integration contracts, validation checklists, stack deep dives, golden path examples, changelog, contribution guide, and release policy.
