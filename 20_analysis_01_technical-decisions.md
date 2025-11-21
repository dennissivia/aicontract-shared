# Technical Decisions

## Trade-offs Documentation
- Capture trade-offs in commits and code comments: why simple solutions were chosen, when technical debt is acceptable, and future migration paths.
- Explain choices such as in-memory vs distributed approaches and why they fit current needs.

## Example Trade-offs in This Project
- In-memory rate limiting is acceptable because few containers run and state loss on restart is not critical.
- No cross-instance coordination is fine for current scale; can migrate to Redis later if needed.
- Configurable capacity simplifies testing (`3 req/min`) versus production (`20 req/min`).
