# Development philosophy
- Prefer simple solutions over clever ones.
- Write code that is clear and self-explanatory.
- Build with the long term in mind.

# Stack
- React
- Tailwind CSS

# Conventions
- Always use functional components. Never use class components.
- Colocate state as close to where it's used as possible. Only lift state when genuinely shared between siblings.
- Use custom hooks to extract reusable logic. Never duplicate stateful logic across components.
- Use controlled components for forms. Never read form values from the DOM directly.
- Fetch data through a dedicated API layer or data-fetching library (e.g. TanStack Query). Never call `fetch` directly inside components.
- Never store derived data in state. Compute it inline or with `useMemo`.
- Use React context sparingly — only for truly global, rarely-changing data (theme, auth). Never use context as a general state manager.
- Always use stable, unique IDs as `key` props in lists. Never use array index as a key for lists that can be reordered, filtered, or modified.
- Always return cleanup functions from effects that create subscriptions, timers, or event listeners.
- Never use `useEffect` for logic that can be computed during render or handled in an event handler.

# Verification
After making changes, always run the following checks and fix any issues before considering work complete:

1. **Lint**: `npm run lint:fix` (ESLint)
2. **Type check**: `npx tsc --noEmit`
3. **Tests**: `npm test`
