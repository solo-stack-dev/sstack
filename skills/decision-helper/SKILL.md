---
name: decision-helper
description: Trigger this if the user says 'decision helper' or 'decision maker'. Add 'light' for the lighter panel, 'ideas' for the wide idea panel.
---

# Decision Helper

Ask a panel of delegates for independent opinions, then decide with the
user. No scores.

Panel (newest model in each family):

- Default: GPT Sol, GPT Astra, Claude Fable, Claude Opus.
- Light: GPT Sol, GPT Terra, Claude Opus, Claude Sonnet.
- Ideas: GPT Sol, GPT Terra, Claude Opus, Claude Sonnet, the best Gemini
  available, and three to five free OpenCode models. The free models change
  often: pick the best on the current list (new or stealth models are often
  strong, which is why they are free). Fewer is fine; skip Gemini if it is
  not up.
- If the user names members, use those.

Find models with `orchestrator_capabilities` (`search` for missing ones).
Start one `delegate_task` per member in parallel, high effort where the
model has it. Report anyone unavailable; do not substitute.

Same brief for all: the decision, the options (plus "or something else"),
goals, constraints, context, what is ruled out. Not your own leaning.
Read-only work.

Ask for: recommendation, reasoning, main risks, what would change their
mind. Ideas: their best ideas.

Report each by name, then where they agree, where they split and why, and
your view. Ideas: also the best ideas from all members in one list, best
first, each with who had it.
The user decides unless they hand it to you. Second round only on new
information or a sharp split.
