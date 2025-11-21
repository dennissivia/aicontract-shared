# Testing Standards

Testing ensures correctness, protects refactoring, and prevents regressions.

## Test Requirements
- Add or update tests for all new features and significant changes, covering:
  - happy paths
  - edge cases
  - error conditions and boundary values
- Run all available test suites before committing or merging:
  - unit tests
  - integration tests
  - end-to-end or system tests where applicable
- All tests must pass before merging or asking for review.

## Test Organization
- Use descriptive test names that explain the intent and expected behavior.
- Group related tests logically and share setup/fixtures where appropriate.
- Prefer clear, minimal setup over deeply nested or overly clever test utilities.
- Extract constants for repeated test data to avoid duplication and improve readability.

## Test Coverage Goals
- Unit tests for core business logic (services, domain functions, core modules).
- Integration tests for public interfaces and I/O boundaries 
  (e.g., HTTP controllers/handlers, APIs, messaging endpoints, CLIs).
- Explicit tests for null/empty/invalid inputs and error paths.
- Tests for concurrent or multi-access scenarios where shared state or thread/async safety matters.

## Behavior for AI Agents
- Follow existing testing patterns, frameworks, and file structure used in the repository.
- Do not introduce new testing libraries or frameworks unless explicitly requested.
- Do not skip, disable, weaken, or work around tests to force a green build.
- If the test tooling reports tests as **skipped/ignored by default** (e.g., slow or integration suites), and it is feasible to run them, run the full suite at least once before considering the work done, or explicitly call out why they could not be run.
- If tests fail or cannot be executed due to environment/tooling issues, stop and ask the user for guidance instead of guessing or bypassing.