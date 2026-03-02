# Go Instructions

## Project layout

- Follow the standard Go project layout: `cmd/` for entry points, `internal/` for private packages, `pkg/` for reusable public packages
- Use `internal/` to enforce package boundaries — code in `internal/` cannot be imported by external modules

## Error handling

- Always handle errors explicitly — never ignore returned errors with `_`
- Wrap errors with context: `fmt.Errorf("doing X: %w", err)`
- Define sentinel errors with `var ErrFoo = errors.New("...")` for errors callers need to check
- Use `errors.Is` and `errors.As` for error inspection — not string matching

## Naming

- Use short, descriptive names for variables in narrow scopes; longer names for package-level identifiers
- Exported names are the public API — name them for callers, not implementers
- Acronyms should be all-caps: `userID`, `parseURL`, `httpClient`

## Interfaces

- Define interfaces at the point of use, not at the point of implementation
- Keep interfaces small — single-method interfaces are idiomatic Go
- Accept interfaces, return concrete types

## Concurrency

- Don't start goroutines you can't stop — always have a way to signal shutdown (context cancellation)
- Use `sync.WaitGroup` to wait for goroutines to finish
- Prefer channels for communication; prefer mutexes for shared state protection
- Use `context.Context` as the first parameter of any function that does I/O or may be cancelled

## Testing

- Use table-driven tests with a slice of structs
- Name subtests descriptively: `t.Run("returns error when input is empty", ...)`
- Use `testify/assert` or standard `testing` package — avoid heavy test frameworks
