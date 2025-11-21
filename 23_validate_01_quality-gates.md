# Quality Gates

Quality checks ensure that changes are safe, consistent, and ready for review. 
They must be run before any git operation (commit, push, PR).

## What to Run
1. Format code using the project’s formatter or linting rules.
2. Run the full test suite (unit + integration/end-to-end if available).
3. Confirm the working tree is clean and no unintended changes were introduced.

## Behavior During Validation
- Treat failing tests or lint errors as blockers; fix them before proceeding.
- Do not modify, skip, disable, rewrite, or work around tests to force a green build.
- If tests cannot be executed (missing tools, broken environment, unclear output), **stop immediately and ask the user for help** rather than guessing or bypassing.
- If tests or formatters do not exist, state this explicitly rather than inventing tools or commands.
- When the output is unclear or surprising, pause and request clarification.

## When to Run
- After implementing or refactoring code.
- Before staging, committing, or pushing.
- When investigating CI failures or unexpected diffs.

## Good Practice
- Keep changes small so quality gates reveal issues early.
- If a failure appears unrelated to your changes, highlight it rather than masking it.
- Use tests to confirm behavior is unchanged during refactoring.
- When in doubt about how to resolve a failing check, ask for confirmation.

The goal is to ensure changes are correct, consistent, and aligned with the project’s standards—without shortcuts or bypasses.
