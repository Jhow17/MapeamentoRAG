---
title: "Connecting the Workday (Self-hosted) connector in Securiti"
slug: "connecting-the-workday-self-hosted-connector-in-securiti"
updated: 2026-07-31T14:08:45Z
published: 2026-07-31T14:08:45Z
canonical: "helpcenter.securiti.ai/connecting-the-workday-self-hosted-connector-in-securiti"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connecting the Workday (Self-hosted) connector in Securiti

This topic covers creating a data system instance and connecting the Workday self-hosted connector.

> [!NOTE]
> Note
> 
> Securiti stores sensitive connector credentials in an encrypted, base-64-encoded form. For self-hosted connectors, these credentials reside on your pod and are also stored in the Securiti cloud. A credential vault can also be used to store credentials for self-hosted connectors. If a vault is being used, credentials are retrieved securely from the vault at runtime on your pod and are not stored in the cloud.
> 
> 
> 
> For Securiti Cloud-hosted connectors, credentials are securely stored only in the Securiti cloud.

## Creating a data system instance

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

## Authenticating the data system instance

After creating a Workday data system instance, in the **Authentication** tab, authenticate your connector:

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
3. In the **Credentials** section, configure the following settings based on the authentication type:

**Basic**

Configure the following settings in case of Basic authentication:

| Setting | Description |
| --- | --- |
| Authentication type | Select **Basic** authentication from the menu. > [!NOTE] > **Important** > > When authenticating and activating the Workday Connector using the Basic method, do not use these special characters in the password: > > - " > - ' > - < > - > > - & |
| Keyring | Enable the **Use Keyring** toggle if you have used a Credential vault to store the Keyring. |
|  | From the **Keyring Type** menu, select one of the following supported keyrings. - **HashiCorp:** For more information, see [Configuring HashiCorp credential vaults](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault). - Credstash: For more information, see [Configuring CredStash credential vaults](/latest/docs/configuring-credential-vaults-credstash-credential-vault). |
|  | From the **Keyring** menu, select the keyring configured under the selected type. |
| User | If you are not using a keyring, enter the Workday username. The username also includes the corresponding tenant name. See example below: *username@tenantname* |
| Password | If you are not using a keyring, enter your Workday password. |
| Tenant | Enter the name of your Workday tenant. |
| Host | Enter the hostname path where you've hosted the Workday instance. |
| WSDL Version | Enter the Workday Web Services version. *v35.0* is the default version. > [!NOTE] > Note > > You must use a **WSDL Version** that supports the modules and web services you use for the Workday connector. Otherwise, it might cause authentication and scanning errors. |
| Module / Service | Enter your module URL supported by Workday, for example, "Staffing." |
| API Timeout | Specify the time an API would take to return with a timeout error if it is unable to complete the request. |

**OAuth 2.0**

Configure the following settings in case of OAuth2.0 authentication:

| Setting | Description |
| --- | --- |
| Authentication type | Select **OAuth 2.0** from the menu. |
| Client ID | Enter your OAuth client id. The client ID follows a string value. See example below: *3MVG9lKcPoNINVBIPJjdw1J9LLM82Hn_9Z1Y39uUexTInpH6rP6ConZah1WmmzPfWvP9CqFJ86G32Wo3mpfiB* |
| Client Secret | Enter the OAuth secret. The client secret follows a string value. See example below: *5678901234567890123* |
| Auth Url AKA Authorization Endpoint | Enter your authorization endpoint that Workday uses to redirect the OAuth flow for granting Permissions. |
| Tenant | Enter the name of your Workday tenant. |
| Host | Enter the hostname path where you've hosted the Workday instance. |
| WSDL Version | Enter the Workday Web Services version. *v35.0* is the default version. > [!NOTE] > Note > > You must use a **WSDL Version** that supports the modules and web services you use for the Workday connector. Otherwise, it might cause authentication and scanning errors. |
| Module / Service | Enter your module URL supported by Workday, for example, "Staffing." |
| API Timeout | Specify the time an API would take to return with a timeout error if it is unable to complete the request. |

- Click **Test Connection**.

Securiti authenticates the connector.

> [!NOTE]
> Note
> 
> Workday syncs indexes and metadata during the Activation process.
> 
> Depending on the size of your Workday Instance, it may take up to 24 hours to move from authenticating to Authentication successful state.
> 
> Also, we recommend you do not run DSRs and Discovery scans against the Instance until the connector status says "Authentication successful."

### Monitoring connection tests and authentication statuses

After authenticating the connector, use this section to review connection test results, verify the configured permissions, and check the authentication statuses for supported capabilities, such as Discovery scans and metadata scans.

For more information, see [Using data system connector authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scan settings

Proceed to the following topics to configure the post-authentication scans settings for the Workday (self-hosted)

- [Configuring discovery scans in Workday](/latest/docs/configure-discovery-scans-in-workday-self-hosted).
- [Configure General scans for Workday (Self-hosted)](/latest/docs/configure-general-configurations-workday-self-hosted).
- [Fulfilling Workday DSR requests](/latest/docs/fulfilling-dsr-requests-for-workday).
