---
title: "Connecting the Snowflake (Self-hosted) connector with Securiti"
slug: "connecting-snowflake-self-hosted-connector-with-securiti"
updated: 2026-09-11T12:49:34Z
published: 2026-09-11T12:49:34Z
canonical: "helpcenter.securiti.ai/connecting-snowflake-self-hosted-connector-with-securiti"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connecting the Snowflake (Self-hosted) connector with Securiti

> [!NOTE]
> Note
> 
> Securiti stores sensitive connector credentials in an encrypted, base-64-encoded form. For self-hosted connectors, these credentials reside on your pod and are also stored in the Securiti cloud. A credential vault can also be used to store credentials for self-hosted connectors. If a vault is being used, credentials are retrieved securely from the vault at runtime on your pod and are not stored in the cloud.
> 
> 
> 
> For Securiti Cloud-hosted connectors, credentials are securely stored only in the Securiti cloud.

## Creating a Snowflake (Self-hosted) data system instance

Perform the following steps to create a Data system instance for self**-**hosted connectors:

1. Log in to Securiti with your admin credentials.
2. To open the main menu, from the upper left corner of the left navigation bar, click the **Jewel** icon.
3. From the Platform Services section in the new navigation, select **Integrations**.
4. From the **Integrations** menu, choose **Monitored Data Systems.**
5. On the top right of the **Integrations** page, click **Add Integration** to create a new data system instance.
6. On the Add Integration page, click the **Self-Hosted** tab.
7. From the data system list, choose your relevant data system.
8. On the **Basic Information** tab, complete the following parameters:

| Parameter | Explanation | Example |
| --- | --- | --- |
| Instance Name | Enter a convenient name for the connector Instance. | Admin-data1 |
| Description | Add a short note to explain the purpose of this instance. | To discover and monitor data sources in the production environment. |
| Hosting Location | Select your preferred **Hosting Location** and configure the Service provider settings where applicable. Securiti supports **SaaS**, or **Private Cloud**, as Hosting options for specific Data system Instances. | SaaS, Private Cloud |
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

1. Under the **Pod Configuration** section, from the **Select** **Pod** menu, choose the pod you configured earlier.
2. On the **Driver files** menu, select the driver file you previously uploaded. Click **Go to driver library** if Driver files are not uploaded.

> [!WARNING]
> **Important**
> 
> You must use the latest driver version as Snowflake deprecated the drivers older than the 3.13 version as of October 31, 2022.

For more information on the required drivers, see [Downloading JDBC drivers for SQL connectors](/latest/docs/downloading-jdbc-drivers-for-sql-connectors).

For more information on uploading drivers, see [Uploading JDBC driver files in Securiti](/latest/docs/uploading-jdbc-driver-files-in-securiti).
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
4. In the **Credentials** section, configure the following settings based on the authentication type:

