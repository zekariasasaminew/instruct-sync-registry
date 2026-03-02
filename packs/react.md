# React Instructions

## Components

- Use functional components with hooks exclusively — no class components
- Keep components small and focused on a single responsibility
- Co-locate component files with their styles and tests
- Prefer named exports over default exports

## Hooks

- Extract reusable logic into custom hooks (`use` prefix required)
- Don't call hooks inside conditions, loops, or nested functions
- Use `useCallback` for functions passed as props to memoized children
- Use `useMemo` only when computation is genuinely expensive — don't over-memoize

## State management

- Prefer `useState` and `useReducer` for local state
- Lift state up only as far as necessary
- Use context for state that is truly global (auth, theme) — not as a general state manager
- Colocate state as close as possible to where it is used

## Performance

- Wrap expensive child components with `React.memo` only when profiling shows a need
- Avoid anonymous functions and object literals in JSX props when passed to memoized components
- Use `key` props that are stable and unique — never use array indices as keys when the list can reorder

## Error handling

- Use error boundaries for recoverable UI errors
- Always handle loading and error states in data-fetching components

## Testing

- Test user behaviour, not implementation details
- Prefer `@testing-library/react` over Enzyme
- Avoid testing internal state directly
