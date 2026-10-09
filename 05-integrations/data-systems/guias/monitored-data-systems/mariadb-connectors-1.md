---
title: "MariaDB"
slug: "mariadb-connectors-1"
status: "new"
updated: 2026-06-23T06:52:47Z
published: 2026-06-23T06:52:55Z
canonical: "helpcenter.securiti.ai/mariadb-connectors-1"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# MariaDB

MariaDB is an open-sourced commercially developed relational database system developed as a fork of the MySQL database framework. Developed primarily as a community-supported alternative in response to Oracle's acquisition of MySQL, limiting its third-party development. Many Unix/Linux-based distributions have accordingly added support for MariaDB as a potential replacement for MySQL due to its open-source non-proprietary nature.

MariaDB falls under the category of [Monitored, Structured data systems](/latest/docs/managing-data-system-connectors).

### Supported Connector types and modules

| Connector type | Modules supported |
| --- | --- |
| MariaDB (Self-hosted) | - Sensitive Data Intelligence - DSR Automation |

### Supported Pod types

MariaDB (self-hosted) supports standard Securiti pod.

### Supported authentication methods

MariaDB (self-hosted) supports Basic authentication method using username and password.

### Supported items for Classification scans

Securiti supports following items for classification. For more information about classification in discovery scans, see [Understanding Discovery Scans](/latest/docs/discovery-scans).

- Databases
- Schema
- Tables
- Views

### Prerequisites for configuring MariaDB Self-hosted connector

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your MariaDB with a Self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints.

For more information on configuring pods, see [Securiti pods](/latest/docs/pods-cluster-version-v128-and-later).

#### 2. Allow to connect MariaDB in SQLtools configuration

In the connection assistant, review your Database Credentials and allow to connect your database to external applications. For more information, see [Obtain database credentials for your MariaDB configuration](/latest/docs/obtain-database-credentials-for-your-mariadb-configuration).

### Connect MariaDB with Securiti

To configure the MariaDB (Self-hosted) connector, perform the procedures in the following topics:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. [Obtain database credentials for your MariaDB configuration](/latest/docs/obtain-database-credentials-for-your-mariadb-configuration).
3. [Connecting MariaDB with Securiti](/latest/docs/connecting-mariadb-with-securiti).
4. [Configure discovery scans in MariaDB](/latest/docs/configure-discovery-scans-in-mariadb).

#### Additional resources

- [Fulfilling DSR requests for MariaDB](/latest/docs/fulfilling-dsr-requests-for-mariadb).
