---
title: "Confluence Cloud"
slug: "confluence-cloud-connector-1"
status: "update"
updated: 2026-09-30T08:06:01Z
published: 2026-09-30T08:06:07Z
canonical: "helpcenter.securiti.ai/confluence-cloud-connector-1"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Confluence Cloud

Confluence Cloud is a powerful collaboration platform offered by Atlassian, designed to enhance teamwork and communication within organizations. As a cloud-based solution, Confluence Cloud provides a centralized and easily accessible space for teams to create, share, and collaborate on content seamlessly. With Confluence Cloud, teams can create dynamic and interactive pages, documents, and knowledge bases, fostering a collaborative and transparent work culture.

Confluence Cloud falls under the category of Monitored, Unstructured data systems. For more information, see [data systems classification](/v1/docs/managing-data-system-connectors).

### Supported Pod types

- Standard Securiti Pod.
- Elastic Pod/EDSS.

### Supported Connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Confluence Cloud (Self-hosted) | Self-hosted connector supports: - Sensitive Data Intelligence - DSR Automation using Full Scan - Workflow - Data Inventory Sync - Breach Analysis - Gencore AI Entitlements scan |

### Supported authentication methods

Confluence Cloud supports OAuth authentication.

### Supported items for Inventory and Classification scans

For more information on inventory and entitlement scans, see [Data Inventory Sync for self-hosted connectors](/v1/docs/data-inventory-sync-for-self-hosted-connectors). For more information about classification in discovery scans, see [Understanding Discovery Scans](/v1/docs/discovery-scans).

- Pages
- Comments (per page or per blogpost)
- Blogposts
- Attachments

### Prerequisites for configuring Confluence Cloud (Self-hosted) connector

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your Confluence Cloud with a self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints. For more information, see the allow-listed URLs section in [Elastic pod manual deployment guide (private cloud)](/v1/docs/elastic-pods-1).

For more information on configuring pods, see [Securiti variables: Platform name pods and elastic pods](/v1/docs/securiti-pods-and-elastic-pods).

#### 2. Allowlisting URLs for Confluence Cloud connector

You must allowlist the following endpoints or URLs to successfully connect to Confluence Cloud and perform operations like discovery scan, DSR scan, access verification, and so on.

#### Base URL

- Default: `https://api.atlassian.com`
- Site URL: `https://{{site_name}}.atlassian.net` or (*.atlassian.net) (when a customer has a lot of sites)

#### Authentication

| Sr. No | Method | URL | Purpose |
| --- | --- | --- | --- |
| 1 | GET | `https://{{site_name}}.atlassian.net/_edge/tenant_info` | Get Cloud ID |
| 2 | GET | `https://api.atlassian.com/ex/confluence/{{site_id}}/wiki/api/v2/spaces` | Get Confluence Spaces V2 |
| 3 | GET | `https://api.atlassian.com/oauth/token/accessible-resources` | Get Confluence Sites |
| 4 | GET | `https://auth.atlassian.com/oauth/token` | Get access token for API authentication |

#### Discovery Scan, Access verification, and Diagnostic utility

| Sr. No | Method | URL | Purpose |
| --- | --- | --- | --- |
| 1 | GET | `https://{{site_name}}.atlassian.net/_edge/tenant_info` | Get Cloud ID |
| 2 | GET | `https://api.atlassian.com/ex/confluence/{{site_id}}/wiki/api/v2/spaces` | Get Confluence Spaces V2 |
| 3 | GET | `https://api.atlassian.com/ex/confluence/{{site_id}}/wiki/rest/api/content/search` | Search Confluence Content by Space |
| 4 | GET | `https://api.atlassian.com/ex/confluence/{{site_id}}/wiki/rest/api/content/{{container_id}}/child/attachment/{{attachment_id}}/download` | Download Confluence Attachment |
| 5 | GET | `https://api.atlassian.com/oauth/token/accessible-resources` | Get Confluence Sites |
| 6 | GET | `https://auth.atlassian.com/oauth/token` | Get access token for API authentication |

#### DSR Scan

| Sr. No | Method | URL | Purpose |
| --- | --- | --- | --- |
| 1 | GET | `https://api.atlassian.com/ex/confluence/{{site_id}}/wiki/rest/api/content/search` | Search Confluence Content by Space |
| 2 | GET | `https://api.atlassian.com/ex/confluence/{{site_id}}/wiki/rest/api/content/{{container_id}}/child/attachment/{{attachment_id}}/download` | Download Confluence Attachment |

#### Data Inventory Sync

You must allowlist the following APIs between your deployed Securiti pod and the Confluence Cloud APIs to successfully run the Data Inventory Sync.

