# Scenario: Security Review

## Prompt

```text
Use Beytron Startup.
Current stage: architecture
Review this feature for security: users connect bank transaction data for budgeting predictions.
```

## Expected Route

```text
architecture -> security review -> architecture update
```

## Expected Reads

- `roles/security-reviewer.md`
- `skills/security-review/SKILL.md`
- `governance/security-standards.md`
- `security/data-classification.md`
- `security/secret-handling.md`
- `security/threat-model-template.md`
- `security/compliance-checklist.md`

## Expected Behavior

- Treats bank transaction data as sensitive financial data.
- Requires data classification.
- Requires auth, authorization, encryption, logging, retention, and consent review.
- Produces security findings and required mitigations.
- Does not mark security as safe without evidence.

## Block Conditions

- Data storage, retention, access control, or third-party processor details are unknown.
