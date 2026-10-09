---
title: "Using EDC Sources"
slug: "using-edc-sources"
updated: 2026-09-17T20:07:30Z
published: 2026-09-21T21:00:02Z
canonical: "helpcenter.securiti.ai/using-edc-sources"
area: governance
modulo: enterprise-data-catalo
tipo: guia
data_captura: 2026-10-08
---

# Using EDC Sources

**Scenario**

As a Data Governance Officer, you must show how data moves between Snowflake tables before you approve it for downstream use. Table definitions alone do not reveal that, so you trace the transformations by hand and still miss relationships that only appear at query time. With EDC Ingestion, you configure the Snowflake connector to read query history logs and extract enhanced lineage, such as a reporting table built from three upstream sources. Every relationship lands in the catalog automatically, giving you an accurate, end-to-end view of your data flows.

## Exploring EDC ingestion dashboard

EDC Ingestion brings metadata from external systems into the Enterprise Data Catalog. Securiti's native discovery scans cover a defined set of data systems. EDC Ingestion extends that reach. You connect a source and extract its metadata, including databases, schemas, tables, and lineage. Those assets then become searchable and governable alongside everything else in the catalog. This is how you catalog sources that native discovery does not support, such as ETL tools like DBT or BI models from Looker.

To open EDC Ingestion new experience:

1. On the Securiti **Dashboard** in the left side navigation, click the **Main Menu** icon.
2. On the **New Navigation** sidebar, choose **Integrations** > **EDC Sources**.

![Securiti dashboard showing integrations and monitored data systems with highlighted EDC Sources.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-17 at 4.31.09 PM.png)

### EDC ingestion prerequisites

You must whitelist the appropriate URL for outbound access, based on your region:

- edc.app.securiti.ai

For US region
- edc.app1.securiti.ai

For US (GCP) region
- edc.app2.securiti.ai

For Jakarta region
- edc.app3.securiti.ai

For Montreal region
- edc.app4.securiti.ai

For Sydney region
- edc.app5.securiti.ai

For UAE region
- edc.app6.securiti.ai

For Mumbai region
- edc.app.eu.securiti.ai

For EU region
- edc.app7.securiti.ai

For KSA region
- edc.app8.securiti.ai

For Qatar region

EDC ingestion plugins runs on your’s on-premise pod and make outbound API calls to one of the above URLs, depending on your region.

- Before starting an EDC ingestion job, ensure that the pod has at least **6 GB** of free memory.
- To work with EDC ingestion, you must have the **Manage Metadata Ingestion** permission enabled for your account. For more information, see [EDC RBAC](/latest/docs/edc-rbac-permissions-and-roles).

### Filtering integrations

- At the top of the page, there is a Filter Bar. It displays the filters currently applied to the list. When no filters are applied, the bar reads Filters appear here. Start by adding one. Click the + icon to add a filter.

To add the filter:

The filter panel lets you narrow the list of integrations by status or by integration type.

**Filtering by status**

1. In the filter bar, click the **+** icon.
2. In the **Properties** list, click **Status**.
3. Confirm the operator. **is one of** matches any of the selected values.
4. Select the checkbox for each status you want to include.
5. Click **Apply**.

**Filtering by integration type**

1. In the filter bar, click the **+** icon.
2. In the **Properties** list, click **Integration Type**.
3. Confirm the operator. **is equal to** matches the exact value you enter.
4. In **Enter Value**, type the integration type and press **Enter**.
5. Click **Apply**.

![Integration settings showing various data systems and their statuses for management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-17 at 4.35.40 PM.png)

Changing or clearing the filter

- To change a filter, click it in the filter bar and adjust the selected values.
- To clear a filter, remove it from the filter bar. To discard selections without applying them, click Cancel.

### Exploring monitored data systems

This section of the EDC ingestion dashboard is the inventory of every data system connector configured in your tenant. Use it to review connector activation and scan readiness, and to identify unmonitored or partially configured systems.

