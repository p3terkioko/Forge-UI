# Forge Frontend — Conventions (Aider entry point)

> This file exists so Aider picks up project conventions automatically.
> The full conventions live in `CONVECTIONS.md` — read that file for the complete rules.
> This file contains the condensed version Aider needs at the start of every session.

---

## Stack

- React 18 + TypeScript strict mode + Vite + Tailwind CSS
- Design tokens in `src/styles/global.css` — never hardcode a hex value or pixel value
- `font-mono` = JetBrains Mono (headings, labels, buttons)
- `font-sans` = Hind Guntur (body text, subtitles)
- API docs at `http://localhost:8000/api/v1/docs`

## What Is Already Built — Do Not Rebuild

- `src/lib/api.ts` — API client. `api.auth.*`, `api.users.*`. Never call `fetch()` anywhere else.
- `src/types/auth.ts` — Auth and user types.
- `src/hooks/useAuth.ts` — Auth context. `useAuth()` returns `{ user, isAuthenticated, isLoading, error, login, logout }`.
- Auth pages complete: `Login`, `Activate`, `ForgotPassword`, `ResetPassword` in `src/pages/`.
- UI components: `Button`, `Input`, `Spinner` in `src/components/ui/`. Check `src/components/README.md` before building.

## Hard Rules

- No `any` types — ever
- No `fetch()` outside `src/lib/api.ts`
- No business logic in components — hooks only
- No hardcoded hex or pixel values — tokens only
- No default exports — named exports only
- Every component handles loading, empty, error, and success states
- Every new component ships with a `.stories.tsx` file
- Mobile-first: 375px base, then `md:` and `lg:` breakpoints
- Wrap async `onSubmit` handlers: `onSubmit={(e) => { void handleSubmit(e) }}`

## File Locations

```
src/components/ui/      Generic reusable components
src/components/forge/   Forge domain components
src/components/layout/  Sidebar, TopBar, PageWrapper
src/hooks/              All custom hooks — business logic lives here
src/lib/api.ts          The only API client
src/types/              TypeScript types per domain (auth.ts, session.ts…)
src/pages/              One file per route
```
