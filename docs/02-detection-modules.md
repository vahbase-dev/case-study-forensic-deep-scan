# 02 — Detection Modules

## Goal
Identify high-signal security issues using deterministic rules and reproducible checks.

## Module Types (Conceptual)
- **SQLi probes:** payload signatures, error pattern matches, anomalous query shapes
- **XSS probes:** reflected payload markers, suspicious script contexts
- **Header anomalies:** origin spoofing, host mismatch, cache poisoning indicators
- **Auth abuse:** credential stuffing patterns, token replay, impossible travel signals
- **PII leak detection:** sensitive field discovery in responses and logs

## Rule Engine
- versioned rules with stable ids
- each finding includes:
  - rule id
  - matched evidence
  - severity
  - confidence score (rule-based, not ML)

## PII Classification (Examples)
- email address patterns
- phone number patterns
- national id / gov id patterns (region-specific)
- API keys / tokens
- password-like fields in plaintext

## Safety Controls
- strict allowlists for active probing targets
- request caps and rate limits
- read-only mode for incident-time scans

## Output
- findings emitted as:
  - `finding.created`
  - `finding.updated`
  - `finding.closed`
- all findings link back to evidence events
