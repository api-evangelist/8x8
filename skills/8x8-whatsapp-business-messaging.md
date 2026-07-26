---
name: Send WhatsApp and chat-app messages with 8x8
description: Send templated and session messages over WhatsApp Business, RCS, Viber, LINE
  and Zalo through the 8x8 Business Messaging (Chat Apps) API, including template
  management and delivery tracking.
api: openapi/8x8-connect-business-messaging-api.json
base_url: https://chatapps.8x8.com
operations:
- get-whatsapp-templates
- add-whatsapp-template
- Send-Message
- send-message-many
- get-chatapps-message-details
- mark-message-read
- send-typing-indicator
- Add-Webhooks-1
- Upload-File
generated: '2026-07-25'
method: generated
---

# Send WhatsApp and chat-app messages with 8x8

## Authentication

Bearer token in the `Authorization` header, per subaccount. Regional hosts:
`chatapps.8x8.com`, `chatapps.us.8x8.com`, `chatapps.8x8.uk`, `chatapps.8x8.id`.

Two identity scopes matter here: `accountId` owns channels, templates and webhooks;
`subAccountId` owns sends and message state. Use the right one per path.

## Steps

1. **Register a delivery webhook first.** `Add-Webhooks-1` (POST
   `/api/v1/accounts/{accountId}/webhooks`). Chat-app outcomes are asynchronous — without
   a webhook you are reduced to polling. Event catalogue:
   `asyncapi/8x8-events-webhooks.yml`.
2. **Check the templates you may send.** `get-whatsapp-templates` (GET
   `/api/v1/accounts/{accountId}/channels/{channelId}/templates`). Outside the 24-hour
   customer service window WhatsApp only permits approved templates.
3. **Add a template if needed.** `add-whatsapp-template` (POST, same path). Approval is
   asynchronous and lives on Meta's side, not 8x8's — poll the template list.
4. **Upload media if the message carries it.** `Upload-File` (POST
   `/api/v1/subaccounts/{subAccountId}/files`).
5. **Send.** `Send-Message` (POST `/api/v1/subaccounts/{subAccountId}/messages`) for one,
   `send-message-many` (POST `.../messages/batch`) for volume. Configure the fallback
   channel/delay in the request when you want automatic failover (for example WhatsApp →
   SMS).
6. **Signal presence (optional).** `send-typing-indicator` (POST
   `/api/v1/subaccounts/{subAccountId}/events`) and `mark-message-read` (POST
   `.../messages/{umid}/read`) for a two-way conversational experience.
7. **Track.** `get-chatapps-message-details` (GET `.../messages/{umid}`), or consume the
   delivery-receipt webhook.

## Rules

- **Template errors are their own class.** Codes `3030`–`3060` cover template name,
  language, parameter count, parameter type, component combination and deletion states.
  `3038` is "Template not found", `3033` "Too much template parameters passed", `3060`
  "Template is being deleted". Full registry: `errors/8x8-error-codes.yml`.
- **Channel-specific identity errors:** `3016` missed WeChatUserId, `3019` missed
  FacebookUserId, `3028` missed ZaloUserId, `3047` missed WhatsApp UserID, `3050` missed
  KakaoId. Check you are populating the identifier the target channel requires.
- **Fallback configuration is validated:** `3022`–`3027` and `3051` cover invalid
  fallback channel, delay range, status and subaccount channel.
- **Error envelope** is `{code, message, errorId, timestamp}` — branch on `code`, keep
  `errorId` for support.
- **No idempotency key.** Retrying a send after a timeout can deliver twice; de-duplicate
  on your own client message id before retrying.
