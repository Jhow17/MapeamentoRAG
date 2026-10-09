---
title: "Connecting Amazon Athena with Securiti"
slug: "connecting-amazon-athena-with-securiti"
updated: 2026-07-01T15:34:55Z
published: 2026-07-01T15:34:55Z
canonical: "helpcenter.securiti.ai/connecting-amazon-athena-with-securiti"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connecting Amazon Athena with Securiti

This topic covers activation of the Amazon Athena (self-hosted) connector.

## Creating an Amazon Athena data system connector instance

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

## Authenticating the Amazon Athena connector

After creating an Amazon Athena connector instance, in the **Authentication** tab, authenticate your connector:

1. Under the **Pod Configuration** section, from the **Select** **Pod** menu, choose the pod you configured earlier.
2. Under the **Drivers** section, from the **Driver** menu, choose the latest driver.
3. > [!WARNING]
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
4. In the **Credentials** section, configure the following settings:

| Parameter | Description |
| --- | --- |
| Authentication Type | Choose **Basic** or **IAM Roles** from the menu. For IAM Roles only: - Enter the AWS account and the IAM role information you recorded from your AWS Management Console. |
| AWS Region | The region field is automatically populated based on the value selected in the **Region** field in the **Basic Information** tab, as described above. The pre-populated value is according to the below region to location mapping: - `us-east-1: northernvirginia` - `us-east-2: ohio` - `us-west-1: northerncalifornia` - `us-west-2: oregon` - `us-gov-east-1: usgov-east` - `us-gov-west-1: usgov-west` - `af-south-1: capetown` - `ap-east-1: hongkong` - `ap-south-1: mumbai` - `ap-south-2: hyderabad` - `ap-northeast-3: osaka` - `ap-northeast-2: seoul` - `ap-southeast-1: singapore` - `ap-southeast-2: sydney` - `ap-southeast-3: jakarta` - `ap-southeast-4: melbourne` - `ap-southeast-5: malaysia` - `ap-northeast-1: tokyo` - `ca-central-1: centralcanada` - `ca-west-1: calgary` - `cn-north-1: beijing` - `cn-northwest-1: ningxia` - `eu-central-1: frankfurt` - `eu-central-2: zurich` - `eu-west-1: ireland` - `eu-west-2: london` - `eu-west-3: paris` - `eu-south-1: milan` - `eu-south-2: spain` - `eu-north-1: stockholm` - `il-central-1: telaviv` - `me-south-1: bahrain` - `me-central-1: uae` - `mx-central-1: mexico` - `sa-east-1: saopaulo` |
| AWS Access Key | Enter your account access key with the appropriate Athena permissions, acquired in [Grant permissions and acquire authentication credentials in Amazon Athena](/latest/docs/grant-permissions-and-acquire-authentication-credentials-in-amazon-athena). See an example below. *AKIAIOSFODNN7EXAMPLE* |
| AWS Secret Key | Enter your account secret key with the appropriate Athena permissions, acquired in [Grant permissions and acquire authentication credentials in Amazon Athena](/latest/docs/grant-permissions-and-acquire-authentication-credentials-in-amazon-athena). See an example below. *wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY* |
| S3 Output Location | Enter the S3 bucket bath where query and calculation results are stored. Enter the path you recorded in [Grant permissions and acquire authentication credentials in Amazon Athena](/latest/docs/grant-permissions-and-acquire-authentication-credentials-in-amazon-athena). For example, the output can be stored in a specified S3 bucket path like `s3://path/to/query/bucket/`. > [!NOTE] > **Note** > > When using a JDBC connection with AWS Athena, query results are stored in a specified **S3 output location**. A periodic job, called **Access Verification**, runs regularly to execute specific queries that verify access permissions using the provided credentials. This service also creates some data files even when no scan is running. |
| Use Keyring | You can Enable the **Use Keyring** toggle if you want to use a keyring to manage credentials for the instance as described in [Using keyrings](/latest/docs/managing-credentials-using-keyrings). |
| Keyring Type (Basic auth type) | Enable the toggle to select keyring type, **AWS Secret Manager** credential vault that you have used previously to store keyring(s). See [AWS Secrets Manager credential vault](/latest/docs/configuring-credential-vaults-aws-secrets-manager-credential-vault) for more information. |
| Keyring (Basic auth type) | Specify your keyring here. |
| Workgroup | (Optional) enter the workgroup to enable data access control and costs associated with running queries. |
| Include Views | (Optional) Enable this toggle to include views as a part of the scan. > [!NOTE] > **Note** > > Including views may take a long time to finish learning and increase the load on the database server. |
| (Optional) Store Sample file on PCS | - **Store Sample files on PCS** toggle is disabled by default. > [!NOTE] > **Note** > > In EPod V2 deployments, Securiti disables this toggle if PCS is not configured in yourtenant. Without PCS, support for storing sample files is unavailable for structured orhybrid data systems. - Keep the toggle disabled to store table training sample files locally on the pod, ensuring they remain within your local environment. - Enable this toggle if you wish to store table training sample files in Private Cloud Storage (PCS). > [!NOTE] > **Note** > > This functionality can only be enabled if Private Cloud Storage is already configured in your tenant. In case of reconfiguring a connector, files stored prior to the reconfiguration remain in their existing location, pods or PCS, until you perform a re-scan, after which Securiti stores sample files in the newly configured location. |
5. Click **Test** **Connection** at the bottom of the page

Securiti activates the connector.

### Monitoring the Overview page and authentication statuses

After authenticating the connector, in the **Overview** section:

- Review connection test results.
- Verify the configured permissions.
- Authenticate the statuses for supported capabilities.

For more information, see [Using the connectors overview page](/latest/docs/new-ui-using-connectors-overview-page).

To monitor the authentication statuses, click **View Diagnostic Report** or the **Authentication** tab. For more information, see [Using data system connector authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scans settings

Proceed to the following topics to configure the post-authentication scans settings for the Amazon Athena:

- [Configure discovery scans in Amazon Athena](/latest/docs/configure-discovery-scans-in-amazon-athena).
- [Fulfilling DSR requests in Amazon Athena](/latest/docs/fulfilling-dsr-requests-for-amazon-athena).
