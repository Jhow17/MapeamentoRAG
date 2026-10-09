---
title: "Apache Hive"
slug: "apache-hive-connectors"
status: "new"
updated: 2026-07-16T05:35:39Z
published: 2026-07-16T05:35:39Z
canonical: "helpcenter.securiti.ai/apache-hive-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Apache Hive

The Apache Hive data warehousing frontend interface is an additional component to the underlying Apache Hadoop framework used for developing large scale big data systems. It provides users with an SQL-based command interface that they can use for modifying the aforementioned data warehouses using a variety of queries. The Hive interface is more efficient in terms of making modifications to large amounts of data or preprocessing data before further manipulation as compared to Spark, another SQL-based tool for modifying big data systems.

Hive falls under the category of [monitored, structured data system](/latest/docs/managing-data-system-connectors#data-systems-classification).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Apache Hive (Self-hosted) | Self-hosted connector supports: - Sensitive Data Intelligence - DSR Automation using SQL queries - Data Access Control |

### Supported pod types for self-hosted connector

Apache Hive (Self-hosted) supports standard Securiti Pod.

### Supported authentication methods

Securiti supports following authentication methods for Apache Hive (Self-hosted) connector:

- Password
- Keytab

#### Keyring support for Apache Hive (self-hosted) connector

You can use following supported keyring to store authentication credentials in a vault product during the connector configuration process to securely access your credentials from a vault. To learn more about keyrings, refer to [Managing Keyrings](/latest/docs/managing-credentials-using-keyrings).

- **HashiCorp**: For more information, see [HashiCorp credential vault](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault).

### Supported items for Classification scans

Securiti scans the following entities for Apache Hive during discovery scans and Data Inventory Syncs. For more information about classification in discovery scans, see [Understanding Discovery Scans](/latest/docs/discovery-scans).

- Databases
- Schemas
- Tables
- Views

### Connect Apache Hive connector with Securiti

This section covers the methods to integrate your Apache Hive (Self-hosted) connector with Securiti.

#### Steps to connect the Apache Hive connector with Securiti

To configure the Apache Hive (Self-hosted) connector, perform the procedures in the following topics:

1. Deploy and configure Pod using [Securiti Pods and Elastic Pods](/latest/docs/securiti-pods-and-elastic-pods).

> [!NOTE]
> Note
> 
> Securiti Pods don’t support a self-signed certificate from a data store as the Pod isn’t able to validate the SSL destination server.
> 
> That's why it's important to leverage a CA (internal or public) to sign a CSR from the Knox Gateway. In the case that you have used an Internal CA to sign the CSR, you now need to upload the ICA’s root certificate to the Securiti Dashboard so that the pod can use it to validate the SSL certificate presented by the Knox Gateway.
> 
> See [Importing certificates into the Trust Store](/v1/docs/securiti-pods-and-elastic-pods) for more information.
2. [Connecting Apache Hive with Securiti](/latest/docs/connecting-apache-hive-with-securiti).
3. [Configure discovery scans in Apache Hive](/latest/docs/configure-discovery-scans-in-apache-hive).

**Additional resources**

- [Fulfilling DSR requests for Apache Hive](/latest/docs/fulfilling-dsr-requests-for-apache-hive).
- [Table training for structured and hybrid data systems](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems).

An application running on a server or compute instance that connects with your on-premises or private data systems to:

- Intelligently scan them to classify content
- Identify personal data
- Upload hashed values of the personal data to your Securiti account
- Act as a hop-off point for DSR requests for your on-premises and user-defined data systems

## Related

- [Importing certificates into the Trust Store](/importing-certificates-into-the-trust-store.md)
- [Fulfilling DSR requests for Apache Hive](/fulfilling-dsr-requests-for-apache-hive.md)
