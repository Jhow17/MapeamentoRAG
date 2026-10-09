---
title: "Gmail (Google Workspace)"
slug: "g-suite-gmail-message-body-attachments-connectors"
status: "update"
updated: 2026-06-23T20:24:05Z
published: 2026-06-23T20:24:05Z
canonical: "helpcenter.securiti.ai/g-suite-gmail-message-body-attachments-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Gmail (Google Workspace)

> [!WARNING]
> Important
> 
> Securiti recommends using the **Gmail (Google Workspace)** (latest) connector for this data system to access new capabilities, ongoing improvements, and full platform support.
> 
> **Legacy connectors are in maintenance mode and do not receive new features or enhancements.** This includes, but is not limited to:
> 
> - API version upgrades
> - Additional Keyrings for this connector
> - New or enhanced scopes for Discovery Scan and Data Inventory Sync
> - Additional modules (for example, HyperDrive, Data Inventory Sync, and DSR)
> - Any future functionality introduced for this connector
> 
> Some of the enhancements listed above may not be available on this connector. Refer to the recommended connector’s documentation for currently supported modules and capabilities.

Gmail (Google Workspace) is an email service developed by Google for businesses and enterprises, offering you a platform to send, receive, and organize your emails. Google Workspace is a [monitored, unstructured data system](/latest/docs/managing-data-system-connectors#data-systems-classification).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Gmail (Google Workspace) (self-hosted) > [!NOTE] > Note > > Securiti recommends you to use this connector. | - DSR Automation using Full Scan - Discovery Scan - Data Inventory Sync and Entitlement Scan - Breach Analysis |
| Gmail (Google Workspace) (Securiti cloud) | - DSR Automation using APIs - Breach Analysis - Security Posture Scan |
| Gmail Message Body (Legacy) | - DSR Automation using Full Scan - Discovery Scan - Breach Analysis |

### Supported pod types for self-hosted connector

- Standard Securiti pod
- Elastic Pod / EDSS

> [!NOTE]
> Note
> 
> Elastic Pod/EDSSOnly is only supported for Gmail Message Body (Legacy) connector

### Supported authentication methods

- For Self-hosted connector:
  - OAuth authentication
- For Securiti Cloud connector:
  - OAuth authentication

### Supported keyrings

Securiti supports the following credential vaults as keyrings for Gmail (Google Workspace) (self-hosted) connector:

- [AWS Secrets Manager](/latest/docs/configuring-credential-vaults-aws-secrets-manager-credential-vault)

### Supported Items for classification scans

During Discovery scans for Gmail (Google Workspace), Securiti scans:

#### For Gmail (Google Workspace) connector

- All the domains present in the data system
- All the groups present in the domain
- All the users present in the group
- All the folders present for the users
- All the message body content and attachments in the folder

#### For Gmail Message Body (Legacy) connector

- All the domains present in the data system
- All the groups present in the domain
- All the users present in the group
- Only the message body in the “**Sent**” folder

Additional resources

- For more information, see [Configure discovery scans in Gmail (Google Workspace) (self-hosted)](/latest/docs/configure-discovery-scans-in-g-suite-gmail-message-body-attachments)
- For more information about classification in discovery scans, see [Discovery scans](/latest/docs/discovery-scans).

### Prerequisites for configuring the Gmail (Google Workspace) connector

#### 1. Pod deployment

> [!WARNING]
> **Important**
> 
> Pod deployment is required for self-hosted connectors only.

You must deploy a Securiti pod in your environment to connect your Gmail (Google Workspace) with a self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints.

For more information on configuring pods, see [Securiti pods and elastic pods](/latest/docs/securiti-pods-and-elastic-pods).

#### 2. Admin access

You must be an admin for your Google account to create projects and allow scopes.

#### 3. Allowlisting APIs for Data Inventory Sync

You must allowlist the following APIs to successfully run the Data Inventory Sync and Discovery Scans for Gmail (Google Workspace) (Self-hosted) connector using the [Allowlisting URLs and APIs for Gmail data inventory sync.](/latest/docs/allowlisting-urls-and-apis-for-scanning-gmail-google-workspace)

For more information, see [Configure Data Inventory Sync for Gmail (Google Workspace)](/latest/docs/configure-data-inventory-sync-for-gmail-google-workspace).

#### 4. Use cases and permissions

This section covers use cases and permissions required for Gmail (Google Workspace) self-hosted and Securiti cloud connectors.

|  |  |  |  |
| --- | --- | --- | --- |
| - Sensitive Data Intelligence (Discovery scan) - Inventory metadata sync - Data Subject Request (DSR) Automation | SDI through Discovery Scans and DSR Automation Indexing is only available on the self-hosted connector. | OAuth scopes: - `https://www.googleapis.com/auth/admin.directory.customer.readonly,` - `https://www.googleapis.com/auth/admin.directory.user.readonly,` - `https://www.googleapis.com/auth/admin.directory.domain.readonly,` - `https://www.googleapis.com/auth/admin.directory.group.readonly,` - `https://www.googleapis.com/auth/gmail.readonly,` - `https://www.googleapis.com/auth/drive.metadata.readonly,` - `https://www.googleapis.com/auth/drive.photos.readonly,` | These permissions let Securiti reads the files and metadata in Gmail for classification purposes. These permissions also build the Personal Data Index for DSR Automation and enables PII data search. |
| Data Inventory Sync and Gencore AI Entitlement scanning | - Available for self-hosted connector only. - Requires allowlisting APIs between your deployed Securiti pod and the Google Workspace APIs. | **OAuth scopes:** - `https://www.googleapis.com/auth/admin.directory.customer.readonly` - `https://www.googleapis.com/auth/admin.directory.user.readonly` - `https://www.googleapis.com/auth/admin.directory.domain.readonly` - `https://www.googleapis.com/auth/admin.directory.group.readonly` - `https://www.googleapis.com/auth/gmail.readonly` | This permission lets Securiti read the files and file metadata in Gmail (Google Workspace) for inventory. The permission also lets Securiti discover entitlements. |
| Security Posture Scan | This capability lets Securiti apply Google APIs for Gmail Security Posture Findings (only for Securiti cloud connector) | **OAuth scopes:** - `https://www.googleapis.com/auth/admin.directory.customer.readonly` - `https://www.googleapis.com/auth/admin.reports.audit.readonly` | These permissions let Securiti retrieve the configuration details required to evaluate the Security Posture rules. |

## Connect Gmail (Google Workspace) with Securiti

#### Steps to connect the Gmail (Google Workspace) or Gmail Message Body (Legacy) connector with Securiti

To configure the Gmail (Google Workspace) or Gmail Message Body (Legacy) connector served through pod:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. [Prerequisites and obtaining authentication credentials for Gmail (Self-hosted)](/latest/docs/prerequisites-and-obtaining-authentication-credentials-in-google-apps)
3. [Connecting the Gmail (Google Workspace) (self-hosted) with Securiti](/latest/docs/new-ui-connecting-the-google-workspace-gmail-message-body-attachments-with-securiti).
4. [Configuring data inventory sync for Gmail (Google Workspace)](/latest/docs/configure-data-inventory-sync-for-gmail-google-workspace)
5. [Configure discovery scans in Gmail (Google Workspace) (self-hosted)](/latest/docs/configure-discovery-scans-in-g-suite-gmail-message-body-attachments).

#### Steps to connect the Gmail (Google Workspace) Securiti Cloud connector with Securiti

To activate the Gmail (Google Workspace) (Securiti cloud) connector, perform the procedures in the following topics:

1. [Prerequisites and obtaining authentication credentials for Gmail (Securiti cloud)](/latest/docs/prerequisites-and-obtaining-authentication-credentials-for-gmail-securiti-cloud)
2. [Connecting the Gmail (Google Workspace) (Securiti cloud) with Securiti](/latest/docs/new-ui-connecting-the-g-suite-gmail-google-workspace-with-securiti)
3. [Configuring General permissions for Gmail (Google Workspace)](/latest/docs/new-ui-configuring-general-permissions-for-g-suit-gmail)

#### Additional resources

1. [Fulfilling DSR requests for Gmail (Google Workspace) (self-hosted)](/latest/docs/fulfilling-g-suite-gmail-message-body-attachments-dsrs).
2. [Fulfilling DSR requests for Gmail (Google Workspace) (Securiti cloud)](/latest/docs/fulfilling-dsr-requests-for-g-suite-gmail)/
