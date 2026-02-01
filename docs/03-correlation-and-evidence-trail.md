# 03 — Correlation and Evidence Trail

## Goal
Turn raw events into a traceable incident narrative with reproducible evidence.

## Correlation Strategy
- group events by:
  - request id
  - session id
  - actor (ip, user id, token hash)
  - endpoint + time window
- build timelines per actor and per endpoint

## Evidence Model
Each finding includes:
- primary evidence events (direct matches)
- supporting evidence events (context)
- derived links (why these events are connected)

## Deterministic Linking Rules (Examples)
- same actor + same endpoint + short time window
- same request id across gateway and application logs
- same payload hash across multiple surfaces

## Noise Reduction
- collapse retries
- merge identical findings within a window
- severity boosts only when multiple independent signals corroborate

## Output
- incident timeline
- per-finding evidence pack
- exportable remediation checklist mapped to affected components
