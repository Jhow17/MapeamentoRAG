---
title: "Connecting DocuSign (Self-hosted) with Securiti"
slug: "activate-the-docusign-connector-in-securiti"
updated: 2026-07-06T05:53:46Z
published: 2026-07-06T05:53:46Z
canonical: "helpcenter.securiti.ai/activate-the-docusign-connector-in-securiti"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connecting DocuSign (Self-hosted) with Securiti

> [!NOTE]
> Note
> 
> Securiti stores sensitive connector credentials in an encrypted, base-64-encoded form. For self-hosted connectors, these credentials reside on your pod and are also stored in the Securiti cloud. A credential vault can also be used to store credentials for self-hosted connectors. If a vault is being used, credentials are retrieved securely from the vault at runtime on your pod and are not stored in the cloud.
> 
> 
> 
> For Securiti Cloud-hosted connectors, credentials are securely stored only in the Securiti cloud.

This article covers the connector activation process for the DocuSign self-hosted connector.

## Creating a DocuSign connector instance

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

## Authenticating the DocuSign connector

After creating a DocuSign connector instance, on the **Authentication** tab, authenticate your connector by configuring the following settings:

| Parameter | Description |
| --- | --- |
| Connect with Pod | From the **Connect with Pod** menu, select the pod you configured earlier. |
| PCS Destination | > [!WARNING] > Important > > - If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation. From the **PCS Destination** menu, select one of the configured PCS to store this data system connector's sensitive data, such as: - Table Training Sample files - Sensitive Data Intelligence protection evidence files - Scan Summary > [!NOTE] > Note > > DSR Automation, Assessment Automation, and the transient metadata used during scanning continue to use the Default PCS configured for your tenant until those modules adopt multi-PCS support. You can also migrate the data from one PCS to another while reconfiguring the connector. To migrate data from one PCS to another: 1. On the activated data system instance, click on the **Reconfigure** link. 2. From the **PCS Destination** menu, select the PCS where you want to migrate the data. 3. Click **Reconfigure connector**. Securiti shows you the migration progress bar to check the status of migration. Sensitive data is stored on the existing PCS bucket until the migration is complete. |
| Environment | Select one of the following: - **Account** for production. - **Demo Account** for development. Both procedures are outlined in [Set up DocuSign API access credentials](/latest/docs/set-up-docusign-api-access-credentials). |
| Client ID | Enter the Client ID you recorded in [Set up DocuSign API access credentials](/latest/docs/set-up-docusign-api-access-credentials). The client ID follows a string value. See an example below. `3MVG9lKcPoNINVBIPJjdw1J9LLM82Hn_9Z1Y39uUexTInpH6rP6ConZah1WmmzPfWvP9CqFJ86G32Wo3mpfiB` |
| Client Secret | Enter the Secret Key you recorded in [Set up DocuSign API access credentials](/latest/docs/set-up-docusign-api-access-credentials). The client secret follows a string value. See an example below. `5678901234567890123` |
| Account ID | Enter the Account ID you recorded in [Set up DocuSign API access credentials](/latest/docs/set-up-docusign-api-access-credentials). The Account ID follows a string value. See an example below. `4b486e94-fb25-4522-999w-0aa8f84c19b0` |

At the bottom of the page, click **Test Connection**. Securiti authenticates the connector.

### Monitoring the overview page and authentication statuses

After authenticating the connector, in the **Overview** section:

- Review connection test results.
- Verify the configured permissions.
- Authenticate the statuses for supported capabilities.

For more information, see [Using the connectors overview page](/latest/docs/new-ui-using-connectors-overview-page). To monitor the authentication statuses, click **View Diagnostic Report** or the **Authentication** tab. For more information, see [Using data system connector authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scan settings

Proceed to the following topics to configure post-authentication scan settings for DocuSign:

- [Configure discovery scans in DocuSign](/latest/docs/configure-discovery-scans-in-docusign)
- [Fulfilling DSR requests for DocuSign (Self-hosted)](/latest/docs/fulfilling-dsr-requests-for-docusign-self-hosted)
- [Configuring general scan settings for DocuSign (Self-hosted)](/latest/docs/configuring-general-scan-settings-for-docusign-self-hosted)
