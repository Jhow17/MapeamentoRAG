---
title: "Connecting LDAP Active Directory with Securiti"
slug: "connecting-ldap-active-directory-with-securiti"
updated: 2026-07-10T07:37:08Z
published: 2026-07-10T07:37:08Z
canonical: "helpcenter.securiti.ai/connecting-ldap-active-directory-with-securiti"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connecting LDAP Active Directory with Securiti

> [!NOTE]
> Note
> 
> Securiti stores sensitive connector credentials in an encrypted, base-64-encoded form. For self-hosted connectors, these credentials reside on your pod and are also stored in the Securiti cloud. A credential vault can also be used to store credentials for self-hosted connectors. If a vault is being used, credentials are retrieved securely from the vault at runtime on your pod and are not stored in the cloud.
> 
> 
> 
> For Securiti Cloud-hosted connectors, credentials are securely stored only in the Securiti cloud.

This topic covers activation of the LDAP Active Directory (Self-hosted) connector.

## Creating a LDAP Active Directory data system connector instance

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
9. In the **Hosting** **Location**, select from the following available hosting locations and service providers:

**SaaS/Privatecloud**

| Parameter | Explanation | Example |
| --- | --- | --- |
| Hosting Location | Select your preferred hosting location as **SaaS** or **Private Cloud**. | SaaS, Private Cloud |

**IaaS-AWS**

| Parameter | Explanation | Example |
| --- | --- | --- |
| Hosting Location | Select your preferred **Hosting Location** as **IaaS** | IaaS |
| Service Provider | Select your **Service provider** as **AWS**. | AWS |
| Account ID | Enter the **Account ID** for your AWS account. | `012345678901` |
| Region | From the **Region**, select your preferred region for the AWS account. | `us-east-1` |
| Managed | Enable the **Managed** toggle to let Securiti differentiate between native and non-native assets (Dark assets) | - |

**IaaS-GCP**

| Parameter | Explanation | Example |
| --- | --- | --- |
| Hosting Location | Select your preferred **Hosting Location** as **IaaS** | IaaS |
| Service Provider | Select your **Service provider** as **GCP**. | GCP |
| Project ID | Enter the **Project ID** for your GCP account. | `project-123456` |
| Region | From the **Region**, select your preferred region for the GCP account. | `us-east-1` |
| Resource Name / Instance Id | In the **Resource Name / Instance Id**, enter the instance id for BigTable or Cloud SQL (MySQL, Postgres or SQLServer) instance, bucket name for cloud storage or dataset name for BigQuery | `my-bigtable-instance` |
| Managed | Enable the **Managed** toggle to let Securiti differentiate between native and non-native assets (Dark assets) | - |

**IaaS-OCI**

| Parameter | Explanation | Example |
| --- | --- | --- |
| Hosting Location | Select your preferred **Hosting Location** as **IaaS** | IaaS |
| Service Provider | Select your **Service provider** as **OCI**. | OCI |
| Tenancy Id | Enter the tenancy id for your OCI account to identify the root container. | `ocid1.tenancy.oc1..aaaaaaaa` |
| Account Id | Enter the account id or OCID for your OCI account to identify a specific resource. | `ocid1.oc1..aaaaaaaa` |
| Region | From the **Region**, select your preferred region for the OCI account. | `us-luke-1` |
| Managed | Enable the **Managed** toggle to let Securiti differentiate between native and non-native assets (Dark assets) | - |

**IaaS-Azure**

| Parameter | Explanation | Example |
| --- | --- | --- |
| Hosting Location | Select your preferred **Hosting Location** as **IaaS** | IaaS |
| Service Provider | Select your **Service provider** as **Azure**. | Azure |
| Subscription ID | Enter the subscription id for your Azure resource. | - |
| Resource Group | Enter the resource group for your Azure resource. | - |
| Server / Storage Account Name | In the **Server / Storage Account Name**, enter the server name for SQL Server or Cosmos DB, or the storage account name for Blob Storage/File Share | - |
| Region | From the **Region**, select your preferred region for the OCI account. | `us-luke-1` |
| Managed | Enable the **Managed** toggle to let Securiti differentiate between native and non-native assets (Dark assets) | - |

1. After configuring the hosting location, continue by completing the following parameters:

