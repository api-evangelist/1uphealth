# 1upHealth (1uphealth)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
