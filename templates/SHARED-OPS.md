# SHARED-OPS.md

## North Star contract
Find -> Build -> Release -> Market -> Measure -> Repeat.

## Agent roster template
1. Orchestrator: owns planning, queue, release gates.
2. Specialist: owns domain execution (build/content/research).
3. Support: owns monitoring, reporting, and QA.

## Runtime map template
| Agent | Profile | Gateway URL |
|---|---|---|
| orchestrator | default | ws://127.0.0.1:18789 |
| specialist | specialist | ws://127.0.0.1:19789 |
| support | support | ws://127.0.0.1:20789 |

## Coordination map template
| Channel | ID | Purpose |
|---|---|---|
| #general | <id> | operator visibility |
| #ops | <id> | run logs and alerts |
| #handoffs | <id> | agent-to-agent coordination |

## Handoff format
`HANDOFF[<project-or-gap-id>]: <what> | <why> | <priority> | <expected-output>`

## Evidence paths
- tracker: `north-star/implementation-tracker.md`
- blockers: `north-star/program/03-blocker-register.md`
- active builds: `north-star/active-builds/`

## Release minimum
1. README + quickstart.
2. Security notes.
3. Examples.
4. Changelog.
5. Distribution packet (D0/D2/D7/D14).

## Safety baseline
1. No destructive actions without approval.
2. No external publishing without approval gate.
3. No secret exfiltration.
