# Compliance Checklist

Use this checklist when a feature handles regulated, sensitive, or user-identifying data.

## Required Checks

- Data classification is complete.
- Purpose of data collection is documented.
- User consent requirements are known.
- Data minimization is applied.
- Retention and deletion plan exists.
- Export/access requirements are known.
- Third-party processors are identified.
- Cross-border data transfer risks are considered.
- Authentication and authorization are documented.
- Sensitive data is encrypted in transit and at rest where required.
- Logs avoid sensitive values.
- Analytics events avoid unnecessary personal data.
- Secrets are stored in approved systems.
- Incident response owner is known.

## Mobile-Specific Checks

- Permissions are requested only when needed.
- Permission purpose is user-visible.
- Platform privacy manifests or declarations are reviewed when applicable.
- Device identifiers are minimized.
- Background activity is documented.

## Block Conditions

Block architecture, development, or release if:

- Sensitive data is unclassified.
- Consent or legal basis is unclear.
- Retention/deletion is undefined.
- Secrets handling is unsafe.
- Authorization model is missing.
- Third-party data sharing is unknown.
- Known high-risk issue lacks owner acceptance.

## Output Format

```text
Compliance checklist: PASS|BLOCKED
Data class: {classification}
Consent: {clear|unclear|not applicable}
Retention: {defined|missing}
Third parties: {listed|missing|none}
Release blockers: {list}
Risk acceptance needed: {yes|no}
```
