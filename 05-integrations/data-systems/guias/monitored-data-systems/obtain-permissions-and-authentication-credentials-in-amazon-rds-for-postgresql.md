---
title: "Obtain permissions and authentication credentials in Amazon RDS for PostgreSQL"
slug: "obtain-permissions-and-authentication-credentials-in-amazon-rds-for-postgresql"
updated: 2026-07-01T19:48:53Z
published: 2026-07-01T19:48:53Z
canonical: "helpcenter.securiti.ai/obtain-permissions-and-authentication-credentials-in-amazon-rds-for-postgresql"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Obtain permissions and authentication credentials in Amazon RDS for PostgreSQL

Do the following to grant PostgreSQL connector database permissions.

> [!NOTE]
> **Note**
> 
> Connect permissions on all databases that require scanning.

1. For usage permission, enable:
  - pg_catalog
  - information_scheme
  - all schemes on all databases that require scanning
2. To enable IAM authentication:

```plaintext
CREATE USER iamuser WITH LOGIN; 
GRANT rds_iam TO iamuser;
```

After you have created the db user for RDS IAM, create a policy to allow DB access to the user, as shown below. For more information, see [Attach IAM Role and create a policy using EC2 instance](/latest/docs/attach-iam-role-and-create-policy-for-ec2-instance).

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
3. To SELECT permissions on tables in each schema of every database:

```plaintext
CREATE ROLE securiti WITH LOGIN PASSWORD '<some-strong-password>'

GRANT CONNECT ON DATABASE <<database>> TO <<usernname>>;
-- use <<database>> to connect to database
GRANT USAGE ON SCHEMA public TO <<usernname>>;
GRANT SELECT ON ALL TABLES IN SCHEMA public TO <<usernname>>;
```

To obtain database credentials for your PostgreSQL configuration:

1. Open your database system client (in this case, Microsoft's Visual Studio running on MacOS).

![PostgreSQL_CreateConnect.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ecc769cb-a597-57b5-8d84-ed90ca932047(1).png)
2. Choose PostgreSQL from the available SQLTools configurations.

![PostgreSQL_CreatePGSQL.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d1f775aa-b3ac-7265-24b4-2e8f518d9106(1).png)
3. Navigate to your networking database settings (in this case, it is called Connection Assistant).
4. Confirm your database connection settings and record the following details to use later:

| Server Host | The server host IP for your database (for example, <*128.X.X.1*>) |
| --- | --- |
| Port | The network access port address for your database (for example, <*1583*>) |
| Database | The exact name of the database you wish to link to Securiti (for example, <*DEMODATA*>) |
| Username | The username associated with accessing your database (for example, <*Master*> |
| Password | The password associated with your database user account (for example, <*pxsxwxrx*> |

![PostgreSQL_ConfigurePGSQL.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-616ac4c9-9e99-7167-df96-8b90ec41a2a5(1).png)
5. Click **Test Connection** and then **Save Connection** after you verify the database access details.
6. Navigate to the final screen of the Connection Assistant and review your database credentials (shown in .json format).

![PostgreSQL_ConnectPGSQL.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6e9d425e-4204-66fb-547b-aacf618f149d(1).png)
7. Click **Connect Now**.

The database is now accessible for linking to external applications such as Securiti.
8. Proceed to [Connecting Amazon RDS for PostgreSQL with Securiti](/latest/docs/connecting-amazon-rds-for-postgresql-with-securiti).
