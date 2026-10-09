---
title: "Oracle Object Storage"
slug: "oracle-object-storage-connectors"
status: "new"
updated: 2026-08-11T10:30:39Z
published: 2026-08-11T10:30:39Z
canonical: "helpcenter.securiti.ai/oracle-object-storage-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Oracle Object Storage

Oracle Object Storage is a cloud-based enterprise services suite which include storage, networking and application solutions operating over a set of geographical disparate Oracle Data Centers.

In terms of its role in the data processing cycle for potential, Oracle assumes the role of a processor to a client enterprise (which is designated as a controller of user information tentative for processing by Oracle as per the client’s needs). Users of Oracle’s Cloud-based services are also expected to ensure breach detection within their databases as Oracle Object Storage alone does not yet distinguish authorized/unauthorized logins to a particular user’s account.

The Oracle Object Storage connector lets you integrate your environment with Securiti to discover and govern unstructured data stored across your Oracle cloud infrastructure.

Oracle Object Storage falls under the category of monitored, unstructured data systems. For more information, see [data systems classification](/latest/docs/managing-data-system-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Oracle Object Storage (Self-hosted) | - Sensitive Data Intelligence - DSR Automation using Full Scan - Breach Analysis |

### Supported pod types for self-hosted connector

- Standard Securiti
- Elastic pods (EDSS)

### Supported authentication methods

Oracle Object Storage (self-hosted) supports the following:

- Basic Authentication
- Oracle Cloud Infrastructure account

#### Keyring support for self-hosted connector

You can use a keyring support to store authentication credentials in a vault during the connector configuration process to securely access your credentials from a vault. For more information, see [Managing Keyrings](/latest/docs/managing-credentials-using-keyrings) for more information.

Securiti currently supports the following keyrings for Oracle Object Storage:

- **CredStash**. For more information, see [CredStash credential vault](/latest/docs/configuring-credential-vaults-credstash-credential-vault)
- **HashiCorp.** For more information, see [HashiCorp credential vault](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault)

### Supported items for classification scans

Securiti supports the following items for classification. For more information, see [Understanding Discovery Scans](/latest/docs/discovery-scans).

- Objects in buckets.

### Prerequisites for configuring Oracle Object Storage in Securiti

You must complete these prerequisites before connecting your Oracle Object Storage connector with Securiti.

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your Oracle Object Storage with a self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints.

For more information on configuring pods, see [Securiti pods](/latest/docs/securiti-pods-and-elastic-pods).

#### 2. Admin access

You must have admin access to use API Permissions and API Signing Keys for the module you want to use and add roles for successful Connector Authentication.

#### 3. Permissions and use cases for Oracle Object Storage

This section covers use cases and permissions required for Oracle Object Storage (Self-hosted) connectors.

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| - Sensitive Data Intelligence (SDI) - Data Subject Request (DSR) Automation Indexing - Breach Analysis | You must grant admin consent to all API permissions. | Access to create **OCI Directory.** Ability to create **API Keys** (specifically Public)**.** **API Permissions** for successful Connector authentication. Access to add **Roles** to user accounts. | These permissions let Securiti to read private key files, tables and schema metadata in Oracle for classification purposes and to build the Personal Data Index for DSR Automation. |

### Steps to connect the Oracle Object Storage connector with Securiti

To configure the Oracle Object Storage connectors, perform the procedures in the following topics:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. [Obtain authentication credentials for Oracle Object Storage](/latest/docs/obtain-authentication-credentials-oracle-object-storage).
3. [Generate Oracle API signing keys](/latest/docs/generate-oracle-api-signing-keys).
4. [Save the public access key to your Oracle user account](/latest/docs/save-the-public-access-key-to-your-oracle-user-account).
5. [Connect Oracle Object Storage with](/latest/docs/connect-oracle-object-storage-connector-with-securiti) Securiti.
6. [Configuring Discovery Scans in Oracle Object Storage.](/latest/docs/configuring-discovery-scans-in-oracle-object-storage)

#### Additional resources

- [Configuring Oracle Object Storage Scanning](/latest/docs/configuring-oracle-object-storage-scanning).
- [Fulfilling DSR requests for Oracle Object Storage](/latest/docs/fulfilling-dsr-requests-for-oracle-object-storage).
