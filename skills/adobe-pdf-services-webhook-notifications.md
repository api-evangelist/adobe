---
name: Receive Adobe PDF Services job completion by webhook
description: >-
  Replace status polling with a CALLBACK notifier so Adobe PDF Services POSTs the job result to
  your own HTTPS endpoint. Covers the notifiers request block, the success and failure payload
  shapes, the acknowledgement the client must return, and the 50-errors-in-10-minutes blocking
  rule that silently disables notifications.
api: openapi/_original/adobe-pdf-services-api-openapi-official.json
generated: '2026-08-13'
method: generated
source: >-
  https://developer.adobe.com/document-services/docs/overview/pdf-services-api/howtos/webhook-notification/
  (harvested verbatim from AdobeDocs/pdfservices-api-documentation); operationIds verified against
  openapi/_original/adobe-pdf-services-api-openapi-official.json
operations:
  - pdfoperations.createpdf
  - pdfoperations.documentgeneration
  - pdfoperations.autotag
  - pdfoperations.extractpdf
---

# Receive Adobe PDF Services job completion by webhook

Polling `pdfoperations.<operation>.jobstatus` works, but it costs a request per poll against a
25–100 RPM budget. Adobe supports a **CALLBACK notifier** instead: add one block to the submit
body and Adobe POSTs the finished job to you.

Available on REST and on SDK **4.x.x only**.

## Add the notifier to the submit call

Any submit operation accepts `notifiers` alongside its normal parameters — `pdfoperations.createpdf`,
`pdfoperations.documentgeneration`, `pdfoperations.autotag`, `pdfoperations.extractpdf`, and the
rest.

```json
{
   "assetID": "<ASSET ID>",
   "notifiers": [
      {
         "type": "CALLBACK",
         "data": {
            "url": "https://your-host.example/adobe/pdf-callback",
            "headers": {
               "x-api-key": "<your own value>",
               "access-token": "<your own value>"
            }
         }
      }
   ]
}
```

- `type` is **required** and `CALLBACK` is currently the only supported value.
- `data.url` is **required** and must be an HTTPS POST endpoint you control.
- `data.headers` is optional — a map Adobe replays on the callback so you can authenticate it.
  Adobe does not sign the callback, so put a shared secret here and verify it; treat an unverified
  callback as untrusted input.

## The payload Adobe sends you

Identical to the `jobstatus` response body, plus `jobID`.

Success:

```json
{
   "jobID": "<JOB ID>",
   "statusResponse": {
      "status": "done",
      "asset": {
         "metadata": { "type": "application/pdf", "size": 318974 },
         "downloadUri": "<DOWNLOAD URI>",
         "assetID": "<ASSET ID>"
      }
   }
}
```

Failure:

```json
{
   "jobID": "<JOB ID>",
   "statusResponse": {
      "status": "failed",
      "error": { "code": "<ERROR CODE>", "message": "<ERROR MESSAGE>", "status": 400 }
   }
}
```

Note the failure envelope nests the same `{code, message}` shape used by the synchronous API — see
`errors/adobe-problem-types.yml`.

## What your endpoint MUST return

```
HTTP 200 OK
{ "ack": "done" }
```

Both parts matter. Adobe treats *either* a non-200 status *or* a missing `{"ack":"done"}` body as
an error response.

## The rule that will bite you

> "In the event of 50 error responses within a 10-minute period, webhook notification support will
> be temporarily blocked for that client for the next 20 minutes."

This is a **client-wide** block, not a per-job one, and it is silent — jobs still run and still
complete, you simply stop being told. An agent using callbacks must therefore:

1. Return `200 {"ack":"done"}` **before** doing any downstream work. Acknowledge first, process
   after, from a queue.
2. Never let a downstream failure (storage full, parse error) turn into a non-200 on the callback.
3. Keep a fallback: record the `location` / job id from the 201 on submit so you can fall back to
   `pdfoperations.<operation>.jobstatus` if a callback never arrives within your expected window.
4. Download from `downloadUri` promptly — it is presigned and short-lived — then `asset.delete`
   both input and output.
