---
title: "Connecting DocuSign (Securiti Cloud) with Securiti"
slug: "connecting-docusign-securiti-cloud-with-securiti"
updated: 2026-07-03T06:54:17Z
published: 2026-07-03T06:54:17Z
canonical: "helpcenter.securiti.ai/connecting-docusign-securiti-cloud-with-securiti"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connecting DocuSign (Securiti Cloud) with Securiti

This article covers the connector activation process for the DocuSign Securiti Cloud connector.

## Creating a DocuSign connector instance

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

## Authenticating the DocuSign connector

After creating a DocuSign connector instance, on the **Authentication** tab, authenticate your connector by configuring the following settings:

| Parameter | Description |
| --- | --- |
| Environment | Select one of the following: - **Account** for production. - **Demo Account** for development. Both procedures are outlined in [Set up DocuSign API access credentials](/latest/docs/set-up-docusign-api-access-credentials). |
| Client ID | Enter the Client ID you recorded in [Set up DocuSign API access credentials](/latest/docs/set-up-docusign-api-access-credentials). The client ID follows a string value. See an example below. `3MVG9lKcPoNINVBIPJjdw1J9LLM82Hn_9Z1Y39uUexTInpH6rP6ConZah1WmmzPfWvP9CqFJ86G32Wo3mpfiB` |
| Client Secret | Enter the Secret Key you recorded in [Set up DocuSign API access credentials](/latest/docs/set-up-docusign-api-access-credentials). The client secret follows a string value. See an example below. `5678901234567890123` |

At the bottom of the page, click **Test Connection**. You will be redirected to the DocuSign screen for authentication, click **Accept**, as shown below.

![Docusign_Authentication_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-209a1874-2c3e-75a4-ca20-2f1e712cc247.png)

Securiti authenticates the connector.

### Monitoring the overview page and authentication statuses

After authenticating the connector, in the **Overview** section:

- Review connection test results.
- Verify the configured permissions.
- Authenticate the statuses for supported capabilities.

For more information, see [Using the connectors overview page](/latest/docs/new-ui-using-connectors-overview-page). To monitor the authentication statuses, click **View Diagnostic Report** or the **Authentication** tab. For more information, see [Using data system connector authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scan settings

Proceed to the following topics to configure post-authentication scan settings for the DocuSign Securiti Cloud connector:

- [Configuring general scan settings for DocuSign (Securiti Cloud)](/latest/docs/configuring-docusign-scanning)
