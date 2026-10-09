---
title: "Obtain credentials in Kafka"
slug: "obtain-credentials-in-kafka"
updated: 2026-06-23T09:53:15Z
published: 2026-06-23T09:53:15Z
canonical: "helpcenter.securiti.ai/obtain-credentials-in-kafka"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Obtain credentials in Kafka

Apache Kafka communicates in PLAINTEXT by default and does not require any permission. If you have configured the Kafka broker and Schema registry using the Secure Sockets Layer (SSL), you require the PKCS12 file to activate or configure the connector. For more information, see [pkcs12 doc](https://www.openssl.org/docs/man1.1.1/man1/pkcs12.html).

Use the matching procedure below to acquire the authentication credentials for Kafka.

> [!NOTE]
> **Important**
> 
> We assume you have access to a setup running Kafka or can contact the Kafka admin to obtain the credentials required for connector activation.

1. Log in to your Kafka Instance.
2. > [!NOTE]
> **Note**
> 
> See [(Optional) Grant permissions for Kafka cluster running ACL](/latest/docs/optional-grant-permissions-for-kafka-cluster-running-acl) if you have an ACL cluster setup.

Enter your broker and authentication information, respectively.
  1. Broker Information:
    - **Host** - Broker host running Kafka cluster.
    - **Port** - Broker port running Kafka cluster.

> [!NOTE]
> **Note**
> 
> You can click the "Add Broker" button to add more than one host and port information for additional Kafka clusters running.
  2. Authentication Information:
    1. | Authentication Type | Details on configuring each Authentication type | Authentication Credentials |
| --- | --- | --- |
| Plain Text | Plain text auth type does not require Authentication. | None |
| SSL without client Authentication | Data is encrypted using SSL (Secure Sockets Layer) with a Trust store, but the client does not provide a Certificate for Authentication. | - PKCS12 File (Trust store) - Truststore password |
| SSL with client Authentication | Both the client and server use SSL certificates for mutual Authentication, providing a higher level of security by verifying both ends of the Connection. - PKCS12 only requires a PKCS12 Trust store file and password. - Username and password to make a Connection with Kafka broker. | - PKCS12 File (Trust store) - Truststore password - PKCS12 File (key store) - Keystore password |
| SSL plain text | SSL plain text uses the PLAIN mechanism, sending the username and password in plain text. For SSL plain text, you can select from the following "Mechanism Type" depending on your Kafka setup: > [!NOTE] > **Note** > > You must enter the User ID and User secret for that option. - Plain - SCRAM-SHA-256 - SCRAM-SHA-512 | - Mechanism Type - User Id - User Secret |
| SASL SSL | SASL is used with SSL, providing a secure and authenticated Connection. - PKCS12 only requires a PKCS12 Trust store file and password. - Select from the following "Mechanism Type" depending on your Kafka setup: > [!NOTE] > **Note** > > You must enter the User ID and User secret for that option. - Plain - SCRAM-SHA-256 - SCRAM-SHA-512 | - PKCS12 File (Trust store) - Truststore Password - Mechanism Type - User Id - User Secret |

> [!NOTE]
> **Note**
> 
> See [Configuring SCRAM](https://docs.confluent.io/platform/current/kafka/authentication_sasl/authentication_sasl_scram.html) for more information on Mechanism Type.
    2. **Kafka Connect Internal Topics** - topics required for Connector scanning, as shown below:

> [!NOTE]
> **Note**
> 
> You should let Securiti create the topics for you by marking the **Automatically create Kafka internal topics** checkbox if you have not already done so.

![Broker_and_Auth_info_Kafka.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8511c8ee-30d1-79f9-b08f-d8f1312669a7(1).png)
      - *securiti-ds-<random-5-alphanumeric-chars>-offsets*
      - *securiti-ds-<random-5-alphanumeric-chars>-configs*
      - *securiti-ds-<random-5-alphanumeric-chars>-status*
      - *securiti-mp-<random-5-alphanumeric-chars>-offsets*
      - *securiti-mp-<random-5-alphanumeric-chars>-configs*
      - *securiti-mp-<random-5-alphanumeric-chars>-status*
3. In the Schema Registry section, apply the following settings, as shown below:
  - (Optional) **Schema Registry Server URL** - enter the HTTP or HTTPS URL used to access Schema Registry Server.
  - **Subject Name strategy** - select the strategy your Schema Registry Server uses:
    - Topic Name Only
    - Record Name Only
    - Topic and Record Names
  - (Optional) Mark the checkbox for the **Schema registry protected by basic Authentication**.

When marked, you must provide the Schema registry Username and Password to authenticate.
  - **Data Format Type** - select the data format type for a given topic to define Schema registry:
    - JSON
    - AVRO
    - JSON With Schema ![Schema_Registry_section_Kafka.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-eac27772-e5be-30ed-54da-d2cc3de9b98f.png)
4. Proceed to [Connecting Kafka with Securiti](/latest/docs/connecting-kafka-with-securiti).
