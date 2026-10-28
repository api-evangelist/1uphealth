# 1upHealth

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

1upHealth is a US healthcare data interoperability company, founded in 2017 and headquartered in Boston, Massachusetts, that operates an HL7 FHIR-first health data platform for claims and clinical data acquisition, exchange, and compute. Built on a lakehouse architecture, the platform lets health plans, providers, and digital health developers ingest, normalize, store, and query patient and member data as FHIR, and ships modular solutions aligned to US federal interoperability mandates - Patient Access, Provider Access, Payer-to-Payer Data Exchange, Provider Directory, Formulary, and Electronic Prior Authorization (CMS Interoperability & Prior Authorization, CMS-0057-F). 1upHealth runs a managed, HIPAA-compliant FHIR REST API cloud server exposing FHIR R4 (4.0.1), STU3 (3.0.2), and DSTU2 (1.0.2) endpoints, each publishing a live CapabilityStatement, secured with SMART-on-FHIR OAuth 2.0. The company is HITRUST, SOC 2, and HIPAA aligned. Home market is the United States. Developer documentation is public at docs.1up.health, while provisioning API credentials and the developer console require an account (gated self-serve / partner onboarding).

**Areas:** Healthcare · United States · FHIR · HL7 · Interoperability · SMART on FHIR · Payers · Claims · Patient Access · Health Data

## 1upHealth on APIs.io

Everything profiled for 1upHealth is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/1uphealth/](https://apis.io/providers/1uphealth/)** — or go straight to one of the APIs or properties below.

### APIs (10)

- [1up FHIR API (R4)](https://apis.io/apis/1uphealth/1uphealth-fhir-r4-api/) — 1upHealth's managed HL7 FHIR R4 (4.0.1) REST API cloud server, exposing 144 FHIR resource types with SMART-on-FHIR OAuth 2.0 security. Publishes a live…
- [1up FHIR API (STU3)](https://apis.io/apis/1uphealth/1uphealth-fhir-stu3-api/) — 1upHealth's managed HL7 FHIR STU3 (3.0.2) REST API cloud server, exposing 117 FHIR resource types. Publishes a live CapabilityStatement at /fhir/stu3/metadata.
- [1up FHIR API (DSTU2)](https://apis.io/apis/1uphealth/1uphealth-fhir-dstu2-api/) — 1upHealth's managed HL7 FHIR DSTU2 (1.0.2) REST API cloud server, exposing 94 FHIR resource types. Publishes a live Conformance statement at…
- [1up Patient Access API](https://apis.io/apis/1uphealth/1uphealth-patient-access-api/) — CMS Patient Access solution delivering member clinical and claims data to patient-authorized third-party apps over FHIR, aligned to the CARIN Blue Button…
- [1up Provider Access API](https://apis.io/apis/1uphealth/1uphealth-provider-access-api/) — CMS Provider Access solution enabling payers to share member data with in-network providers over FHIR, aligned to the Da Vinci implementation guides.
- [1up Payer-to-Payer Data Exchange API](https://apis.io/apis/1uphealth/1uphealth-payer-to-payer-api/) — CMS Payer-to-Payer Data Exchange solution for sharing a member's historical clinical and claims data between health plans over FHIR when a member changes…
- [1up Provider Directory API](https://apis.io/apis/1uphealth/1uphealth-provider-directory-api/) — Publicly accessible FHIR Provider Directory publishing accurate provider and network listings, aligned to the Da Vinci PDEX Plan-Net implementation guide.
- [1up Electronic Prior Authorization API](https://apis.io/apis/1uphealth/1uphealth-epa-api/) — CMS-0057-F Electronic Prior Authorization solution automating prior authorization submission and decisioning over FHIR, aligned to the Da Vinci PAS / DTR /…
- [1up Patient Connect](https://apis.io/apis/1uphealth/1uphealth-patient-connect-api/) — Connectivity solution that acquires patient-authorized clinical records from a national network of EHR/provider and payer connections and normalizes them…
- [1up Population Connect (Bulk FHIR)](https://apis.io/apis/1uphealth/1uphealth-population-connect-api/) — Population-scale connectivity and Bulk Data (Flat FHIR) export solution for acquiring and computing over large member/patient populations as FHIR.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [1Uphealth Subscription Webhooks](https://apis.io/asyncapis/1uphealth/1uphealth-subscription-webhooks/)

#### GraphQL (1)

GraphQL schemas.

- [1upHealth GraphQL API](https://apis.io/graphqls/1uphealth/1uphealth-graphql/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [1uphealth-fhir](https://apis.io/servers/1uphealth/1uphealth-fhir/)

#### JSON-LD (1)

Linked-data contexts for the provider's vocabulary.

- [1Uphealth Context](https://apis.io/jsonld/1uphealth/1uphealth-context/)

#### Security (3)

Authentication, trust centre, and vulnerability disclosure.

- [1Uphealth Authentication](https://apis.io/security/1uphealth/1uphealth-authentication/)
- [1Uphealth Domain Security](https://apis.io/security/1uphealth/1uphealth-domain-security/)
- [1Uphealth Trust Center](https://apis.io/security/1uphealth/1uphealth-trust-center/)

#### OAuth scopes (1)

The permissions the API asks for.

- [1Uphealth Scopes](https://apis.io/scopes/1uphealth/1uphealth-scopes/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [1Uphealth Plans Pricing](https://apis.io/plans/1uphealth/1uphealth-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [1Uphealth Rate Limits](https://apis.io/rate-limits/1uphealth/1uphealth-rate-limits/)

#### FinOps (1)

What the API costs to run, by operation.

- [1Uphealth Finops](https://apis.io/finops/1uphealth/1uphealth-finops/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://1up.health/)
- [Documentation](https://docs.1up.health/)
- [Getting started](https://docs.1up.health/docs/get-started/faq)
- [API reference](https://docs.1up.health/help-center/Content/en-US/api-references/rest-api-reference.html)
- [Sign up](https://app.1up.health/login)
- [Support](https://1uphealth.my.site.com/)
- [Blog](https://1up.health/blog/)
- [Security](https://trust.1up.health/)
- [Compliance](https://trust.1up.health/)
- [Trust centre](https://trust.1up.health/)
- [Terms of service](https://1up.health/terms-of-service/)
- [Privacy policy](https://1up.health/privacy-policy/)
- [GitHub](https://github.com/1uphealth)
- [Status](https://status.1up.health/)

## API Evangelist rating

**Kin Score 70.6** — exemplar · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 83.3 |
| Contract quality | 57.0 |
| Contract governance | 18.2 |
| Operational transparency | 84.2 |
| Developer ergonomics | 66.1 |
| Access clarity | 81.6 |

**Agent readiness 30.6** — agent-ready

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | — |
| Reversibility Documented | — |
| MCP Server | documented (partial credit) |
| Auth Clarity | bearer (partial credit) |
| Idempotency | documented (partial credit) |
| Error Semantics | derived (partial credit) |
| OpenAPI Examples | — |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | yes |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | na |
| Operation Distinctiveness | na |

**Regulatory alignment 47.7** — Health

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/1uphealth/](https://apis.io/providers/1uphealth/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for 1upHealth: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/1uphealth/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
