---
name: full-send
description: Trigger this if the user says 'full send'. Ship the current change straight to main, with a quick GPT Sol review first only if unsure.
---

# Full Send

The user has authorized merging and pushing this change to `main`. Do not
ask again.

1. Finish the change and run the relevant checks (tests, build, lint).
   Never ship failing checks.
2. Judge your confidence. Confident means the change is understood, checks
   pass, and no open risk remains. If confident, go to step 4.
3. If not confident, resolve the newest GPT Sol model with
   `orchestrator_capabilities` and start one `delegate_task` for a quick,
   read-only review. Brief it with the goal, the diff, and what you are
   unsure about. Fix real findings yourself and rerun the checks. One
   round only. If a serious problem remains, stop and tell the user.
4. Commit, update from the latest `main`, resolve conflicts, rerun checks
   if anything changed, merge into `main` (merge the PR if one exists),
   and push. Never force-push or skip hooks.
5. Report the commit SHA, what shipped, and whether a review ran and what
   it changed.
