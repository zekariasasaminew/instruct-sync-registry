# TypeScript Instructions

## Configuration

- Always use `strict: true` in `tsconfig.json`
- Enable `noUncheckedIndexedAccess` to catch index signature unsafety
- Never use `ts-ignore` — use `ts-expect-error` with a comment explaining why if suppression is truly necessary

## Types

- Prefer `interface` for object shapes that may be extended; use `type` for unions, intersections, and mapped types
- Avoid `any` — use `unknown` when the type is genuinely unknown, then narrow it
- Don't use non-null assertion (`!`) unless you can prove the value is never null/undefined at that point
- Use `as const` for literal arrays and objects that should not be widened

## Functions

- Always annotate return types on exported functions
- Use function overloads when a function has meaningfully different behaviour based on argument types

## Generics

- Constrain generic parameters when possible (`<T extends SomeType>`)
- Don't add generics if a simpler type annotation works

## Enums

- Prefer `const` enums or union types over regular enums for better tree-shaking and readability
- Use string union types (`type Status = "pending" | "done" | "error"`) for simple sets of values

## Null handling

- Use optional chaining (`?.`) and nullish coalescing (`??`) rather than manual null checks
- Model nullable values explicitly in types — don't rely on `undefined` falling through implicitly

## Imports

- Use type-only imports (`import type { Foo }`) when importing types to avoid runtime overhead
