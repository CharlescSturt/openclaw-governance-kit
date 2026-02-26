# SHARED-OPS.md

## North Star contract
Find -> Build -> Release -> Market -> Measure -> Repeat.

## Agent roster
1. Orchestrator
2. Specialist
3. Support

## Runtime map
| Agent | Profile | Gateway URL |
|---|---|---|
| orchestrator | default | ws://127.0.0.1:18789 |
| specialist | specialist | ws://127.0.0.1:19789 |
| support | support | ws://127.0.0.1:20789 |

## Channels
| Channel | ID | Purpose |
|---|---|---|
| #general | channel:123 | operator-facing updates |
| #ops | channel:456 | reports and alerts |
| #handoffs | channel:789 | inter-agent handoffs |

## Handoff format
`HANDOFF[gap-id]: what | why | priority | expected-output`
