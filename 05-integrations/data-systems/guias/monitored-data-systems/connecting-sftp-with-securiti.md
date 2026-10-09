---
title: "Connecting SFTP with Securiti"
slug: "connecting-sftp-with-securiti"
updated: 2026-07-15T05:18:51Z
published: 2026-07-15T05:18:51Z
canonical: "helpcenter.securiti.ai/connecting-sftp-with-securiti"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connecting SFTP with Securiti

> [!NOTE]
> Note
> 
> Securiti stores sensitive connector credentials in an encrypted, base-64-encoded form. For self-hosted connectors, these credentials reside on your pod and are also stored in the Securiti cloud. A credential vault can also be used to store credentials for self-hosted connectors. If a vault is being used, credentials are retrieved securely from the vault at runtime on your pod and are not stored in the cloud.
> 
> 
> 
> For Securiti Cloud-hosted connectors, credentials are securely stored only in the Securiti cloud.

This topic covers activation of the SFTP (Self-hosted) connector.

## Creating a SFTP Data system instance

Perform the following steps to create a Data system instance for self**-**hosted connectors:

1. Log in to Securiti with your admin credentials.
2. To open the main menu, from the upper left corner of the left navigation bar, click the **Jewel** icon.
3. From the Platform Services section in the new navigation, select **Integrations** > **Monitored Data Systems**
4. On the top right of the **Integrations** page, click **Add Integration** to create a new data system instance.
5. On the **Add** **Integration** page, click the **Self-Hosted** tab.
6. From the data system list, choose your relevant data system.
7. On the **Basic Information** tab, complete the following parameters to create an instance:

| Parameter | Explanation | Example |
| --- | --- | --- |
| Instance Name | Enter a convenient name for the connector Instance. | Admin-data1 |
| Description | Add a short note to explain the purpose of this instance. | To discover and monitor data sources in the production environment. |
8. In the **Hosting** **Location**, select the following available hosting locations:
  - **SaaS**
  - **Private Cloud**
  - **IaaS**

> [!NOTE]
> Note
> 
> For SaaS and private Cloud hosting location, below mentioned IaaS configurations must be skipped.

For the IaaS hosting location, complete the following parameters for each service provider:

**IaaS-AWS**

| Parameter | Explanation | Example |
| --- | --- | --- |
| Service Provider | Select your service provider as **AWS.** | AWS |
| Account ID | To obtain the **Account ID**, log in to your AWS Management Console, and your account ID can be found in the upper right corner of the dashboard. | `012345678901` |
| Region | Specify the AWS region where you want to host your Securiti instance. | `us-east-1` |
| Managed | Enable the **Managed** toggle to let Securiti differentiate between native and non-native assets (Dark assets). | - |

**IaaS-GCP**

| Parameter | Explanation | Example |
| --- | --- | --- |
| Service Provider | Select your service provider as **GCP**. | GCP |
| Project ID | To obtain the **Project ID**, log in to your Google Cloud Console, select your project, and the Project ID can be found on the project dashboard. | `project-123456` |
| Region | Specify the GCP region where you want to host your Securiti instance. | `us-east-1` |
| Resource Name / Instance Id | In the **Resource Name / Instance Id**, enter the instance id for BigTable or Cloud SQL (MySQL, Postgres or SQLServer) instance, bucket name for cloud storage or dataset name for BigQuery. | `my-bigtable-instance` |
| Managed | Enable the **Managed** toggle to let Securiti differentiate between native and non-native assets (Dark assets). | - |

**IaaS-OCI**

| Parameter | Explanation | Example |
| --- | --- | --- |
| Service Provider | Select your service provider as **OCI**. | OCI |
| Tenancy Id | To obtain the **Tenancy Id**, log in to your OCI Console, navigate to your tenancy details, and the Tenancy Id can be found in the tenancy information. | `ocid1.tenancy.oc1..aaaaaaaa` |
| Account Id | Similar to the Tenancy ID, the **Account ID** can be found in the tenancy information. | `ocid1.oc1..aaaaaaaa` |
| Region | Specify the OCI region where you want to host your Securiti instance. | `us-luke-1` |
| Managed | Enable the **Managed** toggle to let Securiti differentiate between native and non-native assets (Dark assets). | - |

**IaaS-Azure**

| Parameter | Explanation | Example |
| --- | --- | --- |
| Service Provider | Select your Service provider as **Azure**. | Azure |
| Subscription ID | Enter the subscription id for your Azure resource. | - |
| Resource Group | Enter the resource group for your Azure resource. | - |
| Server / Storage Account Name | In the **Server / Storage Account Name**, enter the server name for SQL Server or Cosmos DB, or the storage account name for Blob Storage/File Share. | - |
| Region | Specify the AZURE region where you want to host your Securiti instance. | `us-luke-1` |
| Managed | Enable the **Managed** toggle to let Securiti differentiate between native and non-native assets (Dark assets). | - |

