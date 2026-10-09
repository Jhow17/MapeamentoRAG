---
title: "(Optional) Grant permissions for Kafka cluster running ACL"
slug: "optional-grant-permissions-for-kafka-cluster-running-acl"
updated: 2025-10-31T07:57:00Z
published: 2025-11-03T06:14:44Z
canonical: "helpcenter.securiti.ai/optional-grant-permissions-for-kafka-cluster-running-acl"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# (Optional) Grant permissions for Kafka cluster running ACL

If you have an ACL setup on your cluster, do the following to configure ACL roles for the Kafka user to proceed with Kafka Data system Authentication and scanning in Securiti.

1. ```plaintext
bin/kafka-acls --bootstrap-server <LIST OF KAFKA BROKERS server1:port,server2:port> 
--command-config <FILE LOCATION>/kafka-admin-client.properties --add --allow-principal 
User:<USER CONFIGURED FOR THE CONNECTOR> --operation DescribeConfigs --cluster --force
```
2. ```plaintext
kafka-acls --bootstrap-server <LIST OF KAFKA BROKERS server1:port,server2:port> 
--command-config <FILE LOCATION>kafka-admin-client.properties --add --allow-principal 
User:<USER CONFIGURED FOR THE CONNECTOR> --operation ALL --topic  "securiti-ds-" --resource-pattern-type PREFIXED --force
```
3. ```plaintext
bin/kafka-acls --bootstrap-server <LIST OF KAFKA BROKERS server1:port,server2:port> 
--command-config <FILE LOCATION>kafka-admin-client.properties --add --allow-principal 
User:<USER CONFIGURED FOR THE CONNECTOR> --operation ALL --group "securiti-mp-" --resource-pattern-type PREFIXED --force
```
4. ```plaintext
bin/kafka-acls --bootstrap-server <LIST OF KAFKA BROKERS server1:port,server2:port> 
--command-config <FILE LOCATION>/kafka-admin-client.properties --add --allow-principal 
User:<USER CONFIGURED FOR THE CONNECTOR> --operation ALL --group  "securiti-ds-" --resource-pattern-type PREFIXED --force
```
5. ```plaintext
kafka-acls --bootstrap-server <LIST OF KAFKA BROKERS server1:port,server2:port> 
--command-config <FILE LOCATION>kafka-admin-client.properties --add --allow-principal 
User:<USER CONFIGURED FOR THE CONNECTOR>--operation ALL --group "connect-discovery:" --resource-pattern-type PREFIXED --force
```
6. ```plaintext
kafka-acls --bootstrap-server <LIST OF KAFKA BROKERS server1:port,server2:port> 
--command-config <FILE LOCATION>/kafka-admin-client.properties --add --allow-principal 
User:<USER CONFIGURED FOR THE CONNECTOR> --operation ALL --group "connect-mask:" --resource-pattern-type PREFIXED --force
```
7. ```plaintext
kafka-acls --bootstrap-server <LIST OF KAFKA BORKERS server1:port,server2:port> 
--command-config <FILE LOCATION>kafka-admin-client.properties --add --allow-principal 
User:<USER CONFIGURED FOR THE CONNECTOR> --operation ALL --topic  "securiti-mp-" --resource-pattern-type PREFIXED --force
```

> [!NOTE]
> **Note**
> 
> Replace the placeholders <*LIST OF KAFKA BROKERS*>, <*USER CONFIGURED FOR THE Connector*>, and <*FILE LOCATION*> above with a list of Kafka brokers, the user you have authorized for Connector Authentication, and properties file location.
8. (Optional) To check with your properties file, see a sample content of how it appears below.

```plaintext
security.protocol = SASL_SSL
sasl.mechanism = SCRAM-SHA-512
ssl.truststore.location = <LOCATION OF TRUST STORE FILE if COMMUNICATION  WITH TLS/SSL>/ca-truststore.jks
ssl.truststore.password = <TRUST STORE PASSWORD>
ssl.truststore.type=JKS
ssl.endpoint.identification.algorithm=
sasl.jaas.config=org.apache.kafka.common.security.scram.ScramLoginModule required \
  username="admin" \
  password="admin-secret";
```
9. Proceed to [Obtain credentials in Kafka](/v1/docs/obtain-credentials-in-kafka).

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>
