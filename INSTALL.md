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

If you are using Codex's **Add plugin marketplace** dialog, add the repository as a marketplace root:

```text
Source:
https://github.com/beytronova/beytron-startup.git

Git ref:
main

Sparse paths:

```

Leave `Sparse paths` empty.

This works because the marketplace manifest now lives at:

```text
.agents/plugins/marketplace.json
```

That marketplace manifest points to the plugin at:

```text
./plugins/beytron-startup
```

The plugin manifest lives at:

```text
plugins/beytron-startup/.codex-plugin/plugin.json
```

Do not use a GitHub blob URL to `plugin.json` as the source.
Do not put `plugins/beytron-startup` in `Sparse paths` when adding the marketplace; Codex needs the repository root so it can read `.agents/plugins/marketplace.json`.

## Plugin Wrapper

The recommended plugin wrapper is:

```text
plugins/beytron-startup
```

The older wrapper remains available at:

```text
plugins/codex
```

Prefer `plugins/beytron-startup` because its folder name matches the plugin name and avoids ambiguity with Codex's own product name.

## Root Plugin Manifest

The repository also keeps a root plugin manifest at:

```text
.codex-plugin/plugin.json
```

The marketplace install path should still use `.agents/plugins/marketplace.json` at the repository root.

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
- Confirm `Sparse paths` is empty when adding the marketplace.
- Confirm `.agents/plugins/marketplace.json` exists.
- Confirm the marketplace entry points to `./plugins/beytron-startup`.
- Confirm `plugins/beytron-startup/.codex-plugin/plugin.json` exists.
- Confirm the marketplace manifest version is `0.4.8` or newer.
- Confirm `AGENTS.md` or the marketplace entry skill is read before task execution.
- Confirm the user prompt explicitly asks to use Beytron Startup when needed.
- Confirm target product repositories also have their own `AGENTS.md`.

If Codex still reports `marketplace root does not contain a supported manifest`, close and reopen the Add plugin marketplace dialog, then retry with `Sparse paths` empty. The dialog may keep a stale staged copy from a previous failed attempt.

## Safe Start Prompt

```text
Use Beytron Startup. Route this request through the correct approval status, workflow, role, skill, checklist, and example before taking action: {request}
```
