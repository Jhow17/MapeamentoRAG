---
title: "Microsoft Dataverse"
slug: "microsoft-dataverse-connectors-1"
status: "new"
updated: 2026-07-25T14:23:37Z
published: 2026-07-28T21:00:00Z
canonical: "helpcenter.securiti.ai/microsoft-dataverse-connectors-1"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Microsoft Dataverse

Microsoft Dataverse is a cloud-based data platform that lets you securely store and manage data used by business applications within Microsoft Power Platform. Data in Dataverse is organized into tables made up of rows and columns, with each column designed to store a specific data type. Beyond a base set of standard tables covering common business scenarios, organizations can create custom tables and populate them using Power Query, which app makers can then leverage through Power Apps to build data-driven applications.

The Dataverse connector lets you integrate your Microsoft Dataverse environment with Securiti to discover and govern structured data stored across your standard and custom tables.

Dataverse falls under the category of monitored, structured data systems. For more information, see [data systems classification](/latest/docs/managing-data-system-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Microsoft Dataverse (Self-hosted) | - Sensitive Data Intelligence - DSR Automation using SQL queries |

### Supported pod types

- Standard Securiti Pods and ePods.

### Supported authentication methods

- Microsoft Azure application based authentication
  - OAuth based authentication

#### Supported Keyring for Microsoft Dataverse (Self-hosted) connector

You can use a keyring support to store authentication credentials in a vault during the connector configuration process to securely access your credentials from a vault. For more information, see [Managing Keyrings](/latest/docs/managing-credentials-using-keyrings).

- **HashiCorp**. HashiCorp is OAuth supported with the Microsoft Dataverse connector. For more information, see [Configuring HashiCorp credential vaults](/latest/docs/hashicorp-credential-vault-authentication-methods-in-hashicorp-vault).

You must configure the HashiCorp OAuth token to activate the connector using the HashiCorp vault authentication. For more information, see [Configure the Hashicorp OAuth token for Microsoft Dataverse](/latest/docs/optional-configure-the-hashicorp-oauth-token-for-microsoft-dataverse)

### Supported items for classification scans

For more information about Classification Scans, see [Understanding Discovery Scans](/latest/docs/discovery-scans).

Following entities are scanned:

- Tables

### Prerequisites for configuring Microsoft Dataverse connectors

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your Microsoft Dataverse with a Self-hosted connector. Make sure the Pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti.ai endpoints, Microsoft Graph API endpoints, and Microsoft Dataverse endpoints.

For more information on configuring pods, see [Securiti pods](/latest/docs/pods-cluster-version-v128-and-later).

#### 2. Admin access

You must be an administrator of the following entities to grant permissions and roles to apps and users.

- Azure Portal.
- Power Platform

#### 3. Assign Security roles to selected user in Power Apps

You must assign Security role to selected user in Power App platform.

For more information, see [Step 4 - Assign Security role to the user](/latest/docs/grant-permissions-and-obtain-credentials-in-microsoft-dataverse).

#### 4. Allowlisting URLs for Discovery scans

You must allowlist the following URLs to run the Discovery scan effectively.

- *https://login.microsoftonline.com*
- *https://<dynamic value>.api.crm.dynamics.com.*

This is dynamic value provided in Host URL. You must use your Host URL in place of dynamic value.

#### 5. Permissions and use cases for Microsoft Dataverse

| Modules use case | Constraint | Permissions/ Roles | Explanation of use case |
| --- | --- | --- | --- |
| - Discovery Scan (Sensitive Data Intelligence) - DSR Automation (Data Subject Rights) | SDI Discovery Scans and DSR Automation Indexing is only available on the self- hosted connector | **user_impersonation** **Security Role in Power App** | These permissions let Securiti to read the tables for classification purposes and to build the Personal Data Index for DSR Automation. |

### Steps to connect Microsoft Dataverse connector with Securiti

To configure the Microsoft Dataverse connector, perform the procedures in the following topics:

1. Configure and deploy Pod. See above in prerequisites section.
2. [Grant permissions and obtain credentials in Microsoft Dataverse](/latest/docs/grant-permissions-and-obtain-credentials-in-microsoft-dataverse).
3. [(Optional) Configure the Hashicorp OAuth token for Microsoft Dataverse](/latest/docs/optional-configure-the-hashicorp-oauth-token-for-microsoft-dataverse).
4. [Connect Microsoft Dataverse connector with Securiti](/latest/docs/connect-microsoft-dataverse-connector-with-securiti).
5. [Configure discovery scans for Microsoft Dataverse](/latest/docs/configure-discovery-scans-for-microsoft-dataverse).

#### Additional resources

- [Do Table Training for Microsoft Dataverse](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems).
- [Fulfilling DSR Requests in Microsoft Dataverse](/latest/docs/fulfilling-dsr-requests-in-microsoft-dataverse).
