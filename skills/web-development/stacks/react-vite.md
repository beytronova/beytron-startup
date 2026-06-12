# React Vite Stack Deep Dive

Use this when a target web repository is a React application built with Vite.

## Stack Signals
- `vite` dependency exists.
- `vite.config.*` exists.
- `src/main.tsx` or `src/main.jsx` exists.
- Routing is client-side, usually with React Router or a local router.

## Primary Language
- TypeScript by default.
- JavaScript only when the repository is JavaScript-first.

## File Structure Rules
- Keep app bootstrap in `src/main.*` and root shell in `src/App.*` or repository equivalent.
- Put reusable UI in `src/components/`.
- Put feature code in `src/features/{feature}/` when feature structure exists.
- Keep hooks in `hooks/` or feature-local files.
- Keep API clients in `api/`, `services/`, or feature data modules.
- Keep tests next to code or under `__tests__` according to repo convention.

## Architecture Rules
- Keep components presentational when possible.
- Move business logic to hooks, services, or domain modules.
- Use React Router patterns already present.
- Use React Query/SWR/Zustand/Redux/Context only when already used or justified.
- Keep environment variables behind Vite `import.meta.env` conventions.

## UI Rules
- Handle loading, empty, error, success, permission, and responsive states.
- Use accessible forms, labels, focus states, and keyboard behavior.
- Avoid layout shifts caused by late-loading state.

## Testing
Common checks:

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
```

## Do Not Do
- Do not put API credentials in browser-exposed env vars.
- Do not add global state for local UI state.
- Do not introduce routing, styling, or state libraries without justification.

## Output Notes
When using this stack, report:

- Vite and router detected
- State/data approach
- UI states covered
- Build/test commands run
- Risks and QA focus
