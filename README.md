# 8x8

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
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

8x8, Inc. is a San Jose, California headquartered cloud communications provider that sells an integrated UCaaS, CCaaS and CPaaS platform (marketed as XCaaS) to business buyers in its home market of the United States and internationally. In the telecom value chain 8x8 sits in the aggregator half of the market, not the mobile network operator half: it does not own radio spectrum, and it resells carrier voice and messaging connectivity while adding contact center, unified communications, video (it owns and operates Jitsi as a Service) and analytics on top. Its API posture is genuinely developer-first for a company of its size — developer.8x8.com is a real self-serve portal, sign-up runs through the 8x8 Connect console, and the entire documentation site including 34 OpenAPI 3.x definitions is published openly on GitHub at 8x8Cloud/public-developer-docs. What 8x8 does not do is the network-API layer: there is no CAMARA reference, no GSMA Open Gateway participation, no Aduna channel, no TM Forum Open API conformance and no CIBA anywhere in its public developer corpus. 8x8 competes with Twilio, Vonage and Sinch on application-layer communications APIs, and buys the underlying network access rather than exposing it.

**Areas:** Telecommunications · United States · CPaaS · UCaaS · CCaaS · Contact Center · Messaging · SMS · Voice · Video · Identity Verification · Webhook

## 8x8 on APIs.io

