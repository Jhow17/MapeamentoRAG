---
title: "Salesforce CRM"
slug: "salesforce-crm-connectors"
status: "update"
updated: 2026-07-31T10:38:45Z
published: 2026-07-31T10:42:32Z
canonical: "helpcenter.securiti.ai/salesforce-crm-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Salesforce CRM

Salesforce CRM commonly refers to a set of customer relationship management (CRM) tools that cater to lead generation and conversion metric tracking needs for enterprises, both large and small-scale. The tools can be deployed across mobile and cloud-driven devices to consistently track engagement in terms of sales and other associated customer activities. Issue ticketing and social media plug-ins are also available for the purpose of engaging customers on external platforms to Salesforce's own.

Salesforce CRM falls under the category of Monitored, Hybrid data systems.

> [!WARNING]
> **Important**
> 
> Salesforce CRM is an enhanced, hybrid version of the existing [Salesforce (Legacy)](/latest/docs/salesforce-connectors-1) connector. With Salesforce CRM, you can scan attachments in addition to the structured data scanning the legacy connector provides.
> 
> **Securiti recommends using Salesforce CRM to access new capabilities, ongoing improvements, and full platform support.**

> [!NOTE]
> **Note**
> 
> Securiti provides API Quota Tracking for the Salesforce CRM connector. This feature monitors API usage and automatically pauses requests when the limit is reached. Once the quota resets, the process continues without causing disruptions.
> 
> For more information, see [API quota tracking for SaaS connectors](/latest/docs/api-quota-tracking-for-saas-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Salesforce CRM (Self-hosted) | - Sensitive Data Intelligence - DSR automation |

### Supported pod types for self-hosted connector

- Standard Securiti
- Elastic pods (EDSS)

### Supported authentication methods

Salesforce supports the following authentication type for authenticating and integrating with Securiti.

| Authentication Type | Authentication Credentials |
| --- | --- |
| OAuth | - Consumer Key - Consumer Secret |

You can use a keyring during the connector configuration process to securely access your credentials from a vault. For more information, see [Using keyrings](/latest/docs/managing-credentials-using-keyrings).

- **HashiCorp**: For more information, see [HashiCorp credential vault](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault).
- **CyberArk**: For more information, see [CyberArk credential vault](/latest/docs/cyberark-credential-vault).
- **CyberArk Conjur**: For more information, see [CyberArk Conjur credential vault](/latest/docs/configuring-credential-vaults-cyberark-conjur-credential-vault).

### Supported items for classification scans

- Salesforce objects

For more information, see [Configure discovery scans in Salesforce CRM](/latest/docs/configure-discovery-scans-in-salesforce-crm).

### Prerequisites for configuring Salesforce CRM in Securiti

#### 1. Pod deployment for self-hosted connector

You must complete these prerequisites before connecting your Salesforce connector with Securiti

You must deploy a Securiti pod in your environment to connect your Salesforce (Legacy) with a self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints.

For more information on configuring pods, see [Securiti pods](/latest/docs/pods-cluster-version-v128-and-later).

#### 2. Admin access in Salesforce CRM

You must have system administrator role to create a connected app and manage OAuth settings.

> [!NOTE]
> Note
> 
> If the connected app is already created, you can activate the connector using a user with the **API User** profile with relevant necessary permissions. For more information, see [Prerequisites for Salesforce CRM connector](/latest/docs/prerequisites-for-salesforce-crm-connector).

#### 3. Add OAuth scopes in the Salesforce CRM application

Add the following OAuth scopes to enable OAuth settings in the Salesforce CRM application:

- Enter the Securiti app URL according to the environment being used.
- `Access the identity URL service (id, profile, email, address, phone)`
- `Manage user data via APIs (api)`
- `Perform requests at any time (refresh_token, offline_access)`

For more information on the OAuth scopes, see [Prerequisites for Salesforce CRM connector](/latest/docs/prerequisites-for-salesforce-crm-connector).

#### 4. Use cases and permissions for Salesforce CRM

This section covers use cases and permissions required for the Salesforce CRM connector.

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| - Discovery Scan (Sensitive Data Intelligence) - DSR Automation (Data Subject Rights) | N/A | Assign the following permission to the Salesforce CRM user activating the connector: - `Query All Files` | This permission lets Securiti to discover and scan Salesforce CRM objects for classification purposes and to build the Personal Data Index for DSR Automation. |

### Connect Salesforce CRM connectors with Securiti

See the sections below to connect your Salesforce CRM connector with Securiti.

#### Steps to connect the Salesforce CRM connector with Securiti

To configure the Salesforce CRM connector, perform the following procedures in sequence:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. [Prerequisites for Salesforce CRM connector](/latest/docs/prerequisites-for-salesforce-crm-connector).
3. [(Optional) Configure the Hashicorp OAuth token for Salesforce CRM](/latest/docs/optional-configure-the-hashicorp-oauth-token-for-salesforce-crm)
4. [Connecting Salesforce CRM with Securiti](/latest/docs/connecting-salesforce-crm-with-securiti).
5. [Configuring General permissions for Salesforce CRM](/latest/docs/new-ui-configuring-general-permissions-for-salesforce-crm).
6. [Configure discovery scans in Salesforce CRM](/latest/docs/configure-discovery-scans-in-salesforce-crm).

#### Additional resources

- [Fulfilling DSR requests for Salesforce CRM](/latest/docs/fulfilling-dsr-requests-for-salesforce-crm).
- [Troubleshooting for Salesforce (CRM) connector](/latest/docs/troubleshooting-for-salesforce-crm-connector).
