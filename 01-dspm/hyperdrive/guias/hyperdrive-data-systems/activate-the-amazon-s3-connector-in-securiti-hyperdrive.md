---
title: "Connecting the Amazon S3 with Securiti (Hyperdrive)"
slug: "activate-the-amazon-s3-connector-in-securiti-hyperdrive"
updated: 2026-07-20T20:30:57Z
published: 2026-07-21T21:00:19Z
canonical: "helpcenter.securiti.ai/activate-the-amazon-s3-connector-in-securiti-hyperdrive"
stale: true
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Connecting the Amazon S3 with Securiti (Hyperdrive)

****Create a data system instance****

Perform the following steps to create a Data system instance:

1. Log in to Securiti with your admin credentials.
2. To open the main menu, from the upper left corner of the left navigation bar, click the **Jewel** icon.
3. From the **Platform Services** section in the navigation, select **Data Systems**. It takes you to the Monitored Data Systems page under Integrations.
4. On the top right of the **Integrations** page, click **Add Integration** to create a new data system instance.
5. On the **Add Integration** page, click the **Self Hosted** tab.
6. From the data system list, choose your relevant data system.
7. On the **Basic Information** tab, apply the following settings:

| **Setting** | **Description** | Example |
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
8. (Optional) Enable the **Hyperdrive mode** toggle to use dynamic compute scaling for data scans through the Securiti Outpost deployment.

> [!NOTE]
> Note
> 
> If the feature is not available in your Securiti tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan.
> 
> Securiti recommends you to use Hyperdrive mode. This option automatically increases compute capacity for large or complex scans and scales back during lighter scans.
9. Click **Create Instance & Continue**.

## Authenticating the connector

After creating Amazon S3 connector instance, in the **Authentication** tab, authenticate your connector:

1. On the **Authentication** page, from the **Outpost** menu, choose the Hybrid Deployment with Outpost or Full SaaS deployment you configured earlier. For more information, see [Securiti outpost deployment](/latest/docs/securiti-outpost-deployment).
2. > [!WARNING]
> Important
> 
> - If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

From the **PCS Destination** menu, select one of the configured PCS to store this data system connector's sensitive data, such as:

  - Table Training Sample files
  - Sensitive Data Intelligence protection evidence files
  - Scan Summary

> [!NOTE]
> Note
> 
> DSR Automation, Assessment Automation, and the transient metadata used during scanning continue to use the Default PCS configured for your tenant until those modules adopt multi-PCS support.

You can also migrate the data from one PCS to another while reconfiguring the connector. To migrate data from one PCS to another:

  1. On the activated data system instance, click on the **Reconfigure** link.
  2. From the **PCS Destination** menu, select the PCS where you want to migrate the data.
  3. Click **Reconfigure connector**.

Securiti shows you the migration progress bar to check the status of migration. Sensitive data is stored on the existing PCS bucket until the migration is complete.
3. In the **Credentials** section, configure the following settings:

