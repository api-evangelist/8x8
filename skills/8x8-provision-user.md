---
name: Provision a user in an 8x8 tenant
description: Create, update and deprovision users in the 8x8 Administration API Suite,
  driving the asynchronous 202-Accepted + poll-the-operation pattern correctly.
api: openapi/8x8-administration-user-api-v1.yaml
base_url: https://api.8x8.com/admin-provisioning
operations:
- listUsers
- createUser
- getUser
- updateUser
- deleteUser
- getOperation
generated: '2026-07-25'
method: generated
---

# Provision a user in an 8x8 tenant

> The Administration API Suite is in **beta / limited access**: API keys cannot be
> generated in Admin Console yet and only beta-programme participants can call it. Confirm
> access before building on it.

## Authentication

`x-api-key: <key>` on **every** request. Keys are created at
https://admin.8x8.com/api-access and begin with `eght_`. Base URL:
`https://api.8x8.com/admin-provisioning`.

## Versioning — get this right or nothing works

The version travels in a media type, not the path:

- Requests **with** a payload (`POST`, `PUT`): `Content-Type: application/vnd.users.v1+json`
- Requests that **return** a payload (`GET`, async `DELETE`): `Accept: application/vnd.users.v1+json`
- Synchronous `DELETE`s that return no content are unversioned.

## Steps

1. **Find out if the user already exists.** `listUsers` (GET `/users`) with an RSQL
   filter, e.g. `filter=basicInfo.status==ACTIVE` or a `primaryEmail` equality. RSQL uses
   `==`, not `=`; a malformed filter returns `400` with code `INVALID_FILTER`.
2. **Page properly.** Send `pageSize` (default 100, max 1000); follow
   `pagination.nextScrollId` into the `scrollId` parameter until `pagination.hasMore` is
   false. Scroll IDs are opaque and encode the filter and sort — never change filter or
   sort mid-scroll, start a new scroll instead.
3. **Create.** `createUser` (POST `/users`) returns **`202 Accepted` with an operation**,
   not the created user.
4. **Poll the operation.** `getOperation` (GET `/operations/{operationId}`, spec
   `openapi/8x8-administration-operation-api-v1.yaml`) until it reaches a terminal state.
   Store the operation ID against your source request for correlation. Do not assume
   success; do not start dependent work before the operation completes.
5. **Read back.** `getUser` (GET `/users/{userId}`).
6. **Update.** `updateUser` (PUT `/users/{userId}`) — **PUT replaces the whole
   resource**. Always GET, modify the returned object, then PUT it back; omitted fields
   may be reset to null or default. Tolerate unknown fields in the response: 8x8 adds
   attributes without a version bump.
7. **Deprovision.** `deleteUser` (DELETE `/users/{userId}`), then poll the returned
   operation.

## Rules

- **Rate limits.** 100 requests/minute per API key, burst 20 in a 10-second window, and
  **10 concurrent in-flight async operations per organization**. Watch
  `x-ratelimit-remaining`; on `429` wait until `x-ratelimit-reset` then back off
  exponentially (2s, 4s, 8s, 16s, 32s).
- **Errors are RFC 7807 problem details** (`status`, `title`, `detail`, `errors[]` with
  `field`/`code`/`message`, plus `requestId` and `responseId`). Capture `requestId` and
  `responseId` — 8x8 support requires both.
- **Common codes:** `VALIDATION_ERROR`, `INVALID_FILTER`, `INVALID_SORT`,
  `INVALID_PAGE_SIZE`, `FORBIDDEN` (often a customer-ID mismatch), `NOT_FOUND`,
  `RATE_LIMIT_EXCEEDED`.
- **No server-side idempotency key on this suite.** 8x8's own guidance is to implement
  idempotency client-side for safe retries and to handle duplicate submissions
  gracefully; correlate by operation ID before re-issuing a create.
- **Breaking changes get 12 months' notice** (90 days for emergency changes) — see
  `lifecycle/8x8-lifecycle.yml`.
