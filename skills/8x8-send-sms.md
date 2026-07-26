---
name: Send an SMS with 8x8 Connect
description: Send a single or batch A2P SMS through the 8x8 Connect SMS API, track its
  delivery, and clean up scheduled messages or PII afterwards.
api: openapi/8x8-connect-sms-api.json
base_url: https://sms.8x8.com
operations:
- Send-Sms-Single
- Send-Many-Sms
- get-sms-message-details
- cancel-scheduled-message
- cancel-many-sms-messages
- delete-pii
- get-account-balance
- get-price-list
generated: '2026-07-25'
method: generated
---

# Send an SMS with 8x8 Connect

## Authentication

Bearer token in the `Authorization` header, scoped to a **subaccount**. Get the token from
the 8x8 Connect console (https://connect.8x8.com/). Every path in this API is rooted at
`/api/v1/subaccounts/{subAccountId}` — the subaccount is the tenancy boundary for
sending, billing, rate limits and webhooks.

Regional hosts: `sms.8x8.com` (default), `sms.us.8x8.com`, `sms.8x8.uk`, `sms.8x8.id`.
Use the host for the region the subaccount lives in.

## Steps

1. **Check you can pay for it.** `get-account-balance` (GET
   `/api/v1/accounts/{accountId}/balance`) and, if you need per-destination cost,
   `get-price-list` (GET `/api/v1/accounts/{accountId}/prices`).
2. **Send one message.** `Send-Sms-Single` (POST
   `/api/v1/subaccounts/{subAccountId}/messages`). Destination numbers are E.164. Set
   the sender ID, encoding and expiry per the request schema; supply `clientIp` when the
   send is triggered by an end-user request so 8x8 can apply client-IP rate limiting as
   an SMS-pumping (AIT) defence.
3. **Send many.** For volume use `Send-Many-Sms` (POST
   `/api/v1/subaccounts/{subAccountId}/messages/batch`) — up to **10,000 messages in a
   single request**. Prefer this over looping `Send-Sms-Single`; it is the documented way
   to stay inside the rate limits.
4. **Track it.** `get-sms-message-details` (GET
   `/api/v1/subaccounts/{subAccountId}/messages/{umid}`) returns status by `umid`. For
   push instead of poll, register a delivery-receipt webhook (`Add-Webhooks-2`) and
   consume the DLR events — see `asyncapi/8x8-events-webhooks.yml`.
5. **Cancel if scheduled.** `cancel-scheduled-message` (DELETE `.../messages/{umid}`) or
   `cancel-many-sms-messages` (DELETE `.../messages/batch/{batchId}`).
6. **Erase on request.** `delete-pii` (DELETE `.../messages/{umid}/pii`) removes
   personally identifiable information for a message from 8x8's databases — this is the
   operation to reach for on a GDPR/CCPA erasure request.

## Rules

- **Rate limits.** 1,800 requests/second per subaccount (adjustable on request) and
  3,000 requests/second per IP, with no daily quota. On `429` read `Retry-After` (in
  seconds) and back off — the Connect suite does **not** emit `x-ratelimit-*` headers.
- **Errors.** Any status ≥ 400 returns `{code, message, errorId, timestamp}`. Branch on
  the numeric `code`, not the message text: `1000` invalid parameter, `1002` invalid
  MSISDN, `1100` bulk limit reached, `1200` unauthorized, `1300` not found/expired,
  `1400` resending-interval violation, `2002` unsupported API version. Full registry in
  `errors/8x8-error-codes.yml`.
- **Log the `errorId`.** It is the UUID 8x8 support asks for.
- **TLS 1.3 minimum.** A `426 Upgrade Required` (or code `1014`) means the client
  negotiated an older TLS version.
- **No idempotency key on this API.** A retried `Send-Sms-Single` sends a second message.
  De-duplicate on your side using your own message key before retrying a timeout.
