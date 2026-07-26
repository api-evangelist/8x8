---
name: Control a contact center call with 8x8
description: Read and set agent status, place an agent-assigned outbound call, apply
  transaction codes and hang up lines on the 8x8 Contact Center Actions & Events APIs.
api: openapi/8x8-actions-events-contact-center-call-api.json
base_url: https://vcc-na30.8x8.com/api/v1
operations:
- getagentsstatus
- getagentstatus
- setagentstatus
- setagentsstatuses
- placePhoneCall
- addTransactionCodes
- hangupAgentHandlingInteraction
- hangupAgentLine
- hangupAgentLines
- deletePhoneInteraction
generated: '2026-07-25'
method: generated
---

# Control a contact center call with 8x8

## Authentication

HTTP **Basic** auth using the credentials from **Configuration Manager → Integration →
API Token**. These are contact-center tenant credentials, not the `eght_` Admin Console
API key used by the Administration suite.

## Pick the right host — this API is region-pinned

The Call API and Agent Status API are served from your tenant's own contact-center
platform host, not from `api.8x8.com`. The specs enumerate 40+ regional hosts
(`vcc-na1..na40`, `vcc-eu2..eu12`, `vcc-ap1`, `vcc-au1`, `vcc-ca1/ca2`, and
`odcc2.bell.ca` for the Bell Canada deployment). Resolve your tenant's host once and pin
it — calling the wrong region returns an authorization failure, not a redirect. Every
path is scoped by `{tenantId}`.

## Steps

1. **Read agent state.** `getagentsstatus` (GET
   `/tenants/{tenantId}/agentstatus/agents`, filterable) for the floor, or
   `getagentstatus` (GET `/tenants/{tenantId}/agentstatus/agents/{agentId}`) for one
   agent. Never place work on an agent without checking state first.
2. **Set agent state.** `setagentstatus` (PUT
   `/tenants/{tenantId}/agentstatus/agents/{agentId}`) for one agent, or
   `setagentsstatuses` (POST `/tenants/{tenantId}/agentstatus/agents/bulk`) for a bulk
   change. Use the bulk operation for shift transitions rather than looping.
3. **Place the call.** `placePhoneCall` (POST `/tenants/{tenantId}/calls`) creates an
   **agent-assigned outbound phone interaction**. Keep the returned `interactionId`.
4. **Code the interaction.** `addTransactionCodes` (PUT
   `/tenants/{tenantId}/calls/{interactionId}/agent/{agentId}/transaction-codes`) amends
   transaction codes for both the interaction and the agent leg — do this during or
   immediately after wrap-up.
5. **End it.** `hangupAgentHandlingInteraction` (DELETE
   `/tenants/{tenantId}/calls/{interactionId}/agent/{agentId}`) drops the agent from the
   call (on a conference, only that agent's leg); `deletePhoneInteraction` (DELETE
   `/tenants/{tenantId}/calls/{interactionId}`) ends the whole interaction.
6. **Free the lines.** `hangupAgentLines` (DELETE
   `/tenants/{tenantId}/agents/{agentId}/calls`) frees all of an agent's lines to take the
   next call; `hangupAgentLine` (DELETE `.../calls/line/{lineNo}`) frees one.

## Rules

- **These are safety-relevant writes.** Hangups and status changes affect a live human
  conversation. Treat them as high-consequence, require an explicit confirmation before an
  agent invokes them autonomously, and audit them — see
  `agentic-access/8x8-agentic-access.yml`.
- **Observe, don't poll.** Agent and interaction state changes are published on the 8x8
  Event Streaming service (Apache Pulsar over WebSocket:
  `AgentStatusChange`, `InteractionCreated`, `InteractionAssigned`, `InteractionDeleted`,
  …). Subscribe rather than polling `getagentsstatus`. Catalogue:
  `asyncapi/8x8-events-webhooks.yml`.
- **No idempotency key.** A retried `placePhoneCall` can dial twice — confirm state via
  the event stream before retrying.
- **Do not hard-code the region host** into shared code; make it tenant configuration.
