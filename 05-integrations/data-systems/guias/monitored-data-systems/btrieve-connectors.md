---
title: "BTrieve"
slug: "btrieve-connectors"
status: "new"
updated: 2026-07-01T15:06:13Z
published: 2026-07-01T15:06:27Z
canonical: "helpcenter.securiti.ai/btrieve-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# BTrieve

Btrieve is a transactional database, differing from conventional relational databases, which is based on ISAM (Indexed Sequential Access Method) that is intended for enabling faster data fetching speeds from storage devices and servers. BTreive, combined with other software interfaces and backend pieces, can form the basis of Pervasive SQL databases which has found widespread usage among end-users.

The Btrieve connector lets you integrate legacy Btrieve databases with Securiti to discover and govern structured data stored in your environment. Btrieve falls under the category of monitored, structured data systems. For more information, see [data systems classification](/v1/docs/managing-data-system-connectors).

### Supported pod types

- Standard Securiti Pod.

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Btrieve/Pervasive SQL (Self-hosted) | Self-hosted connector supports: - Sensitive Data Intelligence (Standard data scan) - DSR Automation using APIs and SQL queries |

### Supported authentication methods

Btrieve/Pervasive SQL supports Basic authentication, using username and password.

### Connect Btrieve/Pervasive SQL with Securiti

To configure the BTrieve connector, perform the procedures in the following topics:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. Activate your Self-hosted data system's connector on the pod as described in [Securiti pods and elastic pods](/v1/docs/securiti-pods-and-elastic-pods).

To use the BTrieve data system, you must link your structured on-premises database to Securiti.
3. [Obtain database credentials for your BTrieve configuration](/v1/docs/obtain-database-credentials-for-your-btrieve-configuration)
4. [Connecting Btrieve with Securiti](/latest/docs/connecting-btrieve-with-securiti)
5. [Configuring General scan settings for Btrieve](/latest/docs/initiate-btrieve-learning)
6. Do [table training](/v1/docs/table-training-for-structured-and-hybrid-data-systems) for the BTrieve data system instance.

For more information about how Securiti uses the BTreive data to respond to DSR requests, see [Fulfilling Btrieve DSR requests in Securiti](/latest/docs/fulfilling-btrieve-dsr-requests-1)

## Related

- [Obtain database credentials for your BTrieve configuration](/obtain-database-credentials-for-your-btrieve-configuration.md)
- [Configuring General scan settings for Btrieve](/initiate-btrieve-learning.md)
