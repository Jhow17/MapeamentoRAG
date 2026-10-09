---
title: "Jira Cloud"
slug: "jira-cloud-connectors-1"
status: "update"
updated: 2026-04-06T10:50:48Z
published: 2026-04-06T10:50:48Z
canonical: "helpcenter.securiti.ai/jira-cloud-connectors-1"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Jira Cloud

Jira is a popular project management and issue tracking tool used by development teams to plan, track, and release. By connecting Jira with Securiti, you can discover sensitive data across your sites. Jira falls under the category of Monitored and is a combination of Unstructured and Structured data systems. For more information, see [Data systems classification](/v1/docs/managing-data-system-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Jira Cloud (Self-hosted) | Self-hosted connector supports: - Sensitive Data Intelligence - Gencore AI |
| Jira Cloud (Securiti Cloud) | Securiti Cloud connector supports: - Standard Data Scan - Automation Policy - Data Breach Management |

### Supported pod types

- Standard Securiti pod.
- Elastic pod/ EDSS.

### Supported authentication methods

- **OAuth** authentication for both self-hosted and cloud connectors

#### Keyring support for Jira Cloud (self-hosted) connector

You can use a keyring support to store authentication credentials in a vault product during the connector configuration process to securely access your credentials from a vault. See [Managing Keyrings](/v1/docs/using-keyrings) for more information.

- **HashiCorp**. See [Configuring HashiCorp credential vaults](/v1/docs/configuring-credential-vaults-hashicorp-credential-vault) for more information.

HashiCorp is OAuth supported.

### Supported items for inventory and classification scans

Securiti scans the following items for Jira Cloud connectors.

- Site(s)
- Project(s) within each site.
- Issues, comments and attachments within each project.

For more information, see [Configuring Data Inventory Sync for Jira Cloud (Self-hosted)](/v1/docs/configuring-data-inventory-sync-for-jira-cloud-self-hosted). For more information about classification in discovery scans, see [Understanding Discovery Scans](/v1/docs/discovery-scans).

### Prerequisites

#### 1. Pod deployment

> [!NOTE]
> **Note**
> 
> Pod deployment prerequisite is for self-hosted connectors only.

You must deploy a Securiti pod in your environment to connect your Jira Cloud with a self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints.

For more information on configuring pods, see [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).

#### 2. Allowlisting APIs for Jira Cloud (self-hosted) Data Inventory Sync

You must allowlist the following APIs between your deployed Securiti pod and the Jira Cloud APIs to run the Data Inventory Sync successfully.

You can use the following URLs to allowlist APIs:

- **Default Base URL:** https://api.atlassian.com/ex/jira
- **Atlassian URL:** https://api.atlassian.com
- **Site URL:** https://{site_name}.atlassian.net

| Sr. No | Method | URL | Purpose |
| --- | --- | --- | --- |
| 1 | GET | https://{site_name}.atlassian.net/_edge/tenant_info | Get Site ID |
| 2 | GET | https://api.atlassian.com/oauth/token/accessible-resources | List accessible resources |
| 3 | GET | https://api.atlassian.com/ex/jira/$site_id/rest/api/2/project/search | Get paginated projects |
| 4 | GET | https://api.atlassian.com/ex/jira/$site_id/rest/api/2/search | Search for issues using JQL |
| 5 | GET | https://api.atlassian.com/ex/jira/$site_id/rest/api/2/issue/$issue_id | Get issue |
| 6 | GET | https://api.atlassian.com/ex/jira/$site_id/rest/api/2/issue/$issue_id/comment | Get comments |
| 7 | GET | https://api.atlassian.com/ex/jira/$site_id/rest/api/2/users/search | Find users |
| 8 | GET | https://api.atlassian.com/ex/jira/$site_id/rest/api/2/permissions/check | Get bulk permissions |

#### 3. Use cases and permissions for Jira Cloud

This section covers use cases and permissions required for Jira Cloud self-hosted and cloud connectors. You must choose the permissions depending on the number of modules or type of connector you are using.

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| - Sensitive Data Intelligence (SDI) - Data Inventory Metadata Sync | Discovery scan is only available for self-hosted connector. | **For Self-hosted connector:** - **Jira platform REST API permissions**: - `read:jira-work` - `read:jira-user` **For Securiti Cloud connector:** - **Jira platform REST API permissions**: - `read:jira-work` - `read:jira-user` - `write:jira-work` | These permissions let Securiti read the files and file metadata in Jira for inventory and classification purposes. |
| Data Inventory Sync and Gencore AI Entitlement scanning | - Available for self-hosted connector only. - Requires whitelisting APIs between your deployed Securiti pod and the Jira APIs. See section above. | **Jira platform REST API permissions**: - `read:jira-work` - `read:jira-user` | These permissions let Securiti read the files and file metadata in Jira for inventory. The permission also let Securiti discover entitlements and read sharing settings. |
| Automation Policy | Available for Securiti Cloud connector only. | **Jira platform REST API permissions**: - `write:jira-work` | This permission let Securitidefine automation policies based on a user-defined scope derived from system findings. |

### Connect Jira Cloud with Securiti

**New UI**

#### Steps to connect Jira Cloud (Self-hosted) connector

To configure the Jira Cloud (Self-hosted) connector, perform the procedures in the following topics:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. Activate your Self-hosted data system's connector on the pod as described in [Securiti pods](/v1/docs/pod-quick-install-guides-cluster-version-v128).
3. [Create an app and obtain credentials for Jira Cloud (self-hosted) connector](/v1/docs/create-an-app-and-obtain-credentials-for-jira-cloud-self-hosted-connector)
4. [(Optional) Configure the Hashicorp OAuth token for Jira Cloud](/v1/docs/optional-configure-the-hashicorp-oauth-token-for-jira-cloud)
5. [(New UI) Connecting Jira Cloud (self-hosted) with Securiti](/latest/docs/new-ui-connecting-jira-cloud-self-hosted-with-securiti)
6. [Configuring Data Inventory Sync for Jira Cloud (Self-hosted)](/v1/docs/configuring-data-inventory-sync-for-jira-cloud-self-hosted)
7. [Configure discovery scans in Jira Cloud (Self-hosted)](/v1/docs/configure-discovery-scans-in-jira-cloud-self-hosted)

#### Steps to connect Jira Securiti Cloud connector

To configure the Jira Cloud Securiti Cloud connector, perform the procedures in the following topics:

1. [Create an app and obtain credentials for Jira Cloud (Securiti Cloud) connector](/v1/docs/create-an-app-and-obtain-credentials-for-jira-cloud-securiti-cloud-connector)
2. [(New UI) Connecting Jira Cloud (Securiti Cloud) with Securiti](/latest/docs/new-ui-connecting-jira-cloud-securiti-cloud-with-securiti)
3. [Initiate Jira Cloud data scanning](/v1/docs/initiate-jira-cloud-data-scanning)

**Classic UI**

#### Steps to connect Jira Cloud (Self-hosted) connector

To configure the Jira Cloud (Self-hosted) connector, perform the procedures in the following topics:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. Activate your Self-hosted data system's connector on the pod as described in [Securiti pods](/v1/docs/pod-quick-install-guides-cluster-version-v128).
3. [Create an app and obtain credentials for Jira Cloud (self-hosted) connector](/v1/docs/create-an-app-and-obtain-credentials-for-jira-cloud-self-hosted-connector)
4. [(Optional) Configure the Hashicorp OAuth token for Jira Cloud](/v1/docs/optional-configure-the-hashicorp-oauth-token-for-jira-cloud)
5. [Activate the Jira Cloud (self-hosted) connector in Securiti](/v1/docs/activate-the-jira-cloud-self-hosted-connector-in-securiti)
6. [Configuring Data Inventory Sync for Jira Cloud (Self-hosted)](/v1/docs/configuring-data-inventory-sync-for-jira-cloud-self-hosted)
7. [Configure discovery scans in Jira Cloud (Self-hosted)](/v1/docs/configure-discovery-scans-in-jira-cloud-self-hosted)

#### Steps to connect Jira Securiti Cloud connector

To configure the Jira Cloud Securiti Cloud connector, perform the procedures in the following topics:

1. [Create an app and obtain credentials for Jira Cloud (Securiti Cloud) connector](/v1/docs/create-an-app-and-obtain-credentials-for-jira-cloud-securiti-cloud-connector)
2. [Activate the Jira Cloud (Securiti Cloud) connector](/v1/docs/activate-the-jira-cloud-securiti-cloud-connector).
3. [Initiate Jira Cloud data scanning](/v1/docs/initiate-jira-cloud-data-scanning)

#### Additional resources

- [Viewing Jira Cloud metadata in Securiti](/v1/docs/viewing-jira-cloud-metadata-in-securiti)
- [Table Training for structured and hybrid data systems](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems)
