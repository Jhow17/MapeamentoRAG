---
title: "Connecting the Adobe Marketo Engage (Securiti-Cloud) connector with Securiti"
slug: "connecting-the-adobe-marketo-engage-securiti-cloud-connector-with-securiti"
updated: 2026-08-04T08:34:37Z
published: 2026-08-04T08:34:37Z
canonical: "helpcenter.securiti.ai/connecting-the-adobe-marketo-engage-securiti-cloud-connector-with-securiti"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connecting the Adobe Marketo Engage (Securiti-Cloud) connector with Securiti

This topic covers activation of the Adobe Marketo Engage (Securiti cloud) connector.

## Creating a Adobe Marketo Engage data system connector instance

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

## Authenticating the Adobe Marketo Engage connector

After creating a Adobe Marketo Engage connector instance, in the **Authentication** tab, authenticate your connector:

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
2. Under the **Credentials** section, in the **Authentication** tab, apply the following settings:

| Parameter | Description |
| --- | --- |
| Client ID | Enter the Client ID that you recorded earlier in [Grant permissions and obtain credentials in Adobe Marketo Engage](/latest/docs/grant-permissions-and-obtain-credentials-in-securiti-cloud-adobe-marketo-engage). The client ID follows a string value. See an example below: *3MVG9lKcPoNINVBIPJjdw1J9LLPfWvP9CqFJ86G32Wo3mpfiB* |
| Client Secret | Enter the Secret Key that you recorded earlier in [Grant permissions and obtain credentials in Adobe Marketo Engage](/latest/docs/grant-permissions-and-obtain-credentials-in-securiti-cloud-adobe-marketo-engage). The client secret follows a string value. See an example below: *5678901234567890123* |
| Account | Enter the domain for your REST API endpoint that you recorded earlier in [Grant permissions and obtain credentials in Adobe Marketo Engage](/latest/docs/grant-permissions-and-obtain-credentials-in-securiti-cloud-adobe-marketo-engage). The Domain uses a string value and is the part of the endpoint after the `https://` and before `.com/rest`. See an example below: *123.ABC.123.mktorest* |
3. Click **Test** **Connection** at the bottom of the page

Securiti activates the connector and displays a "Connection Established Successfully" message. The connector status changes to green.

### Monitoring the overview page and authentication statuses

After authenticating the connector, in the **Overview** section:

- Review connection test results.
- Verify the configured permissions.
- Verify the statuses for supported capabilities.

For more information, see [Using the connectors overview page](/latest/docs/new-ui-using-connectors-overview-page).

To monitor the authentication statuses, click **View Diagnostic Report** or the **Authentication** tab. For more information, see [Using data system connector authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scan settings

Proceed to the following topics to configure the post-authentication scans settings for the Adobe Marketo Engage:

- [Fulfilling DSR Requests for Adobe Marketo Engage](/latest/docs/fulfilling-dsr-requests-for-adobe-marketo-engage-securiti-cloud)

## Related

- [Grant permissions and obtain credentials in Adobe Marketo Engage (Securiti-Cloud)](/grant-permissions-and-obtain-credentials-in-securiti-cloud-adobe-marketo-engage.md)
- [Fulfilling DSR Requests for Adobe Marketo Engage (Securiti-Cloud)](/fulfilling-dsr-requests-for-adobe-marketo-engage-securiti-cloud.md)
