---
title: "MongoDB"
slug: "mongodb-connectors"
status: "update"
updated: 2026-08-11T04:32:05Z
published: 2026-08-11T04:32:05Z
canonical: "helpcenter.securiti.ai/mongodb-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# MongoDB

MongoDB is a leading NoSQL database that provides flexibility and scalability for managing large volumes of complex data. Although MongoDB is inherently schema-flexible, it can be analyzed in a structured manner within the platform to support discovery, governance, and compliance processes.

MongoDB falls under the category of monitored and structured data systems. For more information, see [Data systems classification](/latest/docs/data-system-connectors).

### Supported modules

MongoDB data system connector supports the following modules:

| Connector type | Modules supported |
| --- | --- |
| MongoDB (Self-hosted) connector | - Sensitive Data Intelligence (Discovery scan) - DSR Automation using SQL queries |

### Supported pod types

Standard Securiti pod

### Supported authentication methods

MongoDB supports the following authentication types for authenticating and integrating with Securiti.

| Authentication Type | Authentication Credentials |
| --- | --- |
| Basic | - User (if keyring is not used) - Password (if keyring is not used) |
| Kerberos | **Kerberos Password:** - User (if keyring is not used) - Password (if keyring is not used) - Service Principal - Kerberos KDC - Kerberos Realm **Kerberos Keytab:** - User Principal - Service Principal - Kerberos KDC - Kerberos Realm - Keytab file |
| X.509 Certificate Authentication | - Keystore File - Keystore Password |

#### Keyring support for MongoDB

You can use a keyring during the connector configuration process to securely access your credentials from a vault. For more information, see [Managing Keyrings](/latest/docs/creating-keyrings).

For more information on the MongoDB supported vaults, refer to the table below.

| Authentication method | Supported vaults |
| --- | --- |
| Password | HashiCorp, CyberArk, CredStash, and Azure Key Vault |
| Kerberos (Password) | HashiCorp and CyberArk |
| Kerberos (Keytab) | CyberArk only |
| X.509 Certificate | CyberArk only |

- **Azure key vault**. See [Configuring Azure key vault](/latest/docs/configuring-credential-vaults-azure-key-vault) for more information.
- **CredStash**. See [Configuring Credstash credential vaults](/latest/docs/configuring-credential-vaults-credstash-credential-vault) for more information.
- **CyberArk**. See [Configuring CyberArk credential vaults](/latest/docs/cyberark-credential-vault) for more information.
- **HashiCorp**. See [Configuring HashiCorp credential vaults](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault) for more information.

### Supported connection strings

- Standard MongoDB connection string
- MongoDB + SRV connection string

> [!NOTE]
> Note
> 
> Kerberos authentication is not available for MongoDB connection + SRV connection string.

### Supported items for discovery scans

- Databases
- Schemas
- Tables
- Views

### Prerequisites for configuring MongoDB connector

You must complete these prerequisites before connecting your MongoDB connector with Securiti.

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your MongoDB with a self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints.

For more information on configuring pods, see [Securiti pods](/latest/docs/securiti-pods-and-elastic-pods).

#### 2. Access to MongoDB

You must have access and privileges to the MongoDB instance to create a user and assign permissions.

For more information, see [Prerequisites for MongoDB connector](/latest/docs/granting-db-permissions).

#### 3. Allowlist the pod IP address

In addition to creating a MongoDB user and/or configuring mTLS, ensure that your MongoDB Atlas project’s IP access list includes the IP address of the pods.

For MongoDB Atlas, perform the following step to add a pod IP address:

- To add an IP address, navigate to **Security** in the **Clusters** view, then choose **Database & Network Access** > **IP Access List** > **Add IP Address**, and add the pod IP.

#### 4. Use cases and permissions

This section covers use cases and permissions required for MongoDB.

| Modules | Permissions | Use case |
| --- | --- | --- |
| - Discovery Scan (Sensitive Data Intelligence) - DSR Automation (Data Subject Request) | **read** access | Lets Securiti connect and access your MongoDB database(s) for data scanning. |

### Steps to connect MongoDB with Securiti

To configure the MongoDB self-hosted connector, perform the procedures in the following topics:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. Create a connection and obtain credentials:
  - [Create a MongoDB connection without srv](/latest/docs/obtain-credentials-for-mongodb-without-srv-connection).
  - [Create a MongoDB connection with srv](/latest/docs/granting-db-permissions).
  - [Configuring mTLS authentication](/latest/docs/configuring-mtls-authentication).
  - [Obtain credentials for various connection methods](/latest/docs/prerequisites-for-mongodb-connector).
3. [Connecting the MongoDB connector with Securiti](/latest/docs/connecting-the-mongodb-connector-with-securiti).
4. [Configure discovery scans in MongoDB](/latest/docs/configure-discovery-scans-in-mongodb).

#### **Additional resources**

- [Troubleshooting for MongoDB](/latest/docs/troubleshooting-for-mongodb).
- [Fulfilling DSR requests for MongoDB](/latest/docs/fulfilling-dsr-requests-for-azure-cosmos-for-mongodb).
