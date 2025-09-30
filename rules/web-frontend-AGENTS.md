# React guideline

- In React 19, `forwardRef` is no longer necessary. Pass `ref` as a prop instead.
- Never use Context, use **Jotai** for state management.
- Never use `useState` `useEffect` for data fetching and pending management, use libraries, like: **Tanstack/Query**, Urql.

# HTML

- Never use `<p>`, always use `<div>`


## JS and CSS guidelines

- Tailwind CSS v4 + DaisyUI v5
- Tailwindcss v4 **no longer needs a tailwind.config.js** 
- Use Tailwind CSS classes and custom CSS rules to create polished, responsive, and visually stunning interfaces.
- Never use @apply when writing raw css
- Always manually write your own tailwind-based components instead of using daisyUI for a unique, world-class design
