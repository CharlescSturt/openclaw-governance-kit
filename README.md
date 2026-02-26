# OpenClaw Governance Kit

Composable governance templates for persistent AI agents.

## Why this exists
Teams running persistent agents repeatedly rebuild the same operating documents from scratch, then discover failures in production (unclear authority, no crash recovery, weak handoffs, missing cost discipline). This kit provides a reusable baseline so teams can ship faster with safer defaults.

## Quick start
```bash
npx degit CharlescSturt/openclaw-governance-kit#main my-agent
cd my-agent
```

Then copy `templates/` files into your runtime workspace and fill placeholders.

## What's included
- `templates/AGENTS.md`: startup protocol, crash recovery, session hygiene, action logging, writable-file boundaries.
- `templates/CONTROL.md`: mission, model routing tiers, autonomy tiers, cost guardrails, incident handling.
- `templates/NOPE.md`: non-negotiable forbidden actions and injection defense baseline.
- `templates/INCIDENT.md`: SEV triage flow (contain -> eradicate -> recover -> postmortem).
- `templates/SHARED-OPS.md`: team-level operating contract, runtime map, handoff format.
- `templates/MEMORY-POLICY.md`: active-task discipline, memory hierarchy, size caps, archive policy.
- `templates/SOUL.md`: identity, values, communication style, boundaries.

## Examples
- `examples/single-agent/`: minimal solo-agent governance setup.
- `examples/multi-agent/`: three-agent team baseline (orchestrator/specialist/support).

## Compatibility
Built for OpenClaw workflows and runtime patterns. Adaptable to any agent framework that uses filesystem-based memory and explicit operational contracts.

## License
MIT. See `LICENSE`.
