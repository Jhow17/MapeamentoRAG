---
title: "Connecting Amazon DynamoDB (Securiti cloud) with Securiti"
slug: "connecting-amazon-dynamodb-securiti-cloud-with-securiti"
updated: 2026-06-01T10:25:47Z
published: 2026-06-01T10:25:47Z
canonical: "helpcenter.securiti.ai/connecting-amazon-dynamodb-securiti-cloud-with-securiti"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connecting Amazon DynamoDB (Securiti cloud) with Securiti

This topic covers activation of the Amazon DynamoDB Securiti cloud connector.

> [!NOTE]
> Note
> 
> Securiti stores sensitive connector credentials in an encrypted, base-64-encoded form. For self-hosted connectors, these credentials reside on your pod and are also stored in the Securiti cloud. A credential vault can also be used to store credentials for self-hosted connectors. If a vault is being used, credentials are retrieved securely from the vault at runtime on your pod and are not stored in the cloud.
> 
> 
> 
> For Securiti Cloud-hosted connectors, credentials are securely stored only in the Securiti cloud.

## Creating an Amazon DynamoDB (Securiti cloud) data system instance

Perform the following steps to create a Data system instance for Securiti cloud connectors:

1. Log in to Securiti with your admin credentials.
2. To open the main menu, from the upper left corner of the left navigation bar, click the **Jewel** icon.
3. From the Platform Services section in the new navigation, select **Integrations**.
4. From the **Integrations** menu, choose **Monitored Data Systems.**
5. On the top right of the **Integrations** page, click **Add Integration** to create a new data system instance.
6. On the Add Integration page, click the **Securiti-Cloud**.
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

## Authenticating Amazon DynamoDB (Securiti cloud) connector

After creating an Amazon DynamoDB connector instance, in the **Authentication** tab, authenticate your connector:

1. > [!WARNING]
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
2. In the **Credentials** section, configure the following settings:

| Setting | Description |
| --- | --- |
| Access Key | Enter the Access Key ID from your AWS Management console you recorded in [obtain credentials for your DynamoDB instance](/latest/docs/obtain-credentials-for-your-dynamodb-instance), The Access Key uses a string value. See the example below. `8a7b3c9d-12e4-567f-89ab-0123456789c` |
| Row Scan Depth | > [!NOTE] > **Important** > > DynamoDB is a NoSQL data system that stores data in JSON format, not tables. > > In this case, the Row Scan Depth parameter refers to how many rows in the JSON schema you should look at during the table training process for the connector to learn all of the keys in the schema. We recommend you specify rows between the limit of 50 to 100. Enter the number of rows you wish to scan through. |
| Secret Key | Enter the Secret Key from your AWS Management console you recorded in [Obtain credentials for your DynamoDB instance](/latest/docs/obtain-credentials-for-your-dynamodb-instance), The Secret Key uses a string value, See the example below. `n3v3rU53th1s_Ke3p1tS3cur3!` |
| Region | The region field is automatically populated based on the value selected in the **Region** field in the Basic Information tab, as described above. |
| Domain | Enter the domain for your AWS instance. See the example below. `datascan-aws-instance.com` |
| (Optional) Timeout | Enter custom timeout if you want the activation session greater than Securiti default. |
3. Click **Test Connection** at the bottom of the page.

Securiti activates the connector.

### Monitoring the Overview page and authentication statuses

After authenticating the connector, in the **Overview** section:

- Review connection test results.
- Verify the configured permissions.
- Authenticate the statuses for supported capabilities.

For more information, see [Using the connectors overview page](/latest/docs/new-ui-using-connectors-overview-page).

To monitor the authentication statuses, click **View Diagnostic Report** or the **Authentication** tab. For more information, see [Using data system connector authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scans settings

Proceed to the following topics to configure the post-authentication scans settings for Amazon DynamoDB (Securiti cloud):

- [Fulfilling DSR requests for Amazon DynamoDB](/latest/docs/fulfilling-dsr-requests-for-amazon-dynamodb).

A horizontal arrangement of data in a table representing multiple attributes arranged in their respective columns.
