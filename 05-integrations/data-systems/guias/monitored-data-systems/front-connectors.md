---
title: "Front"
slug: "front-connectors"
status: "update"
updated: 2026-08-11T10:11:02Z
published: 2026-08-11T10:11:10Z
canonical: "helpcenter.securiti.ai/front-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Front

Front is a shared inbox and customer relationship management software that offers integration with other services like Gmail, Twilio, and Twitter. It provides a centralized platform for all conversations, letting you manage them in one place.

The Front connector lets you integrate your Front environment with Securiti to discover and govern both the structured contact and workflow data and the unstructured conversation content generated across your shared inboxes and communication channels.

Front falls under the category of monitored, hybrid data systems. For more information, see [data systems classification](/latest/docs/managing-data-system-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Front (Self-hosted) | - DSR Automation using Full Scan |

### Supported pod types for self-hosted connector

- Standard Securiti pod
- Elastic pods (EDSS)

### Supported authentication methods

- Front application based authentication
  - API Key based authentication

### Supported items for DSR automation

Securiti supports full scan DSR Automation for Front data systems.

### Prerequisites for configuring Front in Securiti

You must complete these prerequisites before connecting your Front connector with Securiti.

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your Front with a self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints.

For more information on configuring pods, see [Securiti pods](/latest/docs/securiti-pods-and-elastic-pods).

#### 2. Admin access

You must have access to use minimum API Permissions for successful connector authentication.

#### 3. Permissions and use cases for Front

This section covers use cases and permissions required for Front (Self-hosted) connectors.

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| - Data Subject Request (DSR) Automation Indexing | You must grant admin consent to all API permissions. | - Minimum **API Permissions** for successful Connector authentication: - Access to: - Create API token - Select scope for API | These permissions let Securiti to read the files and schema metadata in Front to build the Personal Data Index for DSR Automation. |

### Steps to connect your Front with Securiti

To configure the Front connector, perform the following procedures in sequence:

1. [Obtain authentication credentials from Front application](/latest/docs/obtain-authentication-credentials-from-front-application).
2. [Connect Front connector with Securiti](/latest/docs/connect-front-connector-with-securiti).
3. [Configuring General scan settings for Front](/latest/docs/initiate-data-scanning-for-front).

#### Additional resources

- [Table training for structured and hybrid data systems](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems).
- [Object scanning in Front](/v1/docs/object-scanning-in-front).
- [Fulfilling Front DSR requests](/v1/docs/fulfilling-front-dsr-requests).
