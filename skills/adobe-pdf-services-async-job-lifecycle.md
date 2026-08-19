---
name: Run an Adobe PDF Services job end to end
description: >-
  Authenticate against Adobe IMS, upload a source document to a presigned URL, submit an
  asynchronous PDF operation, poll the job to completion, download the result, and clean up the
  asset. This is the shape of EVERY Adobe PDF Services operation — learn it once and all 24
  operations follow it.
api: openapi/_original/adobe-pdf-services-api-openapi-official.json
generated: '2026-08-13'
method: generated
source: >-
  operationIds verified verbatim against openapi/_original/adobe-pdf-services-api-openapi-official.json
  (harvested from AdobeDocs/pdfservices-api-documentation); conventions from
  conventions/adobe-conventions.yml and errors/adobe-problem-types.yml
operations:
  - authentication.generatetoken
  - asset.uploadpresignedurl
  - asset.get
  - asset.metadata
  - asset.delete
  - pdfoperations.extractpdf
  - pdfoperations.extractpdf.jobstatus
---

# Run an Adobe PDF Services job end to end

Adobe PDF Services is **asynchronous by design**. Nothing returns a finished document. You submit
a job, get a `location` header, and poll it. There is no synchronous shortcut.

## Base URL

Pick the region and stay on it for the whole job — an asset uploaded in one region is not
addressable from the other.

| Region | Host |
|---|---|
| United States (default) | `https://pdf-services-ue1.adobe.io` |
| Europe | `https://pdf-services-ew1.adobe.io` |

`https://pdf-services.adobe.io` also resolves and is what most SDK samples use.

## Step 1 — get an access token (`authentication.generatetoken`)

`POST /token` with your Adobe Developer Console OAuth Server-to-Server credentials
(`client_id` + `client_secret`). The token is a bearer token issued by Adobe Identity Management
Services (IMS).

Every subsequent call needs **both** headers — this trips people up, because the API key is not
redundant with the token:

```
Authorization: Bearer <access_token>
x-api-key: <client_id>
```

## Step 2 — upload the source document (`asset.uploadpresignedurl`)

`POST /assets` with `{"mediaType": "application/pdf"}`. The response gives you an `assetID` and a
presigned `uploadUri`. **PUT the file bytes to `uploadUri` directly** — you do not stream the
document through the Adobe API host. The presigned URL is short-lived; upload immediately.

## Step 3 — submit the operation (e.g. `pdfoperations.extractpdf`)

`POST /operation/extractpdf` with the `assetID` from step 2 in the body.

A successful submit returns **HTTP 201 with an empty body**. The thing you need is in the headers:

- `location` — the job status URI to poll
- `x-request-id` — echo this in support tickets; it is the correlation id for the whole job

Do not treat the 201 as success of the *operation*. It is success of the *submission*.

## Step 4 — poll (`pdfoperations.extractpdf.jobstatus`)

`GET` the `location` URI (`/operation/extractpdf/{jobID}/status`). Poll with backoff. The response
carries a `status` field:

- `in progress` — keep polling
- `done` — the response contains the output `asset` with a `downloadUri`
- `failed` — the response contains `error.code` and `error.message`; see
  `errors/adobe-problem-types.yml`

Every operation has its own status operationId (`pdfoperations.<operation>.jobstatus`). The one
exception to the naming is Create PDF, whose status operation is the bare
`pdfoperations.jobstatus`.

**Prefer not to poll at all** where you can: pass a `notifiers` block on the submit and Adobe will
POST the completion payload to your own HTTPS URL. See the sibling skill
`adobe-pdf-services-webhook-notifications.md`.

## Step 5 — download, then clean up (`asset.get`, `asset.delete`)

`GET /assets/{assetId}` returns a fresh `downloadUri`; `GET /assets/{assetId}/metadata` returns
size and media type without transferring bytes. Download from the presigned URI, then
`DELETE /assets/{assetId}` for both the input and output assets. Adobe expires assets on its own
schedule, but deleting explicitly is the correct behaviour for anything containing customer data.

`DELETE` returns **204 with no body**.

## Rules an agent must follow

1. **There is no idempotency key.** Adobe PDF Services publishes no `Idempotency-Key` header and no
   request-deduplication contract. A retried submit is a *second billable job*. Retry only on 5xx
   and 429, never on a timeout you cannot correlate — use the `x-request-id` you sent to check
   before resubmitting.
2. **Billing is per Document Transaction, not per call.** One transaction covers up to 50 pages for
   most operations; Extract and PDF To Markdown count 1 per 5 pages; Accessibility Auto-Tag counts
   **10 per page**; Electronic Seal counts 10 per PDF. A 200-page auto-tag job is 2,000 transactions
   and will exhaust a 500/month free tier four times over. Check page count before submitting.
3. **Respect the rate limit.** 25 RPM on the free tier, 100 RPM on enterprise. Exhaustion returns
   `429` with `error.code` of `TOO_MANY_REQUESTS` (rate) or `INSUFFICIENT_QUOTA` (monthly
   allowance). These need different handling: back off for the first, stop for the second.
4. **Usage limits are hard failures, not warnings.** 100MB per file; 20 documents for Combine /
   Insert / Replace / Split; 400 pages for Extract; 200 for Auto-Tag; 150 for scanned input; 10MB
   for the Document Generation JSON. Over the limit the job fails — it does not degrade.
5. **Errors are not RFC 9457.** The envelope is `{"error": {"code": "...", "message": "..."}}` with
   a mnemonic `code`. Branch on `error.code`, never on the message text; Adobe documents the code
   list as extendable.
