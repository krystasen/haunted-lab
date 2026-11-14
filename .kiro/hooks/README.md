# Agent hooks — to create in Kiro IDE (Week 2)

Kiro hook configuration lives in the IDE; this file records the two hooks
the submission write-up will cite, so they are created deliberately rather
than invented at write-up time. Do not claim either hook exists until it is
created in Kiro and observed working.

## Hook 1 — test on save

- **Trigger:** a file under the repo is saved.
- **Action:** run the mixing-rule checks (property tests once they exist;
  until then, a syntax check of `index.html`'s script).
- **Purpose:** a broken recipe rule is caught at save time, not at demo time.

## Hook 2 — spec-change reminder

- **Trigger:** any file under `.kiro/specs/haunted-lab/` changes.
- **Action:** remind the agent to update `tasks.md` (check off / add tasks)
  so the spec and the task list never drift apart.
- **Purpose:** keeps the spec-driven workflow visible to the judges.

## How to create them

In Kiro IDE: Agent Hooks → create hook → set the trigger and action above →
verify once (save a file / edit a spec file and confirm the hook fires).
Record the exact hook names in the Kiro usage write-up once created.
