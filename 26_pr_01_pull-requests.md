
---

## 🧩 `26_pr_01_pull-requests.md` (updated)

```md
# Pull Requests

Pull requests are the final narrative of a change set. They should be cohesive, reviewable, and aligned with the commit history.

## Creating PRs
- **Single-commit PR**:
  - Use `gh pr create --fill` to auto-populate from the commit message.
- **Multi-commit PR**:
  - Do **not** use `--fill` (it only uses the last commit).
  - Manually craft the PR body using `gh pr edit <number> --body "..."`, mirroring the structured commit template.

## PR Content
- Keep the PR narrative cohesive across all commits:
  - What problem are we solving?
  - What is the overall solution?
  - What are the key trade-offs or risks?
- For mixed user-facing and technical changes:
  - Center the PR on the user-facing feature.
  - List supporting technical work under an “Additional changes” or similar section.

## Preconditions Before Opening a PR
- Quality gates have been run and are passing:
  - formatter/linter
  - tests (unit, integration, end-to-end where applicable)
- The branch contains only intended changes; no stray or debug files.
- Commit messages follow the structured template and correctly describe the work.
- The branch is based on the appropriate target branch (typically `main`) and up to date as agreed for the project.

## Safety Rules
- Do not open a PR with known failing tests or lint issues unless the PR is explicitly about fixing them—and call this out clearly.
- Do not force push (`--force`) or perform history rewrites on the PR branch unless explicitly instructed by the user.
- If CI fails:
  - Investigate and summarize the failure.
  - Fix it if it is clearly related to your changes.
  - If it appears unrelated or environment-specific, highlight this and ask how to proceed.

## Keeping PRs in Sync
- Ensure the PR body reflects the **final** state of the branch, not an earlier intermediate state:
  - Update the PR description if the approach changes during development.
  - Remove references to experiments or directions that were abandoned.
- When adding new commits that change behavior, re-check whether the PR description needs updating.

## Communication
- After creating or updating a PR, share the PR link and a short summary:
  - what it does,
  - what needs review,
  - anything that reviewers should pay special attention to (e.g., risky areas, migrations).
- Be explicit about what has been tested and what is still uncertain.