![Integration status overview showing various data sources and their current statuses.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-17 at 4.33.58 PM.png)

- At the top, the search bar lets you enter an instance name or a data system type. The table filters as you type. To narrow the list further, use the filter bar.
- Below the search bar, the statistics tiles describe your connector inventory:

| Tile name | Description |
| --- | --- |
| Configured connectors | The number of connectors that have been set up in the tenant. |
| Active connectors | The number of configured connectors that are currently active. |
| Securiti-cloud hosted connectors | The number of connectors that run on Securiti cloud. |
| Self-hosted connectors | The number of connectors that run on your own appliance. |

Each row below the statistics tiles, each row represents one connector instance. The details of the column of the table are as follows:

| **Column** | **Description** |
| --- | --- |
| Instance Name | The name assigned to the connector instance. |
| Status | Whether the instance is **Active**, **Inactive**, **In Progress**, or **Auth Failed**. |
| Data System Type | The data system the connector connects to, with its platform icon. For example, Snowflake, PostgreSQL, or SQL Server. |
| Data System Hosting | Where the data system is hosted. For example, **Private Cloud** or **SaaS**. |
| Connector Type | Whether the connector runs on **Securiti Cloud** or is **Self-Hosted**. |
| Authenticated | Whether the connector authenticated successfully with the data system. |
| Data Inventory Sync | The state of the **Data Inventory Sync** for the instance. |
| Scoping Inventory Sync | The state of the **Scoping Inventory Sync** for the instance. |
| Discovery Scan | The state of the **Discovery Scan** for the instance. |

#### Adding an integration

1. At the top right corner of the page, click **Add Integration**.

![Integration options for AWS, Azure, and GCP with various data sources listed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-08 at 3.54.04 PM.png)

1. Locate the integration you want to add. Enter its name in the search field, or scroll to its category.
2. Click the integration card.
3. On the setting page, configure the following details:

| Setting | Description |
| --- | --- |
| Basic information | 1. In **Instance Name**, enter a name for the instance. This field is required, and the name appears in the **Instance Name** column on the **EDC Ingestion** page. 2. In **Description**, enter a brief description of what the instance ingests. This field is optional. 3. Click **Create and Continue**. ![Basic Information section for integration setup with instance name and description fields.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-08 at 4.04.00 PM.png) |
| Authentication | The Authentication step is where you tell Securiti where to run the connector and how to connect to the source. The fields shown below are for Redshift; they differ by source. **Configuring connection** - **Select Pod** — the pod the connector runs on. The pod must have network access to the source. - **Host and Port** — the host and port where the source is running, for example `redshift:5439`. The host must be reachable from the network where the connector runs, or allowed through an IP allow list or AWS PrivateLink. - **Database** — the database to ingest metadata for. - **Username** — the account used to extract metadata. - **Password** — the password for that account. ![Pod configuration settings for connecting to AWS Redshift database with authentication details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-08 at 4.05.53 PM(1).png) **Testing connection** - Click **Test Connection** to validate the details. The button stays disabled until all required fields are filled. - Securiti then shows the connection test result, including each connectivity check that ran. - If the test fails, correct the details and test again. - If the test succeeds, click **Continue** to move to the **Configuration** step. ![Connection test successful with basic connectivity checks and authentication details displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-08 at 4.06.37 PM.png) > [!NOTE] > Note > > - In the classic EDC Ingestion experience, the following sources could only be configured by writing a recipe in YAML: > - DynamoDB, > - Glue > - Superset > - Athena > - ClickHouse > - Druid > - Metabase > - MLflow > - Mode > - Azure AD > - Okta > - Vertica > > The new EDC Ingestion experience adds support for configuring the recipe through UI fields, so you can set up these sources without writing YAML. |
| Configuration | Choose how you want to configure the integration: - **Upload YAML** — upload a YAML file that defines the configuration. Use this when you already have a recipe, or want to reuse one across instances. - **Manual Config** — configure filters and advanced settings through the form. The fields available under **Manual Config** depend on the source you are ingesting from. For the settings specific to your source, see the article for that source in the **EDC Ingestion** category. When the configuration is complete, click **Save Configuration** to apply it. |

