---
name: Create and update FHIR resources with optimistic concurrency
description: Safely create (idempotently) and update FHIR resources on 1upHealth using If-None-Exist and If-Match/ETag.
api: fhir/1uphealth-fhir-r4-capabilitystatement.json
operations: [create, update, vread]
auth: SMART-on-FHIR OAuth 2.0 (Bearer)
---

# Write FHIR resources safely on 1upHealth

Every resource on the 1up FHIR R4 server declares `versioning: versioned-update`, so
writes participate in optimistic concurrency. Use this to avoid duplicates and lost
updates.

## Steps

1. **Get a token** with a write scope (e.g. `system/Observation.write`).

2. **Idempotent create** (`create`): `POST /fhir/r4/{ResourceType}` with the resource
   body. To dedupe by natural key, send `If-None-Exist: <search-params>` — if a match
   exists the server returns it instead of creating a duplicate (`200`), otherwise it
   creates (`201`). The response `ETag` carries the new `versionId`.

3. **Concurrency-safe update** (`update`): before overwriting, read the current
   resource and capture its `ETag`. `PUT /fhir/r4/{ResourceType}/{id}` with header
   `If-Match: "<etag>"`. If another writer changed it first, the server rejects with
   `409`/`412` — re-read and retry.

4. **Audit history** (`vread`): `GET /fhir/r4/{ResourceType}/{id}/_history/{versionId}`
   to inspect a prior version.

## Rules

- Never PUT without `If-Match` on data you did not just read — that is how lost updates happen.
- `409`/`412` = version conflict: re-read, reconcile, retry (`conventions/1uphealth-conventions.yml`).
- PUT-by-id is idempotent; retries are safe.
