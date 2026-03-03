# AI Agent Instructions

General coding best practices for all AI agents (Copilot, Cursor, Claude, Windsurf, Cline).

## Code Quality

- Prefer explicit, readable code over clever one-liners
- Use meaningful variable and function names that describe intent
- Keep functions small and focused on a single responsibility
- Prefer immutability — use `const`, avoid mutating function arguments
- Handle errors explicitly — never swallow exceptions silently

## Comments

- Comment *why*, not *what* — the code explains what, comments explain why
- Only add comments when the logic is non-obvious
- Keep comments short and current — outdated comments are worse than none

## Testing

- Write tests for all non-trivial logic
- Test edge cases and error paths, not just the happy path
- Tests should be deterministic — no random data, no time-dependent logic
- Prefer small, focused tests over large integration tests

## Git

- Write commit messages in the imperative mood: "Add feature" not "Added feature"
- Keep commits small and focused on one change
- Don't commit commented-out code, debug logs, or TODO notes

## Security

- Never hardcode secrets, tokens, or credentials in source code
- Validate and sanitize all external input (user input, API responses, env vars)
- Use parameterized queries — never interpolate user input into SQL strings
- Keep dependencies up to date; audit regularly

## Dependencies

- Prefer the standard library when it's sufficient
- Evaluate new dependencies carefully — check maintenance status, license, and bundle size
- Pin exact versions in lockfiles
