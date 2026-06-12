# Beytron Startup

Beytron Startup is a Codex plugin blueprint for running an agile AI delivery organization across product repositories.

It defines reusable roles, workflows, skills, routing registries, handoffs, templates, checklists, and governance rules so Codex can move a project from idea to delivery with traceable decisions, explicit approvals, and quality gates.

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
config/
roles/
workflows/
skills/
handoffs/
templates/
checklists/
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

## How To Use

1. Start with the current stage or user intent.
2. Read `config/workflow-map.yaml` to route the request.
3. Read `config/role-skill-map.yaml` to select role and skill.
4. Read `config/tool-access.yaml` before using external tools.
5. Read the selected workflow, role, and skill files.
6. Use templates for produced artifacts.
7. Use handoff files when responsibility moves between roles.
8. Use checklists before moving to the next workflow stage.
9. Apply governance files before development, QA, release, or risk acceptance.

## Required Operating Rules

- Do not code directly from an idea.
- Development requires approved scope, PRD, architecture, ticket reference, target repository, and test impact.
- Jira issue creation requires explicit approval unless the user asks for it directly.
- GitHub branches, PRs, and repo changes must preserve the target repository's own `AGENTS.md` instructions.
- Release requires QA evidence, known-risk review, rollback plan, and release approval.

## Role Model

Each role defines mission, ownership, required inputs, workflow protocol, artifact contracts, collaboration points, stop conditions, quality gates, and example prompts.

## Plugin Status

Version `0.3.0` now includes routing, core skills, integration contracts, and validation checklists. Upcoming phases add stack deep dives, examples/golden paths, and versioning/release discipline.