| Setting | Description |
| --- | --- |
| Authentication Type | You can select the following authentication types from the menu. - IAM Keys - IAM Roles - S3 Inventory |
| Region | The region field is automatically populated based on the value selected in the **Region** field in the **Basic Information** tab, as described above. The pre-populated value is according to the below region to location mapping: - `us-east-1: northernvirginia` - `us-east-2: ohio` - `us-west-1: northerncalifornia` - `us-west-2: oregon` - `us-gov-east-1: usgov-east` - `us-gov-west-1: usgov-west` - `af-south-1: capetown` - `ap-east-1: hongkong` - `ap-south-1: mumbai` - `ap-south-2: hyderabad` - `ap-northeast-3: osaka` - `ap-northeast-2: seoul` - `ap-southeast-1: singapore` - `ap-southeast-2: sydney` - `ap-southeast-3: jakarta` - `ap-southeast-4: melbourne` - `ap-southeast-5: malaysia` - `ap-northeast-1: tokyo` - `ca-central-1: centralcanada` - `ca-west-1: calgary` - `cn-north-1: beijing` - `cn-northwest-1: ningxia` - `eu-central-1: frankfurt` - `eu-central-2: zurich` - `eu-west-1: ireland` - `eu-west-2: london` - `eu-west-3: paris` - `eu-south-1: milan` - `eu-south-2: spain` - `eu-north-1: stockholm` - `il-central-1: telaviv` - `me-south-1: bahrain` - `me-central-1: uae` - `mx-central-1: mexico` - `sa-east-1: saopaulo` |
| Bucket(s) | It automatically fetches the Bucket you recorded when creating a data system instance. *Datascan-ows-connector* |
| (Optional) Use Keyring | Keyring support is not available for Hyperdrive mode. |
| (Optional) Use Native Inventory | Enable the toggle to use **Native Inventory** method instead of **Listing** method in Data Inventory Syncs. The toggle does not appear for the **S3 Inventory** authentication type, which uses **Native Inventory** by default. You must provide values for the following parameters in case you enable the toggle. - **Inventory Report Bucket**: Specify the destination bucket name where the s3 inventory report is generated. See an example below. *securiti-inventory-reports* - **Inventory Report Path**: Specify the path to the inventory directory excluding the destination bucket name. See an example below. */inventory/<SOURCE_BUCKET_NAME>/inventory-details/* > [!NOTE] > **Note** > > You must enable the fields required for S3 Inventory as mentioned in [Obtain credentials for Inventory-based authentication in Amazon S3](/v1/docs/obtain-credentials-for-inventory-based-authentication-in-amazon-s3). For more information, see [Amazon's documentation on Cataloging data with S3 inventory](https://docs.aws.amazon.com/AmazonS3/latest/userguide/storage-inventory.html#storage-inventory-contents). |
| **IAM Keys Authentication Type** |
| Token Id | If you are not using Keyring, enter the Token Id you recorded from [Amazon documentation](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_access-keys.html). The Token Id uses a string value. See the example below. *AkiAIoSfODnN7* |
| Token Secret | If you are not using Keyring, enter the Token Secret you recorded from [Amazon documentation](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_access-keys.html). The Token Secret uses a string value. See the example below. *XwWJalrXUtnFEMI/K7MDENG/bPxRfiCY* |
| **IAM Roles Authentication Type** |
| AWS Master Account ID | Specify the master account ID that can assume a member role. The master account ID uses the 12-digit numeric value. See an example below. *123456789012* |
| Data Scan Master IAM Role | Specify the IAM role in the master account that can assume a member role. See an example below. *SecuritiMasterRole* |
| AWS Member Account IDs | Specify the AWS account IDs of the member accounts that have permissions to perform data scans on the S3 bucket. The account ID uses the 12-digit numeric value. See an example below of the comma-separated member IDs. *987654321001, 987654321002* |
| Data Scan Member IAM Role | Specify the IAM role in the member accounts that has permissions to perform data scans on the S3 bucket. See an example below. *SecuritiMemberRole* |
| External Id for Master and Member IAM Roles | > [!NOTE] > Note > > - External Id is optional parameter if you are using Hybrid deployment with Outpost. > - External Id is required parameter if you are using Full SaaS deployment model. Specify a unique, hard-to-guess string for the External ID for master and member IAM roles. See an example below. `Securiti-9f3Kx7LmQ2pR8vN5` > [!CAUTION] > Caution > > In case of Full SaaS deployment, ensure that the External ID in the Master role trust policy exactly matches the External ID entered on the connector activation page. Any mismatch prevents Securiti from establishing the connection. |
| **S3 Inventory Authentication Type** > [!NOTE] > **Note** > > You must enable the fields required for S3 Inventory as mentioned in [Obtain credentials for Inventory-based authentication in Amazon S3](/latest/docs/obtain-credentials-for-inventory-based-authentication-in-amazon-s3-hyperdrive). For more information, see [Amazon's documentation on Cataloging data with S3 inventory](https://docs.aws.amazon.com/AmazonS3/latest/userguide/storage-inventory.html#storage-inventory-contents). |
| Inventory Report Bucket | Specify the destination bucket name where the s3 inventory report is generated. The bucket names uses a string value. See an example below. *securiti-inventory-reports* |
| Inventory Report Path | Specify the path to the inventory directory excluding the destination bucket name. The inventory report path follows a string format. See example below. */inventory//<SOURCE_BUCKET_NAME>/inventory-details/* |
| Inventory Token Id | Specify the Token Id for inventory you acquired in [Obtain credentials for Inventory-based authentication in Amazon S3](/latest/docs/obtain-credentials-for-inventory-based-authentication-in-amazon-s3-hyperdrive). |
| Inventory Token Secret | Specify the Token Secret for inventory you acquired in [Obtain credentials for Inventory-based authentication in Amazon S3](/latest/docs/obtain-credentials-for-inventory-based-authentication-in-amazon-s3-hyperdrive). |
| **Auto-generate Dynamic Credentials Authentication Type** > [!NOTE] > **Note** > > Auto-Generate Dynamic Credentials is not supported for Amazon S3 using Hyperdrive mode. |
| Keyring Type | N/A |
| Keyring | N/A |
| **Optional fields for all authentication types** |
| (Optional) Evaluate data system size | Mark the checkbox to evaluate the data system size during authentication. This calculates the total size and object count across the specified buckets. Securiti calculates resource size on a weekly basis to keep the data size value up to date. > [!NOTE] > **Note** > > Ensure that AWS credentials have permission to query cloudwatch API `GetMetricStatistics` to evaluate size. |
4. Click **Authenticate & Activate Connector**.

Securiti activates the connector.

### Monitoring connection tests and authentication statuses

After authenticating the connector, use this section to review connection test results, verify the configured permissions, and check the authentication statuses for supported capabilities, such as Discovery scans and metadata scans.

For more information, see [Using authentication statuses (Hyperdrive)](/latest/docs/using-authentication-statuses-hyperdrive).

## Configuring post-authentication scans settings

Proceed to the following topics to configure the post-authentication scans settings for the Amazon S3 (self-hosted)

- [Configuring Data Inventory Sync for Amazon S3 (Hyperdrive)](/latest/docs/configuring-data-inventory-sync-for-amazon-s3-hyperdrive)
- [Configure discovery scans in Amazon S3 (Hyperdrive)](/latest/docs/configuring-discovery-scans-in-amazon-s3-hyperdrive)