| Parameter | Explanation | Example |
| --- | --- | --- |
| Country | Select the country from the dropdown where the data source or resource is located. | America, Canada |
| (Optional) State | Select the state or region from the dropdown within the chosen country. | Alberta |
| (Optional) City | Enter the city where the data source or resource is located. | Calgary |
| Owners | Choose the primary owner for the Instance. By default, you are the primary owner. | John.doe@securiti.ai |
| (optional) Additional owners can be added after creating an instance by enabling the **Add** **Co-owner** tab on the Basic Information page. From the dropdown, select users to add as additional owners. | Alex.doe@securiti.ai |
| (optional) Enable the toggle for **Send Notification to all Owners** to notify owners. |  |
2. At the Bottom of the page, click **Create and Continue**.
3. It redirects you to the **Authentication** page.

## Authenticating LDAP Active Directory connector

After creating a LDAP Active Directory (Self-hosted) connector instance, in the **Authentication** tab, authenticate your connector:

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

| Setting | Description |
| --- | --- |
| BaseDN | The BaseDN serves as a login credential that specifies the starting point from which the scanning process will start. See the example below. `BaseDN:dc=demo, dc=com` would set the initial scan point to occur from the "Admin" user. |
| Host | Enter the IP Address or Host Name and Port Address for your LDAP Active Directory you acquired in [Obtain LDAP configuration information](/latest/docs/obtain-ldap-configuration-information). See the example below. `192.1.2.1:1212` |
| (Optional) Use Keyring | Enable the **Use Keyring** toggle if you have used a Credential vault to store the Keyring. |
| From the **Keyring Type** dropdown, select one of the following supported keyrings. - **Credstash**: For more information, see [CredStash credential vault](/latest/docs/configuring-credential-vaults-credstash-credential-vault). - **Basic.** For more information on credential vaults, see [Configuring credential vaults](/latest/docs/managing-credentials-configuring-credential-vaults). |
| From the **Keyring** dropdown, select the keyring configured under the selected type. For more information on keyrings, see [Managing keyrings](/v1/docs/managingcredentials-using-keyrings). |
| User | If not using keyring, enter the username for the account with administrative rights over your LDAP Active Directory you acquired in [Obtain LDAP configuration information](/latest/docs/obtain-ldap-configuration-information). See the example below. `cn=Administrator` |
| Password | If not using keyring, enter the password for the account that has administrative rights over your LDAP Active Directory you acquired in [Obtain LDAP configuration information](/latest/docs/obtain-ldap-configuration-information). |
| Valid LDAP Filter | Enter a search filter in the LDAP Active Directory if you wish to search for a specific kind of information. if you wish to sync only Person-relevant information from your organization's Active Directory, enter `(&amp;(objectClass=organizationalPerson))`*.* |
| Server Name | Enter the name of the server where the Active Directory is hosted as you acquired earlier in [Obtain LDAP configuration information](/latest/docs/obtain-ldap-configuration-information). |
| (Optional) Insecure Skip Verify | Toggle this setting to enable or disable verification prompts if the connection to the Active Directory is on an insecure network or through an insecure internet Connection. Insecure Skip Verify uses a boolean value, you can set it as true or false. |
| (Optional) Use SSL | Toggle this setting to enable or disable SSL encryption on incoming and outgoing connections between the Securiti connector and your Active Directory. Use SSL uses a boolean value, you can set it as true or false. |
| (Optional) Skip TLS | Toggle this setting to enable or disable server Certificate checks every time the Connector interfaces with the Active Directory for its contents. Skip TLS uses a boolean value, you can set it as true or false. |
4. Click **Test** **Connection** at the bottom of the page.

Securiti activates the connector.

### Monitoring the Overview page and authentication statuses

After authenticating the connector, in the **Overview** section:

- Review connection test results.
- Verify the configured permissions.
- Authenticate the statuses for supported capabilities.

For more information, see [Using the connectors overview page](/latest/docs/new-ui-using-connectors-overview-page).

To monitor the authentication statuses, click **View Diagnostic Report** or the **Authentication** tab. For more information, see [Using data system connector authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scans settings

Proceed to the following topics to configure the post-authentication scans settings for the LDAP Active Directory (Self-hosted):

- [Configure discovery scans in LDAP Active Directory](/latest/docs/configure-discovery-scans-in-ldap-active-directory).

**Additional resources**

- [Table training for structured and hybrid data systems](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems).

A secure container for storing cryptographic keys or login credentials. See Managing keyrings, for more information.
