---
title: "Confluent Kafka"
slug: "confluent-kafka-connectors"
status: "new"
updated: 2026-06-23T07:18:41Z
published: 2026-06-23T07:18:41Z
canonical: "helpcenter.securiti.ai/confluent-kafka-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Confluent Kafka

Confluent Kafka is a cloud-native event streaming platform built on Apache Kafka that enables organizations to process, integrate, and govern real-time data streams at scale. By connecting Confluent Kafka with Securiti, you can discover and monitor sensitive data across streaming topics to support data security, privacy, and compliance initiatives.

Confluent Kafka falls under the category of [Monitored, streaming data systems](/latest/docs/managing-data-system-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Confluent Kafka (Self-hosted) | Sensitive Data Intelligence |

### Supported pod types

Confluent Kafka (Self-hosted) support standard Securiti pod.

### Supported authentication methods

Confluent Kafka (Self-hosted) supported following authentication method:

- Plain Text
- SSL Without Client Authentication
- SSL With Client Authentication
- SASL plain text
- SASL SSL

#### Keyring support for Confluent Kafka connector

You can use a keyring support to store authentication credentials in a vault product during the connector configuration process to securely access your credentials from a vault. See [Managing Keyrings](/latest/docs/managing-credentials-using-keyrings) for more information.

- **HashiCorp**: For more information, see [HashiCorp credential vault](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault).

### Supported items for inventory and classification scans

Securiti scans the following items for Confluent Kafka connectors.

- Topic(s)

For more information about classification in discovery scans, see [Understanding Discovery Scans](/latest/docs/discovery-scans).

### Prerequisites

#### 1. Pod deployment

> [!NOTE]
> **Note**
> 
> Pod deployment prerequisite is for self-hosted connectors only.

You must deploy a Securiti pod in your environment to connect your Jira Cloud with a self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints.

For more information on configuring pods, see [Securiti pods](/latest/docs/pods-cluster-version-v128-and-later).

#### 2. Use cases and permissions for Confluent Kafka

This section covers use cases and permissions required for Confluent Kafka connector. You must choose the permissions depending on the number of modules or type of connector you are using.

For more information on configuring ACL roles, see [(Optional) Grant permissions for Confluent Kafka cluster running ACL](/latest/docs/optional-grant-permissions-for-confluent-kafka-cluster-running-acl).

| Use case | Permissions | Explanation of use case |
| --- | --- | --- |
| Sensitive Data Intelligence (SDI) | configure ACL roles for the Confluent Kafka user | These permissions let Securiti read the files and file metadata in Confluent Kafka for classification purposes. |

### Connect Confluent Kafka with Securiti

To configure the Confluent Kafka (Self-hosted) connector, perform the procedures in the following topics:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. [Obtain credentials in Confluent Kafka](/latest/docs/obtain-credentials-in-confluent-kafka).

[(Optional) Grant permissions for Confluent Kafka cluster running ACL](/latest/docs/optional-grant-permissions-for-confluent-kafka-cluster-running-acl).
3. [Connecting Confluent Kafka with Securiti](/latest/docs/connecting-confluent-kafka-with-securiti)
4. [Configure discovery scans in Confluent Kafka](/latest/docs/configure-discovery-scans-in-confluent-kafka)
