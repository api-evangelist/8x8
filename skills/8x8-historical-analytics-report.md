---
name: Pull a historical contact center analytics report from 8x8
description: Authenticate with OAuth 2.0 client credentials, create a historical metrics
  report, poll it to completion and download the data from the 8x8 Analytics for Contact
  Center API.
api: openapi/8x8-analytics-8x8-analytics-for-contact-center-historical-metrics-api.json
base_url: https://api.8x8.com/analytics/cc/v8/historical-metrics
operations:
- cc-historical-analytics-report-types
- cc-historical-analytics-report-type-by-type
- cc-historical-report-create
- cc-historical-report-status-by-id
- cc-historical-report-details-by-id
- cc-historical-report-data-by-id
- cc-historical-report-download-by-id
- cc-historical-report-links-by-id
- cc-detailed-report-create
- cc-detailed-report-data-by-id
generated: '2026-07-25'
method: generated
---

# Pull a historical contact center analytics report from 8x8

## Authentication

This is the one 8x8 surface that uses real **OAuth 2.0 client credentials**. Exchange
your client id/secret at `https://api.8x8.com/oauth/v2/token` for a bearer token; the
declared scopes are `read`, `write` and `admin` (`scopes/8x8-scopes.yml`). The spec also
declares an `x-api-key` alternative — prefer OAuth where both are accepted.

## Pick the regional base URL

The report data is region-resident. Choose one and stay on it:

- `https://api.8x8.com/analytics/cc/v8/historical-metrics` (US)
- `https://api.8x8.com/eu/analytics/cc/v8/historical-metrics`
- `https://api.8x8.com/au/analytics/cc/v8/historical-metrics`
- `https://api.8x8.com/ca/analytics/cc/v8/historical-metrics`

## Steps

1. **Discover what you can ask for.** `cc-historical-analytics-report-types` (GET
   `/report-types`) lists the available report types;
   `cc-historical-analytics-report-type-by-type` (GET `/report-types/{type}`) returns the
   format details — the columns, dimensions and required parameters for that type. Read
   this before constructing a request; do not guess field names.
2. **Create the report.** `cc-historical-report-create` (POST `/`) with the report type,
   time range and filters. This is asynchronous — it returns a report `id`, not data.
3. **Poll status.** `cc-historical-report-status-by-id` (GET `/{id}/status`) until the
   report reaches a terminal state. Back off between polls; do not tight-loop.
   `cc-historical-report-details-by-id` (GET `/{id}`) returns the report's definition and
   metadata.
4. **Read the data.** `cc-historical-report-data-by-id` (GET `/{id}/data`) for inline
   consumption, `cc-historical-report-download-by-id` (GET `/{id}/download`) for a file,
   or `cc-historical-report-links-by-id` (GET `/{id}/links`) for download links when the
   result is chunked.
5. **Need interaction-level rows, not aggregates?** Use `cc-detailed-report-create` (POST
   `/detailed-reports`) and `cc-detailed-report-data-by-id` (GET
   `/detailed-reports/{id}/data`) — same create-poll-read shape.

## Rules

- **Historical, not live.** For current queue and agent state use the Real-time Metrics
  API (`openapi/8x8-analytics-8x8-analytics-for-contact-center-real-time-metrics-api.json`)
  or the Pulsar event stream — never poll historical reports for a live dashboard.
- **Token lifetime.** Refresh the client-credentials token on expiry; do not mint one per
  request.
- **Reports are jobs.** Reuse the report `id` across polls rather than re-creating the
  report; re-creating is expensive and produces duplicate jobs.
- **Time zones.** Report windows are ISO 8601; be explicit about the offset rather than
  relying on a server default.
- **Retention.** Recordings and stored media referenced by report rows live in the Cloud
  Storage Service API (`openapi/8x8-analytics-cloud-storage-service-public-api.json`) and
  are region-scoped the same way.
