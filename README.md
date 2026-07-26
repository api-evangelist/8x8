# 8x8 (8x8)

8x8, Inc. is a San Jose, California headquartered cloud communications provider that sells an integrated UCaaS, CCaaS and CPaaS platform (marketed as XCaaS) to business buyers in its home market of the United States and internationally. In the telecom value chain 8x8 sits in the aggregator half of the market, not the mobile network operator half: it does not own radio spectrum, and it resells carrier voice and messaging connectivity while adding contact center, unified communications, video (it owns and operates Jitsi as a Service) and analytics on top. Its API posture is genuinely developer-first for a company of its size — developer.8x8.com is a real self-serve portal, sign-up runs through the 8x8 Connect console, and the entire documentation site including 34 OpenAPI 3.x definitions is published openly on GitHub at 8x8Cloud/public-developer-docs. What 8x8 does not do is the network-API layer: there is no CAMARA reference, no GSMA Open Gateway participation, no Aduna channel, no TM Forum Open API conformance and no CIBA anywhere in its public developer corpus. 8x8 competes with Twilio, Vonage and Sinch on application-layer communications APIs, and buys the underlying network access rather than exposing it.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/8x8/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/8x8/refs/heads/main/apis.yml)

## Tags

- Telecommunications
- United States
- CPaaS
- UCaaS
- CCaaS
- Contact Center
- Messaging
- SMS
- Voice
- Video
- Identity Verification
- Webhooks
- Cloud Communications

## Timestamps

- **Created:** 2026-07-25
- **Modified:** 2026-07-25

## Telecom Standards Posture

- **CAMARA:** no CAMARA reference found. A full-corpus grep of 8x8's own public developer documentation repository (github.com/8x8Cloud/public-developer-docs, 2,342 files, cloned 2026-07-25) returns zero matches for "camara", "open gateway", "sim swap", "silent auth", "network exposure function" or "network slicing". 8x8 does not claim CAMARA and does not implement it.
- **GSMA Open Gateway:** not a participant. No Aduna channel evidenced.
- **TM Forum Open APIs:** no conformance certification evidenced; zero TMF references in the corpus.
- **3GPP exposure:** none — no NEF/SCEF, no network slicing, no edge/MEC API.
- **Where 8x8 actually sits:** the CPaaS/UCaaS aggregator half of the telecom split. It resells carrier connectivity and publishes an application-layer API surface on top of it.

## Developer Surface