| **Setting** | **Description** |
| --- | --- |
| Authentication Type | Choose one of the following Authentication types. - Basic (Deprecated) - OAuth 2.0 - Key Pair Authentication > [!WARNING] > **Important** > > - You can configure [Security Posture Scan Settings](/latest/docs/configure-general-and-access-scan-settings-for-snowflake-self-hosted) for your data system instance with the **OAuth** or **Key Pair** authentication methods. > - You can update the authentication type even after connector activation through the reconfiguration option. If a scan is paused, Securiti applies the updated authentication type automatically when the scan resumes. |
| Provider | Select the Service provider for your Snowflake Instance from the menu. The Service provider can be AWS, AZURE, GCP. |
| Warehouse | Specify the warehouse name you configured. By default, the field is automatically filled with the warehouse name. > [!NOTE] > **Note** > > You must enter the correct warehouse name and cannot leave the field blank. Otherwise, Securiti fails to establish the Connection through the JDBC proxy. |
| (Optional) Use Keyring | Enable the **Use Keyring** toggle if you want to use a keyring to manage credentials for the instance as described in [Using keyrings](/latest/docs/managing-credentials-using-keyrings). |
| From the **Keyring Type** menu, select one of the following supported keyrings. - **HashiCorp**: For more information, see [Configuring HashiCorp credential vaults](/latest/docs/hashicorp-credential-vault-configuring-hashicorp-vault-instance-in-securiti). - **CyberArk Vault**: For more information, see [Configuring CyberArk vault](/latest/docs/cyberark-credential-vault). - **Credstash**: For more information, see [Configuring Credstash](/latest/docs/configuring-credential-vaults-credstash-credential-vault) vault. - **Azure Key Vault**: For more information, see [Configuring Azure Key Vault](/latest/docs/configuring-credential-vaults-azure-key-vault). |
| From the **Keyring** menu, select the keyring configured under the selected type. |
| User Name | Enter the username for your Snowflake account. The username uses a string value. See an example below. `john` |
| Account | Enter the unique identifier listed within your Snowflake account URL. The account identifier uses a string value. See an example below. In **democo.us-west-2.snowflakecomputing.com** account URL, **democo.us-west-2** would be your unique account identifier. For private link connectivity, the account identifier uses the following format. *<account identifier>.<region>.privatelink* See an example below. **democo.us-west-2.privatelink** |
| Database | Enter the name(s) of the databases you wish to scan. For Securiti Cloud connectors, you can only enter a single Database name. You can enter a comma-separated list of names. > [!WARNING] > **Important** > > The Database name(s) are case-sensitive. Enter them exactly as they appear in the Data system. > > You can activate the Connector for all databases in the warehouse, even if a Connector was previously activated with a specific Database in the same warehouse. |
| **Basic Authentication (deprecated)** |
| **OAuth 2.0 Authentication** |
| Client ID | Enter the client ID you recorded earlier in [Acquire authentication credentials in Snowflake](/latest/docs/acquire-authentication-credentials-in-snowflake). The client ID uses a string value. See an example below. `VHMgkimnh123` |
| Client Secret | Enter the client secret you recorded earlier in [Acquire authentication credentials in Snowflake](/latest/docs/acquire-authentication-credentials-in-snowflake). The client ID uses a string value. See an example below. `a3fb2c1e5d4` |
| **Key Pair Authentication** |
| Private Key File | Upload the private key file required for the key pair Authentication method. The private key file supports **.pem** or **.p8** file extensions. |
| (Optional) Passphrase | In case you are not using a Keyring, enter the passphrase for your private key encryption. For a decrypted private key, the passphrase is not needed. > [!NOTE] > **Note** > > Passphrase is optional to use for key pair Authentication. As you provide the encrypted key, the passphrase is needed to decrypt the key and authenticate the Connector. The passphrase is not needed when the key is in plaintext. The passphrase uses a string value. See an example below. `Snowflake$Passphrase123` |
| **Additional settings for all Authentication types** |
| (Optional) Additional Connection string options | Specify any JDBC additional string connections. You can specify multiple options separated by a semicolon ';'. > [!WARNING] > **Important** > > You must add **JDBC_TREAT_DECIMAL_AS_INT=false** as an additional Connection parameter if the Database tables contain very large numbers to avoid running into errors. |
| (Optional) Enable Bernoulli Sampling | Enable the toggle to perform Bernoulli sampling on your Snowflake Database's data by randomly selecting a fraction of rows instead of processing the entire dataset. |
| (Optional) Bypass Proxy Configuration | Enable the toggle to connect your Snowflake Database to Securiti directly, bypassing any proxy server settings. |
| (Optional) Store Sample file on PCS | - **Store Sample files on PCS** toggle is disabled by default. > [!NOTE] > **Note** > > In EPod V2 deployments, Securiti disables this toggle if PCS is not configured in yourtenant. Without PCS, support for storing sample files is unavailable for structured orhybrid data systems. - Keep the toggle disabled to store table training sample files locally on the pod, ensuring they remain within your local environment. - Enable this toggle if you wish to store table training sample files in Private Cloud Storage (PCS). > [!NOTE] > **Note** > > This functionality can only be enabled if Private Cloud Storage is already configured in your tenant. In case of reconfiguring a connector, files stored prior to the reconfiguration remain in their existing location, pods or PCS, until you perform a re-scan, after which Securiti stores sample files in the newly configured location. |
5. Click **Test** **Connection** at the bottom of the page.

### Monitoring connection tests and authentication statuses

After authenticating the connector, use this section to review connection test results, verify the configured permissions, and check the authentication statuses for supported capabilities, such as Discovery scans and metadata scans.

For more information, see [Using data system connector authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scan settings

Proceed to the following topics to configure the post-authentication scan settings for the Snowflake (self-hosted)

- [Configuring discovery scans in Snowflake](/latest/docs/configure-discovery-scans-in-snowflake).
- [Configuring General scans](/latest/docs/configure-general-and-access-scan-settings-for-snowflake-self-hosted).
- [Fulfilling Snowflake DSR requests](/latest/docs/fulfilling-snowflake-dsr-requests).

- In the **Security Posture scan Settings**, apply the following settings:

> [!WARNING]
> **Important**
> 
> - Initiating the Posture scan lets you retrieve the security posture-related Configuration for this specific asset.
> - Securiti supports Posture scan for your Snowflake data systems using only Key pair and OAuth Authentication methods.
  1. Mark the **Enable Security Posture Management** checkbox.
  2. In Select Mode, mark the radio buttons for either **Monitor only** or **Monitor and remediate** modes depending on your SaaS Configuration scan policies.
  3. Configure **Hourly** and **Exclusion Time** menus to suit, and click **Run a scan now**.
- Proceed to [Configure discovery scans in Snowflake](/latest/docs/configure-discovery-scans-in-snowflake).
