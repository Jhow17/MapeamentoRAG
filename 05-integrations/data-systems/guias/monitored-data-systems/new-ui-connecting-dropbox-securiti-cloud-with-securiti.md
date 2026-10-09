---
title: "Connecting Dropbox (Securiti-Cloud) with Securiti"
slug: "new-ui-connecting-dropbox-securiti-cloud-with-securiti"
updated: 2026-03-10T05:14:08Z
published: 2026-03-10T05:14:08Z
canonical: "helpcenter.securiti.ai/new-ui-connecting-dropbox-securiti-cloud-with-securiti"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# (New UI) Connecting Dropbox (Securiti cloud) with Securiti

This topic covers activation of the Dropbox (Securiti cloud) connector.

## Creating Dropbox data system connector instance

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

## Authenticating Dropbox (Securiti cloud) connector

After creating a Dropbox connector instance, in the **Authentication** tab, authenticate your connector:

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
| Client ID | Enter the **Client ID** you recorded in [Configure the Hashicorp OAuth token](/latest/docs/optional-configure-the-hashicorp-oauth-token-for-dropbox). The Client ID uses string value. See the example below. `8a7b3c9d-12e4-567f-89ab-0123456789cd` |
| Client Secret | Enter the **Client** **Secret** you recorded in [Configure the Hashicorp OAuth token](/latest/docs/optional-configure-the-hashicorp-oauth-token-for-dropbox). The Client Secret uses string value. See the example below. `n3v3rU53th1s_Ke3p1tS3cur3!` |
3. Click **Authenticate & Activate Connector**.

Securiti redirects you to Dropbox to authenticate the new app.

![C00323.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a604f87a-9ab3-673b-bb86-b97bb8dcc572.png)
4. Log in to Dropbox with your admin Credentials

Dropbox redirects you back to Securiti.
5. Securiti activates the Connector and the status changes to "Active."

### Monitoring connection tests and authentication statuses

After authenticating the connector, use this section to review connection test results, verify the configured permissions, and check the authentication statuses for supported capabilities, such as Discovery scans and metadata scans.

For more information, see [Using data system connector authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scans settings

Proceed to the following topics to configure the post-authentication scans settings for the Dropbox (Securiti hosted)

- [(New UI) Configuring General permissions for Dropbox (Securiti cloud)](/latest/docs/new-ui-configuring-general-permissions-for-dropbox-securit-cloud)
