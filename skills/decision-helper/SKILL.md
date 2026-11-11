---
name: decision-helper
description: Trigger this if the user says 'decision helper' or 'decision maker'. Add 'light' for the lighter panel.
---

# Decision Helper

Get independent opinions on a decision from a panel of delegates, then
decide with the user. No scores.

Panel (always the newest model in each family):

- Default: GPT Sol, GPT Astra, Claude Fable, Claude Opus.
- Light: GPT Sol, GPT Terra, Claude Opus, Claude Sonnet.
- If the user names members, use those.

Resolve models with `orchestrator_capabilities` (use `search` for a family
missing from the short list), then start one `delegate_task` per member in
parallel at high effort. If a member is unavailable, report it; do not
substitute.

Send every member the same brief: the decision, the options (plus "or
something else"), goals, constraints, relevant context, and what is ruled
out. Leave out your own leaning. Keep their work read-only.

Ask each for their recommendation, reasoning, main risks, and what would
change their mind.

Report each opinion by name, then where they agree, where they disagree
and why, and your own view. The user makes the final call unless they hand
it to you. Offer a second round only if the user adds new information or
the panel splits sharply.
