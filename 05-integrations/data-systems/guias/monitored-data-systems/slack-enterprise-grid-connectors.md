---
title: "Slack Enterprise Grid"
slug: "slack-enterprise-grid-connectors"
status: "update"
updated: 2025-12-09T14:03:10Z
published: 2025-12-09T14:03:10Z
canonical: "helpcenter.securiti.ai/slack-enterprise-grid-connectors"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Slack Enterprise Grid

> [!CAUTION]
> Warning
> 
> Slack Enterprise Grid is currently unavailable due to Slack platform prerequisites required for integration.

Slack Enterprise Grid is a Self-Hosted collaboration suite for both enterprises and groups of individuals consisting of communication and productivity tools. It is based on the sharing of workspace addresses which are created and moderated by a specific team member with administrative rights. The Slack Enterprise Grid Plan allows collaboration of multiple workspaces. The enterprise edition has some more features such as it allows access to private and public conversations and data of all users (including DMs and Multi-party DMs) within Slack. This feature is available through Slack Discovery APIs which are not publicly available and Slack Team needs to be contacted to enable these APIs.

Securiti supports the following Slack data systems:

- [Slack](/v1/docs/slack-connectors)
- [Slack Enterprise Grid](/v1/docs/slack-enterprise-grid-connectors)

> [!NOTE]
> **Note**
> 
> Securiti provides API Quota Tracking for the Slack Enterprise Grid connector. This feature monitors API usage and automatically pauses requests when the limit is reached. Once the quota resets, the process continues without causing disruptions.
> 
> 
> 
> See [API quota tracking for SaaS connectors, for more information](/v1/docs/api-quota-tracking-for-saas-connectors).

Following are the differences between Slack (Self-hosted) and Slack Enterprise Grid features.

| Features | Slack (Self-hosted) | Slack Enterprise Grid (Self-hosted) |
| --- | --- | --- |
| Data type | Unstructured data system | Unstructured data system |
| Data system scope | Includes all channels in a single workspace | Includes all workspaces and channels |
| Attachment scanning | Securiti retrieves attachments from the following: - All public channels Securiti does not retrieve attachments from the following: - Private channels - Multi party direct messages (MPDMs) - Direct messages (DMs) | Securiti retrieves attachments from the following: - All public channels - All private channels - All MPDMs - All DMs - Drafts (when the discovery scan is configured for All) - Canvases (when the discovery scan is configured for All) |
| Conversation messages scanning | For Slack, data scanning doesn't include conversations from private channels, public channels, MPDMs, and DMs. | Includes conversations from the following: - All public channels - All private channels - All MPDMs - All DMs |
| Data Subject Rights (DSR) requests | Securiti supports the following DSR requests for Slack: - Access - Port | Securiti supports the following DSR requests for Slack Enterprise Grid: - Access - Port |

To configure the Slack Enterprise Grid connector, perform the procedures in the following topics:

1. [Create and configure the connecting app in Slack Enterprise Grid](/v1/docs/create-and-configure-the-connecting-app-in-slack-enterprise-grid)
2. [Activate the Slack Enterprise Grid connector in Securiti](/v1/docs/activate-the-slack-enterprise-grid-connector-in-securiti)
3. [Slack Enterprise Grid connectors](/v1/docs/slack-enterprise-grid-connectors)

See [Fulfilling DSR requests for Slack Enterprise Grid](/v1/docs/fulfilling-dsr-requests-for-slack-enterprise-grid) for more information about how Securiti uses the Slack Enterprise data to respond to DSR requests.
