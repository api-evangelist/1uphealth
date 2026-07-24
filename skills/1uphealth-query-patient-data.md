---
name: Authenticate and query a patient's FHIR data
description: Get a SMART-on-FHIR token, then search and read a patient's clinical/claims data from the 1up FHIR R4 API.
api: fhir/1uphealth-fhir-r4-capabilitystatement.json
operations: [token, search-type, read, Patient/$everything]
auth: SMART-on-FHIR OAuth 2.0 (Bearer)
---

# Query a patient's FHIR data on 1upHealth

Use this to read a patient's data from the 1up managed FHIR R4 server
(`https://api.1up.health/fhir/r4`). All calls require a SMART-on-FHIR OAuth 2.0 Bearer
token. Never hardcode credentials — provision a client in the 1up Dev Portal.

## Steps

1. **Get an access token.** POST client credentials to the SMART token endpoint
   `https://auth.1up.health/oauth2/token` (grant `client_credentials` for backend
   access, or the SMART `authorization_code` flow via
   `https://auth.1up.health/oauth2/authorize/system` for a user-launched app). Request
   the SMART scopes covering the resources you need (e.g. `system/Patient.read`,
   `system/Observation.read`). See `authentication/1uphealth-authentication.yml` and
   `scopes/1uphealth-scopes.yml`.

2. **Find the patient** (`search-type`): `GET /fhir/r4/Patient?...` with FHIR search
   params (name, identifier, birthdate). The response is a FHIR `Bundle`; page with
   `Bundle.link[relation=next]` and control size with `_count`.

3. **Read a resource** (`read`): `GET /fhir/r4/Patient/{id}` (or any of the 144
   resource types). Send `Accept: application/fhir+json`.

4. **Pull the whole compartment** (`Patient/$everything`):
   `GET /fhir/r4/Patient/{id}/$everything` to retrieve all data referencing the patient.

## Rules

- Bearer every request; a 401 means re-auth, a 403 means the token lacks the SMART scope.
- Errors come back as a FHIR `OperationOutcome` — read `issue[].code`/`diagnostics`
  (see `errors/1uphealth-problem-types.yml`).
- Paginate via Bundle links, not by guessing offsets (`conventions/1uphealth-conventions.yml`).
