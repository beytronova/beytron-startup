# Backend API Golden Path

Use this example when an approved ticket requires API, service, database, integration, or backend behavior changes.

## Example User Prompt

```text
Approval Status = APPROVED_FOR_DEVELOPMENT
Implement BEY-31: create subscription prediction API.
```

## Route

- Stage: development
- Workflow: `workflows/backlog-to-development.md`
- Primary role: Backend Developer
- Supporting roles: Architect, Security Reviewer, QA Developer, DevOps Release
- Primary skill: `skills/backend-development/SKILL.md`

## Required Inputs

- Approved Jira ticket
- API contract or expected request/response
- Data model impact
- Auth and authorization expectations
- Migration requirements
- Observability requirements
- Test expectations

## Step 1: Read Backend Context

Read:

- Target repository `AGENTS.md`
- `roles/backend-developer.md`
- `skills/backend-development/SKILL.md`
- Matching stack deep dive:
  - `skills/backend-development/stacks/nestjs.md`
  - `skills/backend-development/stacks/fastapi.md`
- `governance/security-standards.md`
- `governance/testing-standards.md`

## Step 2: Confirm Contract

Document:

- Endpoint or handler name
- Method and path
- Request schema
- Response schema
- Error responses
- Auth requirements
- Rate limit or abuse constraints
- Backward compatibility concerns

Stop if the contract is missing or ambiguous.

## Step 3: Plan Data Changes

If persistence is required, identify:

- Tables/collections affected
- Migration file
- Indexes
- Seed/test data
- Rollback considerations
- PII or sensitive data handling

Do not make database changes without migration and rollback notes when the stack requires them.

## Step 4: Implement API Slice

Rules:

- Keep controllers/routers thin.
- Put business logic in services/use cases.
- Keep data access in repositories/ORM layer.
- Validate inputs at boundaries.
- Return predictable errors.
- Add structured logs for important failure paths.
- Never log secrets, tokens, credentials, or sensitive personal data.

## Step 5: Test

Minimum checks:

- Unit tests for service/use case logic
- API/handler tests for success and failure paths
- Auth/permission tests when relevant
- Migration tests when supported
- Contract tests when consumers depend on the API

Common commands by stack:

NestJS:

```bash
npm test
npm run lint
npm run build
```

FastAPI:

```bash
pytest
ruff check .
mypy .
```

Use repository-specific commands when available.

## Step 6: Release Notes and QA Handoff

Include:

- API contract summary
- Migration details
- Test evidence
- Monitoring/logging notes
- Rollback notes
- Consumer impact
- Security review result when applicable

## Expected Final Response Shape

```text
Backend path: FastAPI
Ticket: BEY-31
Implemented: POST /subscriptions/predictions, prediction service, repository query, API tests
Verified: pytest, ruff check .
Migration: none
Security: authenticated user scope enforced; no sensitive data logged
QA focus: invalid payload, empty subscriptions, large subscription list
```
