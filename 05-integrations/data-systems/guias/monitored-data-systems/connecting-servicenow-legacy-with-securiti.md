---
title: "Connecting ServiceNow (Legacy) with Securiti"
slug: "connecting-servicenow-legacy-with-securiti"
updated: 2026-06-11T15:06:49Z
published: 2026-06-11T15:06:49Z
canonical: "helpcenter.securiti.ai/connecting-servicenow-legacy-with-securiti"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connecting ServiceNow (Legacy) with Securiti

This topic covers activation of the ServiceNow (Legacy) (Securiti-Cloud) connector.

## Creating a ServiceNow (Legacy) Data system instance

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
| Hosting Location | Select your preferred **Hosting Location** and configure the Service provider settings where applicable. Securiti supports **SaaS**, **or** **Private Cloud**, as Hosting options for specific Data system Instances. | SaaS, Private Cloud |
| Country | Select the **country** from the dropdown where the data source or resource is located. | America, Canada |
| (Optional) State | Select the **state** or region from the dropdown within the chosen country. | Alberta |
| (Optional) City | Enter the **city** where the data source or resource is located. | Calgary |
| Owners | Choose **Primary** **Owner** for the Instance. By default, you are the primary owner. | John.doe@securiti.ai |
| (optional) Additional owners can be added after creating an instance by enabling the **Add** **Co-owner** tab on the Basic Information page. From the dropdown, select users to add as additional owners. | Alex.doe@securiti.ai |
| (optional) Enable the toggle for **Send Notification to all Owners** to notify owners. |  |
9. At the Bottom of the page, click **Create and Continue**.

It redirects you to the **Authentication** page.

## Authenticating ServiceNow (Legacy) (Securiti-Cloud) connector

After creating ServiceNow (Legacy) connector instance, in the **Authentication** tab, authenticate your connector:

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

| Setting | Description |
| --- | --- |
| Instance ID | Enter the Instance ID for the Instance that you created earlier. The Instance ID follows a string value. See the example below. `Dev12345` |
| Client ID | Enter the client ID you acquired and recorded earlier. The client ID uses alphanumeric string values. See the example below. `VHMgkimnh123` |
| Client Secret | Enter the client secret you acquired you recorded earlier. The client secret uses alphanumeric string values. See the example below. `a3fb2c1e5d4` |
- Click **Test** **Connection** at the bottom of the page
- Securiti redirects you to your Instance's Authentication page in ServiceNow.

Click **Allow**.

ServiceNow redirects you back to Securiti. You have finished activating the Connector.

### Monitoring the Overview page and authentication statuses

After authenticating the connector, in the **Overview** section:

For more information, see [Using the connectors overview page](/latest/docs/new-ui-using-connectors-overview-page).

To monitor the authentication statuses, click **View Diagnostic Report** or the **Authentication** tab. For more information, see [Using data system connector authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scans settings

Proceed to the following topics to configure the post-authentication scans settings for the ServiceNow (Legacy):
  - Review connection test results.
  - Verify the configured permissions.
  - Authenticate the statuses for supported capabilities.
- [Configuring General permissions for ServiceNow (Legacy)](/latest/docs/configuring-general-permissions-for-servicenow-legacy).

A collection of organized data or repositories and their corresponding management software, which could be IaaS, SaaS, or SQL. Data systems are configured in Securiti so that it can help you protect sensitive data and also locate personal data for data subjects who submit DSR requests. Data systems can be monitored, un-monitored, or user-defined. For each monitored or user-defined data system, you configure a connector that Securiti uses to interact with the data system.
