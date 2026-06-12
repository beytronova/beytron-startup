# Security & Compliance Hardening

This directory defines deeper security and compliance guidance for Beytron Startup.

Use these files whenever a feature touches authentication, authorization, personal data, financial data, health data, payments, secrets, integrations, logging, analytics, mobile permissions, or release risk.

## Files

- `data-classification.md`
- `secret-handling.md`
- `threat-model-template.md`
- `compliance-checklist.md`
- `mobile-privacy.md`

## Rules

- Security uncertainty is a blocker, not a minor note.
- Sensitive data must be classified before architecture or development approval.
- Secrets must never be written into tickets, docs, code, logs, examples, or prompts.
- Authentication and authorization changes require explicit tests.
- Release must include known security risks and mitigations.
