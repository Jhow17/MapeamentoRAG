---
title: "Greenplum"
slug: "greenplum-connectors"
status: "new"
updated: 2026-07-07T11:09:06Z
published: 2026-07-07T11:09:06Z
canonical: "helpcenter.securiti.ai/greenplum-connectors"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Greenplum

Greenplum Database is a powerful, massively parallel processing (MPP) database system designed to handle large-scale analytics, data warehousing, and business intelligence workloads. Built on PostgreSQL, it provides high performance, scalability, and flexibility for modern data-driven organizations..

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Greenplum (Self-hosted) | - Sensitive Data Intelligence - DSR Automation |
| Greenplum (Securiti Cloud) | - Sensitive Data Intelligence - DSR Automation |

### Supported pod types

- Standard Securiti Pod.

### Supported authentication method

- Basic authentication

### Supported items for Classification scans

For more information about classification in discovery scans, see [Understanding Discovery Scans](/latest/docs/discovery-scans).

- Databases
- Schemas
- Tables

### Prerequisites for configuring Greenplum (Self-hosted) connector

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your Greenplum with a Self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints, and Greenplum API endpoints. For more information, see the allow-listed URLs section in [Elastic pod manual deployment guide (private cloud)](/latest/docs/elastic-pods-v2).

For more information on configuring pods, see [Securiti pods and elastic pods](/latest/docs/securiti-pods-and-elastic-pods).

#### 2. Running Greenplum database instance

You must have a running Greenplum database instance at your end.

- For more information, refer to Greenplum [Installing the Greenplum Database Software](https://techdocs.broadcom.com/us/en/vmware-tanzu/data-solutions/tanzu-greenplum/7/greenplum-database/install_guide-install_gpdb.html) and set up a database according your environment.

#### 3. Create user rights

You must have create user rights to assign permissions and select database tables for scanning.

- For more information, see [Create a user and assign permissions in Greenplum](/latest/docs/create-a-user-and-assign-permissions-in-greenplum) for connecting Greenplum to Securiti

#### 4. Drivers required

You must upload the Greenplum or PostgresSQL drivers to ensure successful authentication of Self-hosted connector. For more information, see [Uploading JDBC driver files in Securiti](/latest/docs/uploading-jdbc-driver-files-in-securiti)

#### 5. Use cases and permissions for Greenplum

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| - Sensitive Data Intelligence (SDI) - Data Subject Request (DSR) Automation Indexing | SDI Discovery Scans and DSR Automation Indexing is only available on the self- hosted connector. | **SELECT** permission to Greenplum user. | These permissions let Securiti read the file metadata in Greenplum for classification purposes. These permissions also build the Personal Data Index for DSR Automation. |

### Connect Greenplum connectors with Securiti

This section covers the methods to integrate your Greenplum with Securiti using self-hosted or Securiti-Cloud connectors, depending on your setup.

#### Steps to connect the Greenplum (Self-hosted) connector with Securiti

To configure the Greenplum (Self-hosted) connector, perform the procedures in the following topics:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. Activate your Self-hosted data system's connector on the pod as described in [Securiti pods and elastic pods](/latest/docs/securiti-pods-and-elastic-pods).
3. [Create a user and assign permissions in Greenplum](/latest/docs/create-a-user-and-assign-permissions-in-greenplum)
4. [Connecting Greenplum (Self-hosted) with Securiti](/latest/docs/connecting-greenplum-self-hosted-with-securiti).
5. [Configure discovery scans in Greenplum](/latest/docs/configure-discovery-scans-in-greenplum)

#### Steps to connect the Greenplum (Securiti-Cloud) connector with Securiti

To configure the Greenplum (Securiti-Cloud) connector, perform the procedures in the following topics:

1. [Create a user and assign permissions in Greenplum](/latest/docs/create-a-user-and-assign-permissions-in-greenplum)
2. [Connecting Greenplum (Securiti-Cloud) with Securiti](/latest/docs/connecting-greenplum-securiti-cloud-with-securiti).

**Additional resources**

- [Table training for structured and hybrid data systems](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems).
