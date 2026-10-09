---
title: "Microsoft Teams"
slug: "microsoft-teams-connectors"
status: "update"
updated: 2026-09-28T07:13:41Z
published: 2026-09-28T07:13:41Z
canonical: "helpcenter.securiti.ai/microsoft-teams-connectors"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Microsoft Teams

Microsoft Teams is a team collaboration application developed by Microsoft as part of the Microsoft 365 family of products, offering workspace chat and video conferencing, file storage, and integration of proprietary and third-party applications and services

The Microsoft Teams connector fall under the category of [Monitored, Unstructured data systems](/v1/docs/managing-data-system-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Microsoft Teams (Self-hosted) | Self-hosted connector supports: - Sensitive Data Intelligence - DSR Automation - Breach Analysis |

### Supported pods type for self-hosted connector

- Standard Securiti Pods.
- Elastic Pods (EDSS).

### Supported Credential Types

Refer to the table below to see the supported credential types of OAuth authentication for Microsoft Teams:

| Credential Type | Credentials |
| --- | --- |
| Client Secret | - Application (Client) ID - Client Secret |
| Certificate | - Application (Client) ID - Certificate |

#### Keyring support for Self-hosted connector

You can use a keyring support to store authentication credentials in a vault during the connector configuration process to securely access your credentials from a vault. For more information, see [Managing Keyrings](/latest/docs/creating-keyrings).

**HashiCorp**: For more information, see [Configuring HashiCorp credential vaults](/v1/docs/configuring-credential-vaults-hashicorp-credential-vault).

> [!NOTE]
> Note
> 
> Keyring support is available only for Client Secret Credential Type.

### Supported items for Inventory and Classification Scans

For more information on inventory and entitlement scans, see [Data Inventory Sync for self-hosted connectors](/v1/docs/data-inventory-sync-for-self-hosted-connectors). For more information about classification in discovery scans, see [Understanding Discovery Scans](/v1/docs/discovery-scans).

- For Scoping Metadata Syncs:
  - Teams in the organizations
  - Channels in the teams.

> [!NOTE]
> Note
> 
> In the case where you scope all channels or all teams, Securiti also scans users’ personal chats.
- For Data Inventory Syncs and Discovery Scans:
  - Channel Messages
  - Chat Messages.

### Prerequisites

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your Microsoft Teams with a Self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints and Microsoft Teams API endpoints.

For more information on configuring pods, see [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).

#### 2. Admin access in Microsoft Entra ID

We assume you own your Office 365 account and run a Microsoft Teams instance with admin privileges.

- For more information on connecting Microsoft Teams (Self-hosted) to Securiti, see [Grant permissions and obtain credentials in Microsoft Teams](/v1/docs/grant-permissions-and-obtain-credentials-in-microsoft-teams).

#### Allowlisting URLs for discovery scan

Securiti requires these URLs to be allowlisted on the customer's firewall for the Microsoft Teams to ensure proper functionality of Sensitive Data Intelligence (SDI) and Data Subject Rights (DSR) to work as expected:

- *https://graph.microsoft.com*
- *https://login.microsoftonline.com*

#### 4. Allowlisting APIs for Data Inventory Sync

You must allowlist the following APIs between your deployed Securiti pod and the Microsoft Teams APIs to successfully run the Data Inventory Sync.

Default URL is *https://graph.microsoft.com/*

| Sr. No | Method | URL | Purpose |
| --- | --- | --- | --- |
| 1 | GET | https://graph.microsoft.com/v1.0/users | Get users |
| 2 | GET | https://graph.microsoft.com/v1.0/teams | Get all teams |
| 3 | GET | https://graph.microsoft.com/v1.0/users/{{user_id}}/chats | Get user chat |
| 4 | GET | https://graph.microsoft.com/v1.0/teams/{{{team_id}}/channels | Get team channels |
| 5 | GET | https://graph.microsoft.com/v1.0/teams/{{{team_id}}/channels/{{channel_id}}/messages/delta | Get channel messages |
| 6 | GET | https://graph.microsoft.com/v1.0/teams/{{team_id}}/members | Get team members |
| 7 | GET | https://graph.microsoft.com/v1.0/teams/{{team_id}} | Get team information |
| 8 | GET | https://graph.microsoft.com/v1.0/teams/{{team_id}}/channels/{{channel_id}} | Get channel information |
| 9 | GET | https://graph.microsoft.com/v1.0/teams/{{team_id}}/channels/{{channel_id}}/sharedWithTeams | Get channel shared with teams |
| 10 | GET | https://graph.microsoft.com/v1.0/teams/%s/channels/%s/members | Get channel members |
| 11 | GET | https://graph.microsoft.com/v1.0/chats/%s/messages | Get channel messages |
| 12 | GET | https://graph.microsoft.com/v1.0/teams/%s/channels | Get team channels |
| 13 | GET | https://graph.microsoft.com/v1.0/teams/{{{team_id}}/channels/{{channel_id}}/messages/{{message_id}}/replies | Get channel message replies |
| 14 | GET | https://graph.microsoft.com/v1.0/teams/{{{team_id}}/channels/{{channel_id}}/messages/{{message_id} | Get channel message |
| 15 | GET | https://graph.microsoft.com/v1.0/chats/{{chat_id}}/messages | Get chat messages |

#### 5. Permissions required

You must assign these permissions to the Microsoft Teams application to meet different use cases.

- Users.Read.All
- Team.ReadBasic.All
- Channel.ReadBasic.All
- ChannelMessage.Read.All
- Chat.ReadBasic.All
- Chat.Read.All
- TeamMember.Read.All
- ChannelMember.Read.All

### Steps to connect your Microsoft Teams with Securiti

To connect your Microsoft Teams, perform the following steps:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. Activate your Self-hosted data system's connector on the pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
3. [Grant permissions and obtain credentials in Microsoft Teams](/latest/docs/grant-permissions-and-obtain-credentials-in-microsoft-teams)
4. [(Optional) Configure the HashiCorp OAuth token for Microsoft Teams](/latest/docs/optional-configure-the-hashicorp-oauth-token-for-microsoft-teams)
5. [Connecting Microsoft Teams with Securiti](/latest/docs/new-ui-creating-microsoft-teams-self-hosted-connector-instance)
6. [Configuring Data Inventory Sync for Microsoft Teams](/latest/docs/configuring-data-inventory-sync-for-microsoft-teams).
7. [Configure Microsoft Teams discovery scans](/latest/docs/configure-microsoft-teams-discovery-scans)

#### Additional resources

- [Fulfilling DSR requests for Microsoft Teams](/latest/docs/fulfilling-dsr-requests-for-microsoft-teams)
- [Troubleshooting guide for Microsoft Teams](/latest/docs/troubleshooting-for-microsoft-teams)
