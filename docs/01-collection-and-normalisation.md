# 01 — Collection and Normalisation

## Goal
Collect heterogeneous security signals and transform them into a single event model for deterministic analysis.

## Inputs (Examples)
- reverse proxy logs
- application logs
- WAF events
- authentication events
- API gateway logs
- database audit logs

## Collection
- pull-based collectors (scheduled)
- push-based collectors (webhooks / agents)
- strict time sync assumptions (UTC timestamps)
- integrity checks (hashes, sizes, gaps)

## Normalisation
- map raw records into a unified schema:
  - `timestamp`
  - `source`
  - `actor`
  - `request`
  - `endpoint`
  - `status`
  - `signal_type`
  - `payload_hash`
- enforce canonical fields and enum values
- attach trace ids when available

## De-duplication
- dedupe key examples:
  - `(timestamp_bucket, source, request_id, payload_hash)`
- collapse near-duplicates to reduce noise

## Output
- append-only event store for replay
- timeline-ready records for correlation stage
