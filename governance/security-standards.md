# Security Standards

## Core Rules

- Do not commit secrets.
- Document sensitive data flows.
- Validate authentication and authorization rules.
- Minimize collected data.
- Review dependencies and integrations for risk.
- Record accepted risks explicitly.

## Security Review Triggers

Security Reviewer must be involved when work includes:

- Authentication or authorization
- Payments or financial data
- Personal, sensitive, or regulated data
- File upload or user-generated content
- External integrations or webhooks
- Secrets, environment variables, or deployment config
- Data migration or deletion
- Admin tools or permission changes

## Risk Severity

- Critical: exploitable data loss, privilege escalation, credential exposure, or release-blocking vulnerability.
- High: likely security or privacy failure with meaningful user/business impact.
- Medium: plausible issue with limited impact or mitigation.
- Low: minor hardening or documentation concern.

## Required Review Output

- Sensitive data involved
- Trust boundaries
- Auth/authz behavior
- Secret handling
- Dependency/integration risks
- Severity
- Mitigation
- Risk acceptance owner when not fixed

## Stop Conditions

- Secret handling is unclear.
- Sensitive data flow is undocumented.
- Auth or authorization rules are missing.
- Critical or high risk lacks mitigation or explicit acceptance.
