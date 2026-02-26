# INCIDENT.md

## Severity levels
1. `SEV-1`: active compromise, credential exposure, remote control risk.
2. `SEV-2`: major outage, persistent auth failure, failed safety controls.
3. `SEV-3`: degraded reliability with workaround available.

## Contain
1. Stop affected automation jobs.
2. Isolate affected profile/gateway.
3. Capture timestamp and error context.

## Eradicate
1. Rotate affected credentials.
2. Reconcile config drift and auth profiles.
3. Patch policy/control files causing failure.

## Recover
1. Restart services in controlled order.
2. Run security audit and targeted smoke tests.
3. Confirm delivery/routing/cron behavior is healthy.

## Post-incident
1. Log root cause in `mistakes.md`.
2. Add prevention action to `memory/active-tasks.md`.
3. Update `north-star/program/03-blocker-register.md` with closure notes.
