# AI Instruction Dispatcher

This repository is the **package contents for a `.agents/` folder**. Follow this dispatcher to load rules predictably.

Loading order:
- `00_index.md` is always first and defines precedence.
- Load `01–09` **global** rules next (communication, safety, boundaries, context).
- Then load workflow packages: `10–19` indexes, followed by their `20–69` stage rules.
- `70–79` are experimental; load only if explicitly requested.
- `80–99` are reserved.

Folder precedence (if a host repo adds subfolders like `shared/`, `vendor/`, `local/`):
- Follow the order defined by this dispatcher or any package index; closest `.agents/` to the code wins if scopes overlap.

Authoring guidelines:
- Keep files modular and scoped to a single topic; add new files rather than inflating existing ones.
- Avoid renumbering unless structure changes; prefer appending new numbers within the appropriate block.
- Keep `.agents/` tracked in git; never ignore it.
