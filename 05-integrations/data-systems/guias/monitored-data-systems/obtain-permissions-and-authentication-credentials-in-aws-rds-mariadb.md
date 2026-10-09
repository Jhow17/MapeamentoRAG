---
title: "Obtain permissions and authentication credentials in Amazon RDS MariaDB"
slug: "obtain-permissions-and-authentication-credentials-in-aws-rds-mariadb"
updated: 2026-08-10T14:26:54Z
published: 2026-08-10T14:26:54Z
canonical: "helpcenter.securiti.ai/obtain-permissions-and-authentication-credentials-in-aws-rds-mariadb"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Obtain permissions and authentication credentials in Amazon RDS MariaDB

Do the following to grant Amazon RDS MariaDB database permission.

1. Create a user, for example, Securiti, and a secure password:

```plaintext
CREATE USER 'securiti'@'<appliance-IP or host>' 
IDENTIFIED BY '<some-strong-password>';
```
2. To enable IAM authentication:

```plaintext
CREATE USER mydbuser IDENTIFIED WITH AWSAuthenticationPlugin AS 'RDS';
```

After you have created the db user for RDS IAM, create a policy to allow DB access to the user, as shown below.

```plaintext
Create a custom aws policy and attach the policy to aws role :

{
  “Version”: “2012-10-17",
  “Statement”: [
    {
      “Effect”: “Allow”,
      “Action”: [
        “rds-db:connect”
      ],
      “Resource”: [
        “arn:aws:rds-db:<region>:<account>:dbuser:<resource id>/iamuser”
      ]
    }
  ]
}
```
3. Grant SELECT permission on everything within the database so that you can run a scan for each database:

```plaintext
GRANT SELECT on <<database>.* to '<<usernname>>'@'<pod-IP or host>';  
```

To obtain database credentials for your MariaDB configuration:

1. Open your database's system client (in this case, it is that of Microsoft's Visual Studio running on the MacOS operating system).
2. Choose **MariaDB** from the available SQLTools configurations.

![MariaDB_SelectDBType.jpg](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-69f2acb3-5f0d-772b-1345-59080a12192c.jpg)
3. Navigate to your networking database settings (in this case, it is called **Connection Assistant**).

![MariaDB_SetupMariaDBConnection.jpg](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7c3fbc2b-1997-6077-f4df-3a8c038db608.jpg)
4. Confirm your database connection settings and record the following details to use later:

| Server Host | The server host IP for your database (for example, *<128.X.X.1>*) |
| --- | --- |
| Port | The network access port address for your database (for example, <*1583*> |
| Database | The exact name of the database you wish to link to Securiti (for example, <*DEMODATA*>) |
| Username | The username associated with accessing your database (for example, <*Master*> |
| Password | The password associated with your database user account (for example, <*pxsxwxrx*> |
5. Click **Test Connection** and then **Save Connection** after you verify the database access details.
6. Navigate to the final screen of the Connection Assistant and review your database credentials (in JSON format).

![MariaDB_StartMariaDBConnection.jpg](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-cdbee6af-7753-3971-3060-d139afe5873d.jpg)
7. Click **Connect Now**.

The database is now accessible for linking to external applications such as Securiti.
8. Proceed to [Connecting Amazon RDS MariaDB with Securiti](/latest/docs/connecting-aws-rds-mariadb-with-securiti).
