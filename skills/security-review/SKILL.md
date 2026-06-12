# Security Review Skill

Use when reviewing architecture, implementation, data handling, authentication, authorization, privacy, dependencies, and release risk.

## Triggers
- Work includes authentication, authorization, payments, personal data, financial data, admin tools, file upload, integrations, webhooks, secrets, or deployment config.
- Architecture or release requires security/privacy review.
- QA or development reports sensitive data, permission, or access-control risk.

## Supported Review Areas
- Authentication and session behavior
- Authorization and access control
- Sensitive data collection, storage, transmission, retention, and deletion
- Secrets and environment variables
- Input validation and output encoding
- Dependency and supply-chain risk
- External integrations and webhooks
- Logging, monitoring, and data leakage
- Mobile permissions and platform privacy
- Release blockers and accepted risk records

## Required Inputs
- PRD or scope
- Architecture and data model
- Auth/permission requirements
- Implementation summary when available
- Dependency and environment notes
- Release scope when applicable

## Required Reading
- `roles/security-reviewer.md`
- `governance/security-standards.md`
- `governance/release-gates.md`
- `handoffs/architecture-to-development.md`
- `workflows/prd-to-architecture.md`
- `workflows/qa-to-release.md`

## Protocol
1. Identify sensitive data, actors, trust boundaries, and privileged operations.
2. Review auth, authorization, validation, storage, transmission, logging, secrets, dependencies, and integrations.
3. Assign severity: critical, high, medium, low.
4. Recommend mitigation, acceptance, or blocker status.
5. State whether the work may proceed to backlog, development, QA, or release.
6. Record accepted risks with owner and review trigger.

## Risk Model
Use this format:

```text
Risk:
Severity: Critical / High / Medium / Low
Area:
Affected users/data:
Attack or failure scenario:
Impact:
Likelihood:
Mitigation:
Owner:
Status: Blocker / Needs mitigation / Accepted / Resolved
Review trigger:
```

## Security Checklist
- Authentication behavior is defined.
- Authorization rules are explicit.
- Sensitive data is minimized.
- Secrets are not committed or exposed.
- Logs do not leak sensitive data.
- Inputs are validated at boundaries.
- External integrations have failure and abuse handling.
- Dependency risk is understood.
- Release blockers are explicit.

## Output Format
- Security review summary
- Sensitive data and trust boundaries
- Risks with severity
- Required mitigations
- Accepted risks
- Blockers
- Release recommendation

## Quality Gates
- Critical/high risks have mitigation or explicit acceptance.
- Auth/authz behavior is testable.
- Sensitive data flow is documented.
- Release recommendation is unambiguous.

## Stop Conditions
- Secret handling is unclear.
- Sensitive data flow is undocumented.
- Auth or authorization rules are missing.
- Critical risk lacks mitigation or explicit acceptance.

## Example Prompts
```text
Use Security Review to inspect this architecture and implementation summary, classify risks, and decide whether release is blocked.
```
