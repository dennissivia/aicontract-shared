# Commit Messages

Commit messages are a core part of the development workflow.  
They are written **for humans**, not machines.  
A good commit message provides clarity, intent, reasoning, and readability.

Use the structured template for all substantive feature work, fixes, and improvements.  
Keep documentation-only updates simple and focused.

---

## Critical Rules
1. **Always start with a fitting emoji.**  
   It visually conveys the type of change and increases scan-ability.

2. **Write for human readers**—reviewers today and future contributors tomorrow.  
   The message must be easy to understand without reading the diff or knowing the conversation.

3. **Explain the goal, the why, and the reasoning.**  
   The diff shows the *what*. The commit message explains the *motivation* and *decisions*.

4. **Stay structured and concise.**  
   Follow the template exactly. No extra sections; no noise or verbose play-by-play.

5. **Lead with user value.**  
   When technical changes accompany a feature, keep the user-facing purpose at the top.

6. **Use short paragraphs and readable sentences.**  
   The message must be digestible in ~30 seconds.

7. **Never include:**
   - debug notes  
   - exploration steps  
   - implementation details evident from the diff  
   - internal monologue  
   - overly technical or low-signal text

---

## Narrative Requirements (Critical)

A high-quality commit message body **must**:

- Describe the **goal** of the change. What is the purpose?
- Explain **why** the change was needed. What problem or gap existed?
- Summarize the key **trade-offs**, considerations, and decisions involved.
- Provide context so a reviewer or future contributor understands intent quickly.
- Be **reader-friendly**: short paragraphs, clear reasoning, no jargon unless necessary.
- Stand on its own—someone reading the commit without the PR or conversation should understand the intent.

Low-quality, non-narrative commit messages must never be produced.

---

## Template

```markdown
<emoji> <short description>

## Summary
<One sentence: what we implemented>

## Problem
<1–2 sentences: why this was needed; what gap or issue existed>

## Solution
<2–3 sentences: how we approached it, key decisions, trade-offs>

## Additional changes (optional)
<Use when mixing user-facing features with supporting technical tasks>
<List supportive work: docs, CI, refactoring, tooling>
<Keep user-facing feature as the main narrative above>

## Quality
- <Which tests ran? All passing?>
- <Any verification steps?>

## Future improvements
- <Next steps, follow-ups, remaining limitations>
