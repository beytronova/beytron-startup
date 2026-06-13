---
name: backend-development
description: Build approved backend work with Node, Nest, Express, FastAPI, API contracts, auth, database migrations, logging, observability, and tests.
---

# Backend Development

Use this skill when an approved ticket targets API, server-side logic, database, auth, integration, jobs, or backend infrastructure.

## Stack Guidance

- Use the repository's existing backend framework first.
- Common stacks: Node.js, NestJS, Express, FastAPI.
- Keep controllers/routes thin.
- Put business rules in services/use cases.
- Keep persistence behind repository/data access boundaries.

## Rules

- Define API request/response contracts.
- Validate input and auth/authorization.
- Treat migrations as release-sensitive.
- Add structured logging for operationally useful events.
- Do not log secrets or sensitive personal data.

## Verification

- Unit tests for business rules.
- Integration tests for API/database behavior.
- Migration rollback notes when applicable.

## Outputs

- Backend implementation plan.
- API contract notes.
- Migration notes.
- Test evidence.
- Operational risk notes.
