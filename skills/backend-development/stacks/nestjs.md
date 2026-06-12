# NestJS Stack Deep Dive

Use this when a target backend repository is a NestJS service.

## Stack Signals
- `@nestjs/core` dependency exists.
- `src/main.ts` bootstraps a Nest application.
- Modules, controllers, and providers are used.

## Primary Language
- TypeScript.

## File Structure Rules
- Keep modules cohesive by domain or feature.
- Controllers handle transport concerns only.
- Services contain business logic.
- Repositories/adapters handle persistence and external systems.
- DTOs define input/output boundary shape.
- Guards, pipes, filters, and interceptors should be used for cross-cutting concerns.

## Architecture Rules
- Validate inputs using DTOs, pipes, or existing validation patterns.
- Keep auth/authz in guards or policy services.
- Keep transactions explicit for multi-step writes.
- Keep external API clients behind providers/adapters.
- Keep configuration in config modules or repository standard.

## Testing
Common checks:

```bash
npm run lint
npm run typecheck
npm test
npm run test:e2e
npm run build
pnpm lint
pnpm typecheck
pnpm test
pnpm build
```

## Do Not Do
- Do not put business logic in controllers.
- Do not bypass guards for protected endpoints.
- Do not change public DTOs without contract and migration notes.
- Do not log secrets or sensitive request bodies.

## Output Notes
When using this stack, report:

- Modules/controllers/providers changed
- DTO/contract changes
- Auth/authz impact
- Migration impact
- Tests/checks run
