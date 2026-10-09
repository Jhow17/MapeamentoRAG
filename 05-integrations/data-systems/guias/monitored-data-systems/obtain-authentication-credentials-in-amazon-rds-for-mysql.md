---
title: "Obtain authentication credentials in Amazon RDS for MySQL"
slug: "obtain-authentication-credentials-in-amazon-rds-for-mysql"
updated: 2026-07-01T19:46:19Z
published: 2026-07-01T19:46:19Z
canonical: "helpcenter.securiti.ai/obtain-authentication-credentials-in-amazon-rds-for-mysql"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Obtain authentication credentials in Amazon RDS for MySQL

> [!NOTE]
> **Note**
> 
> This procedure assumes that you already have a running Amazon RDS for MySQL instance, which automatically creates a master user with administrative privileges.
> 
> However, the [Amazon RDS documentation](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_MySQL.html#:~:text=When%20you%20create%20a%20DB%20instance) advises not to use the master user for application-level tasks such as connector integration. For security and compliance, it is recommended to create a separate user with only the minimum required privileges instead.

### Obtain credentials for Basic authentication

Perform the following steps to create a user and grant permissions to Amazon RDS for MySQL connector database in case of basic authentication.

1. Create a user, for example, Securiti, and a secure password.

```plaintext
CREATE USER 'securiti'@'<appliance-IP or host>' 
IDENTIFIED BY '<some-strong-password>';
```

Replace "securiti" and "StrongPassword" with your actual username and a secure password.
2. Record the username and password for connector activation.
3. Grant SELECT and FLUSH permissions on everything within the database so that you can run a scan for each database.

```plaintext
GRANT SELECT on <<database>.* to '<<usernname>>'@'<pod-IP or host>';
FLUSH PRIVILEGES;
```

### Obtain credentials for IAM Roles authentication

Perform the following steps to create a user and grant permissions to Amazon RDS for MySQL connector database in case of IAM Roles authentication.

1. To enable IAM authentication:

```plaintext
CREATE USER mydbuser IDENTIFIED WITH AWSAuthenticationPlugin AS 'RDS';
```
2. Record the username and password of IAM user for connector activation.
3. After you have created the db user for RDS IAM, create a policy to allow DB access to the user, as shown below.

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
4. Record the **Account Id** and **Region** of IAM user to use it later for connector activation.

### Obtain connector activation credentials

After recording Basic or IAM Roles authentication credentials, you must also record the following credentials for connector activation.

- Host that is IP Address for your MySQL database.
- The port number for your MySQL database (usually 3306).
- Name of your MySQL database.

### Connection requirements

The user account must have access to connect from host to ensure successful authentication.

The table below shows the connection requirements based on MySQL connector types.

| Connector type | Connection requirement |
| --- | --- |
| MySQL (Self-hosted) | The user account must have access to connect from pod host. |
| MySQL (Securiti Cloud) | The user account must have access to connect from any host. |

See the example below to provide GRANT permission.

```plaintext
GRANT ALL ON <dbname>.* TO '<username>' @ '<client_hostname>'.
```

Replace <dbname>, <username>, <client_hostname> with appropriate values. <client_hostname> is the name of the client machine from which the connection is established. Set the value to **'%'** to connect from any client machine.

For more information on GRANT permission, see [MySQL documentation](https://dev.mysql.com/doc/refman/5.7/en/grant.html).

When you have the required credentials, proceed to [Connecting Amazon RDS for MySQL with Securiti](/latest/docs/connecting-amazon-rds-for-mysql-with-securiti).
