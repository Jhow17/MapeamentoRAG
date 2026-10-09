---
title: "Connecting the Snowflake (Securiti Cloud) connector with Securiti"
slug: "connecting-snowflake-cloud-connector-with-securiti"
updated: 2026-08-10T13:01:41Z
published: 2026-08-10T13:01:41Z
canonical: "helpcenter.securiti.ai/connecting-snowflake-cloud-connector-with-securiti"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connecting the Snowflake (Securiti Cloud) connector with Securiti

> [!NOTE]
> Note
> 
> Securiti stores sensitive connector credentials in an encrypted, base-64-encoded form. For self-hosted connectors, these credentials reside on your pod and are also stored in the Securiti cloud. A credential vault can also be used to store credentials for self-hosted connectors. If a vault is being used, credentials are retrieved securely from the vault at runtime on your pod and are not stored in the cloud.
> 
> 
> 
> For Securiti Cloud-hosted connectors, credentials are securely stored only in the Securiti cloud.

## Creating a data system instance

Perform the following steps to create a Data system instance for Securiti cloud connectors:

1. Log in to Securiti with your admin credentials.
2. To open the main menu, from the upper left corner of the left navigation bar, click the **Jewel** icon.
3. From the Platform Services section in the new navigation, select **Integrations**.
4. From the **Integrations** menu, choose **Monitored Data Systems.**
5. On the top right of the **Integrations** page, click **Add Integration** to create a new data system instance.
6. On the Add Integration page, click the **Securiti-Cloud** tab.
7. From the data system list, choose your relevant data system.
8. On the **Basic Information** tab, complete the following parameters:

| Parameter | Explanation | Example |
| --- | --- | --- |
| Instance Name | Enter a convenient name for the connector Instance. | Admin-data1 |
| Description | Add a short note to explain the purpose of this instance. | To discover and monitor data sources in the production environment. |
| Hosting Location | Select your preferred **Hosting Location** and configure the Service provider settings where applicable. Securiti supports **SaaS**, **or** **Private Cloud**, as Hosting options for specific Data system Instances. | SaaS, Private Cloud |
| Country | Select the **country** from the dropdown where the data source or resource is located. | America, Canada |
| (Optional) State | Select the **state** or region from the dropdown within the chosen country. | Alberta |
| (Optional) City | Enter the **city** where the data source or resource is located. | Calgary |
| Owners | Choose **Primary** **Owner** for the Instance. By default, you are the primary owner. | John.doe@securiti.ai |
| (optional) Additional owners can be added after creating an instance by enabling the **Add** **Co-owner** tab on the Basic Information page. From the dropdown, select users to add as additional owners. | Alex.doe@securiti.ai |
| (optional) Enable the toggle for **Send Notification to all Owners** to notify owners. |  |
9. At the Bottom of the page, click **Create and Continue**.

It redirects you to the **Authentication** page.

> **Note**
> 
> Securiti lets you connect to multiple warehouses using the same account.

## Authenticating the data system instance

After creating a Snowflake data system instance, in the **Authentication** tab, authenticate your connector:

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
2. In the **Credentials** section, configure the following settings based on the authentication type:

| **Setting** | **Description** |
| --- | --- |
| Authentication Type | Choose one of the following Authentication types. - Basic (Deprecated) - OAuth 2.0 - Key Pair Authentication |
| Provider | Select the Service provider for your Snowflake Instance from the menu. The Service provider can be AWS, AZURE, GCP. |
| Warehouse | Specify the warehouse name you configured. By default, the field is automatically filled with the warehouse name. > [!NOTE] > **Note** > > You must enter the correct warehouse name and cannot leave the field blank. Otherwise, Securiti fails to establish the Connection through the JDBC proxy. |
| User Name | Enter the username for your Snowflake account. The username uses a string value. See the example below. *john* |
| Account | Enter the unique identifier listed within your Snowflake account URL. The account identifier uses a string value. See an example below. In **democo.us-west-2.snowflakecomputing.com** account URL, **democo.us-west-2** would be your unique account identifier. For private link connectivity, the account identifier uses the following format. *<account identifier>.<region>.privatelink* See an example below. **democo.us-west-2.privatelink** |
| Database | Enter the name(s) of the databases you wish to scan. For Securiti Cloud connectors, you can only enter a single Database name. > [!WARNING] > **Important** > > The Database name(s) are case-sensitive. Enter them exactly as they appear in the Data system. |
| **Basic Authentication (deprecated)** |
| **OAuth 2.0 Authentication** |
| Client ID | Enter the client ID you recorded earlier in [Acquire authentication credentials in Snowflake](/latest/docs/acquire-authentication-credentials-in-snowflake). The client ID uses a string value. See an example below. *VHMgkimnh123VHMgkimnh123* |
| Client Secret | Enter the client secret you recorded earlier in [Acquire authentication credentials in Snowflake](/latest/docs/acquire-authentication-credentials-in-snowflake). The client ID uses a string value. See an example below. *a3fb2c1e5d4a3fb2c1e5d4* |
| **Key Pair Authentication** |
| Private Key File | Upload the private key file required for the key pair Authentication method. The private key file uses a **.pem** file extension. See an example below. *private-key.pem* |
| (Optional) Passphrase | Enter the passphrase for your private key encryption. For decrypted private key, passphrase is not needed. > [!NOTE] > **Note** > > Passphrase is optional to use for key pair Authentication. As you provide the encrypted key the passphrase is needed to decrypt the key and authenticate the Connector. Passphrase is not needed when the key is in plaintext. The passphrase uses a string value. See an example below. *Snowflake$Passphrase123* |
| **Additional settings for all Authentication types** |
| (Optional) Additional Connection string options | Specify any additional JDBC string connections. You can specify multiple options separated by a semicolon ';'. |
| (Optional) Enable Bernoulli Sampling | Enable the toggle to perform Bernoulli sampling on your Snowflake Database's data, by randomly selecting a fraction of rows instead of processing the entire dataset. |
| (Optional) Include Views | Enable the toggle to include views as a part of the scan. > [!NOTE] > **Note** > > Including views may take a long time to finish Learning and increase the load on the Database server. |
| (Optional) Enable Random Sampling | Enable the toggle to perform a random sampling of datasets in case of large datasets. |
3. Click **Authenticate & Activate Connector**.

> [!NOTE]
> **Note**
> 
> We assume, you have the required drivers before Activation. Otherwise, Securiti shows an error message reminding you to upload drivers.

Securiti activates the Connector.

### Monitoring connection tests and authentication statuses

After authenticating the connector, use this section to review connection test results, verify the configured permissions, and check the authentication statuses for supported capabilities, such as Discovery scans and metadata scans.

For more information, see [Using data system connector authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scan settings

Proceed to the following topics to configure the post-authentication scan settings for the Snowflake (self-hosted):

- [Initiate Snowflake data scanning](/latest/docs/initiate-snowflake-data-scanning).
- [Configuring general and access scan settings](/latest/docs/configure-general-and-access-scan-settings-for-snowflake-securiti-cloud).
- [Fulfilling Snowflake DSR requests](/latest/docs/fulfilling-snowflake-dsr-requests).
