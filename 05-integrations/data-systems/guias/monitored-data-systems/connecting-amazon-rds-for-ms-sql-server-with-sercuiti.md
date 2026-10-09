---
title: "Connecting Amazon RDS for Sql Server with Securiti"
slug: "connecting-amazon-rds-for-ms-sql-server-with-sercuiti"
updated: 2026-07-01T19:44:56Z
published: 2026-07-01T19:44:56Z
canonical: "helpcenter.securiti.ai/connecting-amazon-rds-for-ms-sql-server-with-sercuiti"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connecting Amazon RDS for Sql Server with Securiti

This topic covers activation of the Amazon RDS for Sql Server (self-hosted) connector.

## Creating an Amazon RDS for Sql Server data system connector instance

Perform the following steps to create a Data system instance for self-hosted connectors:

1. Log in to Securiti with your admin credentials.
2. To open the main menu, from the upper left corner of the left navigation bar, click the **Jewel** icon.
3. From the Platform Services section in the new navigation, select **Integrations**.
4. From the **Integrations** menu, choose **Monitored Data Systems.**
5. On the top right of the **Integrations** page, click **Add Integration** to create a new data system instance.
6. On the Add Integration page, click the **Self-Hosted** tab.
7. From the data system list, choose your relevant data system.
8. On the **Basic Information** tab, complete the following parameters:

| **Parameter** | **Explanation** | **Example** |
| --- | --- | --- |
| Instance Name | Enter a convenient name for the connector Instance. | Admin-data1 |
| Description | Add a short note to explain the purpose of this instance. | To discover and monitor data sources in the production environment. |
| Hosting Location | The **Hosting Location** is automatically set to **IaaS**. | IaaS |
| Service Provider | This field is automatically set to your data system's service provider. | AWS |
| Account ID | Enter the AWS **Account ID** for your data system account. The account ID uses an alphanumeric string value. | `1234567891011` |
| Region | Select the region from the menu. | `us-east-2` |
| Managed | Enable the toggle to differentiate between native and non-native (dark) assets. |  |
| Country | Select the **country** from the dropdown where the data source or resource is located. | `Australia` |
| (Optional) State | Select the **state** or region from the dropdown within the chosen country. | `Australian Capital Territory` |
| (Optional) City | Enter the **city** where the data source or resource is located. | `Canberra` |
| Owners | Choose **Primary** **Owner** for the Instance. By default, you are the primary owner. | `John.doe@securiti.ai` |
| (optional) Additional owners can be added after creating an instance by enabling the **Add** **Co-owner** tab on the Basic Information page. From the dropdown, select users to add as additional owners. | `Alex.doe@securiti.ai` |
| (optional) Enable the toggle for **Send Notification to all Owners** to notify owners. |  |
9. At the Bottom of the page, click **Create and Continue**.

It redirects you to the **Authentication** page.

## Authenticating the Amazon RDS for Sql Server connector

After creating an Amazon RDS for Sql Server connector instance, in the **Authentication** tab, authenticate your connector:

1. Under the **Pod Configuration** section, from the **Select** **Pod** menu, choose the pod you configured earlier.
2. Under the **Drivers** section, from the **Driver** menu, choose the latest driver.
3. > [!WARNING]
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
4. In the **Credentials** section, configure the following settings:

| Parameter | Description |
| --- | --- |
| Host | Enter the endpoint address for your Amazon RDS for SQL Server database, as described in [Prerequisites for Amazon RDS for Sql Server](/latest/docs/prerequisites-for-amazon-rds-for-ms-sql-server-en). See an example below: *<db-1234.abcdefgh.us-west-2.rds.amazonaws.com>* |
| Port | Enter the port number, as described in [Prerequisites for Amazon RDS for Sql Server](/latest/docs/prerequisites-for-amazon-rds-for-ms-sql-server-en). For SQL Server, the port number is 1433. |
| Database | Enter the database name for your RDS instance to scan. You can enter a comma-separated list of names or upload a .csv file containing database names. > [!WARNING] > Important > > The database name is case-sensitive. Enter it exactly as it appears in the data system. |
| Use SSL | Enable the toggle if SSL is on in the RDS instance and leave the toggle disabled if off, as described in [Prerequisites for Amazon RDS for Sql Server](/latest/docs/prerequisites-for-amazon-rds-for-ms-sql-server-en). |
| Additional Connection String Options | (Optional) Specify any additional JDBC string connections. You can specify multiple options separated by a semicolon ';' For more information, see the [driver guide](https://jdbc.postgresql.org/documentation/use/#connection-parameters). |
| (Optional) Use Keyring | You can enable the Use Keyring toggle if you want to use a keyring to manage credentials for the instance as described in [Managing keyrings](/modules/connectors/en/index-en.html?contextId=settingsKeyrings). Then choose the keyring type, such as HashiCorp and keyring (applies to the Self-hosted app version). - AWS Secrets Manager. See [Configuring AWS Secrets Manager](/latest/docs/configuring-credential-vaults-aws-secrets-manager-credential-vault), for more information. - CredStash. See [Configuring CredStash credential vaults](/latest/docs/configuring-credential-vaults-credstash-credential-vault), for more information. - CyberArk. See [Configuring CyberArk credential vaults](/latest/docs/cyberark-credential-vault), for more information. - HashiCorp. See [Configuring HashiCorp credential vaults](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault), for more information. |
| User | In case you are not using keyring, enter your Amazon RDS for SQL Server database username, as described in [Prerequisites for Amazon RDS for Sql Server](/latest/docs/prerequisites-for-amazon-rds-for-ms-sql-server-en). See an example below: *admin* |
| Password | Enter your Amazon RDS for SQL Server account password. |
| (Optional) Store Sample file on PCS | **Store Sample files on PCS** toggle is disabled by default. In EPod V2 deployments, Securiti disables this toggle if PCS is not configured in your tenant. Without PCS, support for storing sample files is unavailable for structured or hybrid data systems. Keep the toggle disabled to store table training sample files locally on the pod, ensuring they remain within your local environment. Enable this toggle if you wish to store table training sample files in Private Cloud Storage (PCS). This functionality can only be enabled if Private Cloud Storage is already configured in your tenant. In case of reconfiguring a connector, files stored prior to the reconfiguration remain in their existing location, pods or PCS, until you perform a re-scan, after which Securiti stores sample files in the newly configured location. |
5. Click **Test** **Connection** at the bottom of the page

Securiti activates the connector.

### Monitoring the Overview page and authentication statuses

After authenticating the connector, in the **Overview** section:

- Review connection test results.
- Verify the configured permissions.
- Authenticate the statuses for supported capabilities.

For more information, see [Using the connectors overview page](/latest/docs/new-ui-using-connectors-overview-page).

To monitor the authentication statuses, click **View Diagnostic Report** or the **Authentication** tab. For more information, see [Using data system connector authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scans settings

Proceed to the following topics to configure the post-authentication scans settings for the Amazon RDS for Sql Server:

- [Configure discovery scans in Amazon RDS for Sql Server](/latest/docs/configure-discovery-scan-in-amazon-rds-for-mysql)
- [Fulfilling DSR requests in Amazon RDS for Sql Server](/latest/docs/fulfilling-dsr-requests-in-amazon-rds-for-ms-sql-server-en)
- [Table training for structured and hybrid data systems](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems)
