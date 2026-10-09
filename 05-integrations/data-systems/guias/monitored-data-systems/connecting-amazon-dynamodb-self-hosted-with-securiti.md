---
title: "Connecting Amazon DynamoDB (self-hosted) with Securiti"
slug: "connecting-amazon-dynamodb-self-hosted-with-securiti"
status: "update"
updated: 2026-09-21T12:21:18Z
published: 2026-09-21T12:21:18Z
canonical: "helpcenter.securiti.ai/connecting-amazon-dynamodb-self-hosted-with-securiti"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connecting Amazon DynamoDB (self-hosted) with Securiti

This topic covers activation of the Amazon DynamoDB self-hosted connector.

> [!NOTE]
> Note
> 
> Securiti stores sensitive connector credentials in an encrypted, base-64-encoded form. For self-hosted connectors, these credentials reside on your pod and are also stored in the Securiti cloud. A credential vault can also be used to store credentials for self-hosted connectors. If a vault is being used, credentials are retrieved securely from the vault at runtime on your pod and are not stored in the cloud.
> 
> 
> 
> For Securiti Cloud-hosted connectors, credentials are securely stored only in the Securiti cloud.

## Creating an Amazon DynamoDB (self-hosted) data system instance

Perform the following steps to create a Data system instance for self-hosted connectors:

1. Log in to Securiti with your admin credentials.
2. To open the main menu, from the upper left corner of the left navigation bar, click the **Jewel** icon.
3. From the Platform Services section in the new navigation, select **Integrations**.
4. From the **Integrations** menu, choose **Monitored Data Systems.**
5. On the top right of the **Integrations** page, click **Add Integration** to create a new data system instance.
6. On the Add Integration page, click the **Self-Hosted** tab.
7. From the data system list, choose your relevant data system.
8. On the **Basic Information** tab, complete the following parameters:

| **Parameter** | **Explanation** | **Example** |
| --- | --- | --- |
| Instance Name | Enter a convenient name for the connector Instance. | Admin-data1 |
| Description | Add a short note to explain the purpose of this instance. | To discover and monitor data sources in the production environment. |
| Hosting Location | The **Hosting Location** is automatically set to **IaaS**. | IaaS |
| Service Provider | This field is automatically set to your data system's service provider. | AWS |
| Account ID | Enter the AWS **Account ID** for your data system account. The account ID uses an alphanumeric string value. | `1234567891011` |
| Region | Select the region from the menu. | `us-east-2` |
| Managed | Enable the toggle to differentiate between native and non-native (dark) assets. |  |
| Country | Select the **country** from the dropdown where the data source or resource is located. | `Australia` |
| (Optional) State | Select the **state** or region from the dropdown within the chosen country. | `Australian Capital Territory` |
| (Optional) City | Enter the **city** where the data source or resource is located. | `Canberra` |
| Owners | Choose **Primary** **Owner** for the Instance. By default, you are the primary owner. | `John.doe@securiti.ai` |
| (optional) Additional owners can be added after creating an instance by enabling the **Add** **Co-owner** tab on the Basic Information page. From the dropdown, select users to add as additional owners. | `Alex.doe@securiti.ai` |
| (optional) Enable the toggle for **Send Notification to all Owners** to notify owners. |  |
9. At the Bottom of the page, click **Create and Continue**.

It redirects you to the **Authentication** page.

## Authenticating Amazon DynamoDB (self-hosted) connector

After creating an Amazon DynamoDB connector instance, in the **Authentication** tab, authenticate your connector:

1. Under the **Pod Configuration** section, from the **Select** **Pod** menu, choose the pod you configured earlier.
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

