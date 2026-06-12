# Next.js Stack Deep Dive

Use this when a target web repository is a Next.js application, especially App Router.

## Stack Signals
- `next` dependency exists.
- `app/` directory exists for App Router.
- `pages/` directory exists for Pages Router.
- `next.config.*` exists.

## Primary Language
- TypeScript by default.
- JavaScript only when the repository is JavaScript-first.

## File Structure Rules
- Keep route segments in `app/` focused on routing, layout, metadata, and server/client boundaries.
- Use `components/` for reusable UI.
- Use `features/{feature}/` when the repo uses feature organization.
- Keep server actions in colocated `actions.ts` or established server modules.
- Keep API routes thin and move business logic to services/domain modules.
- Keep data fetching close to the server boundary when possible.

## Server / Client Rules
- Default to Server Components.
- Add `use client` only for interactivity, browser APIs, local state, effects, or client-only libraries.
- Do not pass non-serializable values across server/client boundaries.
- Keep secrets and privileged data access on the server.
- Use route handlers or server actions for mutations according to repository pattern.

## Data and State
- Prefer server data fetching for initial page data.
- Use React Query, SWR, Zustand, Redux, or Context only if already present or justified.
- Validate forms and API boundaries with the existing schema library when available.
- Keep optimistic updates tied to rollback/error handling.

## UI Rules
- Implement loading, empty, error, success, permission, and responsive states.
- Use `loading.tsx`, `error.tsx`, and `not-found.tsx` when appropriate.
- Preserve design system and component library conventions.
- Ensure semantic HTML, labels, focus states, and keyboard behavior.

## Testing
Preferred checks, depending on repository scripts:

```bash
npm run lint
npm run typecheck
npm test
npm run build
pnpm lint
pnpm typecheck
pnpm test
pnpm build
```

## Do Not Do
- Do not turn Server Components into Client Components unnecessarily.
- Do not fetch secrets or privileged data in client components.
- Do not introduce global state for local screen state.
- Do not bypass repository routing or data-fetching conventions.

## Output Notes
When using this stack, report:

- App Router or Pages Router detected
- Server/client boundary changes
- Data fetching or mutation approach
- Build/test commands run
- Risks and QA focus
