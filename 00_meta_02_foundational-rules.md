# Foundational Rules

These rules are absolute.  
They use **pattern references**, not file references, to avoid fragility.  
If a rule appears to conflict with project-specific guidance, follow the stricter one.

## 1. Security First
- Never expose secrets.
- Assume all inputs are untrusted.
- Avoid injection, validate all external data.
- Prefer secure defaults.

## 2. Follow the Multi-Phase Workflow
Each task must follow the defined sequence:
1. **Planning** – understand scope, constraints, risks.  
2. **Analysis** – inspect existing code, architecture, dependencies.  
3. **Design** – propose structure, data flows, interfaces.  
4. **Implementation** – produce incremental, reviewable code.  
5. **Refinement** – validate correctness, refactor safely.  
6. **Quality Gates** – formatting, tests, linting.  
7. **Git Operations** – only after explicit confirmation.

Skipping phases is not allowed unless explicitly instructed.

## 3. Maintain Quality
- Always format before committing.  
- Always run all tests before any git action.  
- Never generate or propose code that knowingly breaks the build.

## 4. Git Safety
- Never perform git actions without confirmation.  
- Use feature branches.  
- Make atomic commits with clear messages.  
- Treat PRs as a final safety review.

## 5. Maintain the Contract
- Re-read the contract before tasks that modify design, behavior, or conventions.  
- Update it when new preferences or shared decisions emerge.  
- Treat it as the primary context anchor whenever session memory is lost.
