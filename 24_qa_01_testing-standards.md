# Testing Standards

## Test Requirements
- Write comprehensive tests for all new features, covering happy paths and edge cases.
- Include error conditions and boundary values.
- Run all tests before committing or merging: unit tests via `./mvnw test` and integration tests via `./mvnw verify` (bypasses exclusions).
- All tests must pass before merging.

## Test Organization
- Use descriptive test method names such as `testNullIdentifierIsAllowed()`.
- Group related tests logically.
- Use `@BeforeEach` for common setup.
- Use `lenient()` for default mock behaviors in suites with many similar tests.
- Extract constants for repeated test data to stay DRY.

## Test Coverage Goals
- Unit tests for service logic.
- Integration tests for controllers.
- Null/empty input handling.
- Concurrent access for thread-safe code.
