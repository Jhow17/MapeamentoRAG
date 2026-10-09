---
title: "Create a +srv connection and a user in the MongoDB"
slug: "granting-db-permissions"
updated: 2026-08-05T22:51:09Z
published: 2026-08-05T22:51:09Z
canonical: "helpcenter.securiti.ai/granting-db-permissions"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Create a +srv connection and a user in the MongoDB

This article provides the procedure to create a MongoDB+srv connection and obtain credentials.

## Create a +srv connection using MongoDB Atlas UI

1. In the Clusters view, click **Connect** for the cluster you want to connect to.
2. On the **Connect to <your-cluster>** popup, set up connection security.
3. In the **Choose a connection method** step under the **Connect to your application**, choose your preferred connection method
4. In the **Connect** step, select the driver option to display a connection string, and choose one of the following authentication methods:
  - **Password:** Choose this option for password authentication.
  - **X.509 Certification:** Choose this option for mTLS authentication.

> [!NOTE]
> Note
> 
> X.509 Certification options appears when you enable the Self-managed X.509 Authentication toggle from Advanced settings under Database & Network Access. For more information, see step 3 in [Configuring mTLS authentication](/latest/docs/configuring-mtls-authentication).
5. From the connection string, record the host value that follows the mongodb.net format. See the example below *cluster0.mongodb.net*

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/509-Authentication.png)
6. Record the connection string for connector activation

### Create a user in MongoDB Atlas

To create a new user with read permission in MongoDB Atlas, perform the following steps:

1. In the MongoDB Atlas console, under **Security**, click **Database & Network Access > Data Access > Database Users.**
2. On the **Database Users** page, click **ADD NEW DATABASE USER.** ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Add-DB-User.png)
3. On the **Add New Database User** popup under the **Password** tab, add a username and generate the password. Use these credentials for connector activation. For certificate authentication user, see [Configuring mTLS authentication](/latest/docs/configuring-mtls-authentication). ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/db-user-popup.png)
4. Scroll down to the **Database User Privileges** section, under the **Built-in Roles**, assign the **Only read any database** role.
5. Click **Add User**.

Or you can also use CLI to create a user/

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
