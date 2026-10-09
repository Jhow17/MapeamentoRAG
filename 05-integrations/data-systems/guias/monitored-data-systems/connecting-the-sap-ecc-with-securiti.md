---
title: "Connecting the SAP ECC with Securiti"
slug: "connecting-the-sap-ecc-with-securiti"
updated: 2026-07-31T11:50:40Z
published: 2026-07-31T11:50:40Z
canonical: "helpcenter.securiti.ai/connecting-the-sap-ecc-with-securiti"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connecting the SAP ECC with Securiti

This topic covers activation of the SAP ECC connector.

## Creating SAP ECC data system connector instance

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

## Authenticating SAP ECC connector

After creating a SAP ECC connector instance, in the **Authentication** tab, authenticate your connector:

1. Under the **Pod Configuration** section, from the **Select** **Pod** menu, choose the pod you configured earlier.
2. Under the **Drivers** section, select the pre-uploaded JDBC driver. For more information, see [Uploading JDBC driver files in Securiti](/latest/docs/uploading-jdbc-driver-files-in-securiti).
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

| Setting | Description |
| --- | --- |
| Host | Enter the IP address or name of the SAP Instance. > [!NOTE] > **Note** > > SAP ECC typically uses its default port. To use a non-default port, you must specify the port in **Host** field using the format below. > > /H/<hostname>/S/<port> The host name uses string value. See example below. `host.docker.internal` |
| User | Enter your username with the profile that allows you "read" access to Securiti's SAP ECC 6.0 Data system Connector for all the desired objects (tables, views, schemas, and databases). The username uses a string value. See example below. `john_securiti` |
| Password | Enter the password for the account with required access Permissions. |
| Client | Enter the client number used for Authentication of SAP ECC Instance. The client number is a 3 digit number ranging from 000 to 999. See example below. *100* |
| System Number | Enter the system number for SAP Data system. The SAP ECC system number is a 2 digit number. See example below. *00* |
| Module | Select the module that needs scanning, from the menu. For more information, see [Acquire authentication credentials in SAP ECC](/latest/docs/acquire-authentication-credentials-in-sap-ecc). The module names follow string values and are listed in the menu. See example below. `Financial Accounting and Controlling` |
| (Optional) Read Table RFC (Remote Function Call) Name | Enter the RFC (Remote Function Call) name for the function module used to read data from a Table in SAP ECC. When left blank, default RFC is used for the read operation. For more information, see [Acquire authentication credentials in SAP ECC](/latest/docs/acquire-authentication-credentials-in-sap-ecc). RFC names use an uppercase string value separated by underscores. See example below. `RFC_GET_TABLE_ENTRIES` |
| (Optional) Comma Separated Table Names | Enter any custom Table names or tables which are missed during defining SAP module to Table names mapping. For more information, see [Acquire authentication credentials in SAP ECC](/latest/docs/acquire-authentication-credentials-in-sap-ecc). The Table names use a string value. See example below. `KNA1, VBAK, MARA` |
| (Optional) Store Sample file on PCS | - **Store Sample files on PCS** toggle is disabled by default. > [!NOTE] > **Note** > > In EPod V2 deployments, Securiti disables this toggle if PCS is not configured in yourtenant. Without PCS, support for storing sample files is unavailable for structured orhybrid data systems. - Keep the toggle disabled to store table training sample files locally on the pod, ensuring they remain within your local environment. - Enable this toggle if you wish to store table training sample files in Private Cloud Storage (PCS). > [!NOTE] > **Note** > > This functionality can only be enabled if Private Cloud Storage is already configured in your tenant. In case of reconfiguring a connector, files stored prior to the reconfiguration remain in their existing location, pods or PCS, until you perform a re-scan, after which Securiti stores sample files in the newly configured location. |
| (Optional) Timeout | Specify the timeout value in seconds for request completion. The timeout value is a number. See example below. *100* |
| (Optional) Additional Connection String Options | Specify any JDBC additional string connections. You can specify multiple options separated by a semicolon ;. See the following example for connection pooling through additional string connections: `UseConnectionPooling=true;PoolMaxSize=20;PoolMinSize=10;PoolIdleTimeout=200;PoolWaitTime=200;` See the following descriptions of properties for connection pooling: UseConnectionPooling: Enables the connection pooling feature, which allows the provider to reuse existing connections instead of creating new ones for each request PoolMaxSize: Specifies the maximum number of connections allowed in the connection pool if not provided defaults to 100. Requires `UseConnectionPooling=True`. PoolMinSize : Specifies the minimum number of connections to be maintained in the connection pool at all times. Requires `UseConnectionPooling=True`. PoolIdleTimeout : Specifies the maximum idle time, in seconds, that a connection can remain in the pool before being closed. Requires `UseConnectionPooling=True`. PoolWaitTime : Specifies the maximum number of seconds a connection request waits for an available connection in the pool. Requires `UseConnectionPooling=True`. For more information, see [Troubleshooting for SAP ECC](/latest/docs/troubleshooting-for-sap-ecc). |
5. Click **Test** **Connection** at the bottom of the page

Securiti activates the Connector.

### Monitoring the overview page and authentication statuses

After authenticating the connector, in the **Overview** section:

- Review connection test results.
- Verify the configured permissions.
- Authenticate the statuses for supported capabilities.

For more information, see [Using the connectors overview page](/latest/docs/new-ui-using-connectors-overview-page).

To monitor the authentication statuses, click **View Diagnostic Report** or the **Authentication** tab. For more information, see [Using data system connector authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scan settings

Proceed to the following topics to configure the post-authentication scans settings for the SAP ECC.

- [Configure discovery scans in SAP ECC](/latest/docs/configure-discovery-scans-in-sap-ecc).
- [Fulfilling DSR requests for SAP ECC](/latest/docs/fulfilling-dsr-requests-for-sap-ecc-1).