1. After configuring the hosting location and service provider information, continue by completing the following parameters:

| Parameter | Explanation | Example |
| --- | --- | --- |
| Country | Select the country from the dropdown where the data source or resource is located. | America, Canada |
| (Optional) State | Select the state or region from the dropdown within the chosen country. | Alberta |
| (Optional) City | Enter the city where the data source or resource is located. | Calgary |
| Owners | Choose the primary owner for the Instance. By default, you are the primary owner. | John.doe@securiti.ai |
| (Optional) Additional owners can be added after creating an instance by enabling the **Add** **Co-owner** tab on the Basic Information page. From the dropdown, select users to add as additional owners. | Alex.doe@securiti.ai |
| (Optional) Enable the toggle for **Send Notification to all Owners** to notify owners. |  |
2. At the bottom of the page, click **Create and Continue**.
3. It redirects you to the **Authentication** page.

## Authenticating SFTP connector

After creating SFTP (Self-hosted) connector instance, in the **Authentication** tab, authenticate your connector:

- Under the **Pod Configuration** section, from the **Select** **Pod** menu, choose the pod you configured earlier.
- > [!WARNING]
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
- In the **Credentials** section, configure the following settings:

| Setting | Authentication Method | Description |
| --- | --- | --- |
| Authentication Type | N/A | Select from the supported authentication types: - ***Password Based*** - ***Key Based*** |
| Host | - Password Based - Key Based | Enter your server IP address in xxx.xxx.xxx.xxx format. See the example below. `192.158.1.38` |
| Port | - Password Based - Key Based | Enter the port you acquired in [Acquire authentication credentials in SFTP](/latest/docs/acquire-authentication-credentials-in-sftp). See the example below. `22` |
| Path | - Password Based - Key Based | Enter the SFTP server path of the files you want to load. See the example below. `/Document` |
| (Optional) Use Keyring | - Password Based - Key Based | Enable the **Use Keyring** toggle if you have used a Credential vault to store the Keyring. For more information, see [Using keyrings in Securiti](/latest/docs/creating-keyrings). |
| From the **Keyring Type** dropdown, select one of the following supported keyrings. - **HashiCorp**: For more information, see [HashiCorp credential vault](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault). - **CredStash**: For more information, see [CredStash credential vault](/latest/docs/configuring-credential-vaults-credstash-credential-vault). - **AWS Secret Manager**: For more information, see [AWS Secrets Manager credential vault](/latest/docs/configuring-credential-vaults-aws-secrets-manager-credential-vault). - **Basic.** |
| From the **Keyring** dropdown, select the keyring configured under the selected type. |
| Username | - Password Based - Key Based | Enter the username that you acquired in [Acquire authentication credentials in SFTP](/latest/docs/acquire-authentication-credentials-in-sftp). |
| Password | Password Based | If not using keyring, enter the Password for SFTP you acquired in [Acquire authentication credentials in SFTP](/latest/docs/acquire-authentication-credentials-in-sftp). |
| Key | Key Based | If not using keyring, upload the key file for SFTP. |
- Click **Test** **Connection** at the bottom of the page.

Securiti activates the connector.

### Monitoring the Overview page and authentication statuses

After authenticating the connector, in the **Overview** section:

For more information, see [Using the connectors overview page](/latest/docs/new-ui-using-connectors-overview-page).

To monitor the authentication statuses, click **View Diagnostic Report** or the **Authentication** tab. For more information, see [Using data system connector authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scans settings

Proceed to the following topics to configure the post-authentication scans settings for the SFTP (Self-hosted):
  - Review connection test results.
  - Verify the configured permissions.
  - Authenticate the statuses for supported capabilities.
- [Configuring discovery scans in SFTP](/latest/docs/configuring-discovery-scans-in-sftp).

**Additional resources**

- [Fulfilling DSR requests for SFTP](/latest/docs/fulfilling-dsr-requests-for-sftp).

A collection of organized data or repositories and their corresponding management software, which could be IaaS, SaaS, or SQL. Data systems are configured in Securiti so that it can help you protect sensitive data and also locate personal data for data subjects who submit DSR requests. Data systems can be monitored, un-monitored, or user-defined. For each monitored or user-defined data system, you configure a connector that Securiti uses to interact with the data system.

A secure container for storing cryptographic keys or login credentials. See Managing keyrings, for more information.
