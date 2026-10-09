---
title: "Azure Data Lake Storage (ADLS) Gen2"
slug: "azure-data-lake-storage-adls-gen2-connectors"
status: "new"
updated: 2026-07-30T08:14:39Z
published: 2026-07-30T08:14:54Z
canonical: "helpcenter.securiti.ai/azure-data-lake-storage-adls-gen2-connectors"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Azure Data Lake Storage (ADLS) Gen2

This documentation covers connector activation process for both self-hosted and Securiti Cloud version of Azure Data Lake Storage Gen2 connector. The Securiti Cloud connector is a scanless connector and is supported for Workflow only. Azure Data Lake Storage (ADLS) Gen2 (Self-hosted) falls under the category of [monitored, unstructured data system](/v1/docs/managing-data-system-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Azure Data Lake Storage (ADLS) Gen2 (Self-hosted) | - Sensitive Data Intelligence - DSR Automation using full Scan - Data Inventory Sync - Breach Analysis |
| Azure Data Lake Storage (ADLS) Gen2 (Securiti cloud) | Workflow |

### Supported pod types for self-hosted connector

- Standard Securiti Pod.
- Elastic Pod/ EDSS.

### Supported authentication methods

| Authentication method | Authentication credentials |
| --- | --- |
| Account Key | Account Key |
| Azure Service Principal (For self-hosted connector only) | - Client ID - Client Secret |

#### Keyring support for Azure Data Lake Storage (ADLS) Gen2 (Self-hosted) connector

You can use a keyring support to store authentication credentials in a vault product during the connector configuration process to securely access your credentials from a vault. See [Managing Keyrings](/latest/docs/managing-credentials-using-keyrings) for more information.

- **HashiCorp**: For more information, see [configuring HashiCorp credential vaults](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault).

If using Hashicorp OAuth token for Azure Data Lake Storage (ADLS) Gen2, see [(Optional) Configure the HashiCorp OAuth token for Azure Data Lake Storage (ADLS) Gen2](/latest/docs/optional-configure-the-hashicorp-oauth-token-for-azure-data-lake-storage-adls-gen2).
- **Azure Key Vault**: For more information, see [configuring Azure Key Vault](/latest/docs/configuring-credential-vaults-azure-key-vault).

### Supported items for Inventory and Classification Scans

For more information on inventory and entitlement scans, see [Data Inventory Sync and Entitlement Scan for data systems](/latest/docs/data-inventory-sync-for-self-hosted-connectors).

For more information about classification in discovery scans, see [Understanding Discovery Scans](/latest/docs/discovery-scans).

- File Systems
- Folder Paths

### Prerequisites for configuring the Azure Data Lake Storage (ADLS) Gen2 connector

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your Azure Data Lake Storage (ADLS) Gen2 with a Self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints. For more information, see [Allow-listing domains or IPs for data system connectors](/latest/docs/allow-listing-domains-or-ips-for-data-system-connectors).

For more information on configuring pods, see [Securiti pods and elastic pods](/latest/docs/securiti-pods-and-elastic-pods).

#### 2. Azure Storage Account

You must have an Azure Storage account in order to facilitate the connector activation process between your Azure Data Lake Storage (ADLS) Gen2 and the Securiti app.

For more information, see [Using Storage Account authentication](/latest/docs/obtain-authentication-credentials-in-azure-data-lake-storage-adls-gen2) .

#### 3. Use cases and permissions for Azure Data Lake Storage (ADLS) Gen2

To provide the Azure Data Lake Storage (ADLS) Gen2 access for data discovery and classification, use the following use cases and permissions.

| Modules use case | Constraint | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| - Data Inventory Sync (Sensitive Data Intelligence) - Discovery Scan (Sensitive Data Intelligence) - DSR Automation (Data Subject Rights (DSR)) | Data Inventory Sync, Discovery Scan, and DSR is only available for self-hosted connector. | **For Azure Service Principal authentication** - Storage Blob Data Reader role. | These permissions let Securiti discover and scan files for inventory and classification purposes and to build the Personal Data Index for DSR Automation. |

### Connect the Azure Data Lake Storage (ADLS) Gen2 connector with Securiti

This section covers the activation of Azure Data Lake Storage (ADLS) Gen2 (self-hosted) and (Securiti cloud) connectors.

#### Steps to connect the Azure Data Lake Storage (ADLS) Gen2 (self-hosted) connector with Securiti

To configure the Azure Data Lake Storage (ADLS) Gen2 (self-hosted) connector, perform the following procedures in sequence:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. Activate your Self-hosted data system's connector on the pod as described in [Securiti pods and elastic pods](/latest/docs/securiti-pods-and-elastic-pods).

To use the Azure Data Lake Storage (ADLS) Gen2 data system, you must link your structured on-premises database to Securiti.
3. [Obtain authentication credentials in Azure Data Lake Storage (ADLS) Gen2](/latest/docs/obtain-authentication-credentials-in-azure-data-lake-storage-adls-gen2).
4. [(Optional) Configure the HashiCorp OAuth token for Azure Data Lake Storage (ADLS) Gen2](/latest/docs/optional-configure-the-hashicorp-oauth-token-for-azure-data-lake-storage-adls-gen2).
5. [Connecting Azure Data Lake Storage (ADLS) Gen2 with Securiti](/latest/docs/connecting-azure-data-lake-storage-adls-gen2-with-securiti).
6. [Configure discovery scans in Azure Data Lake Storage (ADLS) Gen2](/latest/docs/configure-discovery-scans-in-azure-data-lake-storage-adls-gen2).
7. [Configuring Data Inventory Sync for ADLS connector](/latest/docs/configuring-data-inventory-sync-for-adls-connector-en).

#### Steps to connect the Azure Data Lake Storage (ADLS) Gen2 (Securiti-Cloud) connector with Securiti

To configure the Azure Data Lake Storage (ADLS) Gen2 (Securiti-Cloud) connector, perform the following procedures in sequence:

1. [Obtain authentication credentials in Azure Data Lake Storage (ADLS) Gen2](/latest/docs/obtain-authentication-credentials-in-azure-data-lake-storage-adls-gen2).
2. [(Optional) Configure the HashiCorp OAuth token for Azure Data Lake Storage (ADLS) Gen2](/latest/docs/optional-configure-the-hashicorp-oauth-token-for-azure-data-lake-storage-adls-gen2).
3. [Connecting Azure Data Lake Storage (ADLS) Gen2 (Securiti-Cloud) with Securiti](/latest/docs/connecting-azure-data-lake-storage-adls-gen2-securiti-cloud-with-securiti).
4. [Configuring General permissions for Azure Data Lake Storage (ADLS) Gen2](/latest/docs/configuring-general-permissions-for-azure-data-lake-storage-adls-gen2).

#### Additional resources

- (For self-hosted connector only) [Viewing ADLS (self-hosted) metadata in Securiti](/latest/docs/viewing-adls-self-hosted-metadata-in-securiti-en).

## Related

- [Obtain authentication credentials in Azure Data Lake Storage (ADLS) Gen2](/obtain-authentication-credentials-in-azure-data-lake-storage-adls-gen2.md)
- [(Optional) Configure the HashiCorp OAuth token for Azure Data Lake Storage (ADLS) Gen2](/optional-configure-the-hashicorp-oauth-token-for-azure-data-lake-storage-adls-gen2.md)
- [Configure discovery scans in Azure Data Lake Storage (ADLS) Gen2](/configure-discovery-scans-in-azure-data-lake-storage-adls-gen2.md)
