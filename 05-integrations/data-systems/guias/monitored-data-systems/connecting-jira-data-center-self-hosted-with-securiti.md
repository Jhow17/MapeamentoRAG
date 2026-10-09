---
title: "Connecting Jira Data Center (Self Hosted) with Securiti"
slug: "connecting-jira-data-center-self-hosted-with-securiti"
updated: 2026-09-30T09:32:56Z
published: 2026-09-30T09:32:56Z
canonical: "helpcenter.securiti.ai/connecting-jira-data-center-self-hosted-with-securiti"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connecting Jira Data Center (Self Hosted) with Securiti

This topic covers activation of the Jira Data Center (self-hosted) connector.

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

Before authenticating the Jira Data Center connector, you must meet the prerequisites described in [Jira Data Center](/latest/docs/jira-data-center-connectors). After creating a Jira Data Center data system instance, in the **Authentication** tab, authenticate your connector:

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

| Setting | Authentication method | Description |
| --- | --- | --- |
| Authentication | All | Select one of the following authentication methods from the menu: - OAuth - Personal Access Token |
| (Optional) Keyring | OAuth | Enable the **Use Keyring** toggle if you want to use Keyring to fetch your Credentials. > [!NOTE] > Note > > Keyring is not supported for the Personal Access Token authentication method. Select **HashiCorp** from the **Keyring Type** menu and select your Keyring. For more information, see [Using keyrings](/v1/docs/using-keyrings) and [HashiCorp credential vault](/v1/docs/hashicorp-credential-vault). > [!WARNING] > **Important** > > For connectors using HashiCorp's OAuth plugin, Securiti dynamically retrieves the Credentials. For multiple accounts requiring different credential paths, you must configure separate keyrings. > > Keyrings can be linked to connectors in the following ways: > > - Multiple connectors can share the same Keyring. > - A Connector can only have one Keyring linked at a time, which can be updated during the Reconfiguration process. |
| Instance URL | All | Enter the Instance URL you recorded in [Grant permissions and obtain credentials in Jira Data Center](/v1/docs/grant-permissions-and-obtain-credentials-in-jira-data-center). Instance URL uses a string value. See example below: *https://yourcompany.atlassian.net* |
| Client ID |  | Enter the Client ID you recorded earlier. Client ID uses a string value. See example below: *def456ghi* |
| Client Secret |  | Enter the Secret you recorded earlier. Client Secret uses a string value. See example below: *secretKey789* |
| Personal Access Token | Personal Access Token | Enter the personal access token you recorded earlier. See the example below. *1234ABCD5678EFGH9012IJKL3456MNOP* |
| Allow Private IP | All | Enable the Allow Private IP toggle if you are using Private IP for activating the connector. |
4. Click **Test** **Connection** at the bottom of the page.
5. Log in to your Instance if required and click **Allow** to the authorize the application.

![authorize_app.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-44408993-d89d-def7-f5f4-32a6e2407c5d.png)

Securiti activates the Connector.

### Monitoring connection tests and authentication statuses

After authenticating the connector, use this section to review connection test results, verify the configured permissions, and check the authentication statuses for supported capabilities, such as Discovery scans and metadata scans.

For more information, see [Using data system connector authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scans configurations

Proceed to the following topics to configure the post-authentication scans settings for the Jira Data Center (self-hosted):

- [Configuring discovery scans in Jira Data Center](/latest/docs/configure-discovery-scans-in-jira-data-center)
