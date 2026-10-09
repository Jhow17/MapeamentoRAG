---
title: "EDC Dashboard - Classic view"
slug: "edc-dashboard-classic"
updated: 2026-10-05T09:09:39Z
published: 2026-10-05T09:09:39Z
canonical: "helpcenter.securiti.ai/edc-dashboard-classic"
area: governance
modulo: enterprise-data-catalo
tipo: guia
data_captura: 2026-10-08
---

# EDC Dashboard - Classic view

The top section of the **Classic** view of the EDC dashboard comprises a search bar that supports column-level searches such as name, description, tag etc. You can use AND, OR statements, full or partial URN, and quoted search analyzer for exact and prefix matches in the search bar to discover data assets.

![Overview of enterprise data catalog dashboard Classic View with datasets, dashboards, and platforms listed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/EDC dashboard - classic view.png)

![EDC_dashboard.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f1fda445-99e6-204e-0022-2fb09b21cbac.png)

At the top right of the page, you can access:

- [Analytics](/v1/docs/usage-analytics)
- Govern

Govern menu lets you access the following:
  - [Glossary](/v1/docs/glossary-terms)
  - [Domains](/v1/docs/domains)
  - [Data products](/v1/docs/data-products)

The dashboard also provides you with a quick view of the following:

- [Domains](/v1/docs/domains)
- [Datasets](/v1/docs/datasets)
- [Charts](/v1/docs/charts)
- [Glossary terms](/v1/docs/glossary-terms)
- [Data products](/v1/docs/data-products)
- [ML models](/v1/docs/ml-models)
- [Dashboards](/v1/docs/dashboard)
- [Pipelines](/v1/docs/data-pipelines)

The **Domains** widget presents a streamlined vertical list of all domains, making it easier to scan and navigate. Each domain clearly shows the number of associated entities and data products, helping you to assess data volume at a glance.

The Platform widget displays a list of data systems ingested into the Enterprise Data Catalog.

- Click on any data system to view its details.

![EDC_dashboard.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c402c733-7976-1ae6-8fb3-2f1fba558ead.png)

The dashboard also provides you with a quick view and convenient access to the following valuable data assets:

- Recently viewed

> [!NOTE]
> **Note**
> 
> If the most viewed datasets are deleted, they become disabled in the **Recently Viewed** section. When you hover over a deleted dataset, you see the help text "This dataset is no longer available."
- Recently edited
- Most popular

> [!NOTE]
> **Note**
> 
> If the most viewed datasets are deleted, they become disabled in the **Most Popular** section. When you hover over a deleted dataset, you see the help text "This dataset is no longer available."
- Top tags
- Top glossary terms

### Using search

Search is available for all EDC users. Although search works out of the box, the more relevant data you ingest, the better the results are. Searching in the Enterprise Data Catalog is as easy as typing in relevant business terms and pressing 'enter' to view matching data assets.

By default, search terms will match against different aspects of a data asset. This includes asset names, descriptions, tags, terms, owners, and even specific attributes like the names of columns in a table.

You can also click the **Explore all** button located at the bottom right of the search bar. This action fetches all the discovered assets and redirects you to the search result page. You can quickly filter by data systems, tags, glossary terms, domain, owners, and more with a single click. You can also do so by clicking on the search bar to filter assets by data systems.

You can also search data systems and containers ingested in the EDC by their names. This is because most of the time you rely on data system names to identify data systems.

> [!NOTE]
> **Note**
> 
> - Existing datasets do not have the data system name property by default. To populate this property in the **Properties** tab, you must execute the **EDC** **Refresh Job**. For the new datasets, the property gets populated as expected.
> - If a data system name changes in the [connector side’s configuration](/latest/docs/configuring-connectors-for-monitored-data-systems), Securiti updates it in the EDC after executing EDC Refresh Job. For more information, see [Structured properties](/v1/docs/structured-properties).
> - The colon `:` is a reserved character in the search field. If the glossary term or domain name you are searching for contains a colon, wrap the search term in double quotes to return accurate results. For example, to search for a term named Customer:ID, enter `Customer:ID` in the search field.

#### Filters

**Basic filters**

The filters sidebar sits on the top side of search results. It lets you find assets by drilling down. You can quickly filter assets based on the following options:

- Platform
- Environment
- Domain
- Type
- Glossary term

> [!NOTE]
> **Note**
> 
> The **Type** filter includes options such as Select_list, Update, and Insert. These are the subtypes of datasets, which define the nature of the intermediate objects in the lineage flow.

- Click the **+ More Filters** option to explore the following filtering options further:
  - Owned by
  - Tag
  - Container
  - Platform instance
  - Governance status
  - Governance flag
  - Schema governance flag
  - Edited field tags

**To use the filters:**

1. Click on any filtering menu and select the desired checkboxes.
2. Click Update to apply the filters and display the desired results.

**Advanced filters**

The advanced filter option lets you apply more complex filters. It is based on an elastic index which means it tries to match against anything in that index. That includes the asset name or any word in the description, schema, etc.

To get there, click **Advanced** in the top right of the filter panel:

**Adding an advanced filter**

Currently, advanced filter supports filtering by:

- Platform
- Column name
- Description (entity or column level)
- Glossary term (entity or column level)
- Tag (entity or column level)
- Container
- Domain
- Owner
- Entity type
- Subtype
- Environment
- Soft deleted

**Adding new filter**

To add a new filter:

1. Click the add filter menu and choose a filter type.

![add_filter_-_dropdown.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-cbc1832d-0d53-0960-6749-e4eb01fc34e0.png)
2. Fill in the values you want to filter by and click **Add**.

![adding_new_filter.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ac439b58-5693-e46c-2af8-6fe685c3a8b3.png)

#### Advanced queries

