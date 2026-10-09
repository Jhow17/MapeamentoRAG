---
title: "Oracle Eloqua"
slug: "oracle-eloqua"
updated: 2026-05-25T21:00:10Z
published: 2026-05-25T21:00:10Z
canonical: "helpcenter.securiti.ai/oracle-eloqua"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Oracle Eloqua

Oracle Eloqua is a cloud-based marketing automation platform used by B2B organizations to manage leads and run personalized campaigns. By integrating Eloqua with Securiti, users can gain visibility into their marketing data, apply governance controls, and manage sensitive customer information in a centralized and compliant way. Oracle Eloqua Marketing falls under the category of [Hybrid data systems](/latest/docs/managing-data-system-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Oracle Eloqua Marketing Automation (self-hosted) | - Sensitive Data Intelligence (SDI) - Data Subject Rights (DSR) |

### Supported pod types

- Standard Securiti Pods V2

### Supported authentication types

Oracle Eloqua Marketing Automation (self-hosted) supports the following authentication types.

| Authentication Type | Authentication credentials |
| --- | --- |
| Basic | - Username - Password - Company Name |
| OAuth App | - Client ID - Client Secret |

#### Supported Keyrings

Oracle Eloqua Marketing Automation (self-hosted) supports the following keyrings for Basic authentication:

- CyberArk Conjur: For more information, see [CyberArk Conjur credential vault](/latest/docs/configuring-credential-vaults-cyberark-conjur-credential-vault).
- Hashicorp: For more information, see [HashiCorp credential vault](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault)

For more information on keyrings, see [Using keyrings](/latest/docs/managing-credentials-using-keyrings).

### Supported items for discovery scans

The discovery scan supports scanning entities for the Oracle Eloqua Marketing Automation.

### Prerequisites for configuring Oracle Eloqua in Securiti

You must complete these prerequisites before connecting your Oracle Eloqua Marketing Automation connector with Securiti

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your Oracle Eloqua Marketing Automation with a self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints.

For more information on configuring pods, see [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).

#### 2. Assign license and access to the security group

You must be an admin to assign:

- License of `Eloqua Marketing Platform` to the user or user’s security group.
- Privileged access to `Asset Manager` to your user or user’s security group.

#### 3. Permissions and use cases for Oracle

| Modules use case | Permissions | Explanation of use case |
| --- | --- | --- |
| - Discovery Scan (Sensitive Data Intelligence) - DSR Automation (Data Subject Rights) | Assign the following **Action** **Permissions** to the security group: - `View Form Submission Data` - `Access to App Cloud Developer` - `Manage Users (General)` Assign the following **Interface** **Permissions** to the security group: - `App Cloud Developer` | These permissions let Securiti to read the tables and schema metadata in Oracle for classification purposes and to build the Personal Data Index for DSR Automation. |

#### 4. Connect your Oracle with Securiti

Perform the following steps to connect your Oracle Eloqua Marketing Automation with Securiti.

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. [Prerequisites for Oracle Eloqua (Self-hosted)](/latest/docs/grant-permissions-and-obtain-credentials-in-oracle-eloqua).
3. [(New UI) Connecting the Oracle Eloqua (Self Hosted) with Securiti](/latest/docs/new-ui-connecting-the-oracle-eloqua-self-hosted-with-securiti).
4. [Configure discovery scans in Oracle Eloqua](/latest/docs/configure-discovery-scans-in-jira-data-center-1).
5. [Table training for structured and hybrid data systems](/latest/docs/table-training-for-structured-and-hybrid-data-systems).

For more information about how Securiti uses the Oracle data to respond to DSR requests, see [Fulfilling DSR requests for Oracle Eloqua](/latest/docs/fulfilling-dsr-requests-for-oracle-eloqua).
