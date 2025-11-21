# Collaborative Workflow

End-to-end development process from feature implementation to pull request.

## Phase 1: Feature Development
- Implement required functionality with incremental, reviewable changes.
- Test as you go to make steady, verifiable progress.

## Phase 2: Quality Measures
- Run required checks before any git operation: format with the project formatter (e.g., `./mvnw fmt:format`) and run the full test suite (e.g., `./mvnw verify`); ensure all pass (details in `120_10_quality-measures.md`).

## Phase 3: Git Operations (Confirmation Required)
- Stop and ask for confirmation before any git action.
- Follow the Git/GitHub workflow contracts in the `130_XX` files.
- Never skip quality measures; they are mandatory safety gates.
