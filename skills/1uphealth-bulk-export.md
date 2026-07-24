---
name: Run a Bulk Data (Flat FHIR) group export
description: Kick off, poll, and download an asynchronous FHIR Bulk Data NDJSON export from 1upHealth.
api: fhir/1uphealth-fhir-r4-capabilitystatement.json
operations: [token, Group/$export]
auth: SMART-on-FHIR OAuth 2.0 (Bearer, client_credentials)
---

# Run a Bulk Data export on 1upHealth

Population-scale export uses the FHIR Bulk Data (Flat FHIR) async pattern against the
1up FHIR R4 server. This is the `1up Population Connect (Bulk FHIR)` solution.

## Steps

1. **Get a backend token.** `client_credentials` at `https://auth.1up.health/oauth2/token`
   with the documented bulk scope `bulk-data|user/*.rs`.

2. **Kick off the export** (`Group/$export`): `GET /fhir/r4/Group/{groupId}/$export`
   with header `Prefer: respond-async` and `Accept: application/fhir+json`. Optionally
   narrow with `_type` (comma-separated resource types) and `_since` (only changes after
   a timestamp). The server responds `202 Accepted` with a `Content-Location` status URL.

3. **Poll status.** `GET {Content-Location}` until `200 OK`; the body lists `output[]`
   NDJSON file URLs (one per resource type). `202` means still running (respect
   `Retry-After`); an `OperationOutcome` means it failed.

4. **Download** each `output[].url` (NDJSON). Delete the job when done if the server
   supports it.

## Rules

- Always send `Prefer: respond-async` on the kick-off; a synchronous `$export` will be rejected.
- Handle `202` + `Retry-After` politely; do not tight-loop.
- Errors are FHIR `OperationOutcome` (`errors/1uphealth-problem-types.yml`).
