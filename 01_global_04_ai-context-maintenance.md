# `.agents/` Maintenance (Global)

The `.agents/` rules are a living system that defines expectations for behavior, workflow, quality, and communication. AI agents must keep it consistent and up to date.

---

## When Starting Work
- Re-read `.agents/` before any substantial change.
- Use it as the primary anchor if the conversational context resets.
- Ask the user if unclear how to apply a rule to the current task.

---

## When Learning New Preferences
- Update the relevant `.agents/` file immediately.
- Keep the numeric structure stable: add new files instead of renumbering existing ones.
- If scopes diverge (shared/vendor/local), document precedence in `00_index.md`.

---

## When Maintaining Consistency
- Avoid duplicating rules in multiple places—reference patterns instead.
- When rules interact, specify which has priority (dispatcher guidance or closest file wins).
- Mark unclear or ambiguous rules for clarification rather than guessing.

---

## When the Rules Grow
- Keep content concise and high-signal.
- Remove outdated information proactively.
- `.agents/` must remain easy to read even in token-constrained scenarios.

---

Use these rules to maintain stable behavior across conversations, sessions, and repositories.
