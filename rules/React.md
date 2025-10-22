# React rules

- In React 19, `forwardRef` is no longer necessary. Pass `ref` as a prop instead.
- Never use Context, use **Jotai** for state management.
- Never use `useState` `useEffect` for data fetching and pending management, use libraries, like: **Tanstack/Query**, Urql.

### React useEffect Guidelines

**Before using `useffect`, read:** [You Might Not Need an Effect](https://react.dev/learn/you-might-not-need-an-effect)

Common cases where `useEffect` is NOT needed:
- Transforming data for rendering (use variables or useMemo instead)
- Handling user events (use event handlers instead)
- Resetting state when props change (use key prop or calculate during render)
- Updating state based on props/state changes (calculate during render)

Only use `useEffect` for:
- Synchronizing with external systems (APIs, DOM, third-party libraries)
- Cleanup that must happen when component unmounts
