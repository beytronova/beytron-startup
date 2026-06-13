# Installation

This guide explains how to add Beytron Startup to a Codex environment.

## Repository

```text
https://github.com/beytronova/beytron-startup
```

## Intended Use

Beytron Startup is not a product repository. It is an AI-readable operating system for product delivery.

Use it to guide:

- Idea discovery
- PRD creation
- Product design handoff
- Architecture planning
- Jira backlog creation
- GitHub implementation workflows
- QA and test automation
- Release planning
- Growth and analytics follow-up

## Add Through Codex Plugin Marketplace Dialog

If you are using Codex's **Add plugin marketplace** dialog, use:

```text
Source:
beytronova/beytron-startup

Git ref:
main

Sparse paths:
plugins/codex
```

If the shorthand source still resolves to an invalid marketplace file, retry with the full Git URL:

```text
Source:
https://github.com/beytronova/beytron-startup.git

Git ref:
main

Sparse paths:
plugins/codex
```

This works because the marketplace-compatible plugin manifest lives at:

```text
plugins/codex/.codex-plugin/plugin.json
```

The manifest uses the supported Codex plugin schema with `name`, `version`, `description`, `author`, `homepage`, `repository`, `license`, `keywords`, `skills`, and `interface` fields.

Do not use a GitHub blob URL to `plugin.json` as the source.

## Root Plugin Manifest

The repository also keeps a root plugin manifest at:

```text
.codex-plugin/plugin.json
```

Use the root manifest only in environments that support adding a repository directly as a plugin source without marketplace sparse paths.

## Prerequisites

Before using the plugin, ensure Codex can access:

- This repository
- Target product repositories when development is requested
- Jira when ticket creation, reading, or updates are requested
- GitHub when branches, pull requests, repository creation, or repository inspection is requested
- Figma or design source when design work is requested
- Web search when research is requested

## First Read Order

When Codex starts work using this plugin, it should read:

1. `AGENTS.md`
2. `README.md`
3. `governance/approval-statuses.md`
4. `config/approval-statuses.yaml`
5. `config/workflow-map.yaml`
6. `config/role-skill-map.yaml`
7. `config/tool-access.yaml`
8. The matching workflow, role, skill, checklist, and example files

## Verification After Installation

Ask Codex:

```text
Using Beytron Startup, explain how a raw idea moves to development approval.
```

Expected behavior:

- Codex should not jump directly to code.
- Codex should mention discovery, PRD, design, architecture, backlog, approval, development, QA, release, and growth.
- Codex should reference approval statuses, routing registries, role/skill selection, checklists, governance, and examples.

## Common Setup Issues

If Codex does not follow the plugin:

- Confirm the repository is accessible.
- For marketplace installation, confirm `plugins/codex` is used as Sparse paths.
- Confirm `plugins/codex/.codex-plugin/plugin.json` exists.
- Confirm the marketplace manifest version is `0.4.6` or newer.
- Confirm `AGENTS.md` or the marketplace entry skill is read before task execution.
- Confirm the user prompt explicitly asks to use Beytron Startup when needed.
- Confirm target product repositories also have their own `AGENTS.md`.

If Codex still reports `marketplace root does not contain a supported manifest`, close and reopen the Add plugin marketplace dialog, then retry with the full Git URL shown above. The dialog may keep a stale staged copy from a previous failed attempt.

## Safe Start Prompt

```text
Use Beytron Startup. Route this request through the correct approval status, workflow, role, skill, checklist, and example before taking action: {request}
```
