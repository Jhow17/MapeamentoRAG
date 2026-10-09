---
title: "Jira Data Center"
slug: "jira-data-center-connectors"
status: "new"
updated: 2026-09-30T10:39:10Z
published: 2026-09-30T10:39:17Z
canonical: "helpcenter.securiti.ai/jira-data-center-connectors"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Jira Data Center

Jira Data Center falls under the category of Monitored and is a combination of Unstructured and Structured data systems. For more information, see [Data systems classification](/v1/docs/managing-data-system-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Jira Data Center (Self-hosted) | Self-hosted connector supports: - Sensitive Data Intelligence - Data Subject Rights (DSR) |

### Supported pod types

- Standard Securiti pod.
- Elastic pod/ EDSS.

### Supported authentication methods

- **OAuth** authentication
- Personal Access Token

#### Keyring support for Jira Data Center (self-hosted) connector

You can use a keyring support to store authentication credentials in a vault product during the connector configuration process to securely access your credentials from a vault. See [Managing Keyrings](/v1/docs/using-keyrings) for more information.

- **HashiCorp**. For more information, see [Configuring HashiCorp credential vaults](/v1/docs/configuring-credential-vaults-hashicorp-credential-vault).

HashiCorp is OAuth supported.

### Prerequisites

#### Deploy a pod

You must deploy a Securiti pod in your environment to connect your Jira Data Center with a self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints.

For more information on configuring pods, see [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).

#### Allow-listing URLs

You must allowlist the following APIs between your deployed Securiti pod and the Jira APIs to run the discovery scan successfully.

You can use the following URLs to allowlist APIs:

- **Default Base URL:** https://{instance_id} (Base URL of your Jira Data Center)

> [!NOTE]
> **Note**
> 
> This Instance ID (Base URL) is provided as input for the connector activation.

| Sr. No | Method | URL | Purpose | Use case |
| --- | --- | --- | --- | --- |
| 1 | POST | https://{{instance_id}}/rest/oauth2/latest/token | Get and refresh the access token | - Authentication - Metadata Sync - Discovery Scan - DSR |
| 2 | GET | https://{intance_id}/rest/api/2/project/$project_id | Get details of a Project | - Discovery Scan |
| 3 | GET | https://{intance_id}/rest/api/2/project | List all Projects | - Authentication - Metadata Sync - Discovery Scan |
| 4 | GET | https://{intance_id}/rest/api/2/search?startAt=$start_at&maxResults=$max_results&fields=*all,-attachment&jql=project=$project_id | List all Issues with metadata and comments without attachments | - Discovery Scan |
| 5 | GET | https://{intance_id}/rest/api/2/search?startAt=$start_at&maxResults=$max_results&fields=attachment,summary&jql=project=$project_id%20AND%20attachments%20is%20not%20EMPTY | List all attachments and summaries for Issues | - Discovery Scan |
| 6 | GET | https://{intance_id}/rest/api/2/search?startAt=$start_at&maxResults=$max_results&fields=attachment,summary&jql=project=$project_id%20AND%20attachments%20is%20not%20EMPTY%20AND%20updated&gt;=$last_sync_timestamp_ms | Lists all modified attachments and summaries for issues | - Discovery Scan |
| 7 | GET | https://{intance_id}/rest/api/2/attachment/$attachment_id | Get details of an attachment | - DSR |
| 8 | GET | https://{intance_id}/secure/attachment/$attachment_id/$file_name | Download an Attachment | - Discovery Scan - DSR |

### Connecting Jira Data Center with Securiti

To configure the Jira Data Center connector, perform the procedures in the following topics:

1. [Grant permissions and obtain credentials in Jira Data Center](/latest/docs/grant-permissions-and-obtain-credentials-in-jira-data-center)
2. [Connecting Jira Data Center (Self Hosted) with Securiti](/latest/docs/connecting-jira-data-center-self-hosted-with-securiti)
3. [Configure discovery scans in Jira Data Center](/latest/docs/configure-discovery-scans-in-jira-data-center)

**Additional resources**

- [Fulfilling DSR requests for Jira Data Center](/latest/docs/fulfilling-dsr-requests-for-jira-data-center)
- [Table Training for structured and hybrid data systems](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems)
