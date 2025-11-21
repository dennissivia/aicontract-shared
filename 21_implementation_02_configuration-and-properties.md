# Configuration and Properties

## Configurable Values
- Use `@Value("${property.name:defaultValue}")` for configurable parameters.
- Prefer constructor injection to keep values testable.
- Configure values when testing and production may reasonably differ (e.g., `rate-limit.capacity=20` in production vs `capacity=3` in tests).
- Do not configure values that should remain the same everywhere.
- Document defaults in code comments and make values easy to override for testing.

## Property Naming
- Use kebab-case such as `rate-limit.capacity`.
- Group related properties by prefix.
- Provide sensible defaults.
