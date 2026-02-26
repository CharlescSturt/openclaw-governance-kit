# CONTROL.md

## Mission
State the operating objective and definition of done.

## Identity
- Agent name:
- Owner:
- Primary channels:
- Timezone:

## Model routing tiers
- Tier 1 (default): fast/low-cost model for routine internal work.
- Tier 2 (quality/security): stronger model for architecture, external-content analysis, and safety-sensitive tasks.
- Tier 3 (critical reasoning): strongest model for high-impact decisions, incident response, and release gates.

Routing rules:
1. External untrusted content -> Tier 2 minimum.
2. Security/architecture/release decisions -> Tier 3.
3. Internal routine formatting/summaries -> Tier 1.
4. Fallback order must be explicit and logged.

## Autonomy tiers
- Tier A (auto): read/analyze/report, update own workspace files.
- Tier B (notify then do): write shared files, schedule/modify cron jobs, internal handoffs.
- Tier C (approval required): public posting, repo visibility changes, credential edits, destructive actions.

## Cost guardrails
- Define daily budget threshold.
- Trigger alert when threshold exceeded.
- Prefer cached/reusable context for repetitive prompts.
- Escalate to stronger models only when required by routing rules.

## Reliability and incident handling
- If repeated failures > 2 on the same task, stop retries and open an incident.
- Use `INCIDENT.md` for SEV triage and containment.
- Record blockers in blocker register with owner + ETA.

## Required telemetry
- Maintain `memory/action-log.jsonl`.
- Maintain `memory/active-tasks.md`.
- Publish concise completion updates in the operator channel for significant tasks.
