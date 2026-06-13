# Beytron Startup

Use this skill when the user asks to use Beytron Startup, Beytronova startup system, agile AI delivery roles, product-to-development workflow, idea-to-PRD flow, Jira/GitHub delivery, mobile development roles, or plugin governance.

## Canonical Repository

The canonical repository is:

```text
https://github.com/beytronova/beytron-startup
```

This marketplace wrapper exists so Codex can install Beytron Startup through the **Add plugin marketplace** dialog using:

```text
Source: https://github.com/beytronova/beytron-startup.git
Git ref: main
Sparse paths: plugins/beytron-startup
```

## Mandatory Operating Order

When using Beytron Startup, follow the repository operating model:

1. Validate approval status using the canonical approval statuses.
2. Route the request through workflow, role, skill, and tool registries.
3. Read the target repository `AGENTS.md` before product code work.
4. Use checklists before moving stages.
5. Use playbooks before Jira or GitHub side effects.
6. Use security guidance for sensitive data, secrets, auth, mobile privacy, or release risk.
7. Do not code directly from an idea.
8. Do not create Jira issues, GitHub branches, PRs, repositories, or releases without explicit approval.

## Canonical Approval Statuses

Use these statuses exactly:

- `WAITING`
- `APPROVED_FOR_RESEARCH`
- `APPROVED_FOR_JIRA_CREATION`
- `APPROVED_FOR_REPO_CREATION`
- `APPROVED_FOR_DEVELOPMENT`
- `APPROVED_FOR_RELEASE_PREPARATION`
- `APPROVED_FOR_RELEASE`
- `APPROVED_FOR_SECURITY_RISK_ACCEPTANCE`
- `REJECTED`

Unknown approval statuses are blockers.

## Core Flow

```text
Idea -> Discovery -> PRD -> Design -> Architecture -> Backlog -> Development -> QA -> Release -> Growth
```

## Required Response Shape

Every substantive Beytron Startup response should include:

```text
Approval status: {status}
Allowed actions: {list}
Blocked actions: {list}
Route used: {stage -> workflow}
Role used: {role}
Skill used: {skill}
Checklist used: {checklist}
Playbook used: {if any}
Security files used: {if any}
Artifacts changed: {files or drafts}
Blockers: {if any}
Next step: {specific action}
```

## When Full Repository Context Is Needed

If this marketplace wrapper is installed without the full repository files and the user asks for detailed role, skill, workflow, checklist, or governance content, inspect the canonical GitHub repository or ask the user to install the full repository without sparse paths.
