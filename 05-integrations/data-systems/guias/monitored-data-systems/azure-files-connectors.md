---
title: "Azure Files"
slug: "azure-files-connectors"
status: "update"
updated: 2026-07-30T08:21:19Z
published: 2026-07-30T08:21:28Z
canonical: "helpcenter.securiti.ai/azure-files-connectors"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Azure Files

Microsoft Azure Files is a cloud storage solution that lets you store cloud-cached files in on-premises-based databases. The Azure Files suite uses the Server Message Block protocol that provides the concurrent synchronization of files, networked peripherals, and serial ports.

Azure Files is compliant and compatible with Azure Active Directory (AAD) integration that provides secure migration of data from on-premises data sources to cloud based storage drives. Access Control Lists are also available as toggles for authorized access to contents stored within the Azure Files cloud by way of requiring AAD credentials for login permissions on part of end-users who wish to access secure data within the Azure Files cloud.

Azure Files falls under the category of monitored, unstructured data systems. For more information, see [data system classification](/latest/docs/managing-data-system-connectors#data-systems-classification).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Azure Files (Self-hosted) | It supports: - Sensitive Data Intelligence - DSR Automation - Data Breach Management |

### Supported pod types for self-hosted connector

- Standard Securiti pod
- Elastic Pod/ EDSS

### Supported authentication methods

| Authentication method | Authentication credentials |
| --- | --- |
| Storage Account | Account Key |
| Service Principal | - Application (Client) Id - Application (Client) Secret Key |

#### Keyring support for Azure Files (Self-hosted) connector

You can use a keyring support to store authentication credentials in a vault product during the connector configuration process to securely access your credentials from a vault. See [Managing Keyrings](/v1/docs/using-keyrings) for more information.

- [HashiCorp](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault)
- [AWS Secrets Manager](/latest/docs/configuring-credential-vaults-aws-secrets-manager-credential-vault)
- [Azure Key Vault](/latest/docs/configuring-credential-vaults-azure-key-vault)
- [CredStash](/latest/docs/configuring-credential-vaults-credstash-credential-vault)

### Supported items for Inventory and Classification Scans

Securiti scans the following data for Azure Files data system. For more information about classification in discovery scans, see [Understanding Discovery Scans](/v1/docs/discovery-scans).

- Azure File Share(s)

### Prerequisites for configuring the Azure Files connector

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your Azure Files with a Self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints. For more information, see [Allow-listing domains or IPs for data system connectors](/latest/docs/allow-listing-domains-or-ips-for-data-system-connectors).

For more information on configuring pods, see [Securiti variables: Platform name pods and elastic pods](/v1/docs/securiti-pods-and-elastic-pods).

#### 2. Azure Storage account or Service Principal

When using Storage Account authentication, you must have an Azure Storage account in order to facilitate the connector activation process between your Azure file shares and the Securiti app.

For more information, see [Obtain authentication credentials in Azure Storage account](/latest/docs/obtain-authentication-credentials-in-azure-storage-account).

In case you are using the Service Principal authentication, ensure you create and assign the required roles to the service principal in Microsoft Entra ID. For more information, see [Using Service Principal to authenticate Azure Files](/latest/docs/using-service-principal-to-authenticate-azure-files).

#### 3. Use cases and permissions for Azure Files

To provide the Azure Files access for data discovery and classification, use the following use cases and permissions.

| Modules use case | Permissions | Explanation of use case |
| --- | --- | --- |
| - Discovery Scan (Sensitive Data Intelligence) - DSR Automation (Data Subject Rights (DSR)) | **For Service Principal authentication** - `Storage File Data Privileged Reader` role - For custom role, add the following **Microsoft Storage** permissions: - `List File Services` - `Get File Service Properties` - `Get File Share` - `List File Shares` | These permissions let Securiti discover and scan file shares for inventory and classification purposes and to build the Personal Data Index for DSR Automation. |
| Data Labeling Policy and File Quarantine Policy | **For Service Principal authentication** - `Storage File Data Privileged Reader` - `Storage File Data Privileged Contributor` | These permissions let Securiti view, manage, and apply labels to Azure File shares. With these permissions, you can apply the Data Labelling Policy to your files. |

### Connect the Azure Files data system connector with Securiti

To configure the Azure Files connector, perform the following procedures in sequence:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. [Obtain authentication credentials in Azure Storage account](/v1/docs/obtain-authentication-credentials-in-azure-storage-account) or [Using Service Principal to authenticate Azure Files](/v1/docs/using-service-principal-to-authenticate-azure-files).
3. [Connecting the Azure Files with securiti](/latest/docs/connecting-the-azure-files-with-securiti)
4. [Configure discovery scans in Azure Files](/v1/docs/configure-discovery-scans-in-azure-files).

#### Additional resources

[Fulfilling DSR requests for Azure Files](/v1/docs/fulfilling-dsr-requests-for-azure-files)

## Related

- [Using Service Principal to authenticate Azure Files](/using-service-principal-to-authenticate-azure-files.md)
- [Configure discovery scans in Azure Files](/configure-discovery-scans-in-azure-files.md)
- [Fulfilling DSR requests for Azure Files](/fulfilling-dsr-requests-for-azure-files.md)
