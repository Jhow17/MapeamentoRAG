---
title: "Connecting Oracle Object Storage connector with Securiti"
slug: "connect-oracle-object-storage-connector-with-securiti"
updated: 2026-08-11T06:11:20Z
published: 2026-08-11T06:11:20Z
canonical: "helpcenter.securiti.ai/connect-oracle-object-storage-connector-with-securiti"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connecting Oracle Object Storage connector with Securiti

This topic covers setup of the Oracle Object Storage (Self-hosted) Connector.

## Creating an Oracle Object Storage data system connector instance

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

## Authenticating Oracle Object Storage (Self-hosted) connector

After creating an Oracle Object Storage connector instance, in the **Authentication** tab, authenticate your connector.

Apply the following settings using Credentials obtained in [Obtain authentication credentials in Oracle Object Storage](/latest/docs/obtain-authentication-credentials-oracle-object-storage).

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

| **Setting** | **Description** |
| --- | --- |
| Oracle Tenant ID | Enter the OCID within your Oracle Tenancy details you acquired in step 4 of [Obtain authentication credentials](/latest/docs/obtain-authentication-credentials-oracle-object-storage). The Oracle Tenant ID uses string value. See the example below. `ocid1.user.oc1..aaaaaaaafuzv6u3xrs7ftjzwcIwo63vivivncbbgnww2w5\|5eh77ckoyrpca` |
| User ID | Enter the OCID for your saved User account you acquired in step 4 of [Obtain authentication credentials](/latest/docs/obtain-authentication-credentials-oracle-object-storage). The Oracle Tenant ID uses string value. See the example below. `ocid1.user.oc1..aaaaaaaak7ph666xd3njwot7qhlpwaccivtf4hic2imhpbi2qgqtizffzigq` |
| Compartment ID | Enter the Compartment ID you acquired in step 6 of [Obtain authentication credentials](/latest/docs/obtain-authentication-credentials-oracle-object-storage). The Compartment ID uses string value. See the example below. `ocid1.compartment.oc1..aaaaaaaaguayv2l4gtiu553yhv624dk7txjalskjv7hi4ewgwxh3j2pld46q` |
| Finger Print | Enter the fingerprint generated (and saved to the user’s account as a public key). |
| Region | Enter the regional code for your Oracle Cloud Instance. See the example below. `us-phoenix-1` |
| Pass Phrase | Enter the Passphrase you set while generating the private key as part of the OpenSSL commands. See the example below. `YourSecurePassphrase654321.!` |
| Bucket | Enter the directory path for Oracle to scan. See the example below `bucket-john-data-a,cspm-bucket` |
| Include SubCompartment | (Optional) Mark the checkbox to enable the scan for root buckets. |
| Credentials | Upload your private keys. |
| (Optional) Use Keyring | Enable the **Use Keyring** toggle if you want to use a keyring to manage credentials for the instance as described in [Using keyrings](/latest/docs/managing-credentials-using-keyrings). |
| From the **Keyring Type** dropdown, select one of the following supported keyrings. - **HashiCorp**: For more information, see [Configuring HashiCorp credential vaults](/latest/docs/hashicorp-credential-vault-configuring-hashicorp-vault-instance-in-securiti). - **Credstash**: For more information, see [Configuring Credstash](/latest/docs/configuring-credential-vaults-credstash-credential-vault) vault. |
| From the **Keyring** dropdown, select the keyring configured under the selected type. |
| Evaluate Data system size | Mark the checkbox to evaluate the Data system size at the time of Authentication. It computes the storage space consumption data for Oracle buckets. Securiti calculates resource size on a weekly basis to keep the data size value up to date. |

> [!WARNING]
> **Important**
> 
> In the case where both *Compartment ID* and *Bucket Name* are provided, the latter takes priority. When there's only *Compartment ID*, the Connector scans for root buckets and any sub-compartment buckets if the *Include SubCompartment* toggle is on. Lastly, the Connector only scans for root buckets if there isn't any bucket or a Compartment ID (provided *Include SubCompartment* toggle is on).
4. Click **Test** **Connection** at the bottom of the page.

### Monitoring the overview page and authentication statuses

After authenticating the connector, in the **Overview** section:

- Review connection test results.
- Verify the configured permissions.
- Verify the statuses for supported capabilities.

For more information, see [Using the connectors overview page](/latest/docs/new-ui-using-connectors-overview-page).

To monitor the authentication statuses, click **View Diagnostic Report** or the **Authentication** tab. For more information, see [Using data system connector authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scan settings

Proceed to the following topics to configure the post-authentication scan settings for the Oracle Object Storage (self-hosted):

- [Configuring discovery scans in Oracle Object Storage](/latest/docs/configuring-discovery-scans-in-oracle-object-storage).

**Additional resources**

- [Configuring Oracle Object Storage Scanning](/latest/docs/configuring-oracle-object-storage-scanning).
- [Fulfilling DSR requests for Oracle Object Storage](/latest/docs/fulfilling-dsr-requests-for-oracle-object-storage).
