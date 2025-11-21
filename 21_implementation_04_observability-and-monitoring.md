# Observability and Monitoring

## Metrics
- Add Micrometer metrics for monitoring critical functionality.
- Choose metric types appropriately: counters for events, gauges for current state.
- Use descriptive names such as `rate_limit.requests.allowed` and include descriptions.
- Test metrics in unit tests.

## Logging
- Log important state changes at INFO level.
- Log errors and warnings appropriately and prefer structured logging when possible.