Everything profiled for 8x8 is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/8x8/](https://apis.io/providers/8x8/)** — or go straight to one of the APIs or properties below.

### APIs (70)

- [8x8 Event Streaming API](https://apis.io/apis/8x8/8x8-event-streaming/) — Real-time contact center event stream delivered over the Apache Pulsar WebSocket interface. Clients connect to…
- [Jitsi as a Service (JaaS)](https://apis.io/apis/8x8/jitsi-as-a-service/) — 8x8's hosted Jitsi Meet video platform, integrated through the Jitsi IFrame API (commands, events and functions) and authorized with RS256-signed JWTs…
- [8x8 CPaaS Voice Webhooks](https://apis.io/apis/8x8/8x8-cpaas-voice-webhooks/) — Subaccount-level HTTP POST callbacks emitted by the 8x8 CPaaS voice platform: VSS (Voice Session Summary) for end-of-session outcomes, VCA (Voice Call…
- [8x8 Addresses API](https://apis.io/apis/8x8/8x8-addresses-api/) — The Addresses API from 8x8 — 2 operation(s) for addresses.
- [8x8 Agent Activity API](https://apis.io/apis/8x8/8x8-agent-activity-api/) — The Agent Activity API from 8x8 — 1 operation(s) for agent activity.
- [8x8 Agent status API](https://apis.io/apis/8x8/8x8-agent-status-api/) — Manages and obtains the status for tenant agents
- [8x8 Agents API](https://apis.io/apis/8x8/8x8-agents-api/) — This API retrieves realtime metrics related to agents for a given queue or group.
- [8x8 Analytics API](https://apis.io/apis/8x8/8x8-analytics-api/) — The Analytics API from 8x8 — 9 operation(s) for analytics.
- [8x8 Attachments API](https://apis.io/apis/8x8/8x8-attachments-api/) — Allows adding and retrieving attachments of a conversation.
- [8x8 Audit API](https://apis.io/apis/8x8/8x8-audit-api/) — Audit api
- [8x8 Authentication API](https://apis.io/apis/8x8/8x8-authentication-api/) — Creates access tokens for endpoint access.
- [8x8 Batch API](https://apis.io/apis/8x8/8x8-batch-api-api/) — The Batch API API from 8x8 — 7 operation(s) for batch api.
- [8x8 Buckets API](https://apis.io/apis/8x8/8x8-buckets-api/) — Manage buckets
- [8x8 Bulk Downloads API](https://apis.io/apis/8x8/8x8-bulk-downloads-api/) — Bulk content operations
- [8x8 Call Details API](https://apis.io/apis/8x8/8x8-call-details-api/) — The Call Details API from 8x8 — 1 operation(s) for call details.
- [8x8 Call Queue Data Table API](https://apis.io/apis/8x8/8x8-call-queue-data-table-api/) — The Call Queue Data Table API from 8x8 — 1 operation(s) for call queue data table.
- [8x8 Call Queue Metrics API](https://apis.io/apis/8x8/8x8-call-queue-metrics-api/) — The Call Queue Metrics API from 8x8 — 1 operation(s) for call queue metrics.
- [8x8 Campaign Control API](https://apis.io/apis/8x8/8x8-campaign-control-api/) — Start, stop, pause campaigns
- [8x8 Cards API](https://apis.io/apis/8x8/8x8-cards-api/) — The Cards API from 8x8 — 3 operation(s) for cards.
- [8x8 Channels API](https://apis.io/apis/8x8/8x8-channels-api/) — Enables ChatAPI channel registration and association with a webhook containing channel.
- [8x8 Chat API](https://apis.io/apis/8x8/8x8-chat-api/) — Send and receive public Chat Room messages
- [8x8 Common Models Dont Remove API](https://apis.io/apis/8x8/8x8-common-models-dont-remove-api/) — The Common Models Dont Remove API from 8x8 — 1 operation(s) for common models dont remove.
- [8x8 Contacts API](https://apis.io/apis/8x8/8x8-contacts-api-api/) — The Contacts API API from 8x8 — 3 operation(s) for contacts api.
- [8x8 Conversations API](https://apis.io/apis/8x8/8x8-conversations-api/) — Provides Contact Center interaction capabilities.
- [8x8 Engage API](https://apis.io/apis/8x8/8x8-engage-api-api/) — The Engage API API from 8x8 — 2 operation(s) for engage api.
- [8x8 Evaluations API](https://apis.io/apis/8x8/8x8-evaluations-api/) — The Evaluations API from 8x8 — 3 operation(s) for evaluations.
- [8x8 External Campaign API](https://apis.io/apis/8x8/8x8-external-campaign-api-api/) — External customer-facing endpoints for campaign management
- [8x8 File Upload API](https://apis.io/apis/8x8/8x8-file-upload-api-api/) — The File Upload API API from 8x8 — 2 operation(s) for file upload api.
- [8x8 Groups API](https://apis.io/apis/8x8/8x8-groups-api-api/) — The Groups API API from 8x8 — 3 operation(s) for groups api.
- [8x8 Groups API](https://apis.io/apis/8x8/8x8-groups-api/) — This API retrieves realtime metrics related to groups.
- [8x8 Interactions API](https://apis.io/apis/8x8/8x8-interactions-api/) — The Interactions API from 8x8 — 11 operation(s) for interactions.
- [8x8 Interactions Insight API](https://apis.io/apis/8x8/8x8-interactions-insight-api/) — Retrieve interaction insights for a customer
- [8x8 Jwk Keys API](https://apis.io/apis/8x8/8x8-jwkkeys-api/) — An API that offers JWK public key access to customers.
- [8x8 Management API](https://apis.io/apis/8x8/8x8-management-api-api/) — The Management API API from 8x8 — 10 operation(s) for management api.
- [8x8 Messages API](https://apis.io/apis/8x8/8x8-messages-api/) — Allows adding and retrieving messages of a conversation.
- [8x8 Miscellaneous API](https://apis.io/apis/8x8/8x8-miscellaneous-api/) — The Miscellaneous API from 8x8 — 4 operation(s) for miscellaneous.
- [8x8 Number Lookup API](https://apis.io/apis/8x8/8x8-number-lookup-api-api/) — The Number Lookup API API from 8x8 — 1 operation(s) for number lookup api.
- [8x8 Objects API](https://apis.io/apis/8x8/8x8-objects-api/) — Manage objects
- [8x8 Operations API](https://apis.io/apis/8x8/8x8-operations-api/) — The Operations API from 8x8 — 1 operation(s) for operations.
- [8x8 Participants API](https://apis.io/apis/8x8/8x8-participants-api/) — Enables participants access control.
- [8x8 Pbxes API](https://apis.io/apis/8x8/8x8-pbxes-api/) — The Pbxes API from 8x8 — 1 operation(s) for pbxes.
- [8x8 Phone calls API](https://apis.io/apis/8x8/8x8-phone-calls-api/) — Manages and assigns phone contacts along with transaction codes and interaction IDs
- [8x8 Queue Agent Activity API](https://apis.io/apis/8x8/8x8-queue-agent-activity-api/) — The Queue Agent Activity API from 8x8 — 1 operation(s) for queue agent activity.
- [8x8 Queues API](https://apis.io/apis/8x8/8x8-queues-api/) — This API retrieves real-time metrics related to queues
- [8x8 Queues per PBX API](https://apis.io/apis/8x8/8x8-queues-per-pbx-api/) — The Queues per PBX API from 8x8 — 1 operation(s) for queues per pbx.
- [8x8 Queues Per Site API](https://apis.io/apis/8x8/8x8-queues-per-site-api/) — The Queues Per Site API from 8x8 — 1 operation(s) for queues per site.
- [8x8 Record Management API](https://apis.io/apis/8x8/8x8-record-management-api/) — Add and remove records from campaigns
- [8x8 Recording API](https://apis.io/apis/8x8/8x8-recording-api-api/) — The Recording API API from 8x8 — 2 operation(s) for recording api.
- [8x8 Report Access API](https://apis.io/apis/8x8/8x8-report-access-api/) — Create Reports, access report content and metadata
- [8x8 Report Defintions API](https://apis.io/apis/8x8/8x8-report-defintions-api/) — The Report Defintions API from 8x8 — 2 operation(s) for report defintions.
- [8x8 Reporting API](https://apis.io/apis/8x8/8x8-reporting-api-api/) — The Reporting API API from 8x8 — 10 operation(s) for reporting api.
- [8x8 Ring Groups API](https://apis.io/apis/8x8/8x8-ringgroups-api/) — The RingGroups API from 8x8 — 3 operation(s) for ringgroups.
- [8x8 Send Message API](https://apis.io/apis/8x8/8x8-send-message-api-api/) — The Send Message API API from 8x8 — 6 operation(s) for send message api.
- [8x8 Send Message Event API](https://apis.io/apis/8x8/8x8-send-message-event-api-api/) — The Send Message Event API API from 8x8 — 2 operation(s) for send message event api.
- [8x8 Send SMS API](https://apis.io/apis/8x8/8x8-send-sms-api-api/) — The Send SMS API API from 8x8 — 5 operation(s) for send sms api.
- [8x8 Sites API](https://apis.io/apis/8x8/8x8-sites-api/) — The Sites API from 8x8 — 3 operation(s) for sites.
- [8x8 Speech Analytics API](https://apis.io/apis/8x8/8x8-speech-analytics-api/) — The Speech Analytics API from 8x8 — 4 operation(s) for speech analytics.
- [8x8 Transcript Summaries API](https://apis.io/apis/8x8/8x8-transcript-summaries-api/) — Retrieve transcript summaries for interactions
- [8x8 Users API](https://apis.io/apis/8x8/8x8-users-api/) — The Users API from 8x8 — 6 operation(s) for users.
- [8x8 Verification API](https://apis.io/apis/8x8/8x8-verification-api-api/) — Phone number verification via SMS, WhatsApp, Viber, voice calls, and Silent Mobile Authentication (SMA). Supports OTP generation, delivery, and validation…
- [8x8 Virtual Number Management API](https://apis.io/apis/8x8/8x8-virtual-number-management-api-api/) — The Virtual Number Management API API from 8x8 — 2 operation(s) for virtual number management api.
- [8x8 Voice Messaging API](https://apis.io/apis/8x8/8x8-voice-messaging-api/) — The Voice Messaging API from 8x8 — 1 operation(s) for voice messaging.
- [8x8 Voice Profile API](https://apis.io/apis/8x8/8x8-voice-profile-api-api/) — The Voice Profile API API from 8x8 — 1 operation(s) for voice profile api.
- [8x8 Webhook Configuration API](https://apis.io/apis/8x8/8x8-webhook-configuration-api-api/) — The Webhook Configuration API API from 8x8 — 1 operation(s) for webhook configuration api.
- [8x8 Webhooks API](https://apis.io/apis/8x8/8x8-webhooks-api-api/) — The Webhooks API API from 8x8 — 2 operation(s) for webhooks api.
- [8x8 Web Hooks API](https://apis.io/apis/8x8/8x8-webhooks-api/) — Enables webhook definitions that can be associated to channels.
- [8x8 Workflow Definition Management API](https://apis.io/apis/8x8/8x8-workflow-definition-management-api/) — The Workflow Definition Management API from 8x8 — 3 operation(s) for workflow definition management.
- [8x8 Workflow Instance Management API](https://apis.io/apis/8x8/8x8-workflow-instance-management-api/) — The Workflow Instance Management API from 8x8 — 3 operation(s) for workflow instance management.
- [8x8 Workflow Triggers API](https://apis.io/apis/8x8/8x8-workflow-triggers-api/) — The Workflow Triggers API from 8x8 — 1 operation(s) for workflow triggers.
- [8x8 Phone Numbers API](https://apis.io/apis/8x8/8x8-phone-numbers-api/) — The Phone Numbers API from 8x8 — 2 operation(s) for phone numbers.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [8X8 Events Webhooks](https://apis.io/asyncapis/8x8/8x8-events-webhooks/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [8x8](https://apis.io/servers/8x8/8x8/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [8X8 Agentic Access](https://apis.io/agentic-access/8x8/8x8-agentic-access/)

#### Collections (61)

Postman and Open Collection request collections.

- [8x8 Contact Center Chat API V2](https://apis.io/collections/8x8/open-8x8-actions-events-8x8-contact-center-chat-api-v2/)
- [8x8 Contact Center Dynamic Campaigns](https://apis.io/collections/8x8/open-8x8-actions-events-8x8-contact-center-dynamic-campaigns/)
- [Contact Center Campaigns API](https://apis.io/collections/8x8/open-8x8-actions-events-8x8-contact-center-new-campaigns/)
- [Chapi - Chat API](https://apis.io/collections/8x8/open-8x8-actions-events-chapi---chat-api/)
- [Contact Center Agent Status API](https://apis.io/collections/8x8/open-8x8-actions-events-contact-center-agent-status-api/)
- [8x8 Contact Center Call API Reference](https://apis.io/collections/8x8/open-8x8-actions-events-contact-center-call-api/)
- [8x8 Analytics for Contact Center Historical Metrics API](https://apis.io/collections/8x8/open-8x8-analytics-8x8-analytics-for-contact-center-historical-metrics-api/)
- [8x8 Analytics for Contact Center Real-time Metrics API](https://apis.io/collections/8x8/open-8x8-analytics-8x8-analytics-for-contact-center-real-time-metrics-api/)
- [Audit Records API](https://apis.io/collections/8x8/open-8x8-analytics-audit-records-api/)
- [Cloud Storage Service Public API](https://apis.io/collections/8x8/open-8x8-analytics-cloud-storage-service-public-api/)
- [Customer 360 API](https://apis.io/collections/8x8/open-8x8-analytics-customer-360-public-api/)
- [Quality Management and Speech Analytics API](https://apis.io/collections/8x8/open-8x8-analytics-quality-management-and-speech-analytics-api/)
- [Work Analytics](https://apis.io/collections/8x8/open-8x8-analytics-work-analytics/)
- [Work Analytics Customer Data](https://apis.io/collections/8x8/open-8x8-analytics-work-analytics-customer-data/)
- [Work Analytics Historical](https://apis.io/collections/8x8/open-8x8-analytics-work-analytics-historical/)
- [Automation API](https://apis.io/collections/8x8/open-8x8-connect-automation-api/)
- [Business Messaging API](https://apis.io/collections/8x8/open-8x8-connect-business-messaging-api/)
- [Common models](https://apis.io/collections/8x8/open-8x8-connect-common-models/)
- [Configuration API](https://apis.io/collections/8x8/open-8x8-connect-configuration-api/)
- [Contacts API](https://apis.io/collections/8x8/open-8x8-connect-contacts-api/)
- [Number Lookup API](https://apis.io/collections/8x8/open-8x8-connect-number-lookup-api/)
- [Number Masking API](https://apis.io/collections/8x8/open-8x8-connect-number-masking-api/)
- [SMS API](https://apis.io/collections/8x8/open-8x8-connect-sms-api/)
- [Verification API](https://apis.io/collections/8x8/open-8x8-connect-verification-api/)
- [Video Interaction API](https://apis.io/collections/8x8/open-8x8-connect-video-interaction-api/)
- …and 36 more published on APIs.io

#### Overlays (35)

OpenAPI overlays, including conversational phrasing for each operation.

- [8X8 Actions Events 8X8 Contact Center Chat Api V2 Overlay](https://apis.io/overlays/8x8/8x8-actions-events-8x8-contact-center-chat-api-v2-overlay/)
- [8X8 Actions Events 8X8 Contact Center Dynamic Campaigns Overlay](https://apis.io/overlays/8x8/8x8-actions-events-8x8-contact-center-dynamic-campaigns-overlay/)
- [8X8 Actions Events 8X8 Contact Center New Campaigns Overlay](https://apis.io/overlays/8x8/8x8-actions-events-8x8-contact-center-new-campaigns-overlay/)
- [8X8 Actions Events Chapi   Chat Api Overlay](https://apis.io/overlays/8x8/8x8-actions-events-chapi---chat-api-overlay/)
- [8X8 Actions Events Contact Center Agent Status Api Overlay](https://apis.io/overlays/8x8/8x8-actions-events-contact-center-agent-status-api-overlay/)
- [8X8 Actions Events Contact Center Call Api Overlay](https://apis.io/overlays/8x8/8x8-actions-events-contact-center-call-api-overlay/)
- [8X8 Actions Events Contact Center Chat Gateway V1 Overlay](https://apis.io/overlays/8x8/8x8-actions-events-contact-center-chat-gateway-v1-overlay/)
- [8X8 Administration Address Api V1 Overlay](https://apis.io/overlays/8x8/8x8-administration-address-api-v1-overlay/)
- [8X8 Administration Operation Api V1 Overlay](https://apis.io/overlays/8x8/8x8-administration-operation-api-v1-overlay/)
- [8X8 Administration Phonenumber Api V1 Overlay](https://apis.io/overlays/8x8/8x8-administration-phonenumber-api-v1-overlay/)
- [8X8 Administration Ringgroup Api V1 Overlay](https://apis.io/overlays/8x8/8x8-administration-ringgroup-api-v1-overlay/)
- [8X8 Administration Site Api V1 Overlay](https://apis.io/overlays/8x8/8x8-administration-site-api-v1-overlay/)
- [8X8 Administration User Api V1 Overlay](https://apis.io/overlays/8x8/8x8-administration-user-api-v1-overlay/)
- [8X8 Analytics 8X8 Analytics For Contact Center Historical Metrics Api Overlay](https://apis.io/overlays/8x8/8x8-analytics-8x8-analytics-for-contact-center-historical-metrics-api-overlay/)
- [8X8 Analytics 8X8 Analytics For Contact Center Real Time Metrics Api Overlay](https://apis.io/overlays/8x8/8x8-analytics-8x8-analytics-for-contact-center-real-time-metrics-api-overlay/)
- [8X8 Analytics Audit Records Api Overlay](https://apis.io/overlays/8x8/8x8-analytics-audit-records-api-overlay/)
- [8X8 Analytics Cloud Storage Service Public Api Overlay](https://apis.io/overlays/8x8/8x8-analytics-cloud-storage-service-public-api-overlay/)
- [8X8 Analytics Customer 360 Public Api Overlay](https://apis.io/overlays/8x8/8x8-analytics-customer-360-public-api-overlay/)
- [8X8 Analytics Quality Management And Speech Analytics Api Overlay](https://apis.io/overlays/8x8/8x8-analytics-quality-management-and-speech-analytics-api-overlay/)
- [8X8 Analytics Work Analytics Customer Data Overlay](https://apis.io/overlays/8x8/8x8-analytics-work-analytics-customer-data-overlay/)
- [8X8 Analytics Work Analytics Historical Overlay](https://apis.io/overlays/8x8/8x8-analytics-work-analytics-historical-overlay/)
- [8X8 Analytics Work Analytics Overlay](https://apis.io/overlays/8x8/8x8-analytics-work-analytics-overlay/)
- [8X8 Connect Automation Api Overlay](https://apis.io/overlays/8x8/8x8-connect-automation-api-overlay/)
- [8X8 Connect Business Messaging Api Overlay](https://apis.io/overlays/8x8/8x8-connect-business-messaging-api-overlay/)
- [8X8 Connect Common Models Overlay](https://apis.io/overlays/8x8/8x8-connect-common-models-overlay/)
- …and 10 more published on APIs.io

#### Governance rules (1)

Spectral rulesets for the provider's contracts.

- [8x8 — api standards rules](https://apis.io/rules/8x8/8x8-api-standards-spectral-rules/)

#### Security (4)

Authentication, trust centre, and vulnerability disclosure.

- [8X8 Authentication](https://apis.io/security/8x8/8x8-authentication/)
- [8X8 Domain Security](https://apis.io/security/8x8/8x8-domain-security/)
- [8X8 Trust Center](https://apis.io/security/8x8/8x8-trust-center/)
- [8X8 Vulnerability Disclosure](https://apis.io/security/8x8/8x8-vulnerability-disclosure/)

#### OAuth scopes (1)

The permissions the API asks for.

- [8X8 Scopes](https://apis.io/scopes/8x8/8x8-scopes/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [8X8 Plans Pricing](https://apis.io/plans/8x8/8x8-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [8X8 Rate Limits](https://apis.io/rate-limits/8x8/8x8-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.8x8.com/)
- [Documentation](https://developer.8x8.com/connect)
- [Getting started](https://developer.8x8.com/connect/docs/getting-started)
- [API reference](https://developer.8x8.com/connect/reference)
- [Pricing](https://cpaas.8x8.com/en/pricing/)
- [Sign up](https://connect.8x8.com/)
- [Support](https://support.8x8.com/)
- [Changelog](https://developer.8x8.com/administration/changelog)
- [Security](https://cpaas.8x8.com/en/security/)
- [Compliance](https://www.8x8.com/why-8x8/security-and-compliance)
- [Terms of service](https://www.8x8.com/terms-and-conditions/api-license-agreement)
- [Privacy policy](https://cpaas.8x8.com/en/privacy-policy/)
- [GitHub](https://github.com/8x8Cloud)
- [Status](https://status.8x8.com)

## API Evangelist rating

**Kin Score 71.3** — exemplar · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 78.6 |
| Contract quality | 64.6 |
| Contract governance | 50.0 |
| Operational transparency | 92.1 |
| Developer ergonomics | 68.0 |
| Access clarity | 38.2 |

**Agent readiness 41.0** — agent-native

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | verified |
| MCP Server | — |
| Auth Clarity | bearer (partial credit) |
| Idempotency | documented (partial credit) |
| Error Semantics | verified |
| OpenAPI Examples | verified |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | yes |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | — |
| Operation Distinctiveness | — |

**Regulatory alignment 45.4** — Telecommunications

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/8x8/](https://apis.io/providers/8x8/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for 8x8: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/8x8/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
