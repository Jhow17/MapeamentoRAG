---
title: "Troubleshooting for MongoDB"
slug: "troubleshooting-for-mongodb"
updated: 2026-08-05T23:36:28Z
published: 2026-08-10T21:00:09Z
canonical: "helpcenter.securiti.ai/troubleshooting-for-mongodb"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Troubleshooting for MongoDB

This topic provides troubleshooting guidance for common issues encountered while configuring or using the MongoDB data system connector.

## Failed to get tables from the database

The following error might occur when your MongoDB setup has more than one replica node, and the default connection string is not able to fetch the database tables properly.

```plaintext
Failed to get tables from database : error : For MDBP-FERPROMO-2.DC.NOVA 
Failed to get accessible databases.Failed to fetch any databases from the connection.
```

If you encounter the above error, add the following value in the Additional Connection String Options parameter while [Connecting the MongoDB connector with Securiti](/latest/docs/connecting-the-mongodb-connector-with-securiti) data system connector to connect to the primary node.

```plaintext
ReplicaSet=node1.example.com:27017,node2.example.com:27017,node3.example.com:27017,
node4.example.com:27017;readPreference=primaryPreferred;SlaveOK=true
```

> [!NOTE]
> Note
> 
> You must replace the ReplicaSet value with your nodes. For example, if you have 4 nodes, add a comma-separated value for each node. See the example below.
> 
> *node1.example.com:27017,node2.example.com:27017,node3.example.com:27017,node4.example.com:27017*
