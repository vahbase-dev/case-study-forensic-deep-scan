# 04 — Reporting and Remediation

## Goal
Produce an actionable report that engineering teams can execute immediately.

## Report Structure
- executive summary
- scope and data sources
- timeline of key events
- findings (grouped by severity)
- affected endpoints and components
- recommended fixes and verification steps

## Remediation Mapping
Each finding maps to:
- root cause hypothesis
- fix steps
- validation steps
- rollback / mitigation option

## Examples (Conceptual)
- SQLi risk → parameterised queries + input validation + WAF rule
- XSS risk → output encoding + CSP hardening
- PII leak → response filtering + log scrubbing + access controls
- auth abuse → rate limits + MFA + token rotation

## Verification
- re-run scan with same rule versions
- confirm finding transitions to `closed`
- store before/after evidence snapshots
