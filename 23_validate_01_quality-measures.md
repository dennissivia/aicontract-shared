# Quality Measures

Always run quality checks before any git operation (commit, push).

## Mandatory Checks
1. Format code using the project formatter (e.g., `./mvnw fmt:format`).
2. Run tests: full suite (e.g., `./mvnw verify`, including integration tests if applicable).
3. Verify: all tests must pass and no formatting issues remain.

## When to Run
- After code changes and before staging/committing.
- Before pushing to confirm the local state is clean.
- When reproducing CI failures.

## Why This Matters
- Catches issues early and maintains consistent code style.
- Ensures tests pass before review, preventing broken builds and wasted review time.
- These checks are mandatory parts of the workflow, not optional.
