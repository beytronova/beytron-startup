---
name: governance-approval
description: Enforce Beytron approval statuses, allowed actions, blocked actions, artifact gates, role routing, and stop conditions across every workflow.
---

# Governance Approval

Use this skill whenever a request includes an approval status, asks what can happen next, or risks skipping Beytron gates.

## Canonical Statuses

- `WAITING`
- `APPROVED_FOR_RESEARCH`
- `APPROVED_FOR_JIRA_CREATION`
- `APPROVED_FOR_REPO_CREATION`
- `APPROVED_FOR_DEVELOPMENT`
- `APPROVED_FOR_RELEASE_PREPARATION`
- `APPROVED_FOR_RELEASE`
- `APPROVED_FOR_SECURITY_RISK_ACCEPTANCE`
- `REJECTED`

## Rules

- Unknown approval statuses are blockers.
- `WAITING` blocks active work.
- Research approval allows planning artifacts only.
- Repo creation approval allows repository proposal/bootstrap only.
- Development approval allows work only in the target product repository.
- Release approval is required before production release.

## Outputs

- Allowed actions.
- Blocked actions.
- Required artifacts.
- Next valid status.
- Stop condition if blocked.
