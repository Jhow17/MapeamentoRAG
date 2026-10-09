---
title: "Connecting Salesforce Customer Data Platform with Securiti"
slug: "connecting-salesforce-customer-data-platform-with-securiti"
updated: 2026-07-31T11:07:44Z
published: 2026-07-31T11:07:44Z
canonical: "helpcenter.securiti.ai/connecting-salesforce-customer-data-platform-with-securiti"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connecting Salesforce Customer Data Platform with Securiti

This topic covers activation of the Salesforce Customer Data Platform connector.

## Creating a Salesforce Customer Data Platform data system connector instance

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

## Authenticating the Salesforce Customer Data Platform connector

After creating a Salesforce Customer Data Platform connector instance, in the **Authentication** tab, authenticate your connector:

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
| Use Domain Id | Enable the toggle to use the domain ID. Specify the domain ID in the field below. |
| Instance / Domain Id | Enter the Instance ID you recorded in [Grant permissions and obtain authentication credentials in the Salesforce Customer Data Platform](/latest/docs/grant-permissions-and-obtain-authentication-credentials-in-the-salesforce-customer-data-platform). In the URL, focus on the portion just after https:// and before the first dot (`.`). This segment is what we refer to as the 'Instance ID'. See examples below. **Example 1:** - URL: <https://***securitiai2****.my.salesforce.com/app/*> - Instance ID: <***securitiai2***> **Example 2:** - URL: <https://***d10000000p6ereay-dev-ed****.lightning.force.com*> - Instance ID: <***d10000000p6ereay-dev-ed***> |
| Consumer Key | Enter the Consumer Key you recorded in [Grant permissions and obtain authentication credentials in the Salesforce Customer Data Platform](/latest/docs/grant-permissions-and-obtain-authentication-credentials-in-the-salesforce-customer-data-platform). The consumer key is the public identifier for the Connector and uses an alphanumeric string value. See the example below. `3MVG9lKcPoNINVBIPJjdw1J9LLM82Hn_9Z1Y39uUexTInpH6rP6ConZah1WmmzPfWvP9CqFJ86G32Wo3mpfiB` |
| Consumer Secret | Enter the consumer secret you recorded in [Grant permissions and obtain authentication credentials in the Salesforce Customer Data Platform](/latest/docs/grant-permissions-and-obtain-authentication-credentials-in-the-salesforce-customer-data-platform). The consumer secret is the confidential key for the Authentication and uses an alphanumeric string value. See the example below. `5678901234567890123` |
4. Click **Test** **Connection** at the bottom of the page

Securiti activates the connector.

### Monitoring the overview page and authentication statuses

After authenticating the connector, in the **Overview** section:

- Review connection test results.
- Verify the configured permissions.
- Authenticate the statuses for supported capabilities.

For more information, see [Using the connectors overview page](/latest/docs/new-ui-using-connectors-overview-page).

To monitor the authentication statuses, click **View Diagnostic Report** or the **Authentication** tab. For more information, see [Using data system connector authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scan settings

Proceed to the following topics to configure the post-authentication scans settings for the Salesforce Customer Data Platform:

- [Configure discovery scans in Salesforce Customer Data Platform](/latest/docs/configure-discovery-scans-in-salesforce-customer-data-platform).

**Additional resources**

- [Fulfilling Salesforce Customer Data Platform DSR requests](/latest/docs/fulfilling-salesforce-customer-data-platform-dsr-requests).
