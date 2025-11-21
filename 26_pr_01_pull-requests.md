# Pull Requests

- Single-commit PR: use `gh pr create --fill` to auto-populate from the commit message.
- Multi-commit PR: manually craft the PR body with `gh pr edit <number> --body "..."`; do not use `--fill` because it only uses the last commit.
- Keep the PR narrative cohesive across all commits and mirror the structured commit template.
- For mixed user-facing and technical changes, center the PR on the user-facing feature and list supporting technical work under additional changes.
- Always share the PR link for review.
