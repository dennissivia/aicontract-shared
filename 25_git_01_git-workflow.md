# Git/GitHub Workflow

## Feature Branches — Mandatory
- Never commit directly to `main` unless explicitly told to for trivial documentation updates.
- Default to feature branches such as `feature/<descriptive-name>` or `fix/<issue-description>`.

## Never Auto-Commit
- Do not start git operations (commit, push, merge) without explicit user confirmation.
- Present the plan first: what will be committed, to which branch, and what happens next.

## Git Operations Flow
1. Ask for confirmation before any git action.
2. Stage files with `git add <files>`.
3. Commit using the structured template (see `130_30_commit-messages.md`).
4. Push to the feature branch (avoid force pushes).
5. Create the PR following `130_20_pull-requests.md` (default: `gh pr create --fill`).

## Git Safety
- Never force push (`git push -f` or `--force`) unless explicitly allowed.
- Always verify the branch name before pushing.
- Run quality measures before any git operation.
