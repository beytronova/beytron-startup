# Beytron Startup

Beytron Startup is a Codex plugin blueprint for running an agile AI delivery organization across product repositories.

It defines reusable roles, workflows, skills, handoffs, templates, and governance rules so Codex can move a project from idea to delivery with traceable decisions, explicit approvals, and quality gates.

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
roles/
workflows/
skills/
handoffs/
templates/
governance/
```

## Core Flow

```text
Idea -> Discovery -> PRD -> Design -> Architecture -> Backlog -> Development -> QA -> Release -> Growth
```

## How To Use

1. Start with the workflow that matches the current stage.
2. Select the role responsible for the next output.
3. Read the matching skill for execution rules.
4. Use templates for produced artifacts.
5. Use handoff files when responsibility moves between roles.
6. Apply governance files before development, QA, release, or risk acceptance.

## Required Operating Rules

- Do not code directly from an idea.
- Development requires approved scope, PRD, architecture, ticket reference, and test impact.
- Jira issue creation requires explicit approval unless the user asks for it directly.
- GitHub branches, PRs, and repo changes must preserve the target repository's own `AGENTS.md` instructions.
- Release requires QA evidence, known-risk review, rollback plan, and release approval.

## Role Model

Each role defines mission, ownership, required inputs, workflow protocol, artifact contracts, collaboration points, stop conditions, quality gates, and example prompts.

## Plugin Status

Version `0.2.0` is an operational scaffold. It is ready to guide Codex work, and can be extended with MCP servers, connector-specific tools, richer role packs, and company-specific policies.