Following are the Base URLs for the Confluence Cloud APIs

- **Default URL:** "https://api.atlassian.com/ex/jira"
- **Atlassian URL:** "https://api.atlassian.com"
- **Site_URL:** "https://{{site_name}}.atlassian.net"

| Sr. No | Method | URL | Purpose |
| --- | --- | --- | --- |
| 1 | GET | https://api.atlassian.com/ex/jira/_edge/tenant_info | Get configured site id |
| 2 | GET | https://api.atlassian.com/ex/jira/oauth/token/accessible-resources | Get accessible sites |
| 3 | GET | https://api.atlassian.com/ex/jira/{{site_id}}/rest/api/2/search | Get all project issues |
| 4 | GET | https://api.atlassian.com/ex/jira/{{site_id}}/rest/api/2/search | Get issues |
| 5 | GET | https://api.atlassian.com/ex/jira/{{site_id}}/rest/api/2/attachment/content/$attachment_id | Download attachment |
| 6 | GET | https://api.atlassian.com/ex/jira/{{site_id}}/rest/api/2/issue/{{issue_id}} | Get an issue |
| 7 | GET | https://api.atlassian.com/ex/jira/{{site_id}}/rest/api/2/issue/{{issue_id}}/comment | Get comments of an issue |
| 8 | GET | https://api.atlassian.com/ex/jira/{{site_id}}/rest/api/2/project/search | List projects |
| 9 | GET | https://api.atlassian.com/ex/jirarest/api/2/users/search | Get all users |
| 10 | GET | https://api.atlassian.com/ex/jira/rest/api/2/permissions/check | Get permissions |

#### 3. Use cases and permissions for Confluence Cloud

This section covers use cases and permissions required for Confluence Cloud self-hosted connector.

If you wish to provide the Confluence Cloud connector access to all of your pages, comments, blogposts, and attachments for data discovery and classification, use the following use cases and permissions.

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| - Sensitive Data Intelligence (SDI) - Data Subject Request (DSR) Automation Indexing | SDI Discovery Scans and DSR Automation Indexing is only available on the self- hosted connector. | **Classic scopes:** - Read Confluence space summary - Read Confluence detailed content - Read Confluence content summary - Search Confluence content and space summaries - Read user - Download content attachments **Granular scopes:** - View space | These permissions let Securiti read the files and file metadata in Confluence Cloud for inventory and classification purposes. These permissions also build the Personal Data Index for DSR Automation. |
| Data Inventory Sync and Gencore AI Entitlement scanning | Requires whitelisting APIs between your deployed Securiti pod and the Confluence APIs. | **Classic scopes:** - read:confluence-groups - read:confluence-content.permission **Granular scopes:** - read:content-details:confluence - read:permission:confluence | These permissions let Securiti read the files and file metadata in Confluence for inventory. The permission also let Securiti discover entitlements and read sharing settings. |

### Connect Confluence Cloud with Securiti

To configure the Confluence Cloud connector, perform the procedures in the following topics:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. Activate your Self-hosted data system's connector on the pod as described in Securiti [pods and elastic pods](/latest/docs/securiti-pods-and-elastic-pods).
3. [Acquire authentication credentials in Confluence Cloud](/latest/docs/acquire-authentication-credentials-in-confluence-cloud)
4. [Connecting Confluence Cloud with Securiti](/latest/docs/connecting-confluence-cloud-with-securiti).
5. [Configure Data Inventory Sync for Confluence Cloud](/latest/docs/configure-data-inventory-sync-for-confluence-cloud).
6. [Configure discovery scans in the Confluence Cloud](/latest/docs/configure-discovery-scans-in-the-confluence-cloud).

**Additional resources**

- [Viewing Confluence Cloud metadata in](/latest/docs/viewing-confluence-cloud-metadata-in-securiti) Securiti.
- [Fulfilling DSR requests for Confluence Cloud](/latest/docs/fulfilling-dsr-requests-for-confluence-cloud).

The cloud term typically refers to cloud computing. Cloud computing is a technology that allows users to access and use computing resources and services over the internet, often from remote data centers.

Type of scan focused on identifying metadata rather than content for files in a data system. Data Inventory sync includes identifying file attributes such as name, size, creation date etc and information such as access permissions, ownership, and entitlement for resources. Data Inventory scan includes inventory and entitlement scanning for Genstack, and is supported for monitored, self-hosted data systems only

Permissions refer to the minimum set of access details required to connect a data system with Securiti and allow scanning of data. Permissions could be of an administrative role where the user has all privileges to scan, share and access data, or it can be READ/WRITE only. Without the required permissions, data cannot be discovered or scanned for sensitive information.
