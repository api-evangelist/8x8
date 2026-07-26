---
name: Verify a phone number with 8x8
description: Run an SMS or voice one-time-passcode verification session end to end, with a
  number-lookup pre-check to avoid spending on unreachable or fraudulent numbers.
api: openapi/8x8-connect-verification-api.json
base_url: https://verify.8x8.com
operations:
- verify-request-v2
- code-validation-v2
- sma-coverage-check
- phone-number-lookup
generated: '2026-07-25'
method: generated
---

# Verify a phone number with 8x8

## Authentication

Bearer token in the `Authorization` header, per subaccount. Regional hosts:
`verify.8x8.com`, `verify.us.8x8.com`, `verify.8x8.uk`, `verify.8x8.id`. The Number
Lookup pre-check lives on a different host (`lookup.8x8.com`) but uses the same token
model.

## Steps

1. **Pre-check the number (optional but recommended).**
   `phone-number-lookup` (GET `/api/v1/subaccounts/{subAccountId}/phones/{phoneNumber}`
   on `lookup.8x8.com`, spec `openapi/8x8-connect-number-lookup-api.json`) returns
   carrier, portability and reachability. Abort the verification if the number is
   invalid or unreachable — this is 8x8's documented anti-fraud / database-hygiene step
   and it is far cheaper than a wasted OTP.
2. **Check silent-authentication coverage (optional).** `sma-coverage-check` (POST
   `/api/v2/subaccounts/{subAccountId}/sma/coverage`) tells you whether the number's
   carrier supports the silent mobile authentication path before you fall back to an OTP.
3. **Start the session.** `verify-request-v2` (POST
   `/api/v2/subaccounts/{subAccountId}/sessions`) generates and delivers the passcode.
   Pass `clientIp` — this endpoint is one of the three 8x8 endpoints that supports
   client-IP rate limiting, the primary defence against OTP-pumping attacks. Keep the
   returned `sessionId`.
4. **Validate the code.** `code-validation-v2` (GET
   `/api/v2/subaccounts/{subAccountId}/sessions/{sessionId}`) with the code the user
   entered. Treat the response as the sole source of truth — never validate the passcode
   locally.

## Rules

- **One session per attempt.** A session is the unit of state; do not reuse a `sessionId`
  after a terminal result.
- **Expiry is server-side.** Error code `1300` ("Object wasn't found or is already
  expired") on validation means the session has expired — start a new one rather than
  retrying the same session.
- **Resend throttling.** Code `1400` is a resending-interval violation; respect the
  interval instead of retrying immediately.
- **Do not log the passcode** — log the `sessionId` and, on failure, the `errorId`.
- **AIT/pumping defence is shared responsibility.** 8x8 documents client-IP rate limiting
  (opt-in per subaccount through the Help Center) as the platform-side control; the
  application side is expected to add its own throttling before calling this API. See
  `conventions/8x8-conventions.yml`.
