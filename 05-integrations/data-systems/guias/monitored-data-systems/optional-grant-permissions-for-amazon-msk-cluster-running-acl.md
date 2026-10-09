---
title: "(Optional) Grant permissions for Amazon MSK cluster running ACL"
slug: "optional-grant-permissions-for-amazon-msk-cluster-running-acl"
updated: 2026-07-14T10:11:45Z
published: 2026-07-14T10:11:45Z
canonical: "helpcenter.securiti.ai/optional-grant-permissions-for-amazon-msk-cluster-running-acl"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# (Optional) Grant permissions for Amazon MSK cluster running ACL

If you have an ACL setup on your cluster, do the following to configure ACL roles for the Amazon MSK user to proceed with Amazon MSK data system authentication and scanning in Securiti.

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
> Replace the placeholders <*LIST OF KAFKA BROKERS*>, <*USER CONFIGURED FOR THE CONNECTOR*>, and <*FILE LOCATION*> above with a list of Kafka brokers, the user you have authorized for connector authentication and properties file location.
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
9. Proceed to [Obtain credentials in Amazon MSK](/latest/docs/obtain-credentials-in-amazon-msk).
