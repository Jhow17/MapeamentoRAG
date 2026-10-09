---
title: "Connecting CockroachDB with Securiti"
slug: "activate-the-cockroachdb-connector-in-securiti-en"
updated: 2026-07-02T21:15:55Z
published: 2026-07-02T21:15:55Z
canonical: "helpcenter.securiti.ai/activate-the-cockroachdb-connector-in-securiti-en"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connecting CockroachDB with Securiti

> [!NOTE]
> Important
> 
> Securiti stores sensitive connector credentials in an encrypted and base64-encoded form. For self-hosted connectors, these credentials reside on your pod and are also stored in the Securiti cloud. A credential vault can also be used to store credentials for self-hosted connectors. If a vault is being used, credentials are retrieved securely from the vault at runtime on your pod and are not stored in the cloud.
> 
> For Securiti Cloud-hosted connectors, credentials are securely stored within the Securiti cloud only.

This article covers the connector activation process for the CockroachDB self-hosted connector.

## Creating a CockroachDB connector instance

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

## Authenticating the CockroachDB connector

After creating a CockroachDB connector instance, on the **Authentication** tab, authenticate your connector by configuring the following settings:

| Parameter | Description |
| --- | --- |
| Driver Files | From the **Driver Files** menu, select the driver file you previously uploaded. Or click **Go to driver file library** to upload it. For more information, see [Uploading JDBC driver files in Securiti](/latest/docs/uploading-jdbc-driver-files-in-securiti). |
| Connect with Pod | From the **Connect with Pod** menu, select the pod you configured earlier. |
| PCS Destination | > [!WARNING] > Important > > - If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation. From the **PCS Destination** menu, select one of the configured PCS to store this data system connector's sensitive data, such as: - Table Training Sample files - Sensitive Data Intelligence protection evidence files - Scan Summary > [!NOTE] > Note > > DSR Automation, Assessment Automation, and the transient metadata used during scanning continue to use the Default PCS configured for your tenant until those modules adopt multi-PCS support. You can also migrate the data from one PCS to another while reconfiguring the connector. To migrate data from one PCS to another: 1. On the activated data system instance, click on the **Reconfigure** link. 2. From the **PCS Destination** menu, select the PCS where you want to migrate the data. 3. Click **Reconfigure connector**. Securiti shows you the migration progress bar to check the status of migration. Sensitive data is stored on the existing PCS bucket until the migration is complete. |
| Host | Enter the IP address or hostname of your CockroachDB database you recorded in [Obtain database credentials for your CockroachDB configuration](/latest/docs/obtain-database-credentials-for-your-cockroachdb-configuration). See an example below. `demo-cluster-00000.x00.aws-us-east-1.cockroachlabs.cloud` |
| Port | Enter the network access port for your database. See an example below. `26257` |
| User | Enter the username for the account with administrative access. See an example below. `john_securiti` |
| Password | Enter the password for the account with administrative access. |
| Default Database | Enter the name of a default database the server uses to connect when no database list is provided. This database is then used to fetch the list of all available databases. > [!NOTE] > **Note** > > If both the **Default Database** and **Database** fields are empty, Securiti connects to the database that matches the username. |
| Database | Enter the name or names of the databases you want to scan. You can enter a comma-separated list of names, or upload a CSV file containing the database names. > [!NOTE] > **Important** > > The database name is case-sensitive. Enter it exactly as it appears in the data system. |
| (Optional) Additional Connection String Options | Specify any additional JDBC string connections. You can specify multiple options separated by an ampersand `&amp;`. |
| (Optional) Use Keyring | Enable the toggle and from the **Keyring Type** menu, choose your preferred vault. CockroachDB supports the following keyring: - HashiCorp. For more information, see [Configuring HashiCorp credential vaults](/latest/docs/configuring-hashicorp-credential-vaults). |
| (Optional) Store Sample file on PCS | - **Store Sample files on PCS** toggle is disabled by default. > [!NOTE] > **Note** > > In EPod V2 deployments, Securiti disables this toggle if PCS is not configured in yourtenant. Without PCS, support for storing sample files is unavailable for structured orhybrid data systems. - Keep the toggle disabled to store table training sample files locally on the pod, ensuring they remain within your local environment. - Enable this toggle if you wish to store table training sample files in Private Cloud Storage (PCS). > [!NOTE] > **Note** > > This functionality can only be enabled if Private Cloud Storage is already configured in your tenant. In case of reconfiguring a connector, files stored prior to the reconfiguration remain in their existing location, pods or PCS, until you perform a re-scan, after which Securiti stores sample files in the newly configured location. |

At the bottom of the page, click **Test Connection**. Securiti authenticates the connector.

### Monitoring the overview page and authentication statuses

After authenticating the connector, in the **Overview** section:

- Review connection test results.
- Verify the configured permissions.
- Authenticate the statuses for supported capabilities.

For more information, see [Using the connectors overview page](/latest/docs/new-ui-using-connectors-overview-page). To monitor the authentication statuses, click **View Diagnostic Report** or the **Authentication** tab. For more information, see [Using data system connector authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scan settings

Proceed to the following topics to configure post-authentication scan settings for CockroachDB:

- [Fulfilling DSR requests for CockroachDB](/latest/docs/fulfilling-dsr-requests-for-cockroachdb)
- For information on table training for the CockroachDB data system, see [Table training for structured and hybrid data systems](/v1/docs/table-training-for-structured-and-hybrid-data-systems).
