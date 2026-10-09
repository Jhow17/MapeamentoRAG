---
title: "Configuring Third Party EDCs"
slug: "configuring-third-party-edcs"
updated: 2026-06-10T15:18:23Z
published: 2026-06-10T15:18:23Z
canonical: "helpcenter.securiti.ai/configuring-third-party-edcs"
stale: true
area: platform
modulo: system-settings
tipo: guia
data_captura: 2026-10-08
---

# Configuring Third Party EDCs

Third Party EDCs (Third party enterprise data catalogs) let you select what metadata is to be synced and to map it to the target data model. This integration augments the catalog’s metadata with Securiti's metadata such as data classification.

Third Party EDCs can significantly enhance data management, governance, and security efforts. They ensure that data is protected, compliant with privacy regulations, and used effectively to achieve your company's mission while maintaining the trust of your customers and partners.

### Prerequisites

- You must have an [active pod](/v1/docs/securiti-pods-and-elastic-pods) to configure the integration.
- You must have a subscription to Securiti’s Sensitive Data Intelligence module to synchronize data assets in Collibra.
- You must configure data sources in Collibra using Collibra’s Edge server.
- You must have [relevant global and resource permissions](/v1/docs/configuring-third-party-edcs) in Collibra for successful asset syncing and mapping.

### Scope

The Third Party EDCs capability is supported for the following data systems:

- AWS RDS
- Amazon Aurora Postgres
- Amazon RDS MariaDB
- GCP PostgreSQL
- GCP SQL Server
- Google BigQuery
- MySQL
- Oracle
- PostgreSQL
- SQL Server
- Snowflake

### Integrating Securiti with Collibra

This section involves a step-by-step procedure to successfully sync and map data assets from Securiti to Collibra.

1. In Securiti, click **Settings**, then choose **Enterprise Data Catalog > EDC Ingestion**.

The Third Party EDCs page lets you configure and manage third party integrations. It lists the supported third party EDCs and available data catalogs.

> [!NOTE]
> **Note**
> 
> Only users with Super admin and Org admin privileges can access this page.
2. On the **Third Party Data Catalogs** page, do one of the following:
  - If you have not yet created any instance, click **Create Instance**.
  - If you already have at least one instance, near the upper right corner of the instance, click **+** to create a new instance.
3. On the **Basic Information** tab, apply the following settings:

| Setting | Description |
| --- | --- |
| Instance Name | Enter a convenient name for the instance. We recommend using the application name you entered when configuring the application in Collibra. |
| Instance Location | Configure your instance location by providing the following details: - Hosting location - Country - State / Region - City |
| Owners | Choose primary and co-owners for the instance. By default, you are the instance owner. - You can enable **Add co-owner** toggle and select co-owner from the menu. - You can enable **send notifications to all owners** toggle to send notifications. |
4. Click **Create Instance & Continue** to set up the connector.

The Connector tab contains the necessary attributes to successfully connect to the Collibra. Apply the following settings as shown below:

| Setting | Description |
| --- | --- |
| Connect with pod | Choose the Securiti pod to connect with the data system instance. |
| Base URL | Enter the base URL of Collibra. For example: `https://example.collibra.com` |
| Username | Enter a username that is a unique identifier for a specific user within the Collibra platform. It is used to distinguish one user from another. You must have the following global and resource permissions in Collibra for successful assets syncing and mapping: - Global permissions - Resources Resources permission lets you view and manage assets, domains and communities. You must have the following Import and Export resource global permissions: - **Import**: You must have import permission to import assets or complex relations. With this role you can also create or edit communities and domains that are related to the imported assets. - **Export**: You must have export permission to export assets or complex relations and their characteristics. - **Edge**: The Edge global permission lets you install and manage Edge sites. - **View Edge connections & capabilities**: With this permission you can open and see the connections and capabilities of an Edge site. - Resource permissions - **Community**: You must have create, update, and remove permissions for communities. - **Domain**: You must have create, update and delete permissions for domains. - **Asset**: You must have create, update and delete permissions for assets. - **Attribute**: You must have permissions to create, update, and delete characteristics of assets. |
| Password | Enter password which is associated with a user's username. |
| Logging level | Logging levels categorize and prioritize log messages generated in the [Logs tab](/v1/docs/configuring-third-party-edcs). Each level corresponds to a specific type of message, that lets you filter and manage logs more effectively. Choose from among the following logging levels: - **Debug**: Debug-level logs provide a detailed debugging information. They provide debug level information to help troubleshoot connectivity, key or data model issues. Under this logging level you can view all types of logs including info, warning and errors. - **Info**: Info-level logs provide informational level details about important events like successful operations, or the completion of critical task. Under this logging level you can view all types of logs except debug. - **Warning**: Warning-level logs indicate potential issues or anomalies that do not prevent the application from functioning but should be monitored. These logs are often used to highlight non-fatal problems. Under this logging level you can view warning and error logs. - **Error**: Error-level logs represent critical issues or failures that can prevent the application from operating as intended. Under this logging level you can view error logs. |
5. Click **Authenticate & Activate Connector**.

Securiti authenticates the connection with Collibra.

> [!NOTE]
> **Note**
> 
> - Click **More Options** to deactivate the connector instance.
> - Click **Reconfigure** to reconfigure the connection. You must have an active pod for reconfiguration.
6. Proceed to **Integration Configurations**.
  1. On the **Integration Configurations** page, apply the following settings as shown below:

