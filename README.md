# Medrio (medrio)

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
