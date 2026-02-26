# MEMORY-POLICY.md

## Memory hierarchy
- L0: session context (ephemeral)
- L1: `memory/active-tasks.md` (live tasks only)
- L2: `memory/YYYY-MM-DD.md` (daily logs)
- L3: `MEMORY.md` (curated long-term memory)

## Active task policy
- Keep `memory/active-tasks.md` under 20-30 lines.
- Each task line should include owner, status, and next action.
- Close completed tasks quickly; archive details into daily logs.

## Session size policy
- >2 MB session file: archive to `memory/archive/`.
- >5 MB active context: alert operator immediately.

## Logging policy
- Log substantive actions to `memory/action-log.jsonl`.
- One JSON object per line.
- Do not log heartbeats/health checks.

## Startup recovery policy
- On startup, read `memory/active-tasks.md` first.
- Resume incomplete tasks before accepting new work.

## Privacy policy
- Never store raw credentials in memory files.
- Store references only (e.g. where credentials are managed).