| Section | Inner section | Description |
| --- | --- | --- |
| Entity Type to Synchronization | Entity type | Select the entity type from the menu. This determines the fields to be used in Collibra. Currently, you can select a table, column or table and column. - If you select the table from the menu, then table-level attributes and properties will be synced. In this case, you don't have to create or update any columns or update their metadata. You can only select table-level attributes to sync, for example, content_profile. - If you select the column from the menu, then both table and column-level attributes and properties will be synced. In this case, columns are also created against a table. You can only select column-level attributes to sync e.g. data_elements. - If you select the table and column from the menu, then, in this case, both table attributes for example, content profiles and processing purpose, and column attributes for example, data elements get synced. |
|  | Collibra community | Select Collibra community from the menu. A community is a grouping of other communities and domains. It often corresponds to functional divisions in a company and works best if it is aligned with the company's governance organization. |
|  | Instance mapping | Instance mapping lets you select one or multiple instances of TPEDCs that will be available to the discovery scans for syncing the assets. For example, if you have mapped **sqlserver1** and **sqlserver2** in the instance mapping, only these will be available to the discovery scans for syncing. - From the **Securiti** menu, select instance created in the Securiti platform. - From the **Collibra** menu, select the instance created in Collibra. > [!NOTE] > **Note** > > Click **+ Add Instance Mapping** to add multiple instances. |
|  | Attribute mapping | Attribute mapping lets you map the attributes that you want to keep in sync. - From the **Securiti** menu, select the attributes created in the Securiti platform. - From the **Collibra** menu, select the Collibra attribute. > [!NOTE] > **Note** > > Click **+ Add Attribute Mapping** to add multiple attributes. For each attribute the direction of the sync is selected as **Securiti -> Collibra**. The other two options are not selectable. Currently, only Securiti to Collibra integration is supported. This means you can only sync metadata from **Securiti** to **Collibra**. |
| Scheduling | Scan trigger | **Scan Trigger** option is pre-selected. This means in order to execute this instance, you must configure and run the scan for each data system Instance configured above. Once the scan is finished, the sync gets started. |
| Run manually | Select this option to synchronize the Collibra instance manually. By choosing this option you can activate and deactivate, and start the sync manually at any time. |
| Run on periodic schedule | Select this option to synchronize the Collibra instance based on the user-defined schedule. You can set the specific time for your scan, choose Daily, Weekly, or Monthly from the Periodic Schedule Frequency, and specify any time of the day, week, or month. - You can also select Custom Cron from the Periodic Schedule Frequency to schedule tasks in Unix-like operating systems. - Enter the expression in the Cron Expression Builder. You can get assistance from the [expression builder](/v1/docs/securiti-pods-and-elastic-pods) to create the expression. Mark the **Create new assets if not present at target data catalog** checkbox to create assets in the target data catalog that are present only in Securiti platform. |
  2. Once done, on the upper right corner of the page, click **Save**.

> [!NOTE]
> **Note**
> 
> If you don’t save the configuration settings, you cannot create the Collibra instance successfully. And ultimately, you cannot search for the configured Collibra instance while [creating the discovery scan](/v1/docs/discovery-scans).
7. Near the top of the page, click the **Audit Trail** tab.

The **Audit Trail** tab lets you view what was modified by whom and when. Particularly, you can capture:
  - Time
  - User
  - Activity
  - Message
  - Click on any row to see the following details:
    - **Object type** - Represents which area this audit trail belongs to.
    - **Session Id** - Associated with user's current login session.
    - **Changed values** - Change in the values as a result of this audit trail activity.
    - **Message description** - The message for this audit trail activity.
    - **IP address** - IP Address of the system from which the activity was generated.
    - **User agent** - Information about the environment you are using to interact with Collibra.
8. Near the top of the page, click the **Logs** tab.

Logs tab lets you view the logs of the activity performed by the integration. This helps you troubleshoot connectivity or other issues, especially API payloads and responses. You can also view the statistics of the integration as well.

The statistics include:

> [!NOTE]
> **Note**
> 
> - Click the download icon to download the logs of each sync in a CSV file.
> - Click **Options (three dots) > Cancel** to cancel in-progress manual syncs. This removes the limitation that prevented new manual syncs from being executed because a previous sync was stuck in progress. Although various conditions might cause a sync to get stuck, the **Cancel** option provides a way to forcefully stop the problematic process. Once canceled, the **Run Now** button is re-enabled for all scheduled sync types, allowing you to resume normal operations.
  - Number of runs
  - Assets (Databases, schemas, tables, columns) created, updated, or removed on Collibra
  - List of changes by source

### Synchronizing data assets in Collibra

1. In Securiti, open the **Sensitive Data Intelligence** module and choose **Scan Definitions > Discovery Scan**.
2. [Configure the discovery scan](/v1/docs/discovery-scans) for the selected data system.
3. Scroll down at the bottom of the page.
4. Expand the **Responses** section and enable **Synchronize Data Assets in the Third Party Data Catalogs** section.
5. From the **Select Integrations** menu, select the Collibra instance that you configured in the **Connector** tab.
6. Mark the **Create assets in Third Party Data Catalog** if they do not exist checkbox.

This creates assets (databases, schemas, tables and columns) that are discovered by the scan and are not present in Collibra. However, if you unmark the checkbox, then you can only update the attributes but cannot create assets.
7. Scroll up the page and on the top right corner of page, click **Finish and Activate** to create the discovery scan.
8. On the **Discovery Scans List** page, run the scan for the configured discovery scan to discover assets.
9. Once the discovery scan completes, login to your Collibra account to view the synced metadata.

## Related

- [Managing organizations](/system-settings-managing-organizations.md)
