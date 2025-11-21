# Testing Standards – Java / Spring Boot

These rules extend the generic testing standards for Java / Spring Boot projects using Maven.

## Test Layers and Expectations

### Unit Tests
- Write unit tests for **all core business logic** (services, domain classes, utility functions).
- Prefer plain JUnit 5 + mocking libraries (e.g., Mockito) **without** starting a Spring context where possible.
- Keep unit tests fast and focused on a single class or behavior.

### Slice and Integration Tests
- Use Spring’s test slices to target specific layers:
  - `@WebMvcTest` for controller/web layer tests.
  - `@DataJpaTest` for JPA repositories and persistence logic.
- Use `@SpringBootTest` (optionally with `webEnvironment = RANDOM_PORT`) for full integration tests that exercise the application end-to-end.
- Tests should cover:
  - controller request/response behavior
  - validation and error handling
  - persistence behavior and transaction boundaries
  - configuration and wiring for critical flows

### Tagging and Speed
- Mark slow or environment-dependent tests with `@Tag("integration")` to keep unit runs fast.
- Quality gates require the full suite (unit + integration) before any git action.

## How to Run Tests

### Default Commands
- Fast/unit-only (excludes `@Tag("integration")` via the Maven property):

  ```bash
  ./mvnw test
  ```

- Full suite (unit + integration) with environment/services running:

  ```bash
  ./bin/run-tests-local.bash
  # or, after services are up:
  ./mvnw clean test -Dexcluded.groups=""
  ```

### Environment for Integration Tests
- Ensure `.env` is loaded (e.g., `set -o allexport && source .env && set +o allexport`).
- Ensure `docker compose up -d --wait` is running so dependencies (e.g., Postgres) are available.
- `./bin/run-tests-local.bash` handles both of these before running the full suite.
