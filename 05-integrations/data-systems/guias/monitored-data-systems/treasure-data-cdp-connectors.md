---
title: "Treasure Data CDP"
slug: "treasure-data-cdp-connectors"
status: "new"
updated: 2026-07-16T07:44:14Z
published: 2026-07-16T07:44:14Z
canonical: "helpcenter.securiti.ai/treasure-data-cdp-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Treasure Data CDP

Treasure Data's state-of-the-art CDP solution brings unparalleled capabilities to unify, manage, and activate customer data across our four brands and third-party platforms, empowering our ability to gain deep insights into customer behavior and preferences..

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Self-hosted connector | - DSR automation - Sensitive Data Intelligence |

### Supported pod types

- Standard Securiti pod

### Supported authentication methods

Treasure Data CDP supports the following authentication type for authenticating and integrating with Securiti

| Authentication Type | Authentication Credentials |
| --- | --- |
| - API-Key based authentication | - API Base URL - Port - Master API Key |

Keyring is not supported for Treasure Data CDP.

### Supported items for discovery scans

- Databases
- Tables

### Prerequisites for configuring Treasure Data CDP

### 1. Pod deployment

You must complete these prerequisites before connecting your Treasure Data CDP connector with Securiti

You must deploy a Securiti pod in your environment to connect your Treasure Data CDP with a self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints.

For more information on configuring pods, see [Securiti pods and elastic pods](/latest/docs/securiti-pods-and-elastic-pods).

### 2. Database instance requirement

You must have a running Treasure Data CDP database instance at your end. You must have active user that you need to assign permissions and obtain credentials. For more information, see [Obtain authentication credentials in Treasure Data CDP](/latest/docs/obtain-authentication-credentials-in-treasure-data-cdp).

### 3. JDBC driver requirement

You must upload the Treasure Data drivers to ensure successful authentication of self-hosted connector. For more information, see [Downloading JDBC drivers for SQL connectors](/latest/docs/downloading-jdbc-drivers-for-sql-connectors), and [Uploading JDBC driver files in Securiti](/latest/docs/uploading-jdbc-driver-files-in-securiti)

### 4. Upload SSL certificate to Trust Store

You must upload SSL certificate to Trust Store for successful authentication otherwise authenticate fails. The Treasure Data CDP service running at [api-presto.treasuredata.com](http://api-presto.treasuredata.com) is configured to only accept incoming connections that are encrypted using SSL or TLS.

For more information, see [Importing certificates into the Trust Store](/latest/docs/importing-certificates-into-the-trust-store).

### 5. Permissions and use cases

You must assign the permissions discussed in the table below for scanning and DSR search use cases.

| Modules use case | Constraint | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| - Discovery Scan (Sensitive Data Intelligence) - DSR Automation (Data Subject Rights) | SDI Discovery Scans and DSR Automation Indexing is only available on the self- hosted connector | **General access** | The permissions let Securiti to read to access or read records of the tables in database using the Master key for classification purpose and to build the Personal Data Index for DSR Automation. |

### Connect Treasure Data CDP connectors with Securiti

To configure the Treasure Data CDP connector, perform the following procedures in sequence:

1. [Obtain authentication credentials in Treasure Data CDP](/latest/docs/obtain-authentication-credentials-in-treasure-data-cdp)
2. [Connecting Treasure Data CDP with Securiti](/latest/docs/connecting-treasure-data-cdp-with-securiti)
3. [Configure discovery scans in Treasure Data CDP](/latest/docs/configure-discovery-scans-in-treasure-data-cdp).

## Additional resources

- [Fulfilling Treasure Data CDP DSR requests](/latest/docs/fulfilling-treasure-data-cdp-dsr-requests)
- [Table training for structured and hybrid data systems](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems)
