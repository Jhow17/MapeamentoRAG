---
title: "Connecting Jira Cloud (legacy) with Securiti"
slug: "connecting-jira-cloud-legacy-self-hosted-with-securiti"
updated: 2026-04-06T10:51:08Z
published: 2026-04-06T10:51:08Z
canonical: "helpcenter.securiti.ai/connecting-jira-cloud-legacy-self-hosted-with-securiti"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connecting Jira Cloud (Legacy) Self-hosted with Securiti

This topic covers activation of the Jira Cloud (self-hosted) connector.

> [!NOTE]
> Note
> 
> Securiti stores sensitive connector credentials in an encrypted, base-64-encoded form. For self-hosted connectors, these credentials reside on your pod and are also stored in the Securiti cloud. A credential vault can also be used to store credentials for self-hosted connectors. If a vault is being used, credentials are retrieved securely from the vault at runtime on your pod and are not stored in the cloud.
> 
> 
> 
> For Securiti Cloud-hosted connectors, credentials are securely stored only in the Securiti cloud.

## Creating data system instance

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

## Authenticating the data system instance

Before authenticating the Jira Cloud connector, you must meet the prerequisites described in [Jira Cloud](/latest/docs/jira-cloud-connectors-1). After creating a Jira Cloud data system instance, in the **Authentication** tab, authenticate your connector:

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
| (Optional) Use Keyring | Enable the toggle to use Keyring to fetch Credentials (Client ID and secret). Select your Keyring from the menu such as **HashiCorp** and specify your Keyring name. > [!NOTE] > **Important** > > For connectors using HashiCorp's OAuth plugin, Securiti dynamically retrieves the Credentials. For multiple accounts requiring different credential paths, you must configure separate keyrings. > > Keyrings can be linked to connectors in the following ways: > > - Multiple connectors can share the same Keyring. > - A Connector can only have one Keyring linked at a time, which can be updated during the Reconfiguration process. |
| (Optional) Custom Domain | Enable the **Custom Domain** toggle option if you want to use a full URL of your Atlassian site. > [!NOTE] > **Note** > > - Custom Domain functionality requires you to set up a minimum Pod version of release **1.132** or higher. > - Enabling this toggle requires you to enter the full **Atlassian Site URL** instead of **Site Name**. |
| Site Name or Atlassian Site URL | - In case of **Site Name**, enter the Jira site name. See an example below. *securiti-dev* - In case of **Custom Domain** option enabled above, enter the complete **Atlassian Site URL** of your custom domain. See the example below. *https://jira.acme.com* |
| Client ID | Enter the Client ID you recorded in [Create an app and obtain credentials for Jira Cloud (self-hosted) connector](/v1/docs/create-an-app-and-obtain-credentials-for-jira-cloud-self-hosted-connector). The Client ID uses string value. See the example below. *8a7b3c9d-12e4-567f-89ab-0123456789cd* |
| Client Secret | Enter the Client Secret you recorded in [Create an app and obtain credentials for Jira Cloud (self-hosted) connector](/v1/docs/create-an-app-and-obtain-credentials-for-jira-cloud-self-hosted-connector). The Client Secret uses string value. See the example below. *n3v3rU53th1s_Ke3p1tS3cur3!* |
4. Click **Test** **Connection** at the bottom of the page
5. In the popup, select the site name from the menu corresponding to one specified in the **Site Name** field during Connector Activation, as shown below.

> [!WARNING]
> **Warning**
> 
> Connector Authentication fails if the site selected from the menu does not Match the one specified during Connector Activation.

![jira_sitename.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3984e9e4-9faf-31ba-5795-ec7d9884dca4.png)
6. Click **Accept** to accept the Jira Cloud Permissions.

> [!NOTE]
> **Important**
> 
> You can only activate one Connector per site.

### Monitoring connection tests and authentication statuses

After authenticating the connector, use this section to review connection test results, verify the configured permissions, and check the authentication statuses for supported capabilities, such as Discovery scans and metadata scans.

For more information, see [Using data system connector authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scans configurations

Proceed to the following topics to configure the post-authentication scans settings for the Jira Cloud (self-hosted):

- [Configuring Data Inventory Sync for Jira Cloud](/latest/docs/configuring-data-inventory-sync-for-jira-cloud-selfhosted)
- [Configuring discovery scans in Jira Cloud](/latest/docs/configure-discovery-scans-in-jira-cloud-self-hosted)
