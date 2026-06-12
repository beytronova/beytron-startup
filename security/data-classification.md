# Data Classification

Use this guide to classify data before architecture, implementation, analytics, or release.

## Public

Information intended for public display.

Examples:

- Marketing copy
- Public product documentation
- Public release notes

Controls:

- Basic integrity review
- No secret handling required

## Internal

Information used by the team but not sensitive to individual users.

Examples:

- Internal roadmap notes
- Non-sensitive architecture decisions
- Operational metrics without user identifiers

Controls:

- Repository access controls
- Avoid public exposure unless approved

## Confidential

Information that may expose business, user, or operational risk.

Examples:

- User email addresses
- Support conversations
- Non-public analytics
- Internal incident notes

Controls:

- Access limited by need
- Avoid unnecessary logging
- Retention policy required

## Sensitive Personal Data

Information that can harm users if exposed.

Examples:

- Financial transaction data
- Payment information
- Government identifiers
- Health data
- Precise location
- Authentication factors

Controls:

- Explicit consent and purpose limitation
- Encryption in transit and at rest
- Strict authorization checks
- Data minimization
- Audit logging without sensitive values
- Retention and deletion plan
- Security review required before development

## Secret

Credentials or material that grants access.

Examples:

- API keys
- OAuth client secrets
- Private keys
- Database passwords
- Signing certificates
- Access tokens

Controls:

- Never store in repo, docs, tickets, prompts, or logs
- Store only in approved secret manager or CI/CD secret store
- Rotate if exposure is suspected
- Use least privilege

## Required Output

```text
Data classification: {public|internal|confidential|sensitive personal data|secret}
Reason: {why}
Controls required: {list}
Blocked until: {missing evidence or approval}
```
