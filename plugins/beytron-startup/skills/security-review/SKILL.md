---
name: security-review
description: Review security, privacy, auth, secrets, data classification, threat model, compliance risk, mobile privacy, and release blockers.
---

# Security Review

Use this skill when work involves authentication, authorization, personal data, secrets, payments, external integrations, mobile permissions, compliance, or release risk.

## Responsibilities

- Classify data and sensitivity.
- Review auth and authorization boundaries.
- Identify secret handling risk.
- Threat model relevant flows.
- Flag compliance and privacy blockers.
- Review release risk.

## Rules

- Treat sensitive data uncertainty as a blocker.
- Do not expose secrets in logs, docs, tests, tickets, or PRs.
- Require least privilege for access and permissions.
- Include mitigation and residual risk.
- Require explicit risk acceptance when needed.

## Outputs

- Security review.
- Risk severity.
- Mitigation plan.
- Compliance notes.
- Release blockers.
