---
title: "Connecting ServiceNow Tables with Securiti"
slug: "connecting-servicenow-tables-with-securiti"
updated: 2026-09-21T10:21:33Z
published: 2026-09-21T21:00:02Z
canonical: "helpcenter.securiti.ai/connecting-servicenow-tables-with-securiti"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connecting ServiceNow Tables with Securiti

> [!NOTE]
> Note
> 
> Securiti stores sensitive connector credentials in an encrypted, base-64-encoded form. For self-hosted connectors, these credentials reside on your pod and are also stored in the Securiti cloud. A credential vault can also be used to store credentials for self-hosted connectors. If a vault is being used, credentials are retrieved securely from the vault at runtime on your pod and are not stored in the cloud.
> 
> 
> 
> For Securiti Cloud-hosted connectors, credentials are securely stored only in the Securiti cloud.

This topic covers activation of the ServiceNow Tables (Self-hosted) connector.

## Creating a ServiceNow Tables Data system instance

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

## Authenticating ServiceNow Tables connector

After creating ServiceNow Tables (Self-hosted) connector instance, in the **Authentication** tab, authenticate your connector:

- Under the **Pod Configuration** section, from the **Select** **Pod** menu, choose the pod you configured earlier.
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

| Setting | Authentication Method | Description |
| --- | --- | --- |
| Authentication Type | N/A | Select from the supported authentication types: - ***Basic*** - ***0Auth 2.0*** - ***OAuth JWT*** |
| Instance ID | - Basic - OAuth 2.0 - *OAuth JWT* | Enter the Instance (name) ID of your ServiceNow Instance you acquired in [Grant permissions and obtain credentials in ServiceNow Tables](/latest/docs/grant-permissions-and-obtain-credentials-in-servicenow-tables) or [Obtain authentication credentials using OAuth JWT authentication in ServiceNow Tables](/latest/docs/obtain-authentication-credentials-using-oauth-jwt-authentication-servicenow). See the example below `Dev12345` |
| (Optional) Use Keyring | Basic | Enable the **Use Keyring** toggle if you have used a Credential vault to store the Keyring. |
| From the **Keyring Type** dropdown, select one of the following supported keyrings. **CredStash**: For more information, see [CredStash credential vault](/latest/docs/configuring-credential-vaults-credstash-credential-vault) |
| From the **Keyring** dropdown, select the keyring configured under the selected type. |
| User | - Basic - OAuth 2.0 - *OAuth JWT* | If not using keyring, enter your ServiceNow account username. |
| Password | - Basic - OAuth 2.0 | If not using keyring, enter your ServiceNow account password. |
| Client ID | - OAuth 2.0 - *OAuth JWT* | Enter the client ID you acquired in [Grant permissions and obtain credentials in ServiceNow Tables](/latest/docs/grant-permissions-and-obtain-credentials-in-servicenow-tables) or [Obtain authentication credentials using OAuth JWT authentication in ServiceNow Tables](/latest/docs/obtain-authentication-credentials-using-oauth-jwt-authentication-servicenow). The Client ID uses string value. See the example below. `8a7b3c9d-12e4-567f-89ab-0123456789cd` |
| Client Secret | - OAuth 2.0 - *OAuth JWT* | Enter the secret you acquired in [Grant permissions and obtain credentials in ServiceNow Tables](/latest/docs/grant-permissions-and-obtain-credentials-in-servicenow-tables) or [Obtain authentication credentials using OAuth JWT authentication in ServiceNow Tables](/latest/docs/obtain-authentication-credentials-using-oauth-jwt-authentication-servicenow). The Client Secret uses string value. See the example below. `A1x$pL9!zQ&amp;vW2rT` |
| Private Key | *OAuth JWT* | Upload JWT signing certificate/private key file for OAuth JWT authentication. It should be a valid PEM file. For more information, see [Obtain authentication credentials using OAuth JWT authentication in ServiceNow Tables](/latest/docs/obtain-authentication-credentials-using-oauth-jwt-authentication-servicenow).. |
| (Optional) Private Key Password | OAuth JWT | Enter the password for the Private Key, required only if the uploaded key is password-protected. |
| (Optional) Additional Connection String Options | - Basic - OAuth 2.0 - *OAuth JWT* | Specify any JDBC additional string connections. You can specify multiple options separated by a semicolon ';'. |
- Click **Test** **Connection** at the bottom of the page
- Securiti redirects you to your Instance's Authentication page in ServiceNow.

> [!WARNING]
> Important
> 
> - OAuth JWT authentication connects ServiceNow to Securiti without any human intervention.
> - For OAuth authentication, ServiceNow lets you create [admin](/latest/docs/grant-permissions-and-obtain-credentials-in-servicenow-tables) and [non-admin](/latest/docs/configuration-steps-for-non-admin-users-in-servicenow-tables) user accounts. Configure and update permissions based on the user type. In this step, when redirected, authenticate using the credentials for that user.

![ServiceNow_ConnectorAuth.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ef75b302-35f9-361b-a657-3ec7bda5a0c3.png)

Click **Allow**.

ServiceNow redirects you back to Securiti. You have finished activating the Connector.

### Monitoring the Overview page and authentication statuses

After authenticating the connector, in the **Overview** section:

For more information, see [Using the connectors overview page](/latest/docs/new-ui-using-connectors-overview-page).

To monitor the authentication statuses, click **View Diagnostic Report** or the **Authentication** tab. For more information, see [Using data system connector authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scans settings

Proceed to the following topics to configure the post-authentication scans settings for the ServiceNow Tables (Self-hosted):
  - Review connection test results.
  - Verify the configured permissions.
  - Authenticate the statuses for supported capabilities.
- [Configuring discovery scans in ServiceNow Tables](/latest/docs/configuring-discovery-scans-in-servicenow-tables).

**Additional resources**

- [Fulfilling DSR requests in ServiceNow Tables](/latest/docs/fulfilling-dsr-requests-in-servicenow-tables).
- [Table training for structured and hybrid data systems](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems).

A collection of organized data or repositories and their corresponding management software, which could be IaaS, SaaS, or SQL. Data systems are configured in Securiti so that it can help you protect sensitive data and also locate personal data for data subjects who submit DSR requests. Data systems can be monitored, un-monitored, or user-defined. For each monitored or user-defined data system, you configure a connector that Securiti uses to interact with the data system.

A secure container for storing cryptographic keys or login credentials. See Managing keyrings, for more information.