The newly created integration appears in the corresponding category on the **Integrations** page.

> [!NOTE]
> Note
> 
> Before configuring an integration that requires credentials, create the secrets it references. See creating secrets for more details.

#### **Creating secrets**

Secrets are named values that Securiti encrypts and stores, so that sensitive configuration such as database usernames and passwords never appears in plain text inside an ingestion recipe. You reference a secret by name in the recipe using the format `${SecretName}`.

To create secrets:

1. On the Integration page, at the top right corner of the page, click **Manage** **Secrets**.
2. On the right side of the **Data Catalog Secrets** popup, click **+ Create new secret**.
3. On the **Add New Secret** popup, enter the following details:

| Field Name | Description |
| --- | --- |
| Name | This is the secret name. This is what you use to reference the secret from your recipes. |
| Value | This is the value of your secret, which is encrypted and stored securely within the Data Catalog. |
| Description | This is the secret description to help keep track of your secret. |

**Viewing and searching secrets**

The **Data Catalog Secrets** popup lists every secret configured for your tenant. The **Secrets** count above the list shows how many secrets exist, and updates to reflect any search term you enter.

Each row shows the secret's name, which is the value you reference in your recipes, and its **Description**.

**Deleting secrets**

You can delete a secret when it is no longer referenced by any ingestion recipe, for example after you rotate credentials or retire an integration.

To delete a secret:

- At the right end of the secret's row, click **Options** (three dots) > **Delete**.

> [!NOTE]
> Note
> 
> - Deleting a secret does not update the recipes that reference it. Any ingestion whose recipe still references ${SecretName} fails with a secret resolution error on its next run. Update the affected recipes before deleting the secret.
> - Secrets cannot be edited. To change a secret's value, delete it and create a new one with the same name, so that the recipes referencing it continue to resolve.

#### Performing actions on created integrations

To act on an integration, click Options (three dots) at the right end of its row. The following table describes the available actions:

| **Action** | **Description** |
| --- | --- |
| Copy URN | Copies the URN of the integration to your clipboard, for use in support requests or API calls. |
| Edit | Opens the integration for editing. Available only before the integration has run. |
| Run | Starts the integration. The **Status** column changes to **RUNNING**, and then to **COMPLETED** or **FAILED** when the run finishes. |
| Delete | Deletes the integration. Deleting an integration terminates all of its scheduled runs. |

#### Running an ingestion source

- To run an integration, click **Options** (three dots) at the right end of its row. This means that your request to execute ingestion has been successfully picked up by the ingestion executor. Shortly after, you see the **Current Status** of the ingestion get changed.

You see the **Current Status** as completed if ingestion is successful. The different statuses of the ingestion are as follows:

| Ingestion Status | Description |
| --- | --- |
| Created | Ingestion is created successfully. You can edit and rerun the created ingestion at any time. |
| Scheduled | Ingestion is scheduled successfully. You cannot edit and rerun the scheduled EDC ingestion, can only view it. |
| Running | Ingestion is in a running state. You cannot edit and rerun the running EDC ingestion. |
| Completed | Ingestion is executed successfully. You can rerun but cannot edit the completed ingestion at any time. |
| Failed | Ingestion is not executed successfully. You cannot edit and rerun the failed EDC ingestion, but can only view it. |

