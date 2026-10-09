---
title: "Acquire authentication credentials in Snowflake"
slug: "acquire-authentication-credentials-in-snowflake"
updated: 2026-07-31T12:15:21Z
published: 2026-07-31T12:15:21Z
canonical: "helpcenter.securiti.ai/acquire-authentication-credentials-in-snowflake"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Acquire authentication credentials in Snowflake

> [!NOTE]
> **Note**
> 
> This procedure assumes you have an existing Snowflake Instance running and have admin access to configure the required Permissions.

The topic covers the procedures to acquire the Authentication Credentials required to connect Snowflake with Securiti. Snowflake supports the following Authentication methods.

| Authentication method | Authentication Credentials |
| --- | --- |
| Basic > [!WARNING] > **Important** > > Snowflake is deprecating its basic username and password Authentication method, with the change taking effect in November 2025. To avoid future Connection failures, we recommend you opt for Key Pair or OAuth 2.0 Authentication method. | - User Name - Password - Account |
| Key Pair Authentication | - Private Key File - User Name - Account |
| OAuth 2.0 | - User Name - Account |

1. Log in to your Snowflake account for example, <***https://cla43452.snowflakecomputing.com/console/login#/?returnUrl=internal%2Fworksheet***>.

The part before *snowflakecomputing.com* is your account name or ID. In the above example, *cla43452* is your Snowflake account name or ID. Record it to use later.
2. For **Basic** Authentication method, record the username and password for your Snowflake account.
3. For **Key pair** Authentication, follow the procedure below:

For more information, see Snowflake's official documentation on [Key Pair Authentication & Key Pair Rotation](https://docs.snowflake.com/en/user-guide/key-pair-auth).
  1. Open Snowflake terminal and generate a private key.

You can generate either an encrypted version of the private key or an unencrypted one.

> [!NOTE]
> **Note**
> 
> The commands below assume *rsa_key* as your custom file name. You can choose a file name of your choice for private key file.

To generate an unencrypted version, use the following command.

```plaintext
$ openssl genrsa 2048 | openssl pkcs8 -topk8 -inform PEM -out rsa_key.p8 -nocrypt
```

To generate an encrypted version, use the following command (which omits “-nocrypt”):

```plaintext
$ openssl genrsa 2048 | openssl pkcs8 -topk8 -v2 des3 -inform PEM -out rsa_key.p8
```

> [!NOTE]
> **Note**
> 
> The command for encrypted key, prompts for a passphrase to regulate access to the key. It is recommended to use a passphrase that complies with PCI DSS standards to protect the locally generated private key.

The commands generate a private key in PEM format as shown below.

```plaintext
-----BEGIN ENCRYPTED PRIVATE KEY-----
MIIE6TAbBgkqhkiG9w0BBQMwDgQILYPyCppzOwECAggABIIEyLiGSpeeGSe3xHP1
wHLjfCYycUPennlX2bd8yX8xOxGSGfvB+99+PmSlex0FmY9ov1J8H1H9Y3lMWXbL
...
-----END ENCRYPTED PRIVATE KEY-----
```

Record the private key for later.
  2. Generate a public key, referencing the private key generated in the previous step.

In the command line, use the following command to generate the public key. The following command assumes the private key is encrypted and contained in the file named *rsa_key.p8.*

```plaintext
$ openssl rsa -in rsa_key.p8 -pubout -out rsa_key.pub
```

The command generates the public key in PEM format as shown below.

```plaintext
-----BEGIN PUBLIC KEY-----
MIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEAy+Fw2qv4Roud3l6tjPH4
zxybHjmZ5rhtCz9jppCV8UTWvEXxa88IGRIHbJ/PwKW/mR8LXdfI7l/9vCMXX4mk
...
-----END PUBLIC KEY-----
```
  3. (Optional) Use the following command to view the key in terminal.

```plaintext
cat rsa_key.pem
```
  4. Save the public and private keys securely.

Copy the public and private key files to a local directory for storage. Record the path to the files.

> [!NOTE]
> **Note**
> 
> The private key is stored using the PKCS#8 (Public Key Cryptography Standards) format and is encrypted using the passphrase.
  5. Assign the Public Key to a Snowflake user.

Use the following [ALTER USER](https://docs.snowflake.com/en/sql-reference/sql/alter-user) command to assign the public key to a Snowflake user.

```plaintext
ALTER USER jsmith SET RSA_PUBLIC_KEY='MIIBIjANBgkqh...';
```

> [!NOTE]
> **Note**
> 
> Only security administrators (i.e. users with the SECURITYADMIN role) or higher can alter a user.
  6. Passphrase is optional to use for key pair Authentication. As you provide the encrypted key, the passphrase is needed to decrypt the key and authenticate the Connector. A passphrase is not needed when the key is in plaintext.
4. To use **OAuth 2.0** Authentication, do the following:
  1. Log in to your Snowflake account.
  2. Near the top right corner of the page, click **DEVUSER** and select **Switch Role > ACCOUNTADMIN**.
  3. Click the **ACCOUNTADMIN** (two-person icon) and choose **ACCOUNTADMIN** from the **Role** menu.

On the same menu, choose the corresponding **Warehouse**, **Database**, and **Schema** values.
  4. To configure **OAuth** for Securiti, follow the procedure below:

For more information, see [Configure Snowflake OAuth for Custom Clients](https://docs.snowflake.com/en/user-guide/oauth-custom.html).
    1. Create a new Integration, for example, "devuser_oauth", as shown below.

> [!NOTE]
> **Note**
> 
> Only account administrators (users with the ACCOUNTADMIN role) or a role with the global CREATE Integration privilege can execute this SQL command. Roles having **global CREATE Integration** privilege can create Snowflake Integration.

The Integration lets refresh tokens, which expire after 1 day (86400 seconds). The Integration blocks users from starting a session with SYSADMIN as the active role.

```plaintext
create or replace security integration devuser_oauth
  type = oauth
  enabled = true
  oauth_client = custom
  oauth_client_type = 'CONFIDENTIAL'
  oauth_redirect_uri = 'https://app.securiti.ai/static/activateConnector.html'
  oauth_issue_refresh_tokens = true
  oauth_refresh_token_validity=86400;
```
    2. Do Delegated Authorizations, as shown below.

```plaintext
alter user devuser add DELEGATED AUTHORIZATION OF ROLE SYSADMIN TO SECURITY INTEGRATION devuser_oauth;
```
    3. Describe Integration using the command below, to obtain the OAuth Authentication Credentials.

```plaintext
desc security integration devuser_oauth;
```

Record the following parameters for later use.
      - Client ID
      - Authorization and Token URLs

For more information, see [Snowflake's documentation on calling the OAuth endpoints](https://docs.snowflake.com/en/user-guide/oauth-custom).
    4. Acquire client secrets using the command below.

```plaintext
select system$show_oauth_client_secrets('DEVUSER_OAUTH');
```

Record for later use.
  5. On the left sidebar of the Snowflake dashboard, click **Databases** to view a list of databases and a panel to execute queries. Expand to view the related information for the selected Database.
5. Proceed to [Connecting the Snowflake (Self-hosted) connector with Securiti](/latest/docs/connecting-snowflake-self-hosted-connector-with-securiti) or [Connecting the Snowflake (Cloud) connector with Securiti](/latest/docs/connecting-snowflake-cloud-connector-with-securiti)
