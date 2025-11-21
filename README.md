# 📘 AI Development Contract – Shared Rules

This folder contains the **shared AI Development Contract**: a small set of reusable rules and guidelines that help teams and AI agents work consistently across projects.

These rules define **organization-wide defaults** for software development.  
They are meant to be:

- **Human-readable**  
- **AI-friendly**  
- **Lightweight and non-prescriptive**  
- **Overridable at the project level**

Projects may extend or override these rules in their own `local/` contract folder. Tool or platform packs contribute rules in `vendor/`.

---

## 🗂️ Structure Overview

Every contract uses the same top-level layout:

```
aidev-contract/
  shared/   → reusable rules (this folder)
  vendor/   → pack- or platform-specific rules
  local/    → project-specific rules (highest precedence)
```

All files in these folders follow the same naming pattern.  
There are **no nested folders**. Structure comes from filenames.

---

## 🔢 File Naming Pattern

Each rule file uses:

```
AA_group_II_slug.md
```

- `AA` → 2-digit namespace (numeric range)  
- `group` → short stage name (e.g., `analysis`, `implementation`, `qa`, `git`, `pr`)  
- `II` → index inside the group (`01–99`)  
- `slug` → short description in kebab-case

Example:

```
21_implementation_02_error-handling.md
```

---

## 🔢 Numeric Ranges (simplified)

These ranges keep the contract predictable but flexible:

| Range | Meaning                                 |
|-------|------------------------------------------|
| 00–09 | Meta & key rules                         |
| 10–19 | Reserved                                 |
| 20–39 | Recommended stages (analysis, impl, …)   |
| 40–69 | Additional org-defined groups            |
| 70–79 | Experimental / WIP                       |
| 80–99 | Reserved                                 |

You can freely mix shared, vendor, and local rules using the same pattern.

---

## 🧩 Common Groups (Stages)

These are the typical groups used across shared/vendor/local:

- `analysis` – thinking before coding: structure, context, spec prep  
- `implementation` – coding conventions, patterns, API & error handling  
- `refactor` – improving existing code safely  
- `validate` – linting, formatting, static checks  
- `qa` – testing strategy and guidance  
- `git` – commit messages, branching, hooks  
- `pr` – pull request conventions and review rules  
- `meta` – overview and how to use the contract

Examples:

```
20_analysis_01_context-crafting.md
21_implementation_01_style-guide.md
24_qa_01_testing-strategy.md
26_pr_01_review-checklist.md
```

---

## 🤖 How Agents Use This

Subagents or coding agents can be configured to “own” certain numeric namespaces or groups (e.g., `21_implementation_*`, `24_qa_*`).  
They load the applicable files from:

1. `shared/` (base rules)  
2. `vendor/` (pack-specific refinements)  
3. `local/` (project-specific overrides)

This predictable structure makes agent behavior consistent across tools.

---

## ✔️ Summary

- Three scopes: **shared**, **vendor**, **local**  
- Flat file structure (no subfolders)  
- Naming convention: `AA_group_II_slug.md`  
- Numeric ranges give light structure  
- Group names communicate intent to humans and agents  
- Local rules override shared & vendor rules

This README is the minimal orientation needed to understand the shared contract.  
More detailed documentation can be added later (e.g., in a `/docs` folder or a separate repo).