> [!NOTE]
> **Note**
> 
> - You can view the reason behind a failed ingestion by hovering on the **Failed** status in the current status column.
> - When one or more tables are deleted from a database and a discovery scan is re-run, the corresponding datasets in EDC are now automatically updated to reflect those deletions. This ensures that the EDC remains consistent with the latest database structure and discovery scan results.
> - Discovery scans take precedence over dataset import and EDC Ingestion. Re-running a discovery scan resets a dataset's metadata to what the scan detects, removing anything added through dataset import or EDC Ingestion.
> 
> For example, a discovery scan registers a dataset with two lineage relationships. You add one through dataset import and one through EDC Ingestion, giving the dataset four. Re-running the discovery scan leaves only the original two.
> 
> After re-running a discovery scan, re-run the dataset import and EDC Ingestion in their original order to restore the overwritten metadata.

#### Debugging a failed ingestion

The following common reasons can be the cause for failure:

- **Recipe misconfiguration:** A recipe has not provided the required or expected configurations for the ingestion source.
- **Failure to resolve secrets:** If the Securiti platform is unable to find secrets that were referenced by your Recipe configuration, the ingestion run will fail. Verify that the names of the secrets referenced in your recipe match those which have been created.
- **Connectivity reachability:** If Securiti platform is unable to reach a data source, for example due to DNS resolution failures, metadata ingestion will fail. Ensure that the network where Securiti is deployed has access to the data source which you are trying to reach.

#### Exploring ingestion history

The **Ingestion History** page lists every ingestion run for the instance, so you can confirm a run completed, see how long it took, and investigate a failure.

![Overview of Databricks Unity Catalog showing ingestion history and status details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-08 at 3.01.58 PM.png)

The following table describes the columns in the list:

| **Column** | **Description** |
| --- | --- |
| Requested At | The date and time the run was requested. |
| Started At | The date and time the run began. A gap between this and **Requested At** means the run was queued. |
| Duration | How long the run took. |
| Status | The outcome of the run, such as **Completed** or **Failed**. |

Use the following controls to work with the list:

| **Control** | **Description** |
| --- | --- |
| Filter bar | Click the **+** icon to narrow the list, which is useful when an instance has run many times. |
| View | Click **View** to open the Ingestion Run Details panel. The panel has four sections, described below. \| **Section** \| **Description** \| \| --- \| --- \| \| Summary \| The outcome of the run and its metrics, including the run status, the total assets ingested, and statistics for entity discovery, profiling, and view definition parsing. You can click **View All** to open the full asset list. \| \| Assets \| The assets the run ingested, each with its name, location, and type. Click **View** on a row to open that asset in the catalog. \| \| Logs \| The logs collected during the run, including the ingestion report. You can click **Download** to save them, or the copy icon to copy them. \| \| Recipe \| The recipe used for the run, in YAML. Sensitive values such as tokens are masked. You can click **Download** to download or copy icon to save or copy it. \| |
| **Section** | **Description** |
| Summary | The outcome of the run and its metrics, including the run status, the total assets ingested, and statistics for entity discovery, profiling, and view definition parsing. You can click **View All** to open the full asset list. |
| Assets | The assets the run ingested, each with its name, location, and type. Click **View** on a row to open that asset in the catalog. |
| Logs | The logs collected during the run, including the ingestion report. You can click **Download** to save them, or the copy icon to copy them. |
| Recipe | The recipe used for the run, in YAML. Sensitive values such as tokens are masked. You can click **Download** to download or copy icon to save or copy it. |
| Refresh | Reloads the list. Use it to follow a run that is still in progress, since the status does not update on its own. |
| Row actions menu | Click **Options** (three dots) at the end of a row to copy the URN or RollBack. Rolling back the ingestion removes any new data ingested during the run. This may exclude data that was previously extracted, but did not change during this run. |

#### Monitoring activity logs

The **Activity Log** page records changes made to the instance, so you can see who changed what and when. The following table describes the columns in the **Audit Log**.

| **Column** | **Description** |
| --- | --- |
| Time | The date and time the action was recorded. |
| User | The account that performed the action. |
| Activity | The type of action performed, such as a configuration change or a run being triggered. |
| Message | The details of the action, including what changed. |
