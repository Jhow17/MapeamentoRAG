---
title: "Connect Microsoft Dynamics 365 CRM Suite (Self-hosted) connector with Securiti"
slug: "connect-microsoft-dynamics-365-crm-suite-self-hosted-with-securiti"
updated: 2026-08-10T12:28:09Z
published: 2026-08-10T12:28:09Z
canonical: "helpcenter.securiti.ai/connect-microsoft-dynamics-365-crm-suite-self-hosted-with-securiti"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connect Microsoft Dynamics 365 CRM Suite (Self-hosted) connector with Securiti

> [!NOTE]
> Note
> 
> Securiti stores sensitive connector credentials in an encrypted, base-64-encoded form. For self-hosted connectors, these credentials reside on your pod and are also stored in the Securiti cloud. A credential vault can also be used to store credentials for self-hosted connectors. If a vault is being used, credentials are retrieved securely from the vault at runtime on your pod and are not stored in the cloud.
> 
> 
> 
> For Securiti Cloud-hosted connectors, credentials are securely stored only in the Securiti cloud.

> [!WARNING]
> **Important**
> 
> You must have the Basic User role in the Microsoft Dynamics 365 CRM (Suite) account and an Application Administrator role in Azure before proceeding with the Connector Activation.

This topic covers activation of the Microsoft Dynamics 365 CRM Suite (Self-hosted) connector.

## Creating a Microsoft Dynamics 365 CRM data system connector instance

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

## Authenticating the Microsoft Dynamics 365 CRM Suite (Self-hosted) connector

After creating a Microsoft Dynamics 365 CRM Suite connector instance, in the **Authentication** tab, authenticate your connector:

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
3. In the **Cloud** **Configuration** section, configure the following settings:

| Setting | Description |
| --- | --- |
| Account | Enter your Account ID. The Account ID uses a string value. See the example below. `org123abc45` |
| Tenant ID (or Domain) | Enter your Tenant ID or Domain that you recorded in [Acquire authentication credentials in Microsoft Dynamics 365 CRM Suite (Self-hosted)](/latest/docs/acquire-authentication-credentials-in-microsoft-dynamics-365-crm-self-hosted). - Domain is usually your company domain. See the example below. `democo.org` - Tenant ID follows the string format. See the example below. `0a1b01a1-aob1b-1a1a-b0b0-101010ab1a01` |
| Region | Specify your region relevant to your Dynamics 365 Instance. See the example below. `North America` |
4. Under the **Credentials** section, in the **Authentication** tab, apply the following settings that you acquired in [Acquire authentication credentials in Microsoft Dynamics 365 CRM Suite (Self-hosted)](/latest/docs/acquire-authentication-credentials-in-microsoft-dynamics-365-crm-self-hosted):

| Setting | Description |
| --- | --- |
| (Optional) Use Keyring | Enable the **Use Keyring** toggle if you want to use a keyring to manage credentials for the instance as described in [Using keyrings](/latest/docs/managing-credentials-using-keyrings). |
| From the **Keyring Type** dropdown, select one of the following supported keyrings. - **HashiCorp**: For more information, see [Configuring HashiCorp credential vaults](/latest/docs/hashicorp-credential-vault-configuring-hashicorp-vault-instance-in-securiti). |
| From the **Keyring** dropdown, select the keyring configured under the selected type. |
| Client ID | Enter your client ID for Azure Active Directory. The client ID uses a string value. See the example below. `c12a345b-678c-90d1-2ef3-45678abc9012` |
| Client Secret | Enter the value for the client secret you acquired in step 1(f) of [Acquire authentication credentials in Microsoft Dynamics 365 CRM Suite (Self-hosted)](/latest/docs/acquire-authentication-credentials-in-microsoft-dynamics-365-crm-self-hosted). The client secret uses an alphanumeric string value. See the example below. `AbCdEfGhIjKlMrStUvWxYz1234567890` |
| Additional Connection String Options | Specify any additional JDBC Connection strings. You can specify multiple values separated by a semicolon (;). |
5. Click **Test** **Connection** at the bottom of the page.

Securiti redirects you to the account login page.

![login_page.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-36888549-8f9c-159f-5068-817980e0522b.png)

Enter the Credentials of the user with the role you assigned (Basic User or Custom security role) in the Microsoft Dynamics 365 CRM account and an Application Administrator role in Azure.

Securiti activates the Connector.

### Monitoring the Overview page and authentication statuses

After authenticating the connector, in the **Overview** section:

- Review connection test results.
- Verify the configured permissions.
- Verify the statuses for supported capabilities.

For more information, see [Using the connectors overview page](/latest/docs/new-ui-using-connectors-overview-page).

To monitor the authentication statuses, click **View Diagnostic Report** or the **Authentication** tab. For more information, see [Using data system connector authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scans settings

Proceed to the following topics to configure the post-authentication scan settings for the Microsoft Dynamics 365 CRM Suite (Self-hosted):

- [Configure discovery scans in Microsoft Dynamics 365 CRM Suite (Self-hosted)](/latest/docs/configure-discovery-scans-in-microsoft-dynamics-365-crm-suite-self-hosted).

**Additional resources**

- [Fulfilling DSR requests for Microsoft Dynamics 365 CRM Suite (Self-hosted)](/latest/docs/fulfilling-dsr-requests-for-microsoft-dynamics-365-crm-suite-self-hosted).
