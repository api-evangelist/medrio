# Medrio (medrio)

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
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Medrio is an eClinical / electronic data capture (EDC) platform "built for small and scaling life sciences teams," spanning EDC, ePRO/eCOA, eConsent, and RTSM for clinical trials across pharma, biotech, medtech, and diagnostics. Medrio exposes two documented REST APIs for integration and data exchange: **Medrio API Connect** (`connectapi.medrio.com`) for study configuration, subject enrollment, eCRF data entry, user/membership administration, reference data, and event subscriptions; and the **mSource API** (`esource.medrio.com`) that backs the mPRO and mCapture eCOA/ePRO applications for subject-, form-, and approval-level source data capture.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/medrio/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/medrio/refs/heads/main/apis.yml)

## Access Model

Medrio's API **documentation is public** - the API Connect Swagger UI and its raw OpenAPI (`swagger/v1/swagger.json`), and the mSource API Help pages, are all viewable without a login. **Actual use is gated to Medrio customers.** Every call requires an OAuth access token issued for a provisioned study/account (API Connect issues tokens at `/Oauth/token`; mSource at `/api/oauth/token` and additionally requires an `X-Medrio-ClientInfo` header). Medrio is commercial eClinical software; pricing is **per study / contact-sales** and is not published. The API is not sold or metered separately - it comes with the underlying study subscription.

Both surfaces are pure request/response REST over HTTPS. There is **no documented public WebSocket API**. API Connect does offer a REST-configured **Subscriptions** resource for study event notifications, but notification delivery is out-of-band rather than a persistent WebSocket channel.

## Tags

- Clinical Trials
- Electronic Data Capture
- EDC
- eClinical
- ePRO
- eCOA
- Clinical Data
- Life Sciences
- Healthcare

## Timestamps

- **Created:** 2026-07-05
- **Modified:** 2026-07-05

## APIs

### Medrio Studies API

List the studies available to your account and read their configuration - domains, enabled features, reason-for-data-change options, and the reference data a study is built from (sites, roles, groups, and subject statuses).

- **Human URL:** [https://connectapi.medrio.com/swagger/index.html](https://connectapi.medrio.com/swagger/index.html)
- **Base URL:** `https://connectapi.medrio.com`

#### Properties

- [API Reference](https://connectapi.medrio.com/swagger/index.html)
- [OpenAPI](https://connectapi.medrio.com/swagger/v1/swagger.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

### Medrio Subjects API

Create, list, and update clinical trial subjects within a study; manage Medrio and study subject identifiers (including their ePRO variants), activate or deactivate subjects, and list deleted subjects.

- **Human URL:** [https://connectapi.medrio.com/swagger/index.html](https://connectapi.medrio.com/swagger/index.html)
- **Base URL:** `https://connectapi.medrio.com`

#### Properties

- [API Reference](https://connectapi.medrio.com/swagger/index.html)
- [OpenAPI](https://connectapi.medrio.com/swagger/v1/swagger.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

### Medrio Data Entry API

Read and write electronic case report form (eCRF) data - list a subject's visits, create subject visits from a template, submit and update data entry at the study or form/visit level, and clear a form. The clinical data capture core of Medrio EDC.

- **Human URL:** [https://connectapi.medrio.com/swagger/index.html](https://connectapi.medrio.com/swagger/index.html)
- **Base URL:** `https://connectapi.medrio.com`

#### Properties

- [API Reference](https://connectapi.medrio.com/swagger/index.html)
- [OpenAPI](https://connectapi.medrio.com/swagger/v1/swagger.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

### Medrio Users and Memberships API

Administer the account user profile and per-study memberships - read and update your user, change password, list study users, add users to a study, assign or remove roles and site access, and remove a user from a study.

- **Human URL:** [https://connectapi.medrio.com/swagger/index.html](https://connectapi.medrio.com/swagger/index.html)
- **Base URL:** `https://connectapi.medrio.com`

#### Properties

- [API Reference](https://connectapi.medrio.com/swagger/index.html)
- [OpenAPI](https://connectapi.medrio.com/swagger/v1/swagger.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

### Medrio Subscriptions API

Configure event subscriptions for a study - read the available events configuration, then create, list, update, and delete subscriptions so downstream systems are notified of study events.

- **Human URL:** [https://connectapi.medrio.com/swagger/index.html](https://connectapi.medrio.com/swagger/index.html)
- **Base URL:** `https://connectapi.medrio.com`

#### Properties

- [API Reference](https://connectapi.medrio.com/swagger/index.html)
- [OpenAPI](https://connectapi.medrio.com/swagger/v1/swagger.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

### Medrio mSource API

The V2 REST API behind Medrio's mSource eCOA/ePRO applications (mPRO and mCapture) - read study configuration, files, and users; read and write subject, form, and approval data with an asynchronous key-based query pattern; and post offline access, audit trail, and diagnostic logs. Secured with OAuth 2.0 and a required `X-Medrio-ClientInfo` header.

- **Human URL:** [https://esource.medrio.com/Help](https://esource.medrio.com/Help)
- **Base URL:** `https://esource.medrio.com`

#### Properties

- [API Reference](https://esource.medrio.com/Help)
- [Documentation (V1)](https://esource.medrio.com/Help?apiVersion=1)

## Common Properties

- [Website](https://medrio.com)
- [LinkedIn](https://www.linkedin.com/company/medrio)
- [Documentation](https://community.medrio.com/documentation/home)
- [API Reference](https://connectapi.medrio.com/swagger/index.html)
- [OpenAPI](https://connectapi.medrio.com/swagger/v1/swagger.json)
- [Sign Up / Contact Sales](https://medrio.com/contact/)
- [Plans](plans/medrio-plans-pricing.yml)
- [Rate Limits](rate-limits/medrio-rate-limits.yml)
- [Fin Ops](finops/medrio-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
