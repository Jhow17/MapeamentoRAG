---
title: "Connecting Salesforce Marketing Cloud Account Engagement (Pardot) with Securiti"
slug: "connecting-salesforce-securiti-cloud-pardot-with-securiti"
updated: 2026-07-31T11:26:15Z
published: 2026-07-31T11:26:15Z
canonical: "helpcenter.securiti.ai/connecting-salesforce-securiti-cloud-pardot-with-securiti"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connecting Salesforce Marketing Cloud Account Engagement (Pardot) with Securiti

This topic covers activation of the Salesforce Marketing Cloud Account Engagement (Pardot) connector.

> [!NOTE]
> Note
> 
> Securiti stores sensitive connector credentials in an encrypted, base-64-encoded form. For self-hosted connectors, these credentials reside on your pod and are also stored in the Securiti cloud. A credential vault can also be used to store credentials for self-hosted connectors. If a vault is being used, credentials are retrieved securely from the vault at runtime on your pod and are not stored in the cloud.
> 
> 
> 
> For Securiti Cloud-hosted connectors, credentials are securely stored only in the Securiti cloud.

## Creating a Salesforce Marketing Cloud Account Engagement (Pardot) data system connector instance

Perform the following steps to create a Data system instance for Securiti cloud connectors:

1. Log in to Securiti with your admin credentials.
2. To open the main menu, from the upper left corner of the left navigation bar, click the **Jewel** icon.
3. From the Platform Services section in the new navigation, select **Integrations**.
4. From the **Integrations** menu, choose **Monitored Data Systems.**
5. On the top right of the **Integrations** page, click **Add Integration** to create a new data system instance.
6. On the Add Integration page, click the **Securiti-Cloud** tab.
7. From the data system list, choose your relevant data system.
8. On the **Basic Information** tab, complete the following parameters:

| Parameter | Explanation | Example |
| --- | --- | --- |
| Instance Name | Enter a convenient name for the connector Instance. | Admin-data1 |
| Description | Add a short note to explain the purpose of this instance. | To discover and monitor data sources in the production environment. |
| Hosting Location | The **Hosting Location** will be set to **SaaS** for the specific data systems. | SaaS |
| Country | Select the **country** from the dropdown where the data source or resource is located. | America, Canada |
| (Optional) State | Select the **state** or region from the dropdown within the chosen country. | Alberta |
| (Optional) City | Enter the **city** where the data source or resource is located. | Calgary |
| Owners | Choose **Primary** **Owner** for the Instance. By default, you are the primary owner. | John.doe@securiti.ai |
| (optional) Additional owners can be added after creating an instance by enabling the **Add** **Co-owner** tab on the Basic Information page. From the dropdown, select users to add as additional owners. | Alex.doe@securiti.ai |
| (optional) Enable the toggle for **Send Notification to all Owners** to notify owners. |  |
9. At the Bottom of the page, click **Create and Continue**.

It redirects you to the **Authentication** page.

## Authenticating Salesforce Marketing Cloud Account Engagement (Pardot) connector

After creating a Salesforce Marketing Cloud Account Engagement (Pardot) connector instance, in the **Authentication** tab, authenticate your connector:

1. > [!WARNING]
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
2. In the **Credentials** section, configure the following settings:

| Setting | Description |
| --- | --- |
| Salesforce Instance | Enter the Instance ID or Domain ID you recorded when creating a connected app, as described in [Configure a Connected App for the OAuth 2.0 Client Credentials Flow](https://help.salesforce.com/s/articleView?id=xcloud.connected_app_client_credentials_setup.htm&amp;type=5). The Instance/domain ID uses a string value. See an example below. `Securiti-123` |
| Environment | Select the deployment environment for your Pardot Instance, from the menu. For example, **Production** or **Sandbox**. |
| Business Unit ID | Enter the unique identifier for your Pardot business unit within Marketing Cloud Account Engagement, as described in [Salesforce documentation for Account Engagement Business ID](https://help.salesforce.com/s/articleView?id=000381973&amp;type=1). The Business Unit ID uses a string value. See an example below. `0Uv4x000000CbGxCAK` |
| Consumer ID | Enter the Consumer ID associated with the OAuth Credentials for your Pardot application, as described in [Configure a Connected App for the OAuth 2.0 Client Credentials Flow](https://help.salesforce.com/s/articleView?id=xcloud.connected_app_client_credentials_setup.htm&amp;type=5). See an example below. `3MVG9lKcPoNINVBIPJjdw1J9LLM82HWo3mpfiB` |
| Consumer Secret | Enter the Consumer Secret associated with the OAuth Consumer ID, as described in [Configure a Connected App for the OAuth 2.0 Client Credentials Flow](https://help.salesforce.com/s/articleView?id=xcloud.connected_app_client_credentials_setup.htm&amp;type=5). See an example below. `SecreT!987654321` |
3. Click **Test** **Connection** at the bottom of the page

Securiti redirects you to Salesforce to authenticate the connecting application's credentials you entered above.

Click **Allow**. ![SF_ConnectAuth_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-25551145-581b-5a1d-8776-25c67471755f.png)

Salesforce redirects you back to the Authentication tab and Securiti activates the connector.

> [!WARNING]
> **Important**
> 
> Securiti sends email notifications to Connector owners when critical access-related issues occur during a metadata or Discovery scan.
> 
> These notifications are triggered by Authentication and authorization issues such as:
> 
> - An expired or invalid access or refresh Token
> - An invalid Connector Configuration
> - Other Authentication grant errors for example, invalid_grant

### Monitoring the overview page and authentication statuses

After authenticating the connector, in the **Overview** section:

- Review connection test results.
- Verify the configured permissions.
- Authenticate the statuses for supported capabilities.

For more information, see [Using the connectors overview page](/latest/docs/new-ui-using-connectors-overview-page).

To monitor the authentication statuses, click **View Diagnostic Report** or the **Authentication** tab. For more information, see [Using data system connector authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scan settings

Proceed to [Configuring Pardot integration in Securiti](https://helpcenter.securiti.ai/docs/configuring-pardot-integration-in-securiti).
