---
title: "Obtain credentials in Amazon MSK"
slug: "obtain-credentials-in-amazon-msk"
updated: 2026-07-14T10:13:14Z
published: 2026-07-14T10:13:14Z
canonical: "helpcenter.securiti.ai/obtain-credentials-in-amazon-msk"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Obtain credentials in Amazon MSK

Use the matching procedure below to activate the Amazon MSK connector in Securiti:

> [!NOTE]
> **Important**
> 
> We assume you have access to a setup running Amazon MSK or can contact the Amazon MSK admin to obtain the credentials required for connector activation.

1. Log in to your Amazon MSK instance.
2. > [!NOTE]
> **Note**
> 
> See [(Optional) Grant permissions for Amazon MSK cluster running ACL](/latest/docs/optional-grant-permissions-for-amazon-msk-cluster-running-acl) if you have an ACL cluster setup.

Enter your broker and authentication information, respectively.
  1. Broker Information:
    - **Host** - Broker host running Amazon MSK cluster.
    - **Port** - Broker port running Amazon MSK cluster.

> [!NOTE]
> **Note**
> 
> You can click the "Add Broker" button to add more than one host and port information for additional Amazon MSK clusters running.
  2. Authentication Information:
    1. | Authentication Type | Details on configuring each authentication type |
| --- | --- |
| Plain Text | Plain text auth type does not require authentication. |
| SSL without client authentication | PKCS12 only requires a PKCS12 trust store file and password. |
| SSL with client authentication | - PKCS12 only requires a PKCS12 trust store file and password. - Username and password to make a connection with Amazon MSK broker. |
| SSL plain text | For SSL plain text, you can select from the following "Mechanism Type" depending on your Amazon MSK setup: > [!NOTE] > **Note** > > You must enter the User ID and User secret for that option. - Plain - SCRAM-SHA-256 - SCRAM-SHA-512 |
| SASL SSL | - PKCS12 only requires a PKCS12 trust store file and password. - Select from the following "Mechanism Type" depending on your Amazon MSK setup: > [!NOTE] > **Note** > > You must enter the User ID and User secret for that option. - Plain - SCRAM-SHA-256 - SCRAM-SHA-512 |

> [!NOTE]
> **Note**
> 
> See [Configuring SCRAM](https://docs.confluent.io/platform/current/Amazon MSK/authentication_sasl/authentication_sasl_scram.html) for more information on Mechanism Type.
    2. **Amazon MSK Connect Internal Topics** - topics required for connector scanning, as shown below:

> [!NOTE]
> **Note**
> 
> You should let Securiti create the topics for you by marking the **Automatically create Amazon MSK internal topics** checkbox if you've not already done so.

![Broker_and_Auth_info_Kafka.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8511c8ee-30d1-79f9-b08f-d8f1312669a7.png)
      - *securiti-ds-<random-5-alphanumeric-chars>-offsets*
      - *securiti-ds-<random-5-alphanumeric-chars>-configs*
      - *securiti-ds-<random-5-alphanumeric-chars>-status*
      - *securiti-mp-<random-5-alphanumeric-chars>-offsets*
      - *securiti-mp-<random-5-alphanumeric-chars>-configs*
      - *securiti-mp-<random-5-alphanumeric-chars>-status*
3. In the Glue Schema Registry section, apply the following settings, as shown below:

Table 1. Glue Schema Registry

| Setting | Description |
| --- | --- |
| Authentication Type | Select from IAM Keys or IAM Roles from the menu. 1. If you have selected IAM Keys, enter these details: - AWS Access Key - AWS Secret Key 2. If you have selected IAM Roles, enter these details: - IAM Role - Account Id |
| AWS Region | Enter the region wherein you registered your AWS instance. |
| Registry Name | Enter the name of your Glue Schema Registry. |
| Subject Name strategy | Select Topic Name Only, Record Name Only, or Topic and Record Names from the menu as your Glue Schema Registry Server. |
| Data Format Type | Select JSON, AVRO, or JSON With SCHEMA from the menu as your date format to define the registry. |
4. Proceed to [Connecting Amazon MSK with Securiti](/latest/docs/connecting-amazon-msk-with-securiti).

## Related

- [(Optional) Grant permissions for Amazon MSK cluster running ACL](/optional-grant-permissions-for-amazon-msk-cluster-running-acl.md)
