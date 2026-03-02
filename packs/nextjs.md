# Next.js Instructions

## App Router

- Use the App Router (`app/`) exclusively — do not mix with Pages Router
- Default to Server Components; add `"use client"` only when you need browser APIs, event listeners, or React state/hooks
- Keep `"use client"` boundaries as deep in the tree as possible

## Data fetching

- Fetch data directly in Server Components using `async/await`
- Use `fetch` with appropriate `cache` and `next.revalidate` options rather than client-side fetching when possible
- Use React's `cache()` to deduplicate requests across a single render pass

## File conventions

- `page.tsx` — route UI
- `layout.tsx` — shared UI that wraps children
- `loading.tsx` — Suspense fallback for the route
- `error.tsx` — error boundary for the route (must be a Client Component)
- `not-found.tsx` — 404 UI
- `route.ts` — API endpoints (replaces `pages/api/`)

## Server Actions

- Use Server Actions for mutations (form submissions, data writes)
- Mark with `"use server"` directive at the top of the function or file
- Validate all inputs on the server — never trust client-provided data
- Return typed results; don't throw errors across the server/client boundary

## Performance

- Use `next/image` for all images — never raw `<img>` tags
- Use `next/font` for fonts to avoid layout shift
- Prefer static rendering (`generateStaticParams`) where content doesn't change per-request

## Environment variables

- Server-only secrets: no `NEXT_PUBLIC_` prefix
- Client-accessible values: `NEXT_PUBLIC_` prefix required
- Validate env vars at startup using a schema (e.g. `zod`)
