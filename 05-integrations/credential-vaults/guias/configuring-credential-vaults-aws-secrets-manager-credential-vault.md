---
title: "AWS Secrets Manager credential vault"
slug: "configuring-credential-vaults-aws-secrets-manager-credential-vault"
updated: 2026-06-08T08:32:37Z
published: 2026-06-22T21:00:21Z
canonical: "helpcenter.securiti.ai/configuring-credential-vaults-aws-secrets-manager-credential-vault"
stale: true
area: integrations
modulo: credential-vaults
tipo: guia
data_captura: 2026-10-06
---

# AWS Secrets Manager credential vault

AWS Secrets Manager helps you manage, retrieve, and rotate database credentials, API keys, and other secrets throughout their life cycles.

It lets you replace hard coded credentials in your code, including passwords, with an API call to Secrets Manager to retrieve the secret programmatically. This helps ensure the secret can't be compromised by someone examining your code, because the secret no longer exists in the code. Also, you can configure Secrets Manager to automatically rotate the secret for you according to a specified schedule. This lets you replace long-term secrets with short-term ones, significantly reducing the risk of compromise.

> [!NOTE]
> **Important**
> 
> You can only activate AWS Secrets Manager Vault instances through Securiti Pods and Elastic Pod clusters. Activating the AWS Secrets Manager Vault instance automatically ensures the necessary AWS Secrets Manager packages are activated on every active Pod cluster on your Securiti instance.

> [!NOTE]
> **Important**
> 
> If the Pod is running in AWS environment and the underlying VM has IMDSv2 enabled, the hop count of the EC2 instance must be configured to no less than 2, for successful authentication.
> 
> If necessary, use the command below to set the hop count to 2.
> 
> ```bash
> aws ec2 modify-instance-metadata-options --instance-id <instance ID> --http-put-response-hop-limit 2
> ```
> 
> Enable IMDSv2 with a hop count of 2 using the command below.
> 
> ```bash
> aws ec2 modify-instance-metadata-options --instance-id <instance-id> \\
> --http-put-response-hop-limit 2 \\
> --region <region> \\
> --http-tokens required \\
> --http-endpoint enabled
> ```
> 
> See an example below.
> 
> ```bash
> aws ec2 modify-instance-metadata-options --instance-id i-0d53eaaaaaa67c3fa \\
> --http-put-response-hop-limit 2 \\
> --region us-west-2 \\
> --http-tokens required \\
> --http-endpoint enabled
> ```

## Roles and permissions

