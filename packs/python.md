# Python Instructions

## Style

- Follow PEP 8 for formatting; use a formatter (black or ruff) to enforce it automatically
- Maximum line length: 88 characters (black default)
- Use type hints on all function signatures — parameters and return types

## Type hints

- Use `from __future__ import annotations` for forward references
- Prefer `X | None` over `Optional[X]` (Python 3.10+)
- Use `list[str]` not `List[str]`, `dict[str, int]` not `Dict[str, int]` (Python 3.9+)
- Use `TypeAlias` for complex type aliases

## Functions and classes

- Keep functions short and focused on one task
- Use dataclasses or Pydantic models for structured data — avoid raw dicts for complex data
- Use `@classmethod` and `@staticmethod` appropriately; don't use them as a substitute for module-level functions

## Error handling

- Use specific exception types — never catch bare `except:`
- Create custom exception classes for domain errors
- Use `contextlib.suppress` for intentionally swallowed exceptions

## Async

- Use `async/await` with `asyncio` for I/O-bound work
- Don't mix sync and async code without explicit bridging (`asyncio.to_thread`)
- Use `asyncio.gather` for concurrent tasks, not sequential `await` calls

## Imports

- One import per line
- Order: standard library → third-party → local (enforced by isort/ruff)
- Avoid wildcard imports (`from module import *`)

## Testing

- Use `pytest` with fixtures for test setup
- Name test functions `test_<what_it_does>` not `test_<method_name>`
- Parametrize tests with `@pytest.mark.parametrize` instead of loops
