# 05 — Reliability and Safety Controls

## Reliability Goals
- replayable runs from the same input logs
- stable rule evaluation with versioning
- safe execution during incidents

## Controls
- append-only event store
- immutable run ids and timestamps
- rule version pinning per run
- idempotent finding updates

## Guardrails
- target allowlists
- rate limiting for active probes
- maximum request budgets
- read-only mode by default

## Data Handling
- redact sensitive values in reports
- store hashes for tokens instead of plaintext
- least-privilege access to evidence packs

## Failure Modes
- missing log sources → mark run as partial and list gaps
- time drift → detect and correct with reference clocks
- noisy inputs → adaptive dedupe windows

## Outcome
A repeatable forensic workflow that produces traceable findings without unsafe probing.