Securiti implements role-based access control on actions that can be performed for credential vaults and keyrings, such as keyring creation. For more information on roles and their permissions, see [Data Systems RBAC permissions](/v1/docs/data-systems-rbac-permissions-and-roles#data-system-permissions-with-default-roles).

### 1. Configure a permissions policy in AWS Secrets Manager

In AWS, configure a policy that grants permission to access secrets on Secrets Manager. For example:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": {
        "AWS": "arn:aws:iam::AccountId:role/EC2RoleToAccessSecrets"
      },
      "Action": [
        "secretsmanager:GetSecretValue",
        "secretsmanager:ListSecrets"
      ],
      "Resource": [
        "arn:aws:secretsmanager:us-west-2:111122223333:secret:secret1",
        "arn:aws:secretsmanager:us-west-2:111122223333:secret:secret2",
        "arn:aws:secretsmanager:us-west-2:111122223333:secret:secret3"
      ]
    }
  ]
}
```

### 2. Configure the AWS Secrets Manager vault instance in Securiti

1. In Securiti, open the main menu and choose **Integrations > Credential Vaults**.
2. On the **Credential Vaults** page, click **Add Integration** to create a new instance.
3. Select **AWS Secrets Manager** from the catalog of available credential vaults.
4. On the **Basic Information** tab, enter a name and location for the AWS Secrets Manager vault instance, and if you want, also choose additional co-owners (by default you are the owner).
5. Click **Create Instance and Continue**.
6. On the **Authentication** tab, select a pod(s) from the **Pod Configuration** menu where a vault authenticates.

> [!NOTE]
> Note
> 
> - Securiti authenticates the vault only on the pods you select. You can choose all pods, a single pod, or multiple pods for a vault instance. If you select **ALL**, Securiti runs vault authentication across all pods.
> - You can update pod selection after creation without recreating the vault configuration.
> - Only vaults associated with the same pod as the data system connector appear as available keyrings during connector configuration.

For Authentication Method, choose one of the following methods:
  - **Default**--Uses the IAM role that is already assigned to the pod, so you only have to provide the AWS region.

After you choose **Default**, choose the AWS region.
  - **Basic**--Key based authentication for which you must provide the Access key and Secret key along with the AWS region. Because it is a key-based authentication method, you can use this method on any pod.

After you choose **Basic**, apply the following settings:

| Setting | Description |
| --- | --- |
| Region | Enter the AWS Region. |
| Access key | Enter the access key that the pod uses to authenticate to AWS Secrets Manager. |
| Secret key | Enter the secret key that the pod uses to authenticate to AWS Secrets Manager. |
  - **IAM Roles**--To use this method, you must provide the AWS Region, AWS AccountId and AWS Role through which Securiti authenticates AWS Secrets Manager.

After you choose Basic, apply the following settings:

| Setting | Description |
| --- | --- |
| Region | Enter the AWS Region. |
| AWS Account | Enter the AWS account ID for the specified role. |
| AWS IAM Role | Enter the AWS IAM role that the pod assumes to authenticate to AWS Secrets Manager |
7. Click **Test and Save**.
8. On the Test Connection popup, click **Yes, proceed with testing**. Securiti validates the authentication information.
9. Review the connection status in the **Overview** tab.

### 3. Create keyrings that use AWS Secrets Manager

Create keyrings that point to the connector secrets that you have placed in your key vault:

1. In System Settings, open **Integrations > Credentials > Keyrings** and click **Create Keyring**.
2. On the Add Keyring popup, apply the following settings, then click **Add Keyring**:

| Setting | Description |
| --- | --- |
| Keyring Name | Enter a descriptive name for the keyring. |
| Keyring Description | (Optional) Enter a description for the keyring. |
| Keyring Type | Choose **AWS Secrets Manager**. |
| Connector Type | Choose the type of data system for the keyring. |
| Vault Instance | Choose the AWS Secrets Manager credential vault you configured earlier. |
| Secret Name | Enter the name of the secret as defined in the policy you created in [1. Configure a permissions policy in AWS Secrets Manager](/v1/docs/aws-secrets-manager-credential-vault). |
| User Key | Enter the name of the user key you configured in AWS secrets manager. The default user key name is `username`. > [!NOTE] > **Note** > > If you configured keyrings for AWS Secrets Manager prior to Securiti release 1.92, you might have to change the user key from `user` to `username` to use the keyring. |
| Password Key | Enter the name of the password key you configured in AWS secrets manager. The default password key name is `password`. |

#### Storing separate credentials for Quarantine in SMB

You can store separate credentials for quarantine flow operations in SMB in the credentials vault. To store Privileged User Key and Privileged Password Key in your credential vault or keyring.

1. On the Add Keyring popup, configure settings to suit and select **SMB** in the **Connector Type** field.
2. In the **Use separate credentials for Quarantine** field in **Credentials Auth Key** section, select **Yes**.
3. In the **Credentials Key Name** section, enter your Privileged User Key and Privileged Password Key in the respective fields

![separate_credentials_keyring.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6975cd06-dc09-0997-b46a-9e6aab45d618(6).png)

### 4. Configure data system connectors to use the AWS Secrets Manager keyrings

Currently, Securiti supports AWS Secrets Manager keyring storage for the following data systems:

- Alfresco
- AliBaba Cloud OSS
- Amazon Athena
- Amazon Aurora for PostgreSQL
- Amazon DocumentDB
- Amazon DynamoDB
- Amazon MSK
- Amazon RDS for MySQL
- Amazon RDS for PostgreSQL
- Amazon RDS MariaDB
- Amazon Redshift
- Amazon S3
- Azure Blob Storage
- Azure Files
- Google Cloud Storage
- HDFS
- MySQL
- Oracle
- PostgreSQL
- S3 Compatible Storage
- SFTP
- SMB
- SQL Server
- Wasabi

For each such data system:

1. In Securiti, open **System Settings** and choose **Integrations > Data Systems > Monitored**.
2. Create a new data system instance, and on the Connector tab apply the following settings, then click **Authenticate & Activate Connector**:

| Setting | Description |
| --- | --- |
| Use Keyring | Enable the toggle. |
| Keyring Type | Choose **AWS Secrets Manager**. |
| Keyring | Choose the keyring you created earlier in [3. Create keyrings that use AWS Secrets Manager](/v1/docs/aws-secrets-manager-credential-vault). |

## Related

- [Azure Key Vault](/configuring-credential-vaults-azure-key-vault.md)
- [Delinea Secret Manager credential vault](/configuring-credential-vaults-delinea-secret-manager-credential-vault.md)
- [GCP Secret Manager credential vault](/configuring-credential-vaults-gcp-secret-manager-credential-vault.md)
