---
title: "Obtain credentials in Confluent Kafka"
slug: "obtain-credentials-in-confluent-kafka"
updated: 2026-06-23T07:19:16Z
published: 2026-06-23T07:19:16Z
canonical: "helpcenter.securiti.ai/obtain-credentials-in-confluent-kafka"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Obtain credentials in Confluent Kafka

Use the matching procedure below to acquire the authentication credentials for Confluent Kafka.

> [!NOTE]
> **Important**
> 
> We assume you have access to a setup running Confluent Kafka or can contact the Confluent Kafka admin to obtain the credentials required for connector activation.

1. Log in to your Confluent Kafka instance.
2. > [!NOTE]
> **Note**
> 
> See [(Optional) Grant permissions for Confluent Kafka cluster running ACL](/latest/docs/optional-grant-permissions-for-confluent-kafka-cluster-running-acl) if you have an ACL cluster setup.

Enter your broker and authentication information, respectively.
  1. Broker Information:
    - **Host** - Broker host running Confluent Kafka cluster.
    - **Port** - Broker port running Confluent Kafka cluster.

> [!NOTE]
> **Note**
> 
> You can click the "Add Broker" button to add more than one host and port information for additional Confluent Kafka clusters running.
  2. Authentication Information:
    1. | Authentication Type | Details on configuring each authentication type | Authentication credentials |
| --- | --- | --- |
| Plain Text | Plain text auth type does not require authentication. | None |
| SSL without client authentication | Data is encrypted using SSL (Secure Sockets Layer) with a Trust store, but the client does not provide a certificate for authentication. | - PKCS12 File (Trust store) - Truststore password |
| SSL with client authentication | Both the client and server use SSL certificates for mutual authentication, providing a higher level of security by verifying both ends of the connection. - PKCS12 only requires a PKCS12 Trust store file and password. - Username and password to make a connection with Kafka broker. | - PKCS12 File (Trust store) - Truststore password - PKCS12 File (key store) - Keystore password |
| SSL plain text | SSL plain text uses the PLAIN mechanism, sending the username and password in plain text. For SSL plain text, you can select from the following "Mechanism Type" depending on your Kafka setup: > [!NOTE] > **Note** > > You must enter the User ID and User secret for that option. - Plain - SCRAM-SHA-256 - SCRAM-SHA-512 | - Mechanism Type - User Id - User Secret |
| SASL SSL | SASL is used with SSL, providing a secure and authenticated connection. - PKCS12 only requires a PKCS12 Trust store file and password. - Select from the following "Mechanism Type" depending on your Kafka setup: > [!NOTE] > **Note** > > You must enter the User ID and User secret for that option. - Plain - SCRAM-SHA-256 - SCRAM-SHA-512 | - PKCS12 File (Trust store) - Truststore Password - Mechanism Type - User Id - User Secret |

> [!NOTE]
> **Note**
> 
> See [Configuring SCRAM](https://docs.confluent.io/platform/current/Confluent Kafka/authentication_sasl/authentication_sasl_scram.html) for more information on Mechanism Type.
    2. **Confluent Kafka Connect Internal Topics** - topics required for connector scanning, as shown below:

> [!NOTE]
> **Note**
> 
> You should let Securiti create the topics for you by marking the **Automatically create Confluent Kafka internal topics** checkbox if you have not already done so.
      - *securiti-ds-<random-5-alphanumeric-chars>-offsets*
      - *securiti-ds-<random-5-alphanumeric-chars>-configs*
      - *securiti-ds-<random-5-alphanumeric-chars>-status*
      - *securiti-mp-<random-5-alphanumeric-chars>-offsets*
      - *securiti-mp-<random-5-alphanumeric-chars>-configs*
      - *securiti-mp-<random-5-alphanumeric-chars>-status*
3. In the **Schema Registry** section, apply the following settings, as shown below:
  - (Optional) **Schema Registry Server URL** - enter the HTTP or HTTPS URL used to access Schema Registry Server.
  - **Subject Name strategy** - select the strategy your Schema Registry Server uses:
    - Topic Name Only
    - Record Name Only
    - Topic and Record Names
  - (Optional) Mark the checkbox for the **Schema registry protected by basic authentication**.

When marked, you must provide the Schema registry Username and Password to authenticate.
  - **Data Format Type** - select the data format type for a given topic to define Schema registry:
    - JSON
    - AVRO
    - JSON With Schema
4. Proceed to [Connecting Confluent Kafka with Securiti](/latest/docs/connecting-confluent-kafka-with-securiti).
