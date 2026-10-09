---
title: "Connecting NetSuite (Securiti-Cloud) with Securiti"
slug: "connecting-netsuite-securiti-cloud-with-securiti"
updated: 2026-07-01T03:47:49Z
published: 2026-07-01T03:47:49Z
canonical: "helpcenter.securiti.ai/connecting-netsuite-securiti-cloud-with-securiti"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connecting NetSuite (Securiti-Cloud) with Securiti

This topic covers activation of the NetSuite Securiti-Cloud connector.

## Creating a NetSuite data system instance

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

## Authenticating NetSuite (Securiti-Cloud) connector

After creating NetSuite connector instance, in the **Authentication** tab, authenticate your connector:

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

| Setting | Authentication Method | Description |
| --- | --- | --- |
| Authentication Type | N/A | In the **Authentication Type**, select from the following supported authentication methods: - **Basic** - **OAuth 2.0** |
| Account ID | - Basic - OAuth 2.0 | Enter your NetSuite account ID. The account ID uses an integer value. See example below. `1234567` |
| Consumer Key | - Basic - OAuth 2.0 | Enter the consumer key you acquired in [Obtain credentials in NetSuite for OAuth 2.0 authentication](/latest/docs/obtain-credentials-in-netsuite-for-oauth-20-authentication). The consumer key uses a string value. See the example below. `12nkjhnnhuYGUKJB454KJKK` |
| Consumer Secret | - Basic - OAuth 2.0 | Enter the secret you obtained in [Acquire the API access token in NetSuite](/latest/docs/acquire-the-api-access-token-in-netsuite). The consumer secret uses a string value. See example below. `Abc12DeFHIJKlmnopk3456` |
| Token ID | Basic | If not using Keyring, enter the Token ID you recorded in [Acquire the API access token in NetSuite](/latest/docs/acquire-the-api-access-token-in-netsuite). The Token ID uses a string value. See example below. `Xyz12DeFHIJKlmnopk3456` |
| Token Secret | Basic | If not using keyring, enter the Token secret you recorded in [Acquire the API access token in NetSuite](/latest/docs/acquire-the-api-access-token-in-netsuite). The Token secret uses a string value. See example below. `Oqguy12DeFHIJKlmnopk3456` |
| Certificate ID | OAuth 2.0 | Enter the Certificate ID you recorded in [Generate the Public Certificate and Private Key](/v1/docs/obtain-credentials-in-netsuite-for-oauth-20-authentication). The Certificate ID is a public Certificate **.pem** file name. See example below. `public-auth-cert.pem` |
| Private Key | OAuth 2.0 | Enter the private key you recorded in [Obtain credentials in NetSuite for OAuth 2.0 authentication](/latest/docs/obtain-credentials-in-netsuite-for-oauth-20-authentication). The private key is a **.pem** file. See example below. `private-key.pem` |
| (Optional) Timeout | - Basic - OAuth 2.0 | Specify the timeout value in seconds for request completion. The timeout value is a number. See example below. `100` |
| (Optional) Page Size | - Basic - OAuth 2.0 | Specify the number of records to be retrieved for a given request. The page size is a number. See example below. `50` |
| (Optional) Additional Connection String Options | - Basic - OAuth 2.0 | Specify any JDBC additional string connections. You can specify multiple options separated by a semicolon ;. |
3. Click **Test Connection** at the bottom of the page.

### Monitoring the Overview page and authentication statuses

After authenticating the connector, in the **Overview** section:

- Review connection test results.
- Verify the configured permissions.
- Authenticate the statuses for supported capabilities.

For more information, see [Using the connectors overview page](/latest/docs/new-ui-using-connectors-overview-page).

To monitor the authentication statuses, click **View Diagnostic Report** or the **Authentication** tab. For more information, see [Using data system connector authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scans settings

Proceed to the following topics to configure the post-authentication scans settings for NetSuite (Securiti-Cloud):

- [Configuring General permissions for NetSuite (Securiti-Cloud)](/latest/docs/clone-configuring-general-permissions-for-netsuite-self-hosted).

**Additional resources**

- [Fulfilling DSR requests for NetSuite](/latest/docs/fulfilling-dsr-requests-for-netsuite).
- [Troubleshooting for NetSuite](/latest/docs/troubleshooting-for-netsuite).
