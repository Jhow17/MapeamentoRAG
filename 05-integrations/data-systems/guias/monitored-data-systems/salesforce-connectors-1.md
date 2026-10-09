---
title: "Salesforce"
slug: "salesforce-connectors-1"
status: "update"
updated: 2026-04-28T04:55:10Z
published: 2026-04-28T04:55:10Z
canonical: "helpcenter.securiti.ai/salesforce-connectors-1"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Salesforce

Salesforce commonly refers to a set of customer relationship management (CRM) tools that cater to lead generation and conversion metric tracking needs for enterprises, both large and small-scale. The tools can be deployed across mobile and cloud-driven devices to consistently track engagement in terms of sales and other associated customer activities. Issue ticketing and social media plug-ins are also available for the purpose of engaging customers on external platforms to that of Salesforce's own. Salesforce falls under the [Monitored, structured data systems.](https://portal.us.document360.io/v1/docs/configuring-connectors-for-monitored-data-systems)

> [!WARNING]
> **Important**
> 
> Securiti recommends using the [Salesforce CRM](/latest/docs/salesforce-crm-connectors) (latest) connector for this data system to access new capabilities, ongoing improvements, and full platform support.
> 
> **Legacy connectors are in maintenance mode and do not receive new features or enhancements.** This includes, but is not limited to:
> 
> - API version upgrades
> - Additional Keyrings for this connector
> - New or enhanced scopes for Discovery Scan and Data Inventory Sync
> - Additional modules (for example, HyperDrive, Data Inventory Sync and DSR)
> - Any future functionality introduced for this connector

> [!NOTE]
> **Note**
> 
> This documentation covers the authentication and activation process for Salesforce (Legacy) and Salesforce (Securiti Cloud) connectors.

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Salesforce (Legacy) (self-hosted) | - DSR automation - Sensitive Data Intelligence - Workflow |
| Salesforce (Securiti cloud) | - DSR automation - Workflow - Sensitive Data Intelligence - Security posture Scan - Privacy Platform Integration |

### Supported pod types for self-hosted connector

- Standard Securiti
- Elastic pods (EDSS)

### Supported authentication methods

Salesforce supports the following authentication type for authenticating and integrating with Securiti

| Authentication Type | Authentication Credentials |
| --- | --- |
| OAuth | - Consumer Key - Consumer Secret |

You can use a keyring during the connector configuration process to securely access your credentials from a vault. For more information, see [Managing Keyrings](/v1/docs/using-keyrings).

- **HashiCorp**. See [Configuring HashiCorp credential vaults](/v1/docs/configuring-credential-vaults-hashicorp-credential-vault) for more information.

### Supported items for classification scans

- Salesforce objects

For more information, see [Configure discovery scans in Salesforce (Legacy)](/v1/docs/configure-discovery-scans-in-salesforce-legacy) and [Initiate Salesforce data scanning](/v1/docs/initiate-salesforce-data-scanning).

### Prerequisites for configuring Salesforce in Securiti

#### 1. Pod deployment for self-hosted connector

You must complete these prerequisites before connecting your Salesforce connector with Securiti

You must deploy a Securiti pod in your environment to connect your Salesforce (Legacy) with a self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints.

For more information on configuring pods, see [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).

#### 2. Permissions and use cases for Salesforce

> [!NOTE]
> **Note**
> 
> The below mentioned scopes are required for both self-hosted and Securiti Cloud connectors.

| Modules use case | Constraint | Scopes | Explanation of use case |
| --- | --- | --- | --- |
| - Discovery Scan (Sensitive Data Intelligence) - DSR Automation (Data Subject Rights) - Security Posture Management - Privacy Platform Integration | - SDI Discovery scans are available on the self- hosted connector - Security Posture scans are available on the Securiti Cloud connector only. - Privacy Platform Integration is currently supported for the Securiti Cloud connector only | - Access the identity URL service (id, profile, email, address, phone) - Manage user data via APIs (api) - Perform requests at any time (refresh_token, offline_access) | These permissions let Securiti to discover and scan Salesforce objects for inventory and classification purposes and to build the Personal Data Index for DSR Automation. |

### Connect Salesforce connectors with Securiti

See the sections below to connect your Salesforce (Legacy) self-hosted or Salesforce ( Securiti Cloud) connectors with Securiti.

**New UI**

#### Steps to connect the Salesforce (Legacy) (Self-hosted) connector with Securiti

To configure the Salesforce (Legacy) self-hosted connector, perform the procedures in the following topics:

1. Deploy and configure Pod using [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. Register application and obtain credentials for Salesforce (Legacy). For more information, see [Register a connecting app in Salesforce](/v1/docs/register-a-connecting-app-in-salesforce)
3. [(New UI) Connecting Salesforce (Legacy) with Securiti](/latest/docs/new-ui-connecting-salesforce-legacy-with-securiti).
4. [Configure discovery scans in Salesforce (Legacy)](/v1/docs/configure-discovery-scans-in-salesforce-legacy)

#### Steps to connect the Salesforce (Securiti Cloud) connector with Securiti

To configure the Salesforce (Securiti Cloud) connector, perform the following steps:

1. Register the application and obtain credentials for Salesforce. For more information, see [Register a connecting app in Salesforce](/v1/docs/register-a-connecting-app-in-salesforce)
2. [(New UI) Connecting Salesforce (Securiti Cloud) with Securiti](/latest/docs/new-ui-connecting-salesforce-securiti-cloud-with-securiti)
3. [(New UI) Configuring General permissions for Salesforce (Securiti Cloud)](/latest/docs/new-ui-configuring-general-permissions-for-salesforce-securiti-cloud)

**Classic UI**

#### Steps to connect Salesforce (Legacy) (Self-hosted) connector with Securiti

To configure the Salesforce (Legacy) self-hosted connector, perform the procedures in the following topics:

1. Deploy and configure Pod using [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. Register application and obtain credentials for Salesforce (Legacy). For more information, see [Register a connecting app in Salesforce](/v1/docs/register-a-connecting-app-in-salesforce)
3. [Activate the Salesforce (Legacy) connectors in Securiti](/v1/docs/activate-the-salesforce-legacy-connectors-in-securiti).
4. [Configure discovery scans in Salesforce (Legacy)](/v1/docs/configure-discovery-scans-in-salesforce-legacy)

#### Steps to connect Salesforce (Securiti Cloud) connector with Securiti

To configure the Salesforce (Securiti Cloud) connector, perform the following steps:

1. Register application and obtain credentials for Salesforce. For more information, see [Register a connecting app in Salesforce](/v1/docs/register-a-connecting-app-in-salesforce)
2. [Activate the Salesforce (Securiti Cloud) connectors in Securiti](/v1/docs/activate-the-salesforce-securiti-cloud-connectors-in-securiti).
3. [Initiate Salesforce data scanning](/v1/docs/initiate-salesforce-data-scanning)

#### Additional resources

- [Fulfilling DSR requests for Salesforce (Legacy) and cloud connectors](/v1/docs/fulfilling-dsr-requests-for-salesforce-legacy-and-cloud-connectors) .