- **Developer portal:** [https://developer.8x8.com/](https://developer.8x8.com/) — HTTP 200, real self-serve Docusaurus portal, not a login wall.
- **Sign-up:** [https://connect.8x8.com/](https://connect.8x8.com/) — HTTP 200.
- **Portal source + specs:** [github.com/8x8Cloud/public-developer-docs](https://github.com/8x8Cloud/public-developer-docs) — 34 OpenAPI 3.x definitions under `docs_oas/`, all harvested verbatim into `openapi/`.
- **Auth:** HTTP bearer tokens (CPaaS), `x-api-key` / `8x8-apikey` headers (Administration, Analytics), OAuth2 client-credentials at `https://api.8x8.com/oauth/v2/token` (Contact Center Analytics), HTTP basic (legacy Contact Center), RS256 JWT (JaaS). **No OIDC, no CIBA.**
- **Events:** VSS / VCA / VCS voice webhooks, plus 8x8 Event Streaming over an Apache Pulsar WebSocket proxy. No AsyncAPI published.
- **SDKs:** Voice SDK for Android and iOS, JaaS mobile SDKs, Jitsi IFrame API. No first-party REST client on npm or PyPI.
- **GraphQL / gRPC / public Postman workspace:** none found.

## APIs

### 8x8 Contact Center Chat API V2

8x8 Contact Center Chat API v2 for creating and driving chat conversations, messages and participants inside the contact center.

- **Human URL:** [https://developer.8x8.com/actions-events](https://developer.8x8.com/actions-events)
- **Base URL:** `https://api.8x8.com`

#### Tags

- Contact Center
- Contact Center
- Chat

#### Properties

- [Documentation](https://developer.8x8.com/actions-events)
- [API Reference](https://developer.8x8.com/actions-events)
- [OpenAPI](openapi/8x8-actions-events-8x8-contact-center-chat-api-v2.json)

### 8x8 Contact Center Dynamic Campaigns

8x8 Contact Center Dynamic Campaigns API for injecting and managing records in dynamic outbound campaigns.

- **Human URL:** [https://developer.8x8.com/actions-events](https://developer.8x8.com/actions-events)
- **Base URL:** `https://vcc-ap1.8x8.com/api/tstats/campaigns`

#### Tags

- Contact Center
- Contact Center
- Campaigns
- Outbound

#### Properties

- [Documentation](https://developer.8x8.com/actions-events)
- [API Reference](https://developer.8x8.com/actions-events)
- [OpenAPI](openapi/8x8-actions-events-8x8-contact-center-dynamic-campaigns.json)

### Contact Center Campaigns API

8x8 Contact Center Campaigns API for creating campaigns and managing campaign records for outbound dialing.

- **Human URL:** [https://developer.8x8.com/actions-events](https://developer.8x8.com/actions-events)

#### Tags

- Contact Center
- Contact Center
- Campaigns
- Outbound

#### Properties

- [Documentation](https://developer.8x8.com/actions-events)
- [API Reference](https://developer.8x8.com/actions-events)
- [OpenAPI](openapi/8x8-actions-events-8x8-contact-center-new-campaigns.json)

### Chapi - Chat API

8x8 Chapi chat API for programmatic creation of chat conversations against the contact center chat service.

- **Human URL:** [https://developer.8x8.com/actions-events](https://developer.8x8.com/actions-events)

#### Tags

- Contact Center
- Contact Center
- Chat

#### Properties

- [Documentation](https://developer.8x8.com/actions-events)
- [API Reference](https://developer.8x8.com/actions-events)
- [OpenAPI](openapi/8x8-actions-events-chapi---chat-api.json)

### Contact Center Agent Status API

8x8 Contact Center Agent Status API for reading and setting agent presence and status codes.

- **Human URL:** [https://developer.8x8.com/actions-events](https://developer.8x8.com/actions-events)
- **Base URL:** `https://vcc-na30.8x8.com/api/v1`

#### Tags

- Contact Center
- Contact Center
- Agents
- Presence

#### Properties

- [Documentation](https://developer.8x8.com/actions-events)
- [API Reference](https://developer.8x8.com/actions-events)
- [OpenAPI](openapi/8x8-actions-events-contact-center-agent-status-api.json)

### 8x8 Contact Center Call API Reference

8x8 Contact Center Call API for controlling in-progress phone interactions handled by contact center agents.

- **Human URL:** [https://developer.8x8.com/actions-events](https://developer.8x8.com/actions-events)
- **Base URL:** `https://vcc-na30.8x8.com/api/v1`

#### Tags

- Contact Center
- Contact Center
- Voice
- Call Control

#### Properties

- [Documentation](https://developer.8x8.com/actions-events)
- [API Reference](https://developer.8x8.com/actions-events)
- [OpenAPI](openapi/8x8-actions-events-contact-center-call-api.json)

### Contact Center Chat Gateway

8x8 Contact Center Chat Gateway API for bridging external chat channels into 8x8 Contact Center conversations.

- **Human URL:** [https://developer.8x8.com/actions-events](https://developer.8x8.com/actions-events)
- **Base URL:** `https://api.8x8.com`

#### Tags

- Contact Center
- Contact Center
- Chat
- Gateway

#### Properties

- [Documentation](https://developer.8x8.com/actions-events)
- [API Reference](https://developer.8x8.com/actions-events)
- [OpenAPI](openapi/8x8-actions-events-contact-center-chat-gateway-v1.yml)

### 8x8 Administration - Address Management API

8x8 Administration Address Management API for managing service and emergency addresses attached to sites and users.

- **Human URL:** [https://developer.8x8.com/administration](https://developer.8x8.com/administration)
- **Base URL:** `https://api.8x8.com/admin-provisioning`

#### Tags

- Administration
- Administration
- Addresses
- E911

#### Properties

- [Documentation](https://developer.8x8.com/administration)
- [API Reference](https://developer.8x8.com/administration)
- [OpenAPI](openapi/8x8-administration-address-api-v1.yaml)

### 8x8 Administration - Operations API

8x8 Administration Operations API for tracking the status of long-running provisioning operations.

- **Human URL:** [https://developer.8x8.com/administration](https://developer.8x8.com/administration)
- **Base URL:** `https://api.8x8.com/admin-provisioning`

#### Tags

- Administration
- Administration
- Operations

#### Properties

- [Documentation](https://developer.8x8.com/administration)
- [API Reference](https://developer.8x8.com/administration)
- [OpenAPI](openapi/8x8-administration-operation-api-v1.yaml)

### 8x8 Administration - Phone Number Management API

8x8 Administration Phone Number Management API for listing and assigning telephone numbers within an 8x8 tenant.

- **Human URL:** [https://developer.8x8.com/administration](https://developer.8x8.com/administration)
- **Base URL:** `https://api.8x8.com/admin-provisioning`

#### Tags

- Administration
- Administration
- Numbers
- Telephony

#### Properties

- [Documentation](https://developer.8x8.com/administration)
- [API Reference](https://developer.8x8.com/administration)
- [OpenAPI](openapi/8x8-administration-phonenumber-api-v1.yaml)

### 8x8 Administration - Ring Group Management API

8x8 Administration Ring Group Management API for creating and managing ring groups and their members.

- **Human URL:** [https://developer.8x8.com/administration](https://developer.8x8.com/administration)
- **Base URL:** `https://api.8x8.com/admin-provisioning`

#### Tags

- Administration
- Administration
- Ring Groups
- Telephony

#### Properties

- [Documentation](https://developer.8x8.com/administration)
- [API Reference](https://developer.8x8.com/administration)
- [OpenAPI](openapi/8x8-administration-ringgroup-api-v1.yaml)

### 8x8 Administration - Site Management API

8x8 Administration Site Management API for creating and managing sites within an 8x8 tenant.

- **Human URL:** [https://developer.8x8.com/administration](https://developer.8x8.com/administration)
- **Base URL:** `https://api.8x8.com/admin-provisioning`

#### Tags

- Administration
- Administration
- Provisioning

#### Properties

- [Documentation](https://developer.8x8.com/administration)
- [API Reference](https://developer.8x8.com/administration)
- [OpenAPI](openapi/8x8-administration-site-api-v1.yaml)

### 8x8 Administration - User Management API

8x8 Administration User Management API for provisioning, updating and deprovisioning users across an 8x8 UCaaS/CCaaS tenant.

- **Human URL:** [https://developer.8x8.com/administration](https://developer.8x8.com/administration)
- **Base URL:** `https://api.8x8.com/admin-provisioning`

#### Tags

- Administration
- Administration
- Provisioning
- Identity

#### Properties

- [Documentation](https://developer.8x8.com/administration)
- [API Reference](https://developer.8x8.com/administration)
- [OpenAPI](openapi/8x8-administration-user-api-v1.yaml)

### 8x8 Analytics for Contact Center Historical Metrics API

8x8 Analytics for Contact Center Historical Metrics API for querying historical queue, agent and interaction metrics, secured with OAuth2 client credentials.

- **Human URL:** [https://developer.8x8.com/analytics](https://developer.8x8.com/analytics)
- **Base URL:** `https://api.8x8.com/eu/analytics/cc/v8/historical-metrics`

#### Tags

- Analytics
- Analytics
- Contact Center
- Historical
- OAuth2

#### Properties

- [Documentation](https://developer.8x8.com/analytics)
- [API Reference](https://developer.8x8.com/analytics)
- [OpenAPI](openapi/8x8-analytics-8x8-analytics-for-contact-center-historical-metrics-api.json)

### 8x8 Analytics for Contact Center Real-time Metrics API

8x8 Analytics for Contact Center Real-time Metrics API for live queue, agent and interaction state, secured with OAuth2 client credentials.

- **Human URL:** [https://developer.8x8.com/analytics](https://developer.8x8.com/analytics)
- **Base URL:** `https://api.8x8.com/eu/analytics/cc/v5/realtime-metrics`

#### Tags

- Analytics
- Analytics
- Contact Center
- Real-time
- OAuth2

#### Properties

- [Documentation](https://developer.8x8.com/analytics)
- [API Reference](https://developer.8x8.com/analytics)
- [OpenAPI](openapi/8x8-analytics-8x8-analytics-for-contact-center-real-time-metrics-api.json)

### Audit Records API

8x8 Audit Records API for retrieving administrative audit trail records across the 8x8 platform.

- **Human URL:** [https://developer.8x8.com/analytics](https://developer.8x8.com/analytics)
- **Base URL:** `https://api.8x8.com/administration/audit/v1`

#### Tags

- Analytics
- Audit
- Governance
- Compliance

#### Properties

- [Documentation](https://developer.8x8.com/analytics)
- [API Reference](https://developer.8x8.com/analytics)
- [OpenAPI](openapi/8x8-analytics-audit-records-api.json)

### Cloud Storage Service Public API

8x8 Cloud Storage Service Public API for listing, retrieving and managing call recordings and other stored media across regional storage tenants.

- **Human URL:** [https://developer.8x8.com/analytics](https://developer.8x8.com/analytics)

#### Tags

- Analytics
- Storage
- Recordings
- Media

#### Properties

- [Documentation](https://developer.8x8.com/analytics)
- [API Reference](https://developer.8x8.com/analytics)
- [OpenAPI](openapi/8x8-analytics-cloud-storage-service-public-api.json)

### Customer 360 API

8x8 Customer 360 API for retrieving a consolidated customer interaction profile across 8x8 channels.

- **Human URL:** [https://developer.8x8.com/analytics](https://developer.8x8.com/analytics)
- **Base URL:** `https://api.8x8.com/cidp-customer-360/us`

#### Tags

- Analytics
- Customer 360
- CDP

#### Properties

- [Documentation](https://developer.8x8.com/analytics)
- [API Reference](https://developer.8x8.com/analytics)
- [OpenAPI](openapi/8x8-analytics-customer-360-public-api.json)

### Quality Management and Speech Analytics API

8x8 Quality Management and Speech Analytics API for evaluations, scorecards, transcripts and speech analytics over recorded contact center interactions.

- **Human URL:** [https://developer.8x8.com/analytics](https://developer.8x8.com/analytics)

#### Tags

- Analytics
- Quality Management
- Speech Analytics
- Contact Center

#### Properties

- [Documentation](https://developer.8x8.com/analytics)
- [API Reference](https://developer.8x8.com/analytics)
- [OpenAPI](openapi/8x8-analytics-quality-management-and-speech-analytics-api.json)

### Work Analytics Customer Data

8x8 Work Analytics Customer Data API for retrieving customer-scoped analytics datasets from the 8x8 Work platform.

- **Human URL:** [https://developer.8x8.com/analytics](https://developer.8x8.com/analytics)
- **Base URL:** `https://api.8x8.com/analytics/work`

#### Tags

- Analytics
- Analytics
- UCaaS

#### Properties

- [Documentation](https://developer.8x8.com/analytics)
- [API Reference](https://developer.8x8.com/analytics)
- [OpenAPI](openapi/8x8-analytics-work-analytics-customer-data.json)

### Work Analytics Historical

8x8 Work Analytics Historical API for querying historical unified communications call and meeting records and aggregates.

- **Human URL:** [https://developer.8x8.com/analytics](https://developer.8x8.com/analytics)
- **Base URL:** `https://api.8x8.com/analytics/work`

#### Tags

- Analytics
- Analytics
- Historical
- UCaaS

#### Properties

- [Documentation](https://developer.8x8.com/analytics)
- [API Reference](https://developer.8x8.com/analytics)
- [OpenAPI](openapi/8x8-analytics-work-analytics-historical.json)

### Work Analytics

8x8 Work Analytics API exposing unified communications usage and quality metrics for the 8x8 Work (UCaaS) product.

- **Human URL:** [https://developer.8x8.com/analytics](https://developer.8x8.com/analytics)
- **Base URL:** `https://api.8x8.com/analytics/work`

#### Tags

- Analytics
- Analytics
- UCaaS
- Metrics

#### Properties

- [Documentation](https://developer.8x8.com/analytics)
- [API Reference](https://developer.8x8.com/analytics)
- [OpenAPI](openapi/8x8-analytics-work-analytics.json)

### Automation API

8x8 Automation API for defining, launching and managing communication workflow definitions and workflow instances across channels.

- **Human URL:** [https://developer.8x8.com/connect/reference](https://developer.8x8.com/connect/reference)
- **Base URL:** `https://automation.8x8.com`

#### Tags

- CPaaS
- Automation
- Workflows

#### Properties

- [Documentation](https://developer.8x8.com/connect)
- [API Reference](https://developer.8x8.com/connect/reference)
- [OpenAPI](openapi/8x8-connect-automation-api.json)

### Business Messaging API

8x8 Business Messaging (Chat Apps) API for sending and receiving rich messages over WhatsApp Business, RCS, Viber Business, LINE Official Account, Zalo ZNS and other chat channels.

- **Human URL:** [https://developer.8x8.com/connect/reference](https://developer.8x8.com/connect/reference)
- **Base URL:** `https://chatapps.8x8.com`

#### Tags

- CPaaS
- Messaging
- WhatsApp
- RCS
- Viber
- Chat Apps

#### Properties

- [Documentation](https://developer.8x8.com/connect)
- [API Reference](https://developer.8x8.com/connect/reference)
- [OpenAPI](openapi/8x8-connect-business-messaging-api.json)

### Configuration API

8x8 Connect Configuration API for subaccount-level configuration of the messaging platform.

- **Human URL:** [https://developer.8x8.com/connect/reference](https://developer.8x8.com/connect/reference)
- **Base URL:** `https://sms.8x8.com`

#### Tags

- CPaaS
- Configuration
- Subaccounts

#### Properties

- [Documentation](https://developer.8x8.com/connect)
- [API Reference](https://developer.8x8.com/connect/reference)
- [OpenAPI](openapi/8x8-connect-configuration-api.json)

### Contacts API

8x8 Contacts API for managing contacts and contact groups used as recipients across the Connect messaging and voice products.

- **Human URL:** [https://developer.8x8.com/connect/reference](https://developer.8x8.com/connect/reference)
- **Base URL:** `https://contacts.8x8.com`

#### Tags

- CPaaS
- Contacts
- CRM

#### Properties

- [Documentation](https://developer.8x8.com/connect)
- [API Reference](https://developer.8x8.com/connect/reference)
- [OpenAPI](openapi/8x8-connect-contacts-api.json)

### Number Lookup API

8x8 Number Lookup API that validates phone numbers and returns carrier, portability and reachability data for database hygiene and anti-fraud checks.

- **Human URL:** [https://developer.8x8.com/connect/reference](https://developer.8x8.com/connect/reference)
- **Base URL:** `https://lookup.8x8.com`

#### Tags

- CPaaS
- Number Lookup
- HLR
- Anti-Fraud

#### Properties

- [Documentation](https://developer.8x8.com/connect)
- [API Reference](https://developer.8x8.com/connect/reference)
- [OpenAPI](openapi/8x8-connect-number-lookup-api.json)

### Number Masking API

8x8 Number Masking API that bridges two parties through virtual numbers so neither participant sees the other's real phone number, with call action handling and session summaries.

- **Human URL:** [https://developer.8x8.com/connect/reference](https://developer.8x8.com/connect/reference)
- **Base URL:** `https://voice.8x8.com`

#### Tags

- CPaaS
- Voice
- Number Masking
- Privacy

#### Properties

- [Documentation](https://developer.8x8.com/connect)
- [API Reference](https://developer.8x8.com/connect/reference)
- [OpenAPI](openapi/8x8-connect-number-masking-api.json)

### SMS API

8x8 Connect SMS API for single and batch A2P SMS delivery worldwide, with sender ID handling, encoding control, delivery receipts and message status lookup.

- **Human URL:** [https://developer.8x8.com/connect/reference](https://developer.8x8.com/connect/reference)
- **Base URL:** `https://sms.8x8.com`

#### Tags

- CPaaS
- SMS
- Messaging
- A2P

#### Properties

- [Documentation](https://developer.8x8.com/connect)
- [API Reference](https://developer.8x8.com/connect/reference)
- [OpenAPI](openapi/8x8-connect-sms-api.json)
- [OpenAPI](openapi/8x8-connect-common-models.json)

### Verification API

8x8 Verification API for generating and validating SMS- and voice-based one-time passcodes for mobile number verification and two-factor authentication.

- **Human URL:** [https://developer.8x8.com/connect/reference](https://developer.8x8.com/connect/reference)
- **Base URL:** `https://verify.8x8.com`

#### Tags

- CPaaS
- Verification
- OTP
- 2FA
- Identity

#### Properties

- [Documentation](https://developer.8x8.com/connect)
- [API Reference](https://developer.8x8.com/connect/reference)
- [OpenAPI](openapi/8x8-connect-verification-api.json)

### Video Interaction API

8x8 Video Interaction API for creating and managing agent-to-customer video sessions initiated from a messaging or voice interaction.

- **Human URL:** [https://developer.8x8.com/connect/reference](https://developer.8x8.com/connect/reference)
- **Base URL:** `https://video-agent.8x8.com`

#### Tags

- CPaaS
- Video
- Interaction

#### Properties

- [Documentation](https://developer.8x8.com/connect)
- [API Reference](https://developer.8x8.com/connect/reference)
- [OpenAPI](openapi/8x8-connect-video-interaction-api.json)

### Voice API

8x8 Connect Voice API for programmable outbound and inbound calling, callflows, voice messaging and IVR session control over the 8x8 cloud telephony platform.

- **Human URL:** [https://developer.8x8.com/connect/reference](https://developer.8x8.com/connect/reference)
- **Base URL:** `https://voice.8x8.com`

#### Tags

- CPaaS
- Voice
- Callflow
- IVR

#### Properties

- [Documentation](https://developer.8x8.com/connect)
- [API Reference](https://developer.8x8.com/connect/reference)
- [OpenAPI](openapi/8x8-connect-voice-v1-api.json)

### 8x8 Contact Center Chat API

8x8 Contact Center Chat API for creating conversations, exchanging messages and managing chat participants.

- **Human URL:** [https://developer.8x8.com/contactcenter](https://developer.8x8.com/contactcenter)
- **Base URL:** `https://api.8x8.com`

#### Tags

- Contact Center
- Contact Center
- Chat

#### Properties

- [Documentation](https://developer.8x8.com/contactcenter)
- [API Reference](https://developer.8x8.com/contactcenter)
- [OpenAPI](openapi/8x8-contactcenter-8x8-contact-center-chat-api.json)

### 8x8 Event Streaming API

Real-time contact center event stream delivered over the Apache Pulsar WebSocket interface. Clients connect to wss://{host}/ws/v2/reader/persistent/{tenant}/{namespace}/{topic} on regional 8x8 Pulsar proxies (pulsar-ws-euw2, pulsar-ws-use1, pulsar-ws-usw2) and consume agent, call, queue and interaction events. Documented with Go, Java, Python, Node.js and browser examples. No AsyncAPI document is published.

- **Human URL:** [https://developer.8x8.com/actions-events/docs/streaming/overview](https://developer.8x8.com/actions-events/docs/streaming/overview)

#### Tags

- Contact Center
- Events
- Streaming
- WebSocket
- Apache Pulsar

#### Properties

- [Documentation](https://developer.8x8.com/actions-events/docs/streaming/overview)
- [Documentation](https://developer.8x8.com/actions-events/docs/streaming/connection)

### Jitsi as a Service (JaaS)

8x8's hosted Jitsi Meet video platform, integrated through the Jitsi IFrame API (commands, events and functions) and authorized with RS256-signed JWTs minted from a JaaS API key pair. Mobile SDKs are published for Android and iOS. No OpenAPI document is published for JaaS.

- **Human URL:** [https://developer.8x8.com/jaas](https://developer.8x8.com/jaas)

#### Tags

- Video
- Jitsi
- Meetings
- WebRTC
- JWT

#### Properties

- [Documentation](https://developer.8x8.com/jaas)
- [Documentation](https://developer.8x8.com/jaas/docs/iframe-api-overview)
- [Authentication](https://developer.8x8.com/jaas/docs/api-keys-jwt)

### 8x8 CPaaS Voice Webhooks

Subaccount-level HTTP POST callbacks emitted by the 8x8 CPaaS voice platform: VSS (Voice Session Summary) for end-of-session outcomes, VCA (Voice Call Action) for in-call callflow decisions, and VCS (Voice Call Status) for real-time call status. Payload schemas are documented per product (IVR, Voice Messaging, Number Masking) but are not published as AsyncAPI.

- **Human URL:** [https://developer.8x8.com/connect/docs/voice/webhook-guides/webhooks-overview](https://developer.8x8.com/connect/docs/voice/webhook-guides/webhooks-overview)

#### Tags

- Webhooks
- Voice
- Events
- CPaaS

#### Properties

- [Documentation](https://developer.8x8.com/connect/docs/voice/webhook-guides/webhooks-overview)

## Common Properties

- [Website](https://www.8x8.com/)
- [DeveloperPortal](https://developer.8x8.com/)
- [Documentation](https://developer.8x8.com/connect)
- [APIReference](https://developer.8x8.com/connect/reference)
- [GettingStarted](https://developer.8x8.com/connect/docs/getting-started)
- [SignUp](https://connect.8x8.com/)
- [Authentication](https://developer.8x8.com/connect/docs/security-1)
- [RateLimits](https://developer.8x8.com/connect/docs/api-rate-limiting)
- [Webhooks](https://developer.8x8.com/connect/docs/voice/webhook-guides/webhooks-overview)
- [Partners](https://developer.8x8.com/tech-partner)
- [GitHubOrganization](https://github.com/8x8Cloud)
- [GitHubRepository](https://github.com/8x8Cloud/public-developer-docs)
- [LinkedIn](https://www.linkedin.com/company/8x8)
- [TermsOfService](https://www.8x8.com/terms-and-conditions/api-license-agreement)

## Maintainers

- Kin Lane — kin@apievangelist.com
