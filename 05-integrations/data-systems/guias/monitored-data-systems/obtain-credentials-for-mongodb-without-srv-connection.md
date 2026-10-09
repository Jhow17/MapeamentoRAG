---
title: "Create a MongoDB connection without the srv"
slug: "obtain-credentials-for-mongodb-without-srv-connection"
updated: 2026-08-05T22:51:18Z
published: 2026-08-05T22:51:18Z
canonical: "helpcenter.securiti.ai/obtain-credentials-for-mongodb-without-srv-connection"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Create a MongoDB connection without the srv

This article provides the procedure to create a connection without srv.

1. In your MongoDB project, under **Database**, click **Cluster**.
2. On the **Cluster** page, click **View monitoring**. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/View-monitoring.png)
3. On the **Metrics** page, record the following credentials:

| Credential | Description |
| --- | --- |
| Primary Host | Use this value as the Host parameter during connector activation. |
| Secondary Host | Use this value when specifying the ReplicaSet in the additional connection string. |
| Default Port | Use this port number during connector activation. |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Primary-Secondary.png)

### Create a user in MongoDB Atlas

To create a new user with read permission in MongoDB Atlas, perform the following steps:

1. In the MongoDB Atlas console, under **Security**, click **Database & Network Access > Data Access > Database Users.**
2. On the **Database Users** page, click **ADD NEW DATABASE USER.** ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Add-DB-User.png)
3. On the **Add New Database User** popup under the **Password** tab, add a username and generate the password. Use username and password credentials for connector activation. For certificate authentication user, see [Configuring mTLS authentication](/latest/docs/configuring-mtls-authentication). ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/db-user-popup.png)
4. Scroll down to the **Database User Privileges** section, under the **Built-in Roles**, assign the **Only read any database** role.
5. Click **Add User**.

## Create a user with CLI commands

You must grant **read** permission to your MongoDB databases for successful data scanning and discovery.

Do the following to grant MongoDB Connector Database Permissions.

1. Create a user with read Permissions with the following command:

```plaintext
db.createUser({ 
  user: "demo", 
  pwd: "<<some-strong-password>>",
  roles: [ { role: "read", db: "db1" }, { role: "read", db: "db2" } ] 
});
```

For more information, see [MongoDB Built-In Roles documentation](https://www.mongodb.com/docs/manual/reference/built-in-roles/).
2. Proceed to [Connecting the MongoDB connector with Securiti](/latest/docs/connecting-the-mongodb-connector-with-securiti).
