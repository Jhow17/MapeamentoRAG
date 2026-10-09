---
title: "Connecting Cloudera Impala with Securiti"
slug: "activate-the-cloudera-impala-connector-in-securiti"
updated: 2026-07-02T21:17:08Z
published: 2026-07-02T21:17:08Z
canonical: "helpcenter.securiti.ai/activate-the-cloudera-impala-connector-in-securiti"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connecting Cloudera Impala with Securiti

> [!NOTE]
> Note
> 
> Securiti stores sensitive connector credentials in an encrypted, base-64-encoded form. For self-hosted connectors, these credentials reside on your pod and are also stored in the Securiti cloud. A credential vault can also be used to store credentials for self-hosted connectors. If a vault is being used, credentials are retrieved securely from the vault at runtime on your pod and are not stored in the cloud.
> 
> 
> 
> For Securiti Cloud-hosted connectors, credentials are securely stored only in the Securiti cloud.

This article covers the connector activation process for the Cloudera Impala self-hosted connector.

## Creating a Cloudera Impala connector instance

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

## Authenticating the Cloudera Impala connector

After creating a Cloudera Impala connector instance, on the **Authentication** tab, authenticate your connector by configuring the following settings:

| Parameter | Description |
| --- | --- |
| Connect with Pod | From the **Connect with Pod** menu, select the pod you configured earlier. |
| PCS Destination | > [!WARNING] > Important > > - If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation. From the **PCS Destination** menu, select one of the configured PCS to store this data system connector's sensitive data, such as: - Table Training Sample files - Sensitive Data Intelligence protection evidence files - Scan Summary > [!NOTE] > Note > > DSR Automation, Assessment Automation, and the transient metadata used during scanning continue to use the Default PCS configured for your tenant until those modules adopt multi-PCS support. You can also migrate the data from one PCS to another while reconfiguring the connector. To migrate data from one PCS to another: 1. On the activated data system instance, click on the **Reconfigure** link. 2. From the **PCS Destination** menu, select the PCS where you want to migrate the data. 3. Click **Reconfigure connector**. Securiti shows you the migration progress bar to check the status of migration. Sensitive data is stored on the existing PCS bucket until the migration is complete. |
| User | Enter the username you created in [Create a user in Cloudera Impala database instance](/latest/docs/create-a-user-in-cloudera-impala-database-instance). See an example below. `Securiti-user` |
| Password | Enter the password you recorded in [Create a user in Cloudera Impala database instance](/latest/docs/create-a-user-in-cloudera-impala-database-instance). |
| Server | Enter your Cloudera Impala database instance server IP you recorded in [Create a user in Cloudera Impala database instance](/latest/docs/create-a-user-in-cloudera-impala-database-instance). The server IP follows this format. `111.222.111.22` |
| Port | Enter the port for your Cloudera Impala instance. The default port is `21050`. |

At the bottom of the page, click **Test Connection**. Securiti authenticates the connector.

### Monitoring the overview page and authentication statuses

After authenticating the connector, in the **Overview** section:

- Review connection test results.
- Verify the configured permissions.
- Authenticate the statuses for supported capabilities.

For more information, see [Using the connectors overview page](/latest/docs/new-ui-using-connectors-overview-page). To monitor the authentication statuses, click **View Diagnostic Report** or the **Authentication** tab. For more information, see [Using data system connector authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scan settings

Proceed to the following topics to configure post-authentication scan settings for Cloudera Impala:

- [Fulfilling DSR requests in Cloudera Impala](/latest/docs/fulfilling-dsr-requests-in-cloudera-impala)
- For information on table training for the Cloudera Impala data system, see [Table training for structured and hybrid data systems](/v1/docs/table-training-for-structured-and-hybrid-data-systems).
