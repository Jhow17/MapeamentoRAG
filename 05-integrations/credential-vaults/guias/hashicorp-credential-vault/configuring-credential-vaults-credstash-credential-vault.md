---
title: "CredStash credential vault"
slug: "configuring-credential-vaults-credstash-credential-vault"
updated: 2026-04-28T04:07:17Z
published: 2026-04-28T04:07:17Z
canonical: "helpcenter.securiti.ai/configuring-credential-vaults-credstash-credential-vault"
stale: true
area: integrations
modulo: credential-vaults
tipo: guia
data_captura: 2026-10-06
---

# CredStash credential vault

Securiti supports credential vaults that you can use to manage privilege account secrets for data systems that you integrate with Securiti.

> [!NOTE]
> **Note**
> 
> The Credential Vaults feature is available by subscription. Contact [support@securiti.ai](mailto:support@securiti.ai) to enable it for your Securiti tenant.

CredStash is a simple, easy-to-use credential management and distribution system that uses AWS Key Management Service (KMS) for key wrapping and master-key storage, and DynamoDB for credential storage and sharing.

> [!NOTE]
> **Note**
> 
> Securiti only supports CredStash when it is installed on a compute instance on AWS.

## Roles and permissions

Securiti implements role-based access control on actions that can be performed for credential vaults and keyrings, such as keyring creation. For more information on roles and their permissions, see [Data Systems RBAC permissions](/v1/docs/data-systems-rbac-permissions-and-roles#data-system-permissions-with-default-roles).

The configuration procedures in the following sections assume that you have already installed and configured CredStash.

### 1. Configure an access policy in CredStash

In CredStash, configure an access policy similar to that shown below to grant permission to perform credential actions to the IAM role that accesses the vault.

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
       "Sid": "VisualEditor1",
       "Effect": "Allow",
       "Action": "dynamodb:ListTables",
       "Resource": "*"
    },
    {
      "Action": [
        "dynamodb:GetItem",
        "dynamodb:PutItem",
        "dynamodb:Query",
        "dynamodb:Scan",
        "dynamodb:TagResource",
        "dynamodb:DeleteItem"
      ],
      "Effect": "Allow",
      "Resource": "arn:aws:dynamodb:us-west-2:16249562xxxx:table/credential-store"
    }
  ]
}
```

### 2. Configure key/secret pairs in CredStash

If you have not already done so, configure key/secret pairs for each data system in CredStash according to the example below. See the CredStash documentation for details.

```bash
credstash put {{username key you would like to configure}} {{ username of your application }}

credstash put {{password key you would like to configure}} {{ password of your application }}

