---
title: "Connecting Salesforce CRM with Securiti"
slug: "connecting-salesforce-crm-with-securiti"
updated: 2026-07-31T10:55:56Z
published: 2026-07-31T10:55:56Z
canonical: "helpcenter.securiti.ai/connecting-salesforce-crm-with-securiti"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connecting Salesforce CRM with Securiti

This topic covers activation of the Salesforce CRM connector.

## Creating a Salesforce CRM data system connector instance

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

## Authenticating the Salesforce CRM connector

After creating a Salesforce CRM connector instance, in the **Authentication** tab, authenticate your connector:

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
| Use Domain ID | Toggle the *Use Domain ID* button to use Domain or Instance ID as the input value |
| Instance/Domain ID | Enter the Instance ID or Domain ID that you recorded earlier in [Prerequisites for Salesforce CRM connector](/latest/docs/prerequisites-for-salesforce-crm-connector). The Instance/domain ID uses a string value. See example below. `Securiti-123` |
| (Optional) Use Keyring | To use Credentials in a Keyring, enable the toggle and then choose the Keyring type and add choose the Keyring you created earlier. Following Keyring types are supported for Salesforce CRM: - [HashiCorp](/v1/docs/configuring-credential-vaults-hashicorp-credential-vault) - [CyberArk](/v1/docs/configuring-credential-vaults-cyberark-credential-vault) - [CyberArk Conjur](/latest/docs/configuring-credential-vaults-cyberark-conjur-credential-vault) For more information, see the following resources. - [Using keyrings](/latest/docs/managing-credentials-using-keyrings) - [Configuring credential vaults](/latest/docs/managing-credentials-configuring-credential-vaults) - [(Optional) Configure the Hashicorp OAuth token for Salesforce CRM](/latest/docs/optional-configure-the-hashicorp-oauth-token-for-salesforce-crm) - [Configuring CyberArk credential vault](/latest/docs/cyberark-credential-vault) - [Configuring CyberArk Conjur vaults](/latest/docs/configuring-credential-vaults-cyberark-conjur-credential-vault) > [!WARNING] > **Important** > > For connectors using HashiCorp's OAuth plugin, Securiti dynamically retrieves the Credentials. For multiple accounts requiring different credential paths, you must configure separate keyrings. > > Keyrings can be linked to connectors in the following ways: > > - Multiple connectors can share the same Keyring. > - A Connector can only have one Keyring linked at a time, which can be updated during the Reconfiguration process. |
| Consumer Key | If you are not using a Keyring, enter the Consumer Key that you recorded earlier in [Prerequisites for Salesforce CRM connector](/latest/docs/prerequisites-for-salesforce-crm-connector). The consumer key is the public identifier for the Connector and uses an alphanumeric string value. See the example below. `3MVG9lKcPoNINVBIPJjdw1J9LLM82Hn_9Z1Y39uUexTInpH6rP6ConZah1WmmzPfWvP9CqFJ86G32Wo3mpfiB` |
| Consumer Secret | If you are not using a Keyring, enter the Consumer Secret that you recorded earlier in [Prerequisites for Salesforce CRM connector](/latest/docs/prerequisites-for-salesforce-crm-connector). The consumer secret is the confidential key for the Authentication and uses an alphanumeric string value. See the example below. `5678901234567890123` |
| (Optional) Store Sample file on PCS | - **Store Sample files on PCS** toggle is disabled by default. > [!NOTE] > **Note** > > In EPod V2 deployments, Securiti disables this toggle if PCS is not configured in yourtenant. Without PCS, support for storing sample files is unavailable for structured orhybrid data systems. - Keep the toggle disabled to store table training sample files locally on the pod, ensuring they remain within your local environment. - Enable this toggle if you wish to store table training sample files in Private Cloud Storage (PCS). > [!NOTE] > **Note** > > This functionality can only be enabled if Private Cloud Storage is already configured in your tenant. In case of reconfiguring a connector, files stored prior to the reconfiguration remain in their existing location, pods or PCS, until you perform a re-scan, after which Securiti stores sample files in the newly configured location. |
4. Click **Test Connection****.**

Securiti redirects you to Salesforce to authenticate the connecting application's Credentials you entered into the Connector tab.
5. Click **Allow**.

![SF_ConnectAuth_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-25551145-581b-5a1d-8776-25c67471755f(3).png)

Salesforce redirects you back to the authentication tab. Securiti activates the connector.

### Monitoring the overview page and authentication statuses

After authenticating the connector, in the **Overview** section:

- Review connection test results.
- Verify the configured permissions.
- Authenticate the statuses for supported capabilities.

For more information, see [Using the connectors overview page](/latest/docs/new-ui-using-connectors-overview-page).

To monitor the authentication statuses, click **View Diagnostic Report** or the **Authentication** tab. For more information, see [Using data system connector authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scan settings

Proceed to the following topics to configure the post-authentication scans settings for the Salesforce CRM:

- [Configuring General permissions for Salesforce CRM](/latest/docs/configuring-general-permissions-for-salesforce-crm).
- [Configure discovery scans in Salesforce CRM](/latest/docs/configure-discovery-scans-in-salesforce-crm).

**Additional resources**

- [Fulfilling DSR requests for Salesforce CRM](/latest/docs/fulfilling-dsr-requests-for-salesforce-crm).
- [Troubleshooting for Salesforce (CRM) connector](/latest/docs/troubleshooting-for-salesforce-crm-connector).
