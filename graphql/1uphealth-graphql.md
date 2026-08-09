# 1upHealth GraphQL API

## Overview

1upHealth provides a GraphQL API endpoint layered on top of its FHIR R4 platform, enabling clients to query FHIR resources and 1upHealth-specific data objects using a single, flexible query language. The GraphQL interface reduces over-fetching and enables precise retrieval of nested FHIR relationships in a single request.

- **Endpoint:** `https://api.1up.health/fhir/graphql`
- **Method:** POST
- **Authentication:** OAuth 2.0 Bearer token (same credentials as the FHIR REST API)
- **Content-Type:** `application/json`

## Authentication

Obtain an access token via the 1upHealth OAuth 2.0 token endpoint before calling GraphQL:

```
POST https://auth.1up.health/oauth2/token
Content-Type: application/x-www-form-urlencoded

grant_type=client_credentials&client_id=<CLIENT_ID>&client_secret=<CLIENT_SECRET>
```

Pass the resulting token as a Bearer header on all GraphQL requests:

```
Authorization: Bearer <ACCESS_TOKEN>
```

## Making Requests

All queries and mutations are submitted as HTTP POST with a JSON body:

```json
{
  "query": "{ patient(id: \"example\") { id name { family given } birthDate } }",
  "variables": {}
}
```

### Example: Fetch a Patient

```graphql
{
  patient(id: "patient-123") {
    id
    name {
      family
      given
    }
    birthDate
    gender
    address {
      line
      city
      state
      postalCode
    }
    telecom {
      system
      value
      use
    }
  }
}
```

### Example: Query Observations for a Patient

```graphql
{
  observationList(patient: "patient-123", category: "laboratory") {
    id
    status
    code {
      coding {
        system
        code
        display
      }
    }
    valueQuantity {
      value
      unit
    }
    effectiveDateTime
  }
}
```

### Example: Retrieve Explanation of Benefits

```graphql
{
  explanationOfBenefitList(patient: "patient-123") {
    id
    status
    type {
      coding {
        code
        display
      }
    }
    total {
      amount {
        value
        currency
      }
    }
    created
  }
}
```

### Example: Check Sync Status

```graphql
{
  syncStatus(id: "sync-job-456") {
    id
    status
    startTime
    endTime
    resourcesProcessed
    errors {
      code
      message
    }
  }
}
```

## FHIR Resource Coverage

The GraphQL schema wraps all HL7 FHIR R4 resource types supported by the 1upHealth platform. Each FHIR resource is exposed as a top-level query field (singular and list form) and includes all standard FHIR elements as typed GraphQL fields.

### Clinical Resources
- Patient, Practitioner, PractitionerRole, Organization, Location
- Encounter, Condition, Observation, DiagnosticReport, Procedure
- MedicationRequest, MedicationDispense, MedicationStatement, Medication
- AllergyIntolerance, Immunization, FamilyMemberHistory
- CarePlan, CareTeam, Goal, ServiceRequest
- DocumentReference, Composition

### Claims and Financial Resources
- Coverage, Claim, ClaimResponse, ExplanationOfBenefit
- InsurancePlan

### Infrastructure Resources
- Device, Endpoint, HealthcareService
- AuditEvent, Provenance, Subscription
- FHIRBundle, FHIRCapabilityStatement

### 1upHealth Platform Types
- HealthRecord, HealthDataSource, PatientConnection
- ConsentRecord, DataExchange, SyncJob, SyncStatus
- User, App, OAuthToken
- Payer, PayerConnection, WebhookEvent

## Pagination

List queries return a `FHIRBundle` wrapper supporting cursor-based pagination:

```graphql
{
  conditionList(patient: "patient-123", _count: 20, _page_token: "next-page-cursor") {
    id
    clinicalStatus {
      coding { code }
    }
    code {
      text
    }
  }
}
```

## Schema Reference

See `1up-health-schema.graphql` in this directory for the full type definitions.

## Additional Resources

- Documentation: https://docs.1up.health/docs
- FHIR R4 Specification: https://hl7.org/fhir/R4/
- Developer Portal: https://1up.health/
- GitHub: https://github.com/1uphealth
- Status Page: https://status.1up.health/
