# Code Quality

## Formatting
- Run `./mvnw fmt:format` before committing and verify with `./mvnw fmt:check`.
- All code must be properly formatted before opening a PR.

## Code Review Focus
- Watch for duplication and unnecessary complexity.
- Extract constants where values repeat.
- Simplify test setup patterns and remove unnecessary helpers.

## Refactoring
- Refactor continuously to avoid accruing technical debt.
- Prefer modern patterns (e.g., `lenient()` mocks instead of ad-hoc setup helpers).
- Keep methods focused and concise; extract repeated logic.
