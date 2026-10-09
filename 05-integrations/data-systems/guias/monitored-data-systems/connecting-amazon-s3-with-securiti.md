---
title: "Connecting Amazon S3 with Securiti"
slug: "connecting-amazon-s3-with-securiti"
updated: 2026-06-22T14:18:07Z
published: 2026-06-22T21:00:21Z
canonical: "helpcenter.securiti.ai/connecting-amazon-s3-with-securiti"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connecting Amazon S3 with Securiti

> [!NOTE]
> Note
> 
> Securiti stores sensitive connector credentials in an encrypted, base-64-encoded form. For self-hosted connectors, these credentials reside on your pod and are also stored in the Securiti cloud. A credential vault can also be used to store credentials for self-hosted connectors. If a vault is being used, credentials are retrieved securely from the vault at runtime on your pod and are not stored in the cloud.
> 
> 
> 
> For Securiti Cloud-hosted connectors, credentials are securely stored only in the Securiti cloud.

## Creating a data system instance

Perform the following steps to create a Data system instance:

1. Log in to Securiti with your admin credentials.
2. To open the main menu, from the upper left corner of the left navigation bar, click the **Jewel** icon.
3. From the **Platform Services** section in the navigation, select **Data Systems**. It takes you to the Monitored Data Systems page under Integrations.
4. On the top right of the **Integrations** page, click **Add Integration** to create a new data system instance.
5. On the **Add Integration** page, click the **Self Hosted** tab.
6. From the data system list, choose your relevant data system.
7. On the **Basic Information** tab, apply the following settings:

| **Setting** | **Description** | **Example** |
| --- | --- | --- |
| Instance Name | Enter a convenient name for the connector Instance. | Admin-data1 |
| Description | Add a short note to explain the purpose of this instance. | To discover and monitor data sources in the production environment. |
| Hosting Location | The hosting location is automatically set to IaaS. | IaaS |
| Service Provider | This field is automatically set to AWS**.** | AWS |
| Account ID | Enter the AWS account ID. The account ID uses a numeric value; see an example below. | *1234567891011* |
| Region | Select your AWS region from the menu. | `australiacentral` |
| Managed | Enable the toggle to differentiate between native and non-native (dark) assets. | N/A |
| Country | Select your country from the menu. | Australia |
| State/Region | Select your state from the menu. | Australian Capital Territory |
| City | Enter your city name. | Canberra |
| Owners | Choose **Primary Owner** for the Instance. By default, you are the primary owner. | John.doe@securiti.ai |
| (Optional) Enable the **Add co-owne**r toggle if you want to add an additional owner for the data system instance. It opens a Co-owner menu. From the **Co-owner** menu, choose up to three co-owners for the data system instance. | Alex.doe@securiti.ai |
| (Optional) Enable the toggle for **Send Notification to all Owners** to notify the owner and co-owners. | N/A |
8. Click **Create Instance & Continue**.

## Authenticating the connector

After creating an Amazon S3 connector instance, in the **Authentication** tab, authenticate your connector:

1. On the **Authentication** page, select the **Pod** you configured earlier in [Pods and Elastic Pods](/latest/docs/securiti-pods-and-elastic-pods).
2. From the **PCS Destination** menu, select one of the configured PCS to store this data system connector's sensitive data. For more information, see [Configuring PCS Destination](/latest/docs/system-settings-configuring-private-cloud-storage).

> [!NOTE]
> Note
> 
> If this feature is not available in your Securiti tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan.
3. In the **Credentials** section, configure the following settings:

