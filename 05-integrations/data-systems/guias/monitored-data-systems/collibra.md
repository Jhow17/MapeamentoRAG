---
title: "Collibra"
slug: "collibra"
status: "new"
updated: 2026-10-05T10:20:15Z
published: 2026-10-05T10:20:15Z
canonical: "helpcenter.securiti.ai/collibra"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Collibra

Collibra is a data intelligence platform that organizations use as their enterprise data catalog to govern, discover, and understand their data assets. Connecting Collibra with Securiti lets you register metadata from your structured data systems into the Collibra catalog and fulfil data subject requests against Collibra. Collibra (Self-hosted) falls under the category of monitored data systems.

### Supported Connector types and modules

| Data system type | Modules supported |
| --- | --- |
| Securiti Cloud connector | Sensitive Data Intelligence |

### Supported authentication methods

- For Self-hosted connector and Securiti Cloud connector:
  - OAuth based authentication

### Prerequisites for configuring Collibra connector

#### 1. Collibra account access

You must have at least a trial account for Collibra to activate the connector.

#### 2. Private Cloud Storage (PCS) configuration

You must configure Private Cloud Storage (PCS) for your tenant to successfully authenticate Collibra data system connector. For more information on configuring PCS, see [Configuring Private Cloud Storage](/latest/docs/system-settings-configuring-private-cloud-storage).

### Steps to connect Collibra with Securiti

To configure the Collibra connector, perform the procedures in the following topics:

- If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
- Activate your Self-hosted data system's connector on the pod as described in Securiti [pods and elastic pods](/v1/docs/securiti-pods-and-elastic-pods).

To use the Collibra data system, you must link your structured on-premises database to Securiti.

[Connecting Collibra with Securiti](/latest/docs/new-ui-connecting-alation-with-securiti-1).
