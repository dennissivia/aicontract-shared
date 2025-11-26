# Shared `.agents/` (software development workflow)

This repository is the **shared `.agents/` subfolder for software development workflows**. Drop these files into your repo’s `.agents/` (or `.agents/shared/`) folder. The structure follows `docs/AGENTS_CODING_SPEC.md`.

## What Lives Here
- Global rules (communication, scope, safety, context) and a development workflow package for coding-focused repos.
- Numeric prefixes set read order: `00_index.md` dispatches; `01–09` are global; `10–69` are workflow stages.
- `00_index.md` explains precedence and how host repos can add `shared/`, `vendor/`, or `local/` layers.

## Global Files (`01–09`)
- `01_global_01_purpose-and-scope.md` — defines the `.agents/` mission and scope.
- `01_global_02_foundational-rules.md` — absolute rules and the required workflow sequence.
- `01_global_03_communication-guidelines.md` — tone, clarity, pause/feedback expectations.
- `01_global_04_ai-context-maintenance.md` — how to keep instructions current and prioritized.

## Workflow Entry and Stages
- `10_dev_workflow.md` — entrypoint for development tasks; follow phases in order.
- `20–26` series — stage-specific rules: analysis, implementation, refactor, validation/QA, git, PRs.

## Target Layout (when installed)
```
.agents/
  00_index.md
  01_global_01_purpose-and-scope.md
  01_global_02_foundational-rules.md
  01_global_03_communication-guidelines.md
  01_global_04_ai-context-maintenance.md
  10_dev_workflow.md
  20_analysis_01_technical-decisions.md
  21_implementation_01_security.md
  21_implementation_02_configuration-and-properties.md
  21_implementation_03_dependency-management.md
  21_implementation_04_observability-and-monitoring.md
  21_implementation_05_bare_python_project_setup.md
  22_refactor_01_code-quality.md
  23_validate_01_quality-gates.md
  24_qa_01_testing-standards.md
  24_qa_02_testing-standards_spring-boot.md
  25_git_01_git-workflow.md
  25_git_02_commit-messages.md
  26_pr_01_pull-requests.md
docs/
  AGENTS_CODING_SPEC.md  (reference standard)
```

## Numbering Guide
- `00`: dispatcher only (must be loaded first)
- `01–09`: global rules (communication, safety, boundaries, context)
- `10–19`: package indexes (development index present here)
- `20–69`: workflow rules (analysis, implementation, validation, git, PR)
- `70–79`: experimental / WIP
- `80–99`: reserved

## Precedence and Layering
- Read files in lexical order by prefix; `00_index.md` defines the load order, then globals (`01–09`), then workflow packages.
- In host repos with multiple scopes (e.g., `shared/`, `vendor/`, `local/`), the closest `.agents/` folder to the code wins; use `00_index.md` to declare load order.
- Keep `.agents/` tracked in git and avoid renaming/renumbering unless the structure changes; prefer adding new topic files.
- Do not use custom names like `.aicontract`; `.agents/` is the canonical location for AI guidance.
