# Shared AI Contract

This repository hosts shared, cross-project AI development rules. It implements the flat three-namespace standard described in TASK.md and TASK2.md:

- `shared/` — reusable base rules (this repo).
- `vendor/` — platform/plugin-provided rules.
- `local/` — repo-specific overrides in consuming projects.

### Naming and structure
- File naming: `AA_group_II_slug.md`
  - `AA` ranges: `00–09` meta/precedence/overview/glossary; `10–19` reserved; `20–39` analysis/implementation/refactor/validate/qa/git/pr; `40–69` free; `70–79` experimental/WIP; `80–99` future.
  - `group`: meta, analysis, implementation, refactor, validate, qa, git, pr.
  - `II`: index within the AA+group namespace (`01–99`); keep indices stable and pick the next free number.
- No nested folders under `shared/`, `vendor/`, or `local/`; each namespace is flat.
- Precedence: local overrides vendor, which overrides shared.
- When adding rules, keep each file to a single conceptual unit and do not renumber existing files.

### Shared rules in this repo
- `shared/00_meta_01_purpose-and-scope.md`
- `shared/00_meta_02_mandatory-rules.md`
- `shared/00_meta_03_collaborative-workflow.md`
- `shared/00_meta_04_ai-context-maintenance.md`
- `shared/20_analysis_01_technical-decisions.md`
- `shared/21_implementation_01_security.md`
- `shared/21_implementation_02_configuration-and-properties.md`
- `shared/21_implementation_03_dependency-management.md`
- `shared/21_implementation_04_observability-and-monitoring.md`
- `shared/22_refactor_01_code-quality.md`
- `shared/23_validate_01_quality-measures.md`
- `shared/24_qa_01_testing-standards.md`
- `shared/25_git_01_git-workflow.md`
- `shared/25_git_02_commit-messages.md`
- `shared/26_pr_01_pull-requests.md`
