# Commit Messages

Use structured commit messages for feature work. Keep dependency updates simple unless the update enables a new feature.

## Critical Rules
1. Always start with a fitting emoji.
2. Be concise—readable in 30 seconds or less.
3. Focus on why, not what; the diff shows the implementation.
4. Follow the template structure without extra sections.
5. Lead with user value; put supporting work under "Additional changes" when needed.

## Template
```markdown
<emoji> <short description>

## Summary
<One sentence: what we implemented>

## Problem
<1-2 sentences: why we needed this>

## Solution
<2-3 sentences: how we implemented it, key decisions, why this approach>

## Additional changes (optional)
<Use when mixing user-facing features with tech improvements>
<List supporting changes: docs, CI, refactoring, tooling>
<Keep user-facing feature as main focus above>

## Quality
- <Testing: X tests, all passing>
- <Key verification steps>

## Future improvements
- <Next steps or known limitations>
```

## Emoji Guidelines
- 🚀 New features or major improvements
- 🔒 Security improvements
- 🐛 Bug fixes
- ⚡ Performance improvements
- ♻️ Refactoring
- 📊 Metrics/observability
- 🎨 Code formatting/style
- 📝 Documentation
- ⬆️ Dependency upgrades
- 🔧 Configuration changes
- ✅ Tests

## Anti-Patterns to Avoid
- Being too verbose or listing every file changed.
- Repeating what git already shows (e.g., "Added X method").
- Missing the "why" by only describing implementation steps.
- Adding extra sections not in the template or a technical play-by-play.

## Good Examples
```
🔒 Delete OAuth tokens on app uninstall

## Summary
Deletes revoked tokens immediately when workspace uninstalls app.

## Problem
Retained revoked tokens in database without audit trail.

## Solution
Modified handleAppUninstalledEvent to delete by team_id and log count. 
Safe because Slack revokes tokens before event fires.

## Quality
- 2 unit tests (happy path + edge case)
- All 50 tests passing

## Future improvements
- Phase 2: Grace period for workspace data (ADR 6)
```
```
🔒 Add rate limiting with Bucket4j

## Summary
Added IP-based rate limiting to prevent installation abuse.

## Problem
No protection against automated installation attacks.

## Solution
Used Bucket4j with in-memory storage (20 req/min). Chose simplicity over 
distributed coordination since state loss on restart is acceptable.

## Quality
- 10 unit tests covering edge cases
- Metrics added for monitoring

## Future improvements
- Migrate to Redis if multi-instance coordination needed
```

## Documentation-Only Changes
- Use simple commit messages for documentation-only updates (markdown files, ADRs, README).
- Example: `📝 Update ADR 6 with CommandLineRunner approach`.
- Use the structured template only when documentation accompanies a larger feature.
- Let the document content speak for itself; do not repeat it in the commit message.
