# Adobe (adobe)

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

Adobe provides APIs and developer resources for its creative, document, and experience cloud platforms. Developers can integrate with PDF services, Creative Cloud, generative AI (Firefly), analytics, e-commerce, e-signatures, and many other Adobe products and services.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/adobe/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/adobe/refs/heads/main/apis.yml)

## Scope

- **Type:** Index

## Tags

- Analytics
- Creative Cloud
- Digital Asset Management
- Document Services
- E-Commerce
- E-Signatures
- Experience Cloud
- Generative AI
- Marketing
- PDF
- Work Management

## Timestamps

- **Created:** 2024-01-01
- **Modified:** 2026-05-19

## APIs

### Adobe PDF Services API

Create, manipulate, and export PDF documents programmatically.

- **Human URL:** [https://developer.adobe.com/document-services/apis/pdf-services/](https://developer.adobe.com/document-services/apis/pdf-services/)
- **Base URL:** `https://pdf-services.adobe.io`

#### Tags

- Conversion
- Documents
- PDF

#### Properties

- [Documentation](https://developer.adobe.com/document-services/docs/overview/pdf-services-api/)
- [Getting Started](https://developer.adobe.com/document-services/docs/overview/pdf-services-api/gettingstarted/)
- [Changelog](https://developer.adobe.com/document-services/docs/overview/releasenotes/)
- [OpenAPI](openapi/adobe-pdf-services-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/adobe-pdf-services-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/adobe-pdf-services-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/adobe-pdf-services-asset-upload-request-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON-LD](json-ld/adobe-pdf-services-context.jsonld) — [JSON-LD](https://www.w3.org/TR/json-ld11/)

### Adobe PDF Extract API

Extract text, images, tables, and more from native and scanned PDFs into structured JSON using AI technology.

- **Human URL:** [https://developer.adobe.com/document-services/docs/overview/pdf-extract-api/](https://developer.adobe.com/document-services/docs/overview/pdf-extract-api/)
- **Base URL:** `https://pdf-services.adobe.io`

#### Tags

- AI
- Extraction
- PDF

#### Properties

- [Documentation](https://developer.adobe.com/document-services/docs/overview/pdf-extract-api/)
- [Getting Started](https://developer.adobe.com/document-services/docs/overview/pdf-extract-api/gettingstarted/)
- [Postman Collection](collections/adobe-pdf-services-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/adobe-pdf-services-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Adobe Acrobat Sign API

Embed e-signature workflows and manage signing agreements programmatically.

- **Human URL:** [https://developer.adobe.com/document-services/apis/sign-api/](https://developer.adobe.com/document-services/apis/sign-api/)
- **Base URL:** `https://api.adobesign.com`

#### Tags

- Documents
- E-Signatures

#### Properties

- [Documentation](https://opensource.adobe.com/acrobat-sign/developer_guide/index.html)
- [API Reference](https://opensource.adobe.com/acrobat-sign/developer_guide/apiusage.html)
- [Getting Started](https://opensource.adobe.com/acrobat-sign/developer_guide/gstarted.html)
- [SDK](https://developer.adobe.com/acrobat-sign/docs/overview/sdks/rest)
- [Changelog](https://opensource.adobe.com/acrobat-sign/releasenotes/acrobatsignreleasenotes.html)
- [Postman Collection](collections/adobe-pdf-services-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/adobe-pdf-services-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Adobe Analytics API

Access and analyze digital marketing data and metrics.

- **Human URL:** [https://developer.adobe.com/analytics-apis/docs/2.0/](https://developer.adobe.com/analytics-apis/docs/2.0/)
- **Base URL:** `https://analytics.adobe.io`

#### Tags

- Analytics
- Metrics

#### Properties

- [Documentation](https://developer.adobe.com/analytics-apis/docs/2.0/)
- [Authentication](https://developer.adobe.com/analytics-apis/docs/2.0/guides/authentication/)
- [Getting Started](https://developer.adobe.com/analytics-apis/docs/2.0/guides/)
- [Postman Collection](collections/adobe-pdf-services-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/adobe-pdf-services-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Adobe Firefly API

Generate and edit images using generative AI models through a RESTful API.

- **Human URL:** [https://developer.adobe.com/firefly-services/docs/firefly-api/](https://developer.adobe.com/firefly-services/docs/firefly-api/)
- **Base URL:** `https://firefly-api.adobe.io`

#### Tags

- Generative AI
- Image Generation

#### Properties

- [Documentation](https://developer.adobe.com/firefly-services/docs/firefly-api/)
- [API Reference](https://developer.adobe.com/firefly-services/docs/firefly-api/api/)
- [Getting Started](https://developer.adobe.com/firefly-services/docs/firefly-api/guides/)
- [SDK](https://developer.adobe.com/firefly-services/docs/guides/sdks/)
- [Changelog](https://developer.adobe.com/firefly-services/docs/firefly-api/guides/changelog/)
- [Postman Collection](collections/adobe-pdf-services-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/adobe-pdf-services-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Adobe Experience Platform API

Build and manage customer experience applications on Adobe Experience Platform.

- **Human URL:** [https://developer.adobe.com/experience-platform-apis/](https://developer.adobe.com/experience-platform-apis/)
- **Base URL:** `https://platform.adobe.io`

#### Tags

- Customer Data
- Experience Platform

#### Properties

- [Documentation](https://experienceleague.adobe.com/docs/experience-platform/landing/platform-apis/api-guide.html)
- [API Reference](https://developer.adobe.com/experience-platform-apis/references/)
- [Getting Started](https://experienceleague.adobe.com/en/docs/experience-platform/landing/platform-apis/api-guide)
- [Postman Collection](collections/adobe-pdf-services-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/adobe-pdf-services-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Adobe Stock API

Search, license, and manage Adobe Stock assets including photos, vectors, videos, and templates.

- **Human URL:** [https://developer.adobe.com/stock/](https://developer.adobe.com/stock/)
- **Base URL:** `https://stock.adobe.io`

#### Tags

- Assets
- Stock

#### Properties

- [Documentation](https://developer.adobe.com/stock/docs/getting-started/)
- [API Reference](https://developer.adobe.com/stock/docs/api/)
- [Getting Started](https://developer.adobe.com/stock/docs/getting-started/)
- [SDK](https://github.com/adobe/stock-api-sdk)
- [Postman Collection](collections/adobe-pdf-services-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/adobe-pdf-services-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Adobe Commerce API

Build and integrate e-commerce applications with REST, GraphQL, and SOAP web APIs.

- **Human URL:** [https://developer.adobe.com/commerce/webapi/](https://developer.adobe.com/commerce/webapi/)

#### Tags

- E-Commerce
- REST

#### Properties

- [Documentation](https://developer.adobe.com/commerce/docs/)
- [API Reference](https://developer.adobe.com/commerce/webapi/rest/reference/)
- [Getting Started](https://developer.adobe.com/commerce/webapi/get-started/)
- [Authentication](https://developer.adobe.com/commerce/webapi/get-started/authentication/)
- [Postman Collection](collections/adobe-pdf-services-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/adobe-pdf-services-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Adobe Marketo Engage API

Automate marketing processes and manage leads, campaigns, and assets via REST APIs.

- **Human URL:** [https://developer.adobe.com/marketo-apis/](https://developer.adobe.com/marketo-apis/)

#### Tags

- Leads
- Marketing Automation

#### Properties

- [Documentation](https://experienceleague.adobe.com/en/docs/marketo-developer/marketo/rest/rest-api)
- [API Reference](https://experienceleague.adobe.com/en/docs/marketo-developer/marketo/rest/endpoint-reference)
- [Authentication](https://experienceleague.adobe.com/en/docs/marketo-developer/marketo/rest/authentication)
- [Getting Started](https://experienceleague.adobe.com/en/docs/marketo-developer/marketo/rest/rest-api)
- [Postman Collection](collections/adobe-pdf-services-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/adobe-pdf-services-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Adobe Workfront API

Manage work, projects, tasks, and resources programmatically with a REST API.

- **Human URL:** [https://developer.adobe.com/workfront-apis/](https://developer.adobe.com/workfront-apis/)

#### Tags

- Projects
- Work Management

#### Properties

- [Documentation](https://experienceleague.adobe.com/en/docs/workfront/using/adobe-workfront-api/workfront-api)
- [API Reference](https://developer.adobe.com/workfront/api-explorer/)
- [Getting Started](https://experienceleague.adobe.com/en/docs/workfront/using/adobe-workfront-api/api-general-information/api-basics)
- [Postman Collection](collections/adobe-pdf-services-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/adobe-pdf-services-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Adobe User Management API

Programmatically manage users, groups, and product entitlements for Adobe enterprise organizations.

- **Human URL:** [https://developer.adobe.com/umapi/](https://developer.adobe.com/umapi/)
- **Base URL:** `https://usermanagement.adobe.io`

#### Tags

- Identity
- User Management

#### Properties

- [Documentation](https://adobe-apiplatform.github.io/umapi-documentation/)
- [API Reference](https://adobe-apiplatform.github.io/umapi-documentation/en/RefOverview.html)
- [Getting Started](https://adobe-apiplatform.github.io/umapi-documentation/en/getstarted.html)
- [Postman Collection](collections/adobe-pdf-services-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/adobe-pdf-services-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Adobe I/O Events API

Subscribe to and receive near real-time events from Adobe services for event-driven integrations.

- **Human URL:** [https://developer.adobe.com/events/](https://developer.adobe.com/events/)
- **Base URL:** `https://platform.adobe.io`

#### Tags

- Events
- Webhooks

#### Properties

- [Documentation](https://developer.adobe.com/events/docs/)
- [API Reference](https://developer.adobe.com/events/docs/guides/api/)
- [Getting Started](https://developer.adobe.com/events/docs/)
- [Postman Collection](collections/adobe-pdf-services-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/adobe-pdf-services-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Adobe Experience Manager API

Create, read, update, and delete content, assets, and forms in Adobe Experience Manager as a Cloud Service.

- **Human URL:** [https://developer.adobe.com/experience-cloud/experience-manager-apis](https://developer.adobe.com/experience-cloud/experience-manager-apis)
- **Base URL:** `https://platform.adobe.io`

#### Tags

- Content Management
- Digital Asset Management

#### Properties

- [Documentation](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service)
- [API Reference](https://developer.adobe.com/experience-cloud/experience-manager-apis)
- [Getting Started](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/implementing/developing/reference-materials)
- [Postman Collection](collections/adobe-pdf-services-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/adobe-pdf-services-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [Arazzo Workflows](arazzo/) — [Arazzo Specification](https://spec.openapis.org/arazzo/latest.html)
- [LinkedIn](https://www.linkedin.com/company/adobe)
- [Portal](https://developer.adobe.com/)
- [Console](https://developer.adobe.com/console/)
- [Authentication](https://developer.adobe.com/developer-console/docs/guides/authentication/)
- [Support](https://developer.adobe.com/developer-support/)
- [Status Page](https://status.adobe.com/)
- [Blog](https://blog.developer.adobe.com/)
- [Terms of Service](https://www.adobe.com/legal/terms.html)
- [Privacy Policy](https://www.adobe.com/privacy/policy.html)
- [Getting Started](https://developer.adobe.com/developer-console/docs/guides/getting-started)
- [GitHub Organization](https://github.com/AdobeDocs/)
- [SDK](https://developer.adobe.com/apis)
- [Sign Up](https://developer.adobe.com/console/)
- [Login](https://developer.adobe.com/console/)
- [OpenAPI](openapi/adobe-pdf-services-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [JSON Schema](json-schema/adobe-pdf-services-asset-upload-request-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON-LD](json-ld/adobe-context.jsonld) — [JSON-LD](https://www.w3.org/TR/json-ld11/)
- [Spectral Rules](rules/adobe-spectral-rules.yml)
- [Vocabulary](vocabulary/adobe-vocabulary.yaml)
- [Features](undefined)
- [Use Cases](undefined)
- [Integrations](undefined)
- [M C P Server](https://blog.developer.adobe.com/en/publish/2025/09/introducing-the-adobe-express-add-on-dev-mcp-server-beta)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
