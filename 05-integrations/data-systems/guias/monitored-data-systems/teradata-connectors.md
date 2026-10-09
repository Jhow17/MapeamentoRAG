---
title: "Teradata"
slug: "teradata-connectors"
status: "update"
updated: 2026-07-16T07:43:53Z
published: 2026-07-16T07:44:00Z
canonical: "helpcenter.securiti.ai/teradata-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Teradata

Teradata is an open source database management system for storing, managing, and analyzing large volumes of data. Scalable and robust, Teradata is used in all business sectors, for customer data management, master data management, finance management, supply chain management, and more.

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Teradata (Self-hosted) | - Sensitive Data Intelligence - DSR Automation |

### Supported pod types

- Standard Securiti Pod.

### Supported authentication method

- Basic authentication
- LDAP authentication

#### Keyring support for Teradata (Self-hosted) connector

You can use a keyring support to store authentication credentials in a vault product during the connector configuration process to securely access your credentials from a vault. See [Using Keyrings](/latest/docs/managing-credentials-using-keyrings) for more information.

- [AWS Secrets Manager](/latest/docs/configuring-credential-vaults-aws-secrets-manager-credential-vault)
- [CredStash](/latest/docs/configuring-credential-vaults-credstash-credential-vault)
- [CyberArk](/latest/docs/cyberark-credential-vault-1)
- [HashiCorp](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault)

### Supported items for Classification scans

For more information about classification in discovery scans, see [Understanding Discovery Scans](/v1/docs/discovery-scans).

- Databases
- Tables
- Schemas
- Views

### Prerequisites for configuring Teradata (Self-hosted) connector

### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your Teradata with a (Self-hosted) connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints, and Teradata API endpoints.

For more information on configuring pods, see [Securiti pods and elastic pods](/latest/docs/securiti-pods-and-elastic-pods).

### 2. Required database permissions

You must have a create user rights in Teradata database to grant permissions to the user. For more information, see [Create a user and assign permissions in Teradata](/latest/docs/create-a-user-and-assign-permissions-in-teradata) for connecting Teradata to Securiti

### 3. JDBC driver requirement

We assume, for the SeIf-hosted connector, you have the required drivers before activation. Otherwise, Securiti shows an error message reminding you to upload drivers

### 4. Use cases and permissions for Teradata

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| - Sensitive Data Intelligence (SDI) - Data Subject Request (DSR) Automation Indexing | SDI Discovery Scans and DSR Automation Indexing is only available on the self- hosted connector. | **Read** permission to Teradata user | These permissions let Securiti read the files and file metadata in Teradata for classification purposes. These permissions also build the Personal Data Index for DSR Automation. |

## Connect Teradata connectors with Securiti

To configure the Teradata connector, perform the procedures in the following topics:

1. [Create a user and assign permissions in Teradata](/latest/docs/create-a-user-and-assign-permissions-in-teradata)
2. [Connecting Teradata with Securiti](/latest/docs/connecting-teradata-with-securiti)
3. [Configure discovery scans in Teradata](/latest/docs/configure-discovery-scans-in-teradata)

### Additional resources

- [Table training for structured and hybrid data systems](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems)