| Setting | Description |
| --- | --- |
| Authentication Type | You can select the following authentication types from the menu. - IAM Keys - IAM Roles - S3 Inventory - Auto-generate Dynamic Credentials |
| Region | The region field is automatically populated based on the value selected in the **Region** field in the **Basic Information** tab, as described above. The pre-populated value is according to the below region to location mapping: - `us-east-1: northernvirginia` - `us-east-2: ohio` - `us-west-1: northerncalifornia` - `us-west-2: oregon` - `us-gov-east-1: usgov-east` - `us-gov-west-1: usgov-west` - `af-south-1: capetown` - `ap-east-1: hongkong` - `ap-south-1: mumbai` - `ap-south-2: hyderabad` - `ap-northeast-3: osaka` - `ap-northeast-2: seoul` - `ap-southeast-1: singapore` - `ap-southeast-2: sydney` - `ap-southeast-3: jakarta` - `ap-southeast-4: melbourne` - `ap-southeast-5: malaysia` - `ap-northeast-1: tokyo` - `ca-central-1: centralcanada` - `ca-west-1: calgary` - `cn-north-1: beijing` - `cn-northwest-1: ningxia` - `eu-central-1: frankfurt` - `eu-central-2: zurich` - `eu-west-1: ireland` - `eu-west-2: london` - `eu-west-3: paris` - `eu-south-1: milan` - `eu-south-2: spain` - `eu-north-1: stockholm` - `il-central-1: telaviv` - `me-south-1: bahrain` - `me-central-1: uae` - `mx-central-1: mexico` - `sa-east-1: saopaulo` |
| Bucket(s) | It automatically fetches the Bucket you recorded in creating data system instance. *Datascan-ows-connector* |
| (Optional) Use Keyring | You can enable the Use Keyring toggle if you want to use a keyring to manage credentials for the instance as described in [Using keyrings](/v1/docs/using-keyrings). Then choose the keyring type, such as HashiCorp and keyring. - [Configuring HashiCorp credential vaults](/v1/docs/configuring-credential-vaults-hashicorp-credential-vault) - [Configuring AWS Secrets Manager credential vaults](/v1/docs/configuring-credential-vaults-aws-secrets-manager-credential-vault) - [Configuring Credstash credential vaults](/v1/docs/configuring-credential-vaults-credstash-credential-vault) - [Configuring CyberArk credential vaults](/latest/docs/cyberark-credential-vault). > [!NOTE] > Note > > If you use CyberArk Credentials vault to manage AWS credentials, Securiti recommends registering the credentials using the **Cloud Services → AWS Access Keys** platform in CyberArk. To learn more about configuration, see [*(Optional) Storing AWS Credentials using CyberArk Cloud Services platform*](/latest/docs/optional-storing-aws-credentials-using-cyberark-cloud-services-platform)*.* |
| (Optional) Use Native Inventory | Enable the toggle to use Native Inventory-based method instead of APIs-based listing method in data inventory syncs and discovery scans. > [!WARNING] > Important > > The toggle does not appear for the S3 Inventory authentication type, which uses Native Inventory-based method by default. Configure the following parameters if you have enabled the **Use Native Inventory** toggle: - **Inventory Report Bucket**: Specify the destination bucket name where the s3 inventory report is generated. See an example below. *securiti-inventory-reports* - **Inventory Report Path**: Specify the path to the inventory directory excluding the destination bucket name. See an example below. */inventory/<SOURCE_BUCKET_NAME>/inventory-details/* > [!NOTE] > **Note** > > - Native Inventory-based listing method is recommended for discovery workloads on clusters with 50+ nodes, as it leverages consistent performance and near-linear scaling. > - You must enable the fields required for S3 Inventory as mentioned in [Obtain credentials for Inventory-based authentication in Amazon S3](/v1/docs/obtain-credentials-for-inventory-based-authentication-in-amazon-s3). For more information, see [Amazon's documentation on Cataloging data with S3 inventory](https://docs.aws.amazon.com/AmazonS3/latest/userguide/storage-inventory.html#storage-inventory-contents). |
| **IAM Keys Authentication Type** |
| Token Id | If you are not using Keyring, enter the Token Id you recorded from [Amazon documentation](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_access-keys.html). The Token Id uses string value. See the example below. *AkiAIoSfODnN7* |
| Token Secret | If you are not using Keyring, enter the Token Secret you recorded rom [Amazon documentation](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_access-keys.html). The Token Secret uses string value. See the example below. *XwWJalrXUtnFEMI/K7MDENG/bPxRfiCY* |
| **IAM Roles Authentication Type** > [!NOTE] > Note > > Securiti supports two options to configure credentials for IAM Role–based authentication methods: > > - **With IRSA (IAM Roles for Service Accounts):** Each Kubernetes pod assumes a dedicated IAM role, enabling fine-grained and secure access control. For more information, see [Obtain credentials for role based authentication in Amazon S3](/latest/docs/obtain-credentials-for-role-based-authentication-in-amazon-s3). > - **Without IRSA (Node IAM Role):** Pods inherit permissions from the underlying EKS node’s IAM role, resulting in shared access across workloads. For more information, see [IRSA Authenticatio for IAM Role in Securiti](/latest/docs/irsa-authentication-steps-for-iam-role-in-securitii). |
| AWS Master Account ID | Specify the master account ID which can assume a member role. The master account ID uses the 12 digit numeric value. See an example below. *123456789012* |
| Data Scan Master IAM Role | Specify the IAM role in the master account which can assume a member role. See an example below. *SecuritiMasterRole* |
| AWS Member Account IDs | Specify the AWS account IDs of the member accounts that has permissions to perform data scans on the S3 bucket. The account ID uses the 12 digit numeric value. See an example below of the comma separated member IDs. *987654321001, 987654321002* |
| Data Scan Member IAM Role | Specify the IAM role in the member accounts that has permissions to perform data scans on the S3 bucket. See an example below. *SecuritiMemberRole* |
| (Optional) External Id for Master and Member IAM Roles | Specify any external IDs for master and member IAM roles. See an example below. *securiti123* |
| **S3 Inventory Authentication Type** > [!NOTE] > **Note** > > You must enable the fields required for S3 Inventory as mentioned in [Obtain credentials for Inventory-based authentication in Amazon S3](/v1/docs/obtain-credentials-for-inventory-based-authentication-in-amazon-s3). For more information, see [Amazon's documentation on Cataloging data with S3 inventory](https://docs.aws.amazon.com/AmazonS3/latest/userguide/storage-inventory.html#storage-inventory-contents). |
| Inventory Report Bucket | Specify the destination bucket name where the s3 inventory report is generated. The bucket names uses a string value. See an example below. *securiti-inventory-reports* |
| Inventory Report Path | Specify the path to the inventory directory excluding the destination bucket name. The inventory report path follows a string format. See example below. */inventory//<SOURCE_BUCKET_NAME>/inventory-details/* |
| Inventory Token Id | Specify the Token Id for inventory you acquired in [Obtain credentials for Inventory-based authentication in Amazon S3](/latest/docs/obtain-credentials-for-inventory-based-authentication-in-amazon-s3). |
| Inventory Token Secret | Specify the Token Secret for inventory you acquired in [Obtain credentials for Inventory-based authentication in Amazon S3](/latest/docs/obtain-credentials-for-inventory-based-authentication-in-amazon-s3). |
| **Auto-generate Dynamic Credentials Authentication Type** > [!NOTE] > **Note** > > Auto-Generate Dynamic Credentials is only supported for HashiCorp Vault and appliance version 1.122 and above. |
| Keyring Type | Your dynamic credentials are stored in the HashiCorp vault. HashiCorp is automatically selected as the keyring for Auto-generate dynamic credentials authentication type. |
| Keyring | Select the HashiCorp keyring from the menu, that you configured for storing your credentials. |
| **Optional fields for all authentication types** |
| Allow Quarantine Actions on this Data System | Enable the toggle to quarantine files from Amazon S3. Securiti lets you create central quarantine destination with Amazon S3 and isolate your files in buckets. > [!WARNING] > Important > > - You must configure your Amazon S3 connector with pod version 1.144.0 and above to enable quarantine actions on the data system. > - When you enable Quarantine policies for this data system, the connector must have read and write privileges on both the scanned target location and the designated quarantine folder. Without these permissions, quarantine actions cannot execute successfully. |
| Evaluate data system size | Mark the checkbox to evaluate the data system size during authentication. This calculates the total size and object count across the specified buckets. Securiti calculates resource size on a weekly basis to keep the data size value up to date. > [!NOTE] > **Note** > > Ensure that AWS credentials have permission to query cloudwatch API `GetMetricStatistics` to evaluate size. |
4. Click **Test Connection**.

Securiti activates the connector.

### Monitoring connection tests and authentication statuses

After authenticating the connector, use this section to review connection test results, verify the configured permissions, and check the authentication statuses for supported capabilities, such as Discovery scans and metadata scans.

For more information, see [Using data system connector authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scans settings

Proceed to the following topics to configure the post-authentication scans settings for the Amazon S3 (self-hosted):

- [Configuring Data Inventory Sync for Amazon S3](/latest/docs/configuring-data-inventory-sync-for-amazon-s3-self-hosted).
- [Configure discovery scans in Amazon S3](/latest/docs/configure-discovery-scans-in-amazon-s3).
- [Configuring Access scan settings for Amazon S3](/latest/docs/new-ui-configuring-general-and-access-permissions).

## Related

- [Configure discovery scans in Amazon S3](/configure-discovery-scans-in-amazon-s3.md)
- [Configuring Data Inventory Sync for Amazon S3 (Self-hosted)](/configuring-data-inventory-sync-for-amazon-s3-self-hosted.md)
- [Troubleshooting for Amazon S3 connector](/troubleshooting-for-amazon-s3-connector.md)
