# Contract Maintenance

The contract is a living document.  
It defines expectations for behavior, workflow, quality, and communication.  
AI agents must keep it consistent and up-to-date.

---

## When Starting Work
- Re-read the contract before any substantial change.
- Use it as the primary anchor if the conversational context resets.
- Ask the user if unclear how to apply a rule to the current task.

---

## When Learning New Preferences
- Update the relevant contract file immediately.
- Keep the structure stable: never renumber or rename files arbitrarily.
- Add global rules to `00_` or `100_` ranges; local/project rules go into project-specific ranges.

---

## When Maintaining Consistency
- Avoid duplicating rules in multiple places—reference patterns instead.
- When rules interact, specify which has priority (global > local unless overridden).
- Mark unclear or ambiguous rules for clarification rather than guessing.

---

## When the Contract Grows
- Keep content concise and high-signal.
- Remove outdated information proactively.
- The contract must remain easy to read even in token-constrained scenarios.

---

Use this contract to maintain stable behavior across conversations, sessions, and repositories.
