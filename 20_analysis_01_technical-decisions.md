# Technical Decisions

## Trade-offs Documentation
- Capture trade-offs in commits and code comments: why simple solutions were chosen, when technical debt is acceptable, and future migration paths.
- Explain choices such as in-memory vs distributed approaches and why they fit current needs.

## Example Trade-offs (patterns to consider)
- In-memory state can be acceptable at small scale when restart loss is tolerable; move to shared/distributed storage as coordination needs grow.
- Avoid cross-instance coordination until scale requires it; design a path to migrate if/when needed.
- Use configuration to tune limits per environment (e.g., lower limits in tests, higher in production).
