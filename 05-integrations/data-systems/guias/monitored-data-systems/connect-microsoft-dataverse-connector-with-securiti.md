---
title: "Connecting Microsoft Dataverse connector with Securiti"
slug: "connect-microsoft-dataverse-connector-with-securiti"
updated: 2026-08-11T06:11:02Z
published: 2026-08-11T06:11:02Z
canonical: "helpcenter.securiti.ai/connect-microsoft-dataverse-connector-with-securiti"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connecting Microsoft Dataverse connector with Securiti

> [!NOTE]
> Note
> 
> Securiti stores sensitive connector credentials in an encrypted, base-64-encoded form. For self-hosted connectors, these credentials reside on your pod and are also stored in the Securiti cloud. A credential vault can also be used to store credentials for self-hosted connectors. If a vault is being used, credentials are retrieved securely from the vault at runtime on your pod and are not stored in the cloud.
> 
> 
> 
> For Securiti Cloud-hosted connectors, credentials are securely stored only in the Securiti cloud.

This topic covers setup of the Microsoft Dataverse (self-hosted) Connector.

## Creating a Microsoft Dataverse data system connector instance

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

## Authenticating Microsoft Dataverse (Self-hosted) connector

After creating a Microsoft Dataverse connector instance, in the **Authentication** tab, authenticate your connector.

Apply the following settings using Credentials obtained in [Grant permissions and obtain credentials in Microsoft Dataverse](/latest/docs/grant-permissions-and-obtain-credentials-in-microsoft-dataverse).

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
| Tenant ID (or Domain) | Enter your Tenant ID or Domain that you recorded earlier. - Domain is usually your company domain. See the example below. `democo.org` - Tenant ID follows the string format. See the example below. `0a1b01a1-aob1b-1a1a-b0b0-101010ab1a01` |
| Host URL | Enter the Host URL you extracted from Web API endpoint URL. See example below. `https://org8bcf25c3.api.crm.dynamics.com` |
| Version | Enter the Version you recorded earlier. See the example below. `v-9.2` |
| Use Keyring | (Optional) Enable the toggle if you have used a Credential vault to store the Keyring. From the **Keyring Type** menu, select one of the following supported keyrings. - **HashiCorp**, see [Configuring HashiCorp credential vaults](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault) for more information. > [!NOTE] > **Note** > > You must configure the HashiCorp OAuth Token to activate the Connector using the HashiCorp vault Authentication. For more information, see [Configure the Hashicorp OAuth token for Microsoft Dataverse](/latest/docs/optional-configure-the-hashicorp-oauth-token-for-microsoft-dataverse) > [!NOTE] > **Important** > > For connectors using HashiCorp's OAuth plugin, Securiti dynamically retrieves the Credentials. For multiple accounts requiring different credential paths, you must configure separate keyrings. > > Keyrings can be linked to connectors in the following ways: > > - Multiple connectors can share the same Keyring. > - A Connector can only have one Keyring linked at a time, which can be updated during the Reconfiguration process. |
| Client ID | Enter the application ID you recorded earlier. The Client ID uses a string value. See an example below. `12345678-abcd-1234-efgh-123456abcdef` |
| Client Secret | Enter the Client Secret you recorded earlier. The Client Secret uses a string value. See an example below. `aB8C~Dsr.10yXyu~a4VAAAAp8ZRTJBA.zlAcy~` |
4. Click **Test** **Connection** at the bottom of the page.
5. Securiti redirects you to the Microsoft login window, as shown below. Log in with your admin Credentials.

![in_privacy5.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3742bc54-34e2-421f-2bc0-62553d4565c1(7).png)
6. Microsoft prompts you to accept the Permissions requested by the Securiti app in Azure, as shown below.

![in_privaci6.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f9d011db-ca3b-a688-ab13-d3f1c2dbf7a0(7).png)
7. Click **Accept**.

Microsoft redirects you back to Securiti. You have finished authenticating the Connector.

### Monitoring the overview page and authentication statuses

After authenticating the connector, in the **Overview** section:

- Review connection test results.
- Verify the configured permissions.
- Verify the statuses for supported capabilities.

For more information, see [Using the connectors overview page](/latest/docs/new-ui-using-connectors-overview-page).

To monitor the authentication statuses, click **View Diagnostic Report** or the **Authentication** tab. For more information, see [Using data system connector authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scan settings

Proceed to the following topics to configure the post-authentication scans settings for the Microsoft Dataverse (self-hosted):

- [Configure discovery scans in Microsoft Dataverse](/latest/docs/configure-discovery-scans-for-microsoft-dataverse).
- [Fulfilling DSR Requests in Microsoft Dataverse](/latest/docs/fulfilling-dsr-requests-in-microsoft-dataverse).
