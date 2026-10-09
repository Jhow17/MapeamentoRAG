---
title: "Connecting Salesforce (Securiti-Cloud) with Securiti"
slug: "connecting-salesforce-securiti-cloud-with-securiti"
updated: 2026-03-10T05:53:01Z
published: 2026-03-10T05:53:01Z
canonical: "helpcenter.securiti.ai/connecting-salesforce-securiti-cloud-with-securiti"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connecting Salesforce (Securiti-Cloud) with Securiti

This topic covers activation of the Salesforce (Legacy) connector.

> [!NOTE]
> Note
> 
> Securiti stores sensitive connector credentials in an encrypted, base-64-encoded form. For self-hosted connectors, these credentials reside on your pod and are also stored in the Securiti cloud. A credential vault can also be used to store credentials for self-hosted connectors. If a vault is being used, credentials are retrieved securely from the vault at runtime on your pod and are not stored in the cloud.
> 
> 
> 
> For Securiti Cloud-hosted connectors, credentials are securely stored only in the Securiti cloud.

## Creating a Salesforce (Securiti cloud) data system connector instance

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

## Authenticating Salesforce (Securiti cloud) connector

After creating a Salesforce (Securiti Cloud) connector instance, in the **Authentication** tab, authenticate your connector:

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
| Use Domain Id | Enable the toggle to use Domain Id as the input value. |
| Instance/Domain id | Enter the **Instance** or **Domain Id** you recorded earlier in [Register a connecting app in Salesforce](/v1/docs/register-a-connecting-app-in-salesforce). The Instance/domain ID uses a string value. See an example below. `Securiti-123` |
| Consumer Key | Enter the Consumer Key you recorded earlier in [Register a connecting app in Salesforce](/v1/docs/register-a-connecting-app-in-salesforce). The consumer key is the public identifier for the Connector and uses an alphanumeric string value. See an example below: `3MVG9lKcPoNINVBIPJjdw1J9LLM82Hn_9Z1Y39uUexTInpmiB` |
| Consumer Secret | Enter the Consumer Secret you recorded earlier in [Register a connecting app in Salesforce](/v1/docs/register-a-connecting-app-in-salesforce). The consumer secret is the confidential key for the Authentication and uses an alphanumeric string value. See an example below. `5678901234567890123` |
3. Click **Test** **Connection** at the bottom of the page

Securiti redirects you to Salesforce to authenticate the connecting application's credentials you entered above.

Click **Allow**. ![SF_ConnectAuth_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-25551145-581b-5a1d-8776-25c67471755f.png)

Salesforce redirects you back to the Authentication tab and Securiti activates the Connector.

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

### Monitoring connection tests and authentication statuses

After authenticating the connector, use this section to review connection test results, verify the configured permissions, and check the authentication statuses for supported capabilities, such as Discovery scans and metadata scans.

For more information, see [Using data system connector authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scans settings

Proceed to the following topics to configure the post-authentication scans settings for the Salesforce (Legacy)

- [(New UI) Configuring General permissions for Salesforce (Securiti Cloud)](/latest/docs/new-ui-configuring-general-permissions-for-salesforce-securiti-cloud)
- [Fulfilling DSR requests for Salesforce (Legacy) and cloud connectors](/v1/docs/fulfilling-dsr-requests-for-salesforce-legacy-and-cloud-connectors) .
