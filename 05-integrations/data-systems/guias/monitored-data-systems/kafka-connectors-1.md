---
title: "Kafka"
slug: "kafka-connectors-1"
status: "new"
updated: 2026-08-25T20:33:40Z
published: 2026-08-25T20:35:11Z
canonical: "helpcenter.securiti.ai/kafka-connectors-1"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Kafka

Kafka is a distributed event streaming platform used to publish, subscribe to, store, and process real-time data streams across applications and systems. By connecting Kafka with Securiti, you can monitor and discover sensitive data flowing through streaming data pipelines, enabling governance and compliance across real-time data environments.

Kafka falls under the category of [Monitored, streaming data systems](/latest/docs/managing-data-system-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Kafka (Self-hosted) | Sensitive Data Intelligence |

### Supported pod types

Kafka (Self-hosted) support standard Securiti pod.

### Supported authentication methods

Kafka (Self-hosted) supported following authentication method:

- Plain Text
- SSL Without Client Authentication
- SSL With Client Authentication
- SASL plain text
- SASL SSL

#### Keyring support for Kafka connector

You can use a keyring support to store authentication credentials in a vault product during the connector configuration process to securely access your credentials from a vault. See [Managing Keyrings](/latest/docs/managing-credentials-using-keyrings) for more information.

- **HashiCorp**: For more information, see [HashiCorp credential vault](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault).

### Supported items for inventory and classification scans

Securiti scans the following items for Kafka connectors.

- Topic(s)

For more information about classification in discovery scans, see [Understanding Discovery Scans](/latest/docs/discovery-scans).

### Prerequisites

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your Kafka (Self-hosted) connector.

For more information on configuring pods, see [Securiti pods](/latest/docs/getting-started-with-securiti-pods).

#### 2. Use cases and permissions for Kafka

This section covers use cases and permissions required for Kafka connector. You must choose the permissions depending on the number of modules or type of connector you are using.

For more information on configuring ACL roles, see [(Optional) Grant permissions for Kafka cluster running ACL](/latest/docs/optional-grant-permissions-for-kafka-cluster-running-acl).

| Use case | Permissions | Explanation of use case |
| --- | --- | --- |
| Sensitive Data Intelligence (SDI) | configure ACL roles for the Kafka user | These permissions let Securiti read the files and file metadata in Kafka for classification purposes. |

### Connect Kafka with Securiti

To configure the Kafka (Self-hosted) connector, perform the procedures in the following topics:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. [Obtain credentials in Kafka](/latest/docs/obtain-credentials-in-kafka).
3. [(Optional) Grant permissions for Kafka cluster running ACL](/latest/docs/optional-grant-permissions-for-kafka-cluster-running-acl).
4. [Connecting Kafka with Securiti](/latest/docs/connecting-kafka-with-securiti).
5. [Configure discovery scans in Kafka](/latest/docs/configure-discovery-scans-in-kafka).