| Setting | Authentication Type | Description |
| --- | --- | --- |
| Authentication type | N/A | You can select from the available authentication types for Amazon DynamoDB: - **Basic** - **IAM Roles** |
| Use Keyring | Basic | You can enable the **Use Keyring** toggle if you want to use a keyring to manage credentials for the instance as described in [Using keyrings](/latest/docs/managing-credentials-using-keyrings). Then choose the supported keyring type: - **AWS Secret Manager:** For more information, see [AWS Secrets Manager credential vault](/latest/docs/configuring-credential-vaults-aws-secrets-manager-credential-vault) |
| From the **Keyring**, select the pre-configured keyrings. |
| Region | - Basic - IAM Roles | The region field is automatically populated based on the value selected in the **Region** field in the **Basic Information** tab. See the list of mapped regions: - `us-east-1: northernvirginia` - `us-east-2: ohio` - `us-west-1: northerncalifornia` - `us-west-2: oregon` - `us-gov-east-1: usgov-east` - `us-gov-west-1: usgov-west` - `af-south-1: capetown` - `ap-east-1: hongkong` - `ap-south-1: mumbai` - `ap-south-2: hyderabad` - `ap-northeast-3: osaka` - `ap-northeast-2: seoul` - `ap-southeast-1: singapore` - `ap-southeast-2: sydney` - `ap-southeast-3: jakarta` - `ap-southeast-4: melbourne` - `ap-southeast-5: malaysia` - `ap-northeast-1: tokyo` - `ca-central-1: centralcanada` - `ca-west-1: calgary` - `cn-north-1: beijing` - `cn-northwest-1: ningxia` - `eu-central-1: frankfurt` - `eu-central-2: zurich` - `eu-west-1: ireland` - `eu-west-2: london` - `eu-west-3: paris` - `eu-south-1: milan` - `eu-south-2: spain` - `eu-north-1: stockholm` - `il-central-1: telaviv` - `me-south-1: bahrain` - `me-central-1: uae` - `mx-central-1: mexico` - `sa-east-1: saopaulo` |
| Access Key | Basic | Enter the Access Key ID from your AWS Management console you recorded in [obtain credentials for your DynamoDB instance](/latest/docs/obtain-credentials-for-your-dynamodb-instance), The Access Key uses a string value. See the example below. `8a7b3c9d-12e4-567f-89ab-0123456789c` |
| Secret Key | Basic | Enter the Secret Key from your AWS Management console you recorded in [Obtain credentials for your DynamoDB instance](/latest/docs/obtain-credentials-for-your-dynamodb-instance), The Secret Key uses a string value, See the example below. `n3v3rU53th1s_Ke3p1tS3cur3!` |
| AWS Account | IAM Role | Enter the AWS account ID you recorded in [Obtain credentials for your DynamoDB instance](/latest/docs/obtain-credentials-for-your-dynamodb-instance). AWS Account identifiers use a numeric value. See an example below. `123456789012` |  |
| (Optional) AWS IAM Role | IAM Role | Specify the AWS role that can be used by the appliance to authenticate with Amazon DynamoDB. This role should be created in the same Amazon DynamoDB account as the above account ID. See [Obtain credentials for your DynamoDB instance](/latest/docs/obtain-credentials-for-your-dynamodb-instance), for more information. IAM role uses a string value. See an example below. `securiti_role` |  |
| Row Scan Depth | - Basic - IAM Roles | > [!NOTE] > **Important** > > DynamoDB is a NoSQL data system that stores data in JSON format, not tables. > > > > In this case, the Row Scan Depth parameter refers to how many rows in the JSON schema you should look at during the table training process for the connector to learn all of the keys in the schema. We recommend you specify rows between the limit of 50 to 100. Enter the number of rows you wish to scan through. |
| (Optional) Additional Connection String Options | - Basic - IAM Roles | Specify any additional JDBC connection string options (delimited by ';') that are specific and special for this data store. See an example below: `param1=value;param2=value2` |
| (Optional) Store Sample file on PCS | - Basic - IAM Roles | - **Store Sample files on PCS** toggle is disabled by default. > [!NOTE] > **Note** > > In EPod V2 deployments, Securiti disables this toggle if PCS is not configured in yourtenant. Without PCS, support for storing sample files is unavailable for structured orhybrid data systems. - Keep the toggle disabled to store table training sample files locally on the pod, ensuring they remain within your local environment. - Enable this toggle if you wish to store table training sample files in Private Cloud Storage (PCS). > [!NOTE] > **Note** > > This functionality can only be enabled if Private Cloud Storage is already configured in your tenant. In case of reconfiguring a connector, files stored prior to the reconfiguration remain in their existing location, pods or PCS, until you perform a re-scan, after which Securiti stores sample files in the newly configured location. |
4. Click **Test Connection** at the bottom of the page.

Securiti activates the connector.

### Monitoring the Overview page and authentication statuses

After authenticating the connector, in the **Overview** section:

- Review connection test results.
- Verify the configured permissions.
- Authenticate the statuses for supported capabilities.

For more information, see [Using the connectors overview page](/latest/docs/new-ui-using-connectors-overview-page).

To monitor the authentication statuses, click **View Diagnostic Report** or the **Authentication** tab. For more information, see [Using data system connector authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scans settings

Proceed to the following topics to configure the post-authentication scans settings for Amazon DynamoDB:

- [Configure discovery scans in Amazon DynamoDB](/latest/docs/configure-discovery-scans-in-amazon-dynamodb).
- [Fulfilling DSR requests for Amazon DynamoDB](/latest/docs/fulfilling-dsr-requests-for-amazon-dynamodb).

A horizontal arrangement of data in a table representing multiple attributes arranged in their respective columns.
