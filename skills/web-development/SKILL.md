# Web Development Skill

Use when implementing approved web application scope.

## Triggers
- User asks to implement, fix, refactor, or test web app behavior.
- An approved Jira ticket targets a web repository.
- UI, API integration, routing, state, or frontend validation work is needed.

## Supported Stacks
- Next.js App Router with React and TypeScript
- React with Vite and TypeScript
- Node.js API routes or BFF code when colocated with the web app
- Tailwind CSS, CSS Modules, styled-components, or the existing design system
- shadcn/ui, Radix, MUI, Chakra, or existing component libraries when already present

## Stack Deep Dives
After detecting the stack, read the matching deep dive when present:

- `skills/web-development/stacks/nextjs.md`
- `skills/web-development/stacks/react-vite.md`

## Primary Languages
- TypeScript for new application code
- JavaScript only when the repository is already JavaScript-first
- CSS/Tailwind for styling
- SQL/schema files only when the approved web scope includes data changes

## Project Structure Rules
- Follow the target repository structure first.
- Prefer feature/module folders for product features.
- Keep reusable UI in `components/` or the local equivalent.
- Keep route/page code thin; move business logic into services, hooks, actions, loaders, or domain modules.
- Keep API clients and data access isolated from presentational components.
- Place tests next to code or in the repository's established test directory.

## Architecture Patterns
- Prefer typed boundaries: props, API responses, form schemas, and domain models.
- Use server/client split intentionally in Next.js.
- Keep server actions, API routes, and client components separated by responsibility.
- Use repository pattern or service layer when data access becomes shared.
- Keep state local unless shared state is required; follow existing Zustand, Redux, React Query, SWR, or Context patterns.

## Coding Rules
- Read target repository `AGENTS.md` before editing.
- Preserve existing framework, routing, styling, state, and test patterns.
- Implement only approved scope.
- Handle loading, empty, error, success, permission, and responsive states where relevant.
- Keep components accessible: semantic HTML, labels, focus states, keyboard support, contrast, and ARIA only when needed.
- Do not add dependencies without explicit justification.
- Do not hardcode secrets, environment-specific URLs, or credentials.

## Validation Commands
Use repository scripts first. Common commands:

```bash
npm run lint
npm run typecheck
npm test
npm run test
npm run build
pnpm lint
pnpm typecheck
pnpm test
pnpm build
yarn lint
yarn test
yarn build
```

## Required Reading
- Target repository `AGENTS.md`
- `roles/web-developer.md`
- `workflows/backlog-to-development.md`
- `handoffs/architecture-to-development.md`
- `governance/coding-standards.md`
- `governance/testing-standards.md`

## Protocol
1. Verify `APPROVED_FOR_DEVELOPMENT`, ticket scope, PRD, architecture, and target repo.
2. Detect stack, package manager, framework, routing, state, styling, and test patterns.
3. Read the matching stack deep dive if available.
4. Implement only approved scope.
5. Cover relevant UI states and accessibility behavior.
6. Run relevant checks or document why they could not run.
7. Produce implementation summary and development-to-QA handoff.

## Output Format
- Stack detected
- Stack deep dive used when applicable
- Package manager detected
- Implementation summary
- Files changed
- Behavior changed
- Tests/checks run
- Tests skipped and why
- Risks
- QA handoff

## Stop Conditions
- Approval is missing.
- Ticket scope is unclear.
- Architecture/API contract is missing.
- Test impact cannot be stated.

## Example Prompts
```text
Use Web Development to implement this approved Jira ticket in the target Next.js repo and prepare QA handoff with tests and risks.
```