example: credstash put username admin
```

### 3. Configure the CredStash vault instance in Securiti

1. In Securiti, open the main menu and select **Integrations > Credential Vaults**.
2. On the Credential Vaults page, near the upper right corner of the page, click **Add Integration** to create a new instance.
3. From the catalog of available credential vaults, select **CredStash**.
4. On the **Basic Information** tab, enter a name and location for the CredStash vault instance, and if you want, also choose additional co-owners (by default, you are the owner).
5. Click **Create Instance & Continue**.
6. On the **Authentication** tab, select a pod(s) from the **Pod Configuration** menu where a vault authenticates.

> [!NOTE]
> Note
> 
> - Securiti authenticates the vault only on the pods you select. You can choose all pods, a single pod, or multiple pods for a vault instance. If you select **ALL**, Securiti runs vault authentication across all pods.
> - You can update pod selection after creation without recreating the vault configuration.
> - Only vaults associated with the same pod as the data system connector appear as available keyrings during connector configuration.
7. On the **Authentication** tab, apply the following settings:

| Setting | Description |
| --- | --- |
| Application Method | Choose one: |
| AWS Default IAM Role | Uses the default IAM role provisioned to establish the session. |
| AWS Assumed IAM role | Uses an assumed IAM role along with account identifiers to establish the session. |
| Region | Choose the AWS region for the CredStash compute instance. |
| AWS IAM Role (AWS Assumed IAM role only) | Enter the name of the AWS IAM role used to access DynamoDB to get secrets. |
| AWS Account (AWS Assumed IAM role only) | Enter the AWS account ID for the AWS IAM role. |
| Credential Store | Enter the name of the CredStash credential store. The default used for most CredStash instances is `credential-store`. |
8. Click **Test and Save**.
9. On the Test Connection popup, click **Yes, proceed with testing**. Securiti validates the authentication information.
10. View the connection status in the **Overview** tab.

### 4. Create keyrings that use CredStash

Create keyrings that point to the connector secrets that you have placed in your CredStash credential vault:

1. In Securiti System Settings, open **Integrations > Credentials > Keyrings** and near the upper right corner of the page click **Create Keyring**.
2. On the Add Keyring popup, apply the following settings, then click **Add Keyring**:

| Setting | Description |
| --- | --- |
| Keyring Name | Enter a descriptive name for the keyring. |
| Keyring Description | (Optional) Enter a description for the keyring. |
| Keyring Type | Choose **CredStash Vault**. |
| Connector Type | Choose the type of data system for the keyring. |
| Vault Instance | Choose the CredStash credential vault you configured earlier. |
| User | Enter the username corresponding to the key/secret pairs you configured in the CredStash vault for the data system. |
| Password | Enter the password corresponding to the key/secret pairs you configured in the CredStash vault for the data system. |
| Credential Version (Optional) | Specify the version of the credential name, or leave blank to use the highest available. Any value you enter must be an integer greater than 0. |
| Encryption Context (Optional) | If necessary, enter the encryption context key/value pairs associated with the secret. Use the form "key=value". Provide comma-separated pairs, for example CTX1=TEST1,CTX2=TEST2. |

#### Storing separate credentials for Quarantine in SMB

You can store separate credentials for quarantine flow operations in SMB in the credentials vault. To store Privileged User Key and Privileged Password Key in your credential vault or keyring.

1. On the Add Keyring popup, configure settings to suit and select **SMB** in the **Connector Type** field.
2. In the **Use separate credentials for Quarantine** field in **Credentials Auth Key** section, select **Yes**.
3. In the **Credentials Key Name** section, enter your Privileged User Key and Privileged Password Key in the respective fields

![separate_credentials_keyring.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6975cd06-dc09-0997-b46a-9e6aab45d618(7).png)

### 5. Configure data systems to use the keyrings

Currently, Securiti supports CredStash vault storage for the following data systems:

- Alfresco
- Alibaba Cloud OSS
- Amazon DocumentDB
- Amazon RDS for MySQL
- Amazon RDS for PostgreSQL
- Amazon Redshift
- Amazon S3
- Azure Blob Storage
- Azure Cosmos DB for MongoDB
- Azure Files
- Cassandra
- Google Cloud Storage
- HDFS
- HP NonStopSQL
- IBM Db2
- IBM Db2 zOS
- LDAP Active Directory
- MongoDB
- MySQL
- Oracle
- Oracle /glos Storage
- PostgreSQL
- ServiceNow Files
- ServiceNow Tables
- SFTP
- SMB
- Snowflake
- SQL Server
- Teradata
- Wasabi
- Workday

For each self-hosted data system that supports CredStash keyring storage:

1. In Securiti, open **System Settings** and choose **Integrations > Data Systems > Monitored**.
2. Create a new data system instance, and on the Connector tab apply the following settings, then click **Authenticate & Activate Connector**:

| Setting | Description |
| --- | --- |
| Use Keyring | Enable the toggle. |
| Keyring Type | Choose **CredStash**. |
| Keyring | Choose the keyring you created earlier in [4. Create keyrings that use CredStash](/v1/docs/credstash-credential-vault). |

## Related

- [CyberArk Conjur credential vault](/configuring-credential-vaults-cyberark-conjur-credential-vault.md)
- [HashiCorp credential vault](/configuring-credential-vaults-hashicorp-credential-vault.md)
