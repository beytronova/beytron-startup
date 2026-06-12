# Backend Development Skill

Use when implementing approved backend services, APIs, data models, integrations, jobs, and persistence.

## Triggers
- Approved ticket targets backend, BFF, API, database, auth, jobs, integrations, or persistence.
- User asks to implement or modify server-side behavior.
- Architecture defines API/data contracts that need implementation.

## Supported Stacks
- Node.js with Express, Fastify, NestJS, Next.js route handlers, or project-native server framework
- Python with FastAPI, Flask, Django, or project-native framework
- REST, GraphQL, gRPC, event-driven, queue-based, or scheduled job systems
- PostgreSQL, MySQL, SQLite, MongoDB, Redis, or repository-defined data stores
- Prisma, TypeORM, Sequelize, SQLAlchemy, Alembic, Django migrations, or existing migration system

## Stack Deep Dives
After detecting the stack, read the matching deep dive when present:

- `skills/backend-development/stacks/nestjs.md`
- `skills/backend-development/stacks/fastapi.md`

## Primary Languages
- TypeScript for Node.js backend code when possible
- JavaScript only in JavaScript-first repositories
- Python for Python services
- SQL for queries, migrations, and schema work
- YAML/JSON for infrastructure, config, and OpenAPI specs when relevant

## Project Structure Rules
- Follow the target repository structure first.
- Keep transport/controllers/routes thin.
- Put business logic in services, use cases, command handlers, or domain modules.
- Keep persistence in repositories, data access modules, models, or ORM layers.
- Keep validation schemas close to API boundaries.
- Keep integration clients isolated behind interfaces or adapters.
- Place unit, integration, API, and migration tests according to existing conventions.

## Architecture Patterns
- Use explicit API contracts: request, response, status codes, errors, and validation rules.
- Keep auth/authz checks close to protected boundaries and shared policies.
- Use transactions for multi-step writes that must remain consistent.
- Use idempotency for retries, webhooks, payments, jobs, and external integrations.
- Use migrations for schema changes; never rely on manual database mutation as the only path.
- Include observability: structured logs, metrics, traces, or project-native logging.

## Coding Rules
- Read target repository `AGENTS.md` before editing.
- Implement only approved ticket scope.
- Validate input and normalize output.
- Handle errors intentionally with stable error shapes.
- Do not leak secrets or sensitive data in logs or responses.
- Do not change public contracts without approval and migration notes.
- Do not add dependencies without justification.

## Validation Commands
Use repository commands first. Common commands:

```bash
npm run lint
npm run typecheck
npm test
npm run test
npm run build
pnpm lint
pnpm typecheck
pnpm test
pytest
python -m pytest
alembic upgrade head
prisma migrate dev
prisma migrate deploy
```

## Required Reading
- Target repository `AGENTS.md`
- `roles/backend-developer.md`
- `workflows/backlog-to-development.md`
- `handoffs/architecture-to-development.md`
- `governance/coding-standards.md`
- `governance/security-standards.md`
- `governance/testing-standards.md`

## Protocol
1. Verify `APPROVED_FOR_DEVELOPMENT`, ticket scope, PRD, architecture, and target repo.
2. Detect framework, language, package manager, database, migration tool, and test commands.
3. Read the matching stack deep dive if available.
4. Confirm API/data contracts, auth/authz rules, validation rules, and migration impact.
5. Implement only approved API, service, data, integration, or job scope.
6. Add or update tests and migration notes where relevant.
7. Document release, rollback, observability, and QA impact.

## Output Format
- Stack detected
- Stack deep dive used when applicable
- API/data contract summary
- Implementation summary
- Files changed
- Migration/rollback impact
- Tests/checks run
- Security/privacy notes
- Risks and QA handoff

## Stop Conditions
- Approval is missing.
- Auth/authz rules are unclear.
- Data ownership or migration strategy is unknown.
- Public contract change lacks approval.
- Test or rollback impact cannot be stated.

## Example Prompts
```text
Use Backend Development to implement this approved API ticket with validation, auth checks, migration notes, tests, and QA handoff.
```
