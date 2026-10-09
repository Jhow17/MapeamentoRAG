---
title: "Connecting the Oracle Eloqua (Self Hosted) with Securiti"
slug: "connecting-the-oracle-eloqua-self-hosted-with-securiti"
updated: 2026-05-25T21:00:10Z
published: 2026-05-25T21:00:10Z
canonical: "helpcenter.securiti.ai/connecting-the-oracle-eloqua-self-hosted-with-securiti"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connecting the Oracle Eloqua (Self Hosted) with Securiti

This topic covers activation of the Oracle Eloqua Marketing Automation (self-hosted) connector.

## Creating an Oracle Eloqua data system connector instance

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

## Authenticating Oracle Eloqua Marketing Automation (Self-hosted) connector

After creating an Oracle Eloqua Marketing Automation connector instance, in the **Authentication** tab, authenticate your connector:

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

| Setting | Authentication Type | Description |
| --- | --- | --- |
| Authentication Type | N/A | From the **Authentication Type**, select the following supported methods: - **OAuth App** - **Basic** > [!NOTE] > Note > > Basic authentication method is only supported for pod version 1.146.0 and above. |
| Use Keyrings | Basic | From the **Keyring Type**, select the following supported keyring types: - **CyberArk Conjur**: For more information, see [CyberArk Conjur credential vault](/latest/docs/configuring-credential-vaults-cyberark-conjur-credential-vault). - **Hashicorp**: For more information, see [HashiCorp credential vault](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault). > [!NOTE] > Note > > Keyring support for Basic authentication method is only supported for pod version 1.146.0 and above. |
| After selecting the Keyring Type, select the **keyring**. For more information on keyrings, see [Using keyrings](/latest/docs/managing-credentials-using-keyrings) |
| Client ID | OAuth App | Enter the Application ID you recorded earlier in [Prerequisites for Oracle Eloqua (Self-hosted)](/latest/docs/grant-permissions-and-obtain-credentials-in-oracle-eloqua). The **Client ID** uses a string value. See an example below. `12345678-abcd-1234-efgh-123456abcdef` |
| Client Secret | OAuth App | Enter the **Client Secret** you recorded earlier in [Prerequisites for Oracle Eloqua (Self-hosted)](/latest/docs/grant-permissions-and-obtain-credentials-in-oracle-eloqua). The Client Secret uses a string value. See an example below. `aB8C~Dsr.10yXyu~a4VAAAAp8ZRTJBA.zlAcy~` |
| Username | Basic | Enter the Username you use to login to the Oracle Eloqua account. See the example below: `Alex.securiti` |
| Password | Basic | Enter the Password for your Oracle Eloqua account. See the example below: `Securiti@123` |
| Company Name | Basic | Enter the Company name for your Oracle Eloqua account. See the example below: `SecuritiSciences` |
| URL | - OAuth App - Basic | Enter the **Base URL** you recorder earlier in [Prerequisites for Oracle Eloqua (Self-hosted)](/latest/docs/grant-permissions-and-obtain-credentials-in-oracle-eloqua). |
4. Click **Test** **Connection** at the bottom of the page

On the Oracle Eloqua’s consent screen, click **Accept** to grant access consent.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-19 at 1.12.03 PM.png)

Your connector is now activated.

### Monitoring the Overview page and authentication statuses

After authenticating the connector, in the **Overview** section:

- Review connection test results.
- Verify the configured permissions.
- Authenticate the statuses for supported capabilities.

For more information, see [Using the connectors overview page](/latest/docs/new-ui-using-connectors-overview-page).

To monitor the authentication statuses, click **View Diagnostic Report** or the **Authentication** tab. For more information, see [Using data system connector authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scans settings

Proceed to the following topics to configure the post-authentication scans settings for the Oracle Eloqua Marketing Automation (self-hosted):

- [Configure discovery scans in Oracle Eloqua](/latest/docs/configure-discovery-scans-in-jira-data-center-1).
- [Table training for structured and hybrid data systems](/latest/docs/table-training-for-structured-and-hybrid-data-systems).
- [Fulfilling DSR requests for Oracle Eloqua](/latest/docs/fulfilling-dsr-requests-for-oracle-eloqua).