The search bar supports advanced queries with pattern matching, logical expressions and filtering by specific field matches. In advance queries, you can specify the attribute name you want to search one. Some examples:

- Name: If you type “name:<search string>”, the search will only search on the name attribute.
- Custom properties: You can search only the custom properties of the dataset by typing “customProperties:<search string>”.
- Field paths: If you are trying to find a match for a particular column, type “fieldPaths::<search string>”.
- Browse path: If you are trying to find assets that contain a specific string in the paths (like a database or schema name), type “browsePaths:<search string>”.

> [!NOTE]
> **Note**
> 
> If an exact match is not required, you can use ***** as a wildcard.

**Searching terms and phrases**

Type any phrase in the search bar and the Securiti system searches the entered phrase in searchable metadata and generates the output.

> [!NOTE]
> **Note**
> 
> If you enter multiple words as a word for example CustomerSuccess. The search breaks this phrase into two words that is Customer and Success. This is because the upper case indicates the start of a new word. So the search tries to look for instances of Customer and Success.
> 
> However, if you type customersuccess, then the system looks for instances of just that word, customersuccess.

**Example**

Searched: Customers or "Customers".

Output: Searched customers word in whole metadata.

![customers_table_-_generic_search_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7cf81cc3-698f-93f1-10e8-765428236c0e.png)

**Searching exact match**

In case of exact matches for a certain type and subtype, you must select type and subtype in the Basic filter and write specific syntaxes.

For example, if you are searching for a specific table, you must apply **type = Datasetss** and **subtype = Table** as basic filter and type **name:tablename** in the search bar.

**Example**

Searched: “name:Customers” or name:"Customers" and applied Table as filter.

Output: Searched only customers tables.

> [!NOTE]
> **Note**
> 
> If you apply the **Table** as subtype filter and search only the string **customers** instead of **name:customers** then you will see matches for tables that contain the string **customers** in any searchable aspect, like column names, descriptions, properties, etc.

**Excluding terms**

You can exclude the results by term using `-` to negate the term.

**Example**

logging -snowflake.

**Term boolean logic with precedence**

You can use `()` to set precedence of boolean term expressions. The logical and and or operations are also supported to link boolean expressions. And is represented by `+`, and OR is represented by `|`. Refer to example below for more clarity.

**Example**

logging **+** (-snowflake **|** os_audit_log)

**Complex queries**

EDC supports complex queries to fetch the required results. You can start the query with the **/q** operator.

```plaintext
/q name:DELETE OR name:bkp OR name:bak OR name:archive OR name:bkup OR name:CHG OR name:201 OR name:199 OR name:200 (name:OperationsManager OR name:qfiniti_platform_2012 OR name:log_backup_table_drops OR name:slow_log_backup OR name:general_log_backup OR name:SubscriptionsBeingDeleted OR name:MT_Microsoft OR name:MT_LW$ OR name:BKUPLUN OR name:BKUPDBConfig OR name:Collect_DataLogBackup_Path OR name:Collect_DataLogBackup_Path_History OR name:Database_Backup_Exception OR name:MT_ServiceStateProbePage OR name:MT_System$NetworkManagement OR name:MT_UINameSpace OR name:BulkDeleteFailureBase OR name:BulkDeleteOperationBase OR name:obs_binary OR name:obs_metric OR name:obs_string OR name:general OR name:backup OR name:mt OR name:lun)
```

#### Downloading search results

To download search results:

1. Search any data catalog item in the search bar.
2. On the right side of the search result page, Click **Options** (three dots) > **Download**.
3. On the **Download** as a popup, specify the name. By default, **results** are mentioned.
4. Click **Download**.

> [!NOTE]
> **Note**
> 
> The link expires in 24 hours, so be sure to download the file promptly.

#### Downloading search results under 1000 records

To download search results under 1000 records:

1. If the search records are less than 1000, the records in the CSV format start downloading. You can see the message on the bottom right of the page as “Preparing Download. Creating CSV with entity_count entities to download.”
2. Soon after the downloading is completed, you can view the .csv file in your local device to view records.

#### Downloading search results over 1000 records

To download search results over 1000 records:

1. When your search results exceed 1000 records, you receive a message on the screen that says, "Started Processing. You will receive an email shortly."
2. Check your registered email address for a message containing the requested CSV file as an attachment.

> [!NOTE]
> **Note**
> 
> - Ensure that your registered email address is up to date to receive the CSV files for large search results.
> - When a CSV export is in progress for a tenant, the system **blocks any new export requests** from that tenant until the current export completes.
> 
> Each tenant’s export process is isolated. An export lock on one tenant does not affect export operations for other tenants.
> 
> To ensure reliability, if an export lock becomes stuck, it automatically expires after 24 hours. This lets new export operations proceed without manual intervention.

#### Editing assets via search results

1. Search any data catalog item in the search bar.
2. On the right side of the search result page, Click **Options** (three dots) > **Edit**.
3. Mark the checkboxes for the assets that you want to edit.
4. At the top right side of the page, you can view the following menus to update assets:

| Menu | Description |
| --- | --- |
| Owners | Click the **Owners** menu to add or remove owners from the asset(s). |
| Glossary terms | Click the **Glossary terms** menu to add or remove the glossary terms from the asset(s). |
| Tags | Click the **Tags** menu to add or remove the tags from the asset(s). |
| Domain | Click the **Domain** menu to set or unset the domain from the asset(s). |
| Delete | Click the **Delete** option to remove the selected assets. Once deleted, these assets will no longer appear in future Data Catalog searches. However, if the assets are re-ingested from an external data platform, they will be restored. |

## Related

- [Glossary terms](/glossary-terms.md)
- [Datasets](/datasets.md)
- [Domains](/domains.md)
