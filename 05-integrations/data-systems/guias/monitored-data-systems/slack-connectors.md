---
title: "Slack"
slug: "slack-connectors"
status: "new"
updated: 2026-07-15T06:40:00Z
published: 2026-07-15T06:40:39Z
canonical: "helpcenter.securiti.ai/slack-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Slack

Slack is a messaging app for businesses that connects people to the information they need. By bringing people together to work as one unified team, Slack transforms the way organizations communicate.

Securiti 's Slack data system supports both Slack Pro and Business+ subscription plans, which include a single Slack workspace. If your Slack account has multiple workspaces, i.e., you have an Enterprise Grid plan, use Securiti's “[Slack Enterprise Grid](/latest/docs/slack-enterprise-grid-connectors)” data system. To learn more about pricing plans and features, refer to [Slack documentation](https://app.slack.com/plans/T079EGYQ9QE).

The table below highlights the key differences between Slack and [Slack Enterprise Grid](/latest/docs/slack-enterprise-grid-connectors) features.

| Features | Slack (Self-hosted) | Slack Enterprise Grid (Self-hosted) |
| --- | --- | --- |
| Data system scope | Includes all channels in a single workspace | Includes all workspaces and channels |
| Attachment scanning | Securiti retrieves attachments from the following: - All public channels Securiti does not retrieve attachments from the following: - Private channels - Multi party direct messages (MPDMs) - Direct messages (DMs) | Securiti retrieves attachments from the following: - All public channels - All private channels - All MPDMs - All DMs - Drafts (when the discovery scan is configured for All) - Canvases (when the discovery scan is configured for All) |
| Conversation messages scanning | Securiti does not scan conversations from private channels, public channels, MPDMs, and DMs. | Securiti scans conversations from the following: - All public channels - All private channels - All MPDMs - All DMs |

### Supported Connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Slack (Self-hosted) | - Sensitive Data Intelligence - DSR Automation using Full Scan - Breach Analysis |
| Slack (Securiti-Cloud) | - Sensitive Data Intelligence - DSR Automation using APIs - Security Posture Management - Breach Analysis |

### Supported Pod types

Slack (Self-hosted) supports following pod types:

- Standard Securiti Pod.
- Elastic Pod (ePods)

### Supported authentication methods

Securiti supports OAuth authentication method for Slack Self-hosted and Securiti-Cloud connectors

#### Keyring support for Slack (Self-hosted) connector

You can use a keyring support to store authentication credentials in a vault product during the connector configuration process to securely access your credentials from a vault. For more information, see [Managing Keyrings](/latest/docs/managing-credentials-using-keyrings).

- **HashiCorp**: For more information, see [Configuring HashiCorp credential vaults](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault).

### Supported items for Classification scans

Securiti supports following items for classification scan in Slack.

- All conversations in a Data System

For more information about classification in discovery scans, see [Understanding Discovery Scans](/latest/docs/discovery-scans).

### Prerequisites for configuring Slack Self-hosted connector

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your Slack with a Self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints.

For more information on configuring pods, see [Securiti pods](/latest/docs/pods-cluster-version-v128-and-later).

#### 2. Slack workspace access

You must be a **Full Member** of the Slack workspace to create and install a Slack app and activate the connector.

#### 3. Slack app

You must create a Slack app in your workspace and configure it with the required Redirect URL and OAuth scopes.

#### 4. OAuth configuration

Configure the Slack app with the appropriate **Redirect URL** for your Securiti deployment.

**Redirect URLs**

- US Cloud: `https://app.securiti.ai/static/activateConnector.html`
- US1 Cloud: `https://app1.securiti.ai/static/activateConnector.html`
- Canada Cloud: `https://app3.securiti.ai/static/activateConnector.html`
- EU Cloud: `https://app.eu.securiti.ai/static/activateConnector.html`
- Indonesia Cloud: `https://app2.securiti.ai/static/activateConnector.html`
- Australia Cloud: `https://app4.securiti.ai/static/activateConnector.html`
- UAE Cloud: `https://app5.securiti.ai/static/activateConnector.html`
- Mumbai Cloud: `https://app6.securiti.ai/static/activateConnector.html`
- KSA Cloud: `https://app7.securiti.ai/static/activateConnector.html`
- Qatar Cloud: `https://app8.securiti.ai/static/activateConnector.html`
- Sovereign deployment: `https://&lt;sovereign_deployment_portal_host&gt;/static/activateConnector.html`

#### 5. Use cases and permissions for Slack

This section covers use cases and permissions required for Slack Self-hosted and Securiti-Cloud connectors.

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| - Sensitive Data Intelligence (SDI) - Data Subject Request (DSR) Automation | Discovery scan is only available for Self-hosted connector. | Add the following required **User Token OAuth scopes**: `channels:history` `channels:read` `groups:history` `groups:read` `im:history` `im:readmp` `im:history` `mpim:read` `users:read` `users.profile:rea` `files:read` `search:read` *(DSR only)* | Lets Securiti access Slack channels, direct messages, group conversations, files, and user profiles to discover and classify sensitive data and process Data Subject Requests. |
| Slack Workflow Node | N/A | Add the following required **User Token OAuth scopes**: `channels:write` `chat:write` `files:write` `groups:write` `im:write` `mpim:write` | Lets Securiti create and manage Slack workflow content, including channels, messages, files, and conversations. |

### Connect Slack with Securiti

This section covers connecting Slack (Self-hosted) and (Securiti-Cloud) connectors with Securiti.

#### Steps to connect Slack (Self-hosted) connector with Securiti

To configure the Slack (Self-hosted) connector, perform the procedures in the following topics:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. [Create and configure the connecting app in Slack](/latest/docs/create-and-configure-the-connecting-app-in-slack).
3. [Connecting Slack (Self-hosted) with Securiti](/latest/docs/connecting-slack-self-hosted-with-securiti).
4. [Configuring General permissions for Slack (Self-hosted)](/latest/docs/configuring-general-permissions-for-slack-self-hosted).
5. [Configure discovery scans in Slack (Self-hosted)](/latest/docs/configure-discovery-scans-in-slack-self-hosted).

#### Steps to connect Slack Securiti-Cloud connector with Securiti

To configure the Slack Securiti-Cloud connector, perform the procedures in the following topics:

1. [Create and configure the connecting app in Slack](/latest/docs/create-and-configure-the-connecting-app-in-slack).
2. [Connecting Slack (Securiti-Cloud) with Securiti](/latest/docs/connecting-slack-securiti-cloud-with-securiti).
3. [Configuring General permissions for Slack (Securiti-Cloud)](/latest/docs/configuring-general-permissions-for-slack-securiti-cloud).

**Additional resources**

- [Fulfilling DSR requests for Slack](/latest/docs/fulfilling-dsr-requests-for-slack).
