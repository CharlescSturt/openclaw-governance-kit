# AGENTS.md

Load `SHARED-OPS.md` first before any other startup file.

## Mission
Define the agent's job clearly in one line.

## Startup protocol (mandatory)
1. Read `SHARED-OPS.md` first.
2. Read `memory/active-tasks.md` immediately. Resume incomplete tasks from file state before starting new work.
3. Read `CONTROL.md`, `SOUL.md`, then `memory/YYYY-MM-DD.md` (today + yesterday).
4. Load `USER.md` and `MEMORY.md` only in trusted/private contexts.

## Session hygiene
- If any session file exceeds 2 MB, archive it in `memory/archive/` and continue in a fresh session.
- If active session context exceeds 5 MB, alert the operator in your ops channel.
- Keep `memory/active-tasks.md` under 2 KB.

## Crash recovery rules
- On task START: write task details to `memory/active-tasks.md`.
- On sub-agent SPAWN: write task + reason + pending session key.
- After spawn: replace pending key with real session key.
- On task COMPLETE/FAIL: update the same line with status and next step.
- On RESTART: read `memory/active-tasks.md` first and resume autonomously.

## Structured action log
For substantive tasks (not heartbeats/health checks), append one JSON line to `memory/action-log.jsonl`:

```json
{"ts":"ISO","task":"short description","model":"model-used","tools":["tool1"],"cost_est":"$X.XX","status":"ok|fail","gap_id":"GAP-XXX or null"}
```

## Writable files (whitelist)
Only modify these without explicit approval:
- `memory/` (all files)
- `STATUS.md`
- `PROJECTS-ACTIVE.md`, `PROJECTS-PIPELINE.md`
- files inside active project directories
- files explicitly requested by the operator

Edits to `CONTROL.md`, `AGENTS.md`, `SOUL.md`, `TOOLS.md`, `IDENTITY.md`, or credentials require operator approval.

## Safety
- Never reveal secrets or credentials.
- Never run destructive commands without explicit approval.
- If external publishing is not explicitly approved, draft only.
