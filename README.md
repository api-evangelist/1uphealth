# 1upHealth (1uphealth)

1upHealth is a US healthcare data interoperability company (founded 2017, Boston, Massachusetts) that operates an HL7 FHIR-first health data platform for claims and clinical data acquisition, exchange, and compute. Built on a lakehouse architecture, it lets health plans, providers, and digital health developers ingest, normalize, store, and query patient and member data as FHIR, with modular solutions aligned to US federal interoperability mandates (CMS Interoperability & Prior Authorization / CMS-0057-F). Home market: United States.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/1uphealth/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/1uphealth/refs/heads/main/apis.yml)

## Tags

- Healthcare
- United States
- FHIR
- HL7
- Interoperability
- SMART on FHIR
- Payer
- Claims
- Patient Access
- Health Data

## Timestamps

- **Created:** 2026-07-24
- **Modified:** 2026-07-24

## API Posture

1upHealth runs a managed, HIPAA-compliant FHIR REST API cloud server at `https://api.1up.health` that serves three FHIR versions concurrently, each publishing a live machine-readable conformance document (harvested verbatim into `fhir/`):

- **FHIR R4 (4.0.1)** — `https://api.1up.health/fhir/r4/metadata` — CapabilityStatement, 144 resources, SMART-on-FHIR security.
- **FHIR STU3 (3.0.2)** — `https://api.1up.health/fhir/stu3/metadata` — CapabilityStatement, 117 resources.
- **FHIR DSTU2 (1.0.2)** — `https://api.1up.health/fhir/dstu2/metadata` — Conformance, 94 resources.

**Auth:** SMART-on-FHIR (OAuth 2.0) — authorize `https://auth.1up.health/oauth2/authorize/system`, token `https://auth.1up.health/oauth2/token`; authorization-code for patient access and client-credentials for system/bulk access. Public product docs are readable at [docs.1up.health](https://docs.1up.health/); API credentials require the login-gated developer console.

## APIs

### 1up FHIR API (R4)

Managed HL7 FHIR R4 (4.0.1) REST server, 144 resource types, SMART-on-FHIR OAuth 2.0.

- **Human URL:** [https://docs.1up.health/docs/fhir-info](https://docs.1up.health/docs/fhir-info)
- **Base URL:** `https://api.1up.health/fhir/r4`
- [CapabilityStatement](fhir/1uphealth-fhir-r4-capabilitystatement.json)

### 1up FHIR API (STU3)

Managed HL7 FHIR STU3 (3.0.2) REST server, 117 resource types.

- **Human URL:** [https://docs.1up.health/docs/fhir-info](https://docs.1up.health/docs/fhir-info)
- **Base URL:** `https://api.1up.health/fhir/stu3`
- [CapabilityStatement](fhir/1uphealth-fhir-stu3-capabilitystatement.json)

### 1up FHIR API (DSTU2)

Managed HL7 FHIR DSTU2 (1.0.2) REST server, 94 resource types.

- **Human URL:** [https://docs.1up.health/docs/fhir-info](https://docs.1up.health/docs/fhir-info)
- **Base URL:** `https://api.1up.health/fhir/dstu2`
- [CapabilityStatement](fhir/1uphealth-fhir-dstu2-conformance.json)

### 1up Patient Access API

CMS Patient Access — member clinical and claims data to patient-authorized apps over FHIR (CARIN Blue Button / US Core).

- **Human URL:** [https://docs.1up.health/docs/patient-access](https://docs.1up.health/docs/patient-access)

### 1up Provider Access API

CMS Provider Access — payer-to-provider member data sharing over FHIR (Da Vinci).

- **Human URL:** [https://docs.1up.health/docs/provider-access](https://docs.1up.health/docs/provider-access)

### 1up Payer-to-Payer Data Exchange API

CMS Payer-to-Payer — historical member data sharing between health plans over FHIR.

- **Human URL:** [https://docs.1up.health/docs/payer-to-payer](https://docs.1up.health/docs/payer-to-payer)

### 1up Provider Directory API

FHIR Provider Directory publishing provider/network listings (Da Vinci PDEX Plan-Net).

- **Human URL:** [https://docs.1up.health/docs/provider-directory](https://docs.1up.health/docs/provider-directory)

### 1up Electronic Prior Authorization API

CMS-0057-F ePA — automated prior authorization over FHIR (Da Vinci PAS / DTR / CRD).

- **Human URL:** [https://docs.1up.health/docs/epa](https://docs.1up.health/docs/epa)

### 1up Patient Connect

Patient-authorized clinical record acquisition from a national EHR/provider/payer network, normalized to FHIR.

- **Human URL:** [https://docs.1up.health/docs/patient-connect](https://docs.1up.health/docs/patient-connect)

### 1up Population Connect (Bulk FHIR)

Population-scale connectivity and Bulk Data (Flat FHIR) export.

- **Human URL:** [https://docs.1up.health/docs/pop-connect](https://docs.1up.health/docs/pop-connect)

## Common Properties

- [Website](https://1up.health/)
- [Developer Portal](https://docs.1up.health/)
- [Documentation](https://docs.1up.health/)
- [Developer Console](https://developer.1up.health/)
- [Blog](https://1up.health/blog/)
- [Status Page](https://status.1up.health/)
- [Trust Center](https://trust.1up.health/)
- [Support](https://1uphealth.my.site.com/)
- [Sign Up / Login](https://app.1up.health/login)
- [GitHub Organization](https://github.com/1uphealth)
- [Terms of Service](https://1up.health/terms-of-service/)
- [Privacy Policy](https://1up.health/privacy-policy/)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
