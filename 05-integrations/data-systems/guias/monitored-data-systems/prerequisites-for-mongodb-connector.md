---
title: "Obtain credentials for various MongoDB connection methods"
slug: "prerequisites-for-mongodb-connector"
updated: 2026-08-05T22:50:58Z
published: 2026-08-05T22:50:58Z
canonical: "helpcenter.securiti.ai/prerequisites-for-mongodb-connector"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Obtain credentials for various MongoDB connection methods

To acquire authentication credentials based on the connection method, you must do the following:

> [!NOTE]
> **Note**
> 
> - This procedure assumes that you have a Database available prior to Connector Activation.
> - When configuring the MongoDB Connector, ensure that the Database Instance being connected to is the primary Instance. The Connector does not connect to a secondary or replica Instance. See [MongoDB Replica Set Members](https://www.mongodb.com/docs/manual/core/replica-set-members/) documentation, for more information. Log in to the server running MongoDB.

## MongoDB connection methods

You can use the following MongoDB connection methods:

- Atlas MongoDB authentication using a replica set of URLs (Preference)
- Atlas MongoDB authentication using Atlas SQL Connection via JDBC
- MongoDB authentication using LDAP

### Atlas MongoDB authentication using a replica set of URLs

For Atlas MongoDB (Replica URL), record the replica URL. The Authentication parameters look as shown in the format below.

1. For the **Host** and **Port**, follow this format and see an example below.

*mongodb://<Primary Node>:<port>;*

For example, *primary-shard.mongodb.net:27017,* where *primary-shard.mongodb.net* is the value for Host and *27017* for port.
2. For the **Additional Connection String Options** field, use this format when you enter its value.

*SlaveOk=true;ReplicaSet=mongodb1.example.com:27018,mongodb2.example.com:27019*

![atlas_mongdb_replica_url.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3972e158-5c60-3350-7f37-f75f4c1e62ac.png)

### Atlas MongoDB authentication using Atlas SQL Connection via JDBC

For Atlas MongoDB (SQL/JDBC), select the JDBC driver option from the menu and record the **URL** and **Port**.

Record the part after *jdbc:mongodb://* for Host, as shown below.

The Host value ends in *mongodb.net*. ![mongodb_sql_jdbc.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2ad12ca3-faf2-2a6d-0bc7-152b36d27d9a.png)

### MongoDB authentication using LDAP

For MongoDB Authentication using LDAP, see [MongoDB Authentication for LDAP Authentication](https://www.mongodb.com/docs/atlas/security-ldaps/). Specify the following parameters.

- For the **User**, record the LDAP username.
- For **Password**, record the LDAP password.
- (In Securiti) For the **Auth Database Name** field, use *$external* as the value.
- (In Securiti) For the **Additional Connection String Options** field, use "AuthScheme = PLAIN".

Proceed to [Connecting the MongoDB connector with Securiti](/latest/docs/connecting-the-mongodb-connector-with-securiti).
