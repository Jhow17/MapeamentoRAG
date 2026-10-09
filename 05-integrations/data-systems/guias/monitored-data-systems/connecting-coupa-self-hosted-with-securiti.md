---
title: "Connecting Coupa (Self-hosted) with Securiti"
slug: "connecting-coupa-self-hosted-with-securiti"
updated: 2026-07-07T06:33:51Z
published: 2026-07-07T06:33:51Z
canonical: "helpcenter.securiti.ai/connecting-coupa-self-hosted-with-securiti"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connecting Coupa (Self-hosted) with Securiti

This topic covers activation of the Coupa (Self-hosted) connector.

> [!NOTE]
> Note
> 
> Securiti stores sensitive connector credentials in an encrypted, base-64-encoded form. For self-hosted connectors, these credentials reside on your pod and are also stored in the Securiti cloud. A credential vault can also be used to store credentials for self-hosted connectors. If a vault is being used, credentials are retrieved securely from the vault at runtime on your pod and are not stored in the cloud.
> 
> 
> 
> For Securiti Cloud-hosted connectors, credentials are securely stored only in the Securiti cloud.

## Creating a Coupa data system instance

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

## Authenticating Coupa connector

After creating a Coupa (Self-hosted) connector instance, in the **Authentication** tab, authenticate your connector:

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
| (Optional) Use Keyring | Enable the **Use Keyring** toggle if you have used a Credential vault to store the Keyring. |
| From the **Keyring Type** dropdown, select one of the following supported keyrings. - **Basic.** - **HashiCorp**: For more information, see [HashiCorp](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault). To configure Hashicorp OAuth tokens, see [(Optional) Configure HashiCorp OAuth token for Coupa](/latest/docs/optional-configure-hashicorp-oauth-token-for-coupa). > [!NOTE] > Note > > For connectors using HashiCorp's OAuth plugin, Securiti dynamically retrieves the credentials. For multiple accounts requiring different credential paths, you must configure separate keyrings. Keyrings can be linked to connectors in the following ways: > > - Multiple connectors can share the same keyring. > - A connector can only have one keyring linked at a time, which can be updated during the reconfiguration process. For more information on credential vaults, see [Configuring credential vaults](/latest/docs/managing-credentials-configuring-credential-vaults). |
| From the **Keyring** dropdown, select the keyring configured under the selected type. For more information on keyrings, see [Using keyrings](/latest/docs/managing-credentials-using-keyrings). |
| Client ID | If not using keyring, enter the identifier you recorded earlier in [Obtain permissions and authentication credentials in Coupa](/latest/docs/obtain-permissions-and-authentication-credentials-in-coupa). |
| Client Secret | If not using keyring, enter the secret you recorded earlier in [Obtain permissions and authentication credentials in Coupa](/latest/docs/obtain-permissions-and-authentication-credentials-in-coupa). |
| Instance Name | Enter the name of your Coupa instance. The Instance Name uses a string value. See example below: `example-instance-name` |
| (Optional) Store Sample file on PCS | - **Store Sample files on PCS** toggle is disabled by default. > [!NOTE] > **Note** > > In EPod V2 deployments, Securiti disables this toggle if PCS is not configured in yourtenant. Without PCS, support for storing sample files is unavailable for structured orhybrid data systems. - Keep the toggle disabled to store table training sample files locally on the pod, ensuring they remain within your local environment. - Enable this toggle if you wish to store table training sample files in Private Cloud Storage (PCS). > [!NOTE] > **Note** > > This functionality can only be enabled if Private Cloud Storage is already configured in your tenant. In case of reconfiguring a connector, files stored prior to the reconfiguration remain in their existing location, pods or PCS, until you perform a re-scan, after which Securiti stores sample files in the newly configured location. |
4. Click **Test Connection** at the bottom of the page.

Securiti activates the connector.

### Monitoring the Overview page and authentication statuses

After authenticating the connector, in the **Overview** section:

- Review connection test results.
- Verify the configured permissions.
- Authenticate the statuses for supported capabilities.

For more information, see [Using the connectors overview page](/latest/docs/new-ui-using-connectors-overview-page).

To monitor the authentication statuses, click **View Diagnostic Report** or the **Authentication** tab. For more information, see [Using data system connector authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scans settings

Proceed to the following topics to configure the post-authentication scans settings for Coupa (Self-hosted):

- [Configuring General scan settings for Coupa](/latest/docs/initiate-coupa-learning).

**Additional resources**

- [Object scanning in Coupa](/latest/docs/object-scanning-in-coupa).
- [Table training for structured and hybrid data systems](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems).

A secure container for storing cryptographic keys or login credentials. See Managing keyrings, for more information.
