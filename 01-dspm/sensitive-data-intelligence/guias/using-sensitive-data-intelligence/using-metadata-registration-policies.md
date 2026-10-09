---
title: "Using Metadata Registration Policies"
slug: "using-metadata-registration-policies"
updated: 2026-08-10T21:00:09Z
published: 2026-08-10T21:00:09Z
canonical: "helpcenter.securiti.ai/using-metadata-registration-policies"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Using Metadata Registration Policies

**Scenario**

A global financial services company regularly ingests structured data from multiple regional data warehouses into its central analytics platform. To maintain data governance and support regulatory audits, the company uses Alation as its enterprise data catalog.

Previously, metadata registration required running periodic scans across each data source, consuming significant compute resources and delaying the onboarding of new data assets. Additionally, the company wanted more precise control—instead of cataloging everything, they wanted to register only specific, important metadata (like a few key columns from certain tables).

The Metadata Registration Policy solves the above problem. The policy enables a policy-driven mechanism to register metadata from structured data systems into Alation and Collibra. Instead of depending on traditional discovery scans, the policy evaluates defined conditions and criteria to determine when and how metadata should be registered.

> [!NOTE]
> Note
> 
> If the metadata registration policy feature is not available in your Securiti tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan.

## Syncing metadata from Securiti into Alation

Metadata Registration Policy for Alation offers a policy-driven method to register metadata from structured data systems into the Alation data system, without relying on traditional discovery scans. Metadata is registered based on defined conditions and criteria.

Simply configure the Alation connector, define the policy, set the scope using graph-powered queries, and specify the target data source for storing metadata. Once the policy runs, the selected metadata can be viewed in Alation.

### Prerequisites

- You must properly configure and authenticate the [Alation connector](/v1/docs/alation-connectors).
- You must have an [active pod](/v1/docs/securiti-pods-and-elastic-pods) to support authentication with Alation.
- You must have a subscription to the Sensitive Data Intelligence and Data Command Graph modules.

**Sensitive Data Intelligence**, and **Data Command Graph** modules are required to define the scope of metadata using graph-based queries that identify specific tables, columns, or relationships.

### Scope

The policy scope is defined using a graph-powered query to select metadata elements precisely. You can target Tables or Columns in the Data Command Graph, apply filters (for example, schema, tags, sensitivity, ownership), and use relationship-based logic to refine the selection.

To create a metadata registration policy:

1. From the main menu, navigate to **Policies**. On the **Policies** page, select **Metadata Registration Policy**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-7LK6ROBS.png)
2. From the upper-right corner of the page, click **+ Create**.
3. On the create policy pop-up, specify a suitable name and description.
4. To enable the policy, activate the **Activate Policy** toggle. Once enabled, the policy immediately begins running upon creation.

> [!WARNING]
> Important
> 
> To ensure the policy stays effective and up-to-date without manual effort, the system automatically runs it every week. You cannot change this schedule from the Securiti platform.

1. In the **Scope** section, choose the **Add scope rule** to define the boundaries and context within which the policy’s rules and privileges are enforced.
2. This opens the Graph Explorer where you can scope tables and columns to include in the policy. For more information, see the [Graph Explorer documentation](/v1/docs/using-graph-explorer).

In the below example, the policy applies to columns where the property Data Element Detected is set to True, and the column resides within a table that is part of the dsr_data dataset. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-6IN3ZDQB.png)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-KRBFW1IT.png)
3. From the **Actions** section, define the automated steps to be executed. Based on the criteria defined in the scope, you can configure specific actions to be executed on the matching metadata nodes. This policy supports only actions related to metadata registration in Alation.

> [!NOTE]
> Note
> 
> Only one action is allowed per Alation instance within a single policy. If you need to register metadata to multiple Alation instances, you must create separate policies for each.

1. Click **Actions**, and in the popup, select an Alation connector. On the right panel of the connector selection popup, you can see an option to register either a column or a table, depending on your selected scope.

- If you selected **Column** in the scope, the **Actions** popup displays the option **Register a Column**.
- If you selected **Table** in the scope, the **Actions** popup displays the option **Register a Table**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-F3TK9S2U.png)

In the initial phase, only Alation-specific actions are supported, and attributes can be synchronized using either of the following methods:

### Choosing and Configuring a mapping method

#### Direct Mapping

This method is selected by default. It assigns target attributes by directly linking them to corresponding source attributes. The direct mapping method is simple and quick to configure, but is limited to exact attribute pairs.

- Click **Re-sync fields** to update custom fields and field changes from Alation directly within the Metadata Registration Policy. This lets you refresh fields without re-authenticating the connector.

By re-syncing, you can:

- Pull in newly added or updated Alation fields into the mapping configuration.
- Ensure your policy setup always reflects the latest metadata.
- Reduce the risk of stale or missing mappings.

- From the **Matching Condition** menu, select the data source field in Alation that Securiti should use to locate the correct data system in the Alation catalog. This field acts as the lookup key that links your Securiti data system to the appropriate Alation source.

You can choose fields such as Title, Description, DB Type, or JDBC URI, depending on which Alation attribute best represents your data system.

If **Title** is selected as the matching condition, the policy will compare the Securiti data system name with the Title field of Alation data sources. When a match is found, the metadata is registered under that specific Alation source.

> [!NOTE]
> Note
> 
> Only Alation Data Source custom fields of type Text are available for selection as matching conditions. Custom fields of other types, such as Object set, Object Reference, People Set, Picker, Multi-Select Picker and Date are not supported.
- From the Securiti's menu, select the property of the table or column that you want to sync to Alation custom fields.
  - For a **table**, you can choose properties such as data system name, content profiles, database, and more.

For a **column**, you can select properties such as column name, data element types, reference columns, and others.

> [!WARNING]
> Important
> 
> 
> 
> - The Create New Asset option determines whether can create assets in Alation during synchronization.
> - If Create New Asset is set to false, Securiti does not create any assets in Alation, including data sources, schemas, tables, or columns. In this configuration, only updates metadata (custom fields in Alation) for assets that already exist. Therefore, the corresponding data source and its schemas, tables, and columns must already be present in Alation, typically created through Alation’s native connectors. then updates the field classifications and metadata for those existing assets.
> - If the data source or its assets do not exist in Alation, the policy evaluation may complete but will result in sync errors, since cannot create new assets when this option is disabled.
> - To synchronize assets for a new data source that is not already present in Alation, you must enable Create New Asset in the policy configuration.

All these properties are available in the **Graph Explorer**, where you can view a wide range of table and column attributes within their respective nodes.

- From the **Alation** menu, choose the target custom field in Alation (for example, Qualytics).
- Click **+ Add Attribute Mapping** to define additional mappings as needed.

In this example, a source attribute like **Data Elements** from **Securiti** is directly mapped to a target attribute such as **Qu****alytics** in **Alation**, establishing a straightforward 1:1 registration without any conditions.

![Interface for registering a table with integration fields and mapping options displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2025-12-09 at 12.46.44 PM.png)

### Expression Mapping

The expression mapping uses conditional logic to dynamically assign target attributes based on the source value. This method is more complex but highly flexible for rule-based scenarios.

> [!NOTE]
> Note
> 
> Re-syncing and matching condition options function the same way as they do in Direct Mapping.

The below-mentioned expression rule ensures that any column named **email** in the source will have its corresponding metadata field **alation_test_table_column_richtext** in Alation set to **test email** during registration.

The system creates the asset in the target catalog only if it is not already present, and the **Create new assets if not present at target catalog** checkbox is selected.

![Interface for registering a table with integration fields and sync logic options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2025-12-09 at 12.48.56 PM.png)

1. After defining the actions, click **Save Action**.
2. Once the changes are made, click **Create Policy**.

Once the policy gets created, you can view it on the metadata registration policy dashboard.

### Using the metadata registration policy dashboard

You can use the metadata registration policy dashboard to create and view the metadata registration policies.

#### Searching and filtering the created policy

- At the top, you can use the following filters, such as Policy ID, Policy Name, Owner, etc, to limit the dashboard view or find a desired policy.
- Below the filters option, you can use the search bar to find a specific created policy by its name.
- Below the search bar, you can view the count of total and created policies.

> [!NOTE]
> Note
> 
> Applying these filters also updates the tile counts for ​**Total**​ and **​Active** Policies​​.

- For each created policy, you can view its:
  - Status
  - Id
  - Name
  - Last executed
  - Last modified
  - Scope
  - Owner
  - State

#### Creating a saved view

The ​**Saved Views**​​ feature lets you save applied filters and reuse them whenever needed. Instead of reapplying multiple filters every time you navigate away and return, you can quickly access your saved view with just a couple of clicks. By making it easier to focus on specific metadata registration policy, Saved Views reduces repetitive effort and helps you analyze results faster.

To save a view:

1. Apply the desired filters.
2. ​Once filters are applied, from the top right corner of the page, the ​**Save View**​​ option becomes enabled.
3. ​Click ​**Save View**​​.
4. ​In the Save View panel, enter:
  1. ​Group name
  2. ​Name of the view
  3. ​Optional description
5. ​Click ​**Save View​​** to confirm.
6. ​Click ​**Saved View**​ button located next to the ​**Save View​​** button to open and select from your saved views.

#### Viewing metadata details

- From the right-most side of any policy entry on this dashboard, click the **Show Metadata** icon to open the policy details.
  - Click **Details** to open the metadata registration policy configuration page, and make changes to the policy.
  - Click **Explore** to view the details of the metadata registration policy, including the discovered metadata and their relationships. To see more information, click on any node within the relationship graph.

### Viewing, editing, cloning, and deleting a metadata registration policy

From the right-most side of any policy entry on this dashboard, click the options (three dots) to view/edit/clone, or even delete the created policy.

> [!NOTE]
> Note
> 
> When a policy is in the **Scheduled** or **Running state**, only its name, description, and status can be modified. The **Scope** and **Actions** fields are locked and cannot be edited.

### Policy logs

On the **Update Policy** page, located at the top-right corner, click **Policy Logs**.

The **Policy Logs** page gives visibility into metadata registration activities across your data systems. It offers a streamlined, filterable, and export-friendly interface for monitoring and auditing registration processes in real time.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-7D9UEU52.png)

#### Applying filters

You can filter logs based on:

- Data system type
- Data system name
- Severity
- Column
- Table
- Schema
- Database
- Timestamp

To apply filters:

1. Click **+ Filters**.
2. Select a property (for example, **Severity**).
3. Use the condition builder (for example, **is equal to Success**).
4. Apply the filter.

> [!NOTE]
> Note
> 
> Filters are combined to refine your log view. You can apply multiple filters at once.

#### Search, Refresh, and Export

- Use the **Search bar** to find logs by keywords in the **Message** field.
- Click **Refresh** to view the latest entries without reapplying filters.
- Click **Export** to download filtered logs. Use this for:
  - Offline diagnostics
  - Internal audits

#### Logs grid

The grid shows you:

- **Timestamp** – When the log entry was generated.
- **Message** – Description of the metadata registration event (e.g., processing a schema, table, or column).
- **Severity** – Classification of the event as:
  - Success
  - Information
  - Warnings / Errors (if present)

> [!NOTE]
> Note
> 
> To customize visible columns, click ​**Column Selector**​​ on the right side of the logs grid.

### Visualizing the results of the metadata registration policy

There are two ways to view the registered metadata as a result of this policy execution.

#### Graph explorer

1. Select **Graph Explorer** on the Securiti homepage.
2. Either click **Begin Your Search** button in the middle of the page or the **Plus Icon** on the top left.
3. From the graph explorer filters, choose **Control > Metadata Registration Policy** to view all the relationships of nodes involved in the policy execution.

#### Alation

1. To view the metadata selected in the policy scope, log in to the Alation platform.
2. From the left navigation menu, expand **Sources**, then locate and open the specific data source where the metadata was registered.
3. Navigate to the ingested tables and columns to view the registered metadata entries.
4. Click on a table or column to view its detailed metadata.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-JL9WCNBI.png)

In the above screenshot, the metadata was ingested based on the expression logic defined in the policy configuration above.

- The email column is selected from the table **dsr_data**.
- On the right panel under **Referenced By**, the metadata field **alation_test_table_column_richtext** is visible.
- Its value is correctly populated with test email, confirming that the expression logic executed as intended. This means the rule is triggered for the column named email, and Alation registered the metadata accordingly.

> [!NOTE]
> Note
> 
> - **Rich text custom fields**​​, ​**Dates**​​, ​**Pickers**​​, and ​**Multi-select Pickers**​​ are supported when registering metadata to Alation. Other custom field types are not supported.
> - Only the ​**default template in Alation**​​ is supported. Custom templates is not applicable by this policy action.
> - When adding a custom field in Alation, ensure it is included in the ​**Custom Templates**​​ for the relevant table or column, depending on your sync type. If the field is not in the template, the re-sync will not capture it.

## Syncing metadata from Securiti into Collibra

Metadata Registration Policy for Collibra offers a policy-driven method to register metadata from structured data systems into the Collibra data system, without relying on traditional discovery scans. Metadata is registered based on defined conditions and criteria.

Simply configure the Collibra connector, define the policy, set the scope using graph-powered queries, and specify the target data source for storing metadata. Once the policy runs, the selected metadata can be viewed in Collibra.

### Prerequisites

- You must properly configure and authenticate the Collibra connector.
- You must have an [active pod](/v1/docs/securiti-pods-and-elastic-pods) to support authentication with Collibra.

> [!NOTE]
> Note
> 
> You must have an appliance version greater than 1.140.0 for the Collibra connector.

You must have a subscription to the Sensitive Data Intelligence and Data Command Graph modules.

Sensitive Data Intelligence, and Data Command Graph modules are required to define the scope of metadata using graph-based queries that identify specific tables, columns, or relationships.

### Scope

The policy scope is defined using a graph-powered query to select metadata elements precisely. You can target Tables or Columns in the Data Command Graph, apply filters (for example, schema), and use relationship-based logic to refine the selection.

### Example use case

A large healthcare organization ingests structured data from multiple clinical and operational systems into its central data warehouse. To support data governance and regulatory compliance, it relies on Collibra as its enterprise data catalog.

Previously, metadata registration required full discovery scans, which were resource-intensive and delayed the availability of new governed assets. The organization also needed finer control, wanting to register only specific, high-value tables and columns rather than entire schemas.

With the Metadata Registration Policy, the organization can precisely select and register only the required metadata into Collibra using graph-powered queries, eliminating heavy scans and accelerating metadata onboarding.

### Creating a metadata registration policy

To create a metadata registration policy:

1. From the main menu, navigate to **Policies**. On the Policies page, select **Metadata Registration Policy**.
2. From the upper-right corner of the page, click **+ Create**.
3. On the create policy pop-up, specify a suitable name and description.
4. To enable the policy, activate the **Activate Policy** toggle. Once enabled, the policy immediately begins running upon creation.

> [!NOTE]
> Note
> 
> To ensure the policy remains effective and up-to-date without manual effort, the system automatically runs it weekly. You cannot change this schedule from the Securiti platform.
> 
> If the ​Activate Policy​​ toggle is not enabled, the policy will be created and its scope saved, but it will remain inactive and will not execute until manually activated.
5. In the **Scope** section, click **Edit Query** to define the boundaries and context within which the policy’s rules and privileges are enforced.
6. This opens the **Graph Explorer** where you can scope tables and columns to include in the policy. For more information, see the [Graph Explorer documentation](/v1/docs/using-graph-explorer).

#### Example

In the example below, the policy applies to columns where the property **Data System Name** is equal to **mysql_cloud**. This means the scope is restricted to all columns originating from that specific data system. Once the policy runs, only the **132 column instances** from this data system (as shown in the instance count) will be evaluated and registered into Collibra according to the configured actions.

![Scope section defining metadata registration policy rules and privileges for data systems.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2025-12-02 at 3.55.52 PM.png)

1. From the **Actions** section, define the automated steps to be executed.

Based on the criteria defined in the scope, you can configure specific actions to be executed on the matching metadata nodes.

> [!NOTE]
> Note
> 
> Only one action is allowed per Collibra instance within a single policy. If you need to register metadata to multiple Collibra instances, you must create separate policies for each.

1. Click **Actions**, and in the popup, select a Collibra connector. On the right panel of the connector selection popup, you can see an option to register either a column or a table, depending on your selected scope.

- If you selected **Column** in the scope, the Actions popup displays the option **Register a Column**.
- If you selected **Table** in the scope, the Actions popup displays the option **Register a Table**.

1. At the top of the popup, click **​Re-sync fields**​​ to update custom fields and field changes from Collibra directly within the Metadata Registration Policy. This lets you refresh fields without re-authenticating the connector.

By re-syncing, you can:

- ​Pull in newly added or updated Collibra fields into the mapping configuration.
- ​Ensure your policy setup always reflects the latest metadata.
- ​Reduce the risk of stale or missing mappings.

1. In the **Integration Fields** section, you can specify how the target domain is assigned when metadata is registered in Collibra. The domain defines where the registered tables or columns will reside within the Collibra catalog hierarchy.

You can choose one of the following options:

| **Option** | **Description** |
| --- | --- |
| Inherit | When selected, the policy uses the domain already defined for the associated data source in the target Collibra environment. |
| Automatic | When selected, Collibra automatically determines the domain where metadata will be placed. By default, the value is automatically created for schema, meaning the metadata is stored in a domain located within the same community as the database’s existing domain. If the required domain does not yet exist, Collibra creates it automatically using the following naming convention: **[edge_connection_name] > [database_name] > [schema_name]** **Example** **Snowflake Connection > CERTIFICATION > CUSTOMERS** This ensures that newly registered tables and columns are consistently organized within Collibra, even when domains need to be created dynamically. |

1. From the **Asset Type** menu, select the Collibra asset type that represents the data system you are integrating with. This determines the asset class in Collibra where the metadata hierarchy begins. Currently, only the System asset type is supported.
2. From the **Matching Condition** menu, select the field in Collibra that the system should use to find and match the correct asset based on your data system name. This acts as the lookup key that Securiti uses to associate your source data system with an existing Collibra asset.

For example, if Description is selected as the matching condition, the policy will compare the Securiti data system name against the Description field of Collibra System assets. This ensures the metadata is registered under the correct asset in the target catalog.

> [!NOTE]
> Note
> 
> Any attributes associated with a System asset type in Collibra are also available for selection as matching conditions.

![Form for registering a column in Collibra with integration fields and options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2025-12-02 at 8.20.07 PM.png)

### Choosing and configuring a mapping method

#### Direct Mapping

The Direct Mapping method lets you sync metadata attributes from Securiti directly into corresponding attributes in Collibra. This method is ideal for simple, one-to-one mappings where the target attribute should receive the exact value stored in Securiti, without applying any additional rules or transformation logic.

Direct Mapping is selected by default when configuring actions for Collibra.

#### Configuring direct attribute mapping

Under **Select Attribute to Sync** option, you can define one or more mappings between Securiti (source) attributes and Collibra (target) attributes.

- From the Securiti menu, select the table- or column-level attribute you want to push into Collibra. These attributes are available within the Graph Explorer and represent the metadata already detected or inferred by Securiti.

Examples include:

- Column-level attributes: Column Name, Data Element Types, etc.
- Table-level attributes: Table Name, Database, Data System Name etc.

- From the Collibra menu, select the target attribute on the Collibra asset where the value should be written.

Examples include:

- Description
- Original Name
- Custom Collibra attributes supported by the integration

Click **+ Add Attribute Mapping** to define additional mappings as needed.

![Mapping attributes between Securiti and Collibra for data synchronization.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2025-12-02 at 8.42.26 PM.png)

- If you enable the **Create new assets if not present at target data catalog** option, the system will automatically create the required table or column assets in Collibra when they do not already exist.

#### Expression mapping

Expression Mapping lets you compute and assign Collibra attribute values based on conditional logic derived from source metadata in Securiti. Unlike Direct Mapping, which performs simple one-to-one attribute sync, Expression Mapping provides granular, rule-based control. This is especially useful when metadata values in Collibra depend on specific criteria, classifications, or patterns detected in the source data.

#### Example

In the example shown, the If condition checks whether the Securiti attribute Data System Type is one of a specified set of values (in this case, **google_bigquery**).

When the condition is met, the clause assigns values to a Collibra target attribute, here represented by a custom multi-select attribute (**multi selector**).

The mapping sets this Collibra attribute to **London**, **UAE** and more for all matching metadata instances.

![Interface for registering a column with matching conditions and sync logic options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2025-12-04 at 12.35.59 PM.png)

This lets Collibra attributes be populated dynamically based on the characteristics of the source system, rather than relying on fixed values.

- If you enable the **Create new assets if not present at target data catalog** option, the system will automatically create the required table or column assets in Collibra when they do not already exist.

1. After defining the actions, click **Save Action**.
2. Once the changes are made, click **Create Policy**.

Once the policy is created, you can view it on the metadata registration policy dashboard.

### Using the metadata registration policy dashboard

You can use the metadata registration policy dashboard to create and view the metadata registration policies.

#### Searching and filtering the created policy

- At the top, you can use the following filters, such as **Policy ID**, **Policy Name**, **Owner**, etc, to limit the dashboard view or find a desired policy.
- Below the filters option, you can use the search bar to find a specific created policy by its name.
- Below the search bar, you can view the count of total and created policies.

> [!NOTE]
> Note
> 
> Applying these filters also updates the tile counts for ​**Total**​ and ​Active Policies​​.

- For each created policy, you can view its:
  - Status
  - Id
  - Policy name
  - Last executed
  - Last modified
  - Data scope
  - Owner
  - State

#### Creating a saved view

The ​**Saved Views**​​ feature lets you save applied filters and reuse them whenever needed. Instead of reapplying multiple filters every time you navigate away and return, you can quickly access your saved view with just a couple of clicks. By making it easier to focus on specific metadata registration policy, Saved Views reduces repetitive effort and helps you analyze results faster.

To save a view:

1. Apply the desired filters.
2. ​Once filters are applied, from the top right corner of the page, the ​**Save View**​​ option becomes enabled.
3. ​Click ​**Save View**​​.
4. ​In the Save View panel, enter:
  1. ​Group name
  2. ​Name of the view
  3. ​Optional description
5. ​Click ​**Save View​​** to confirm.
6. ​Click ​**Saved View**​ button located next to the ​**Save View​​** button to open and select from your saved views.

#### Viewing metadata details

- From the right-most side of any policy entry on this dashboard, click the **Show Metadata** icon to open the policy details.
  - Click **Details** to open the metadata registration policy configuration page, and make changes to the policy.
  - Click **Explore** to view the details of the metadata registration policy, including the discovered metadata and their relationships. To see more information, click on any node within the relationship graph.

### Viewing, editing, cloning, and deleting a metadata registration policy

From the right-most side of any policy entry on this dashboard, click the options (three dots) to view/edit/clone, or even delete the created policy.

> [!NOTE]
> Note
> 
> When a policy is in the **Scheduled** or **Running state**, only its name, description, and status can be modified. The **Scope** and **Actions** fields are locked and cannot be edited.

### Policy logs

On the **Update Policy** page, located at the top-right corner, click **Policy Logs**.

The **Policy Logs** page gives visibility into metadata registration activities across your data systems. It offers a streamlined, filterable, and export-friendly interface for monitoring and auditing registration processes in real time.

#### Applying filters

You can filter logs based on:

- Data system type
- Data system name
- Severity
- Column
- Table
- Schema
- Database
- Timestamp

To apply filters:

1. Click **+ Filters**.
2. Select a property (for example, **Severity**).
3. Use the condition builder (for example, **is equal to Success**).
4. Apply the filter.

> [!NOTE]
> Note
> 
> Filters are combined to refine your log view. You can apply multiple filters at once.

#### Search, Refresh, and Export

- Use the **Search bar** to find logs by keywords in the **Message** field.
- Click **Refresh** to view the latest entries without reapplying filters.
- Click **Export** to download filtered logs. Use this for:
  - Offline diagnostics
  - Internal audits

#### Logs grid

The grid shows you:

- **Timestamp** – When the log entry was generated.
- **Message** – Description of the metadata registration event (e.g., processing a schema, table, or column).
- **Severity** – Classification of the event as:
  - Success
  - Information
  - Warnings / Errors (if present)

> [!NOTE]
> Note
> 
> To customize visible columns, click ​**Column Selector**​​ on the right side of the logs grid.

### Visualizing the results of the metadata registration policy

There are two ways to view the registered metadata as a result of this policy execution.

#### Graph explorer

1. Select **Graph Explorer** on the Securiti homepage.
2. Either click **Begin Your Search** button in the middle of the page or the **Plus Icon** on the top left.
3. From the graph explorer filters, choose **Control > Metadata Registration Policy** to view all the relationships of nodes involved in the policy execution.

#### Collibra

To view the metadata registered through the metadata registration policy, log in to the Collibra platform.

1. Navigate to the appropriate Domain or Community.

From the Collibra navigation panel, browse to the Domain or Community where the metadata assets were registered. The placement depends on your configuration (for example, Inherit vs Automatic domain creation).

1. Locate the registered asset type.

Open the asset type corresponding to your integration, such as:

- Systems
- Databases
- Schemas
- Tables
- Columns

1. Browse or search for the ingested assets.

Use Collibra’s search or filtering tools to locate the newly created or updated assets. These assets reflect the metadata brought in from Securiti based on your policy scope.

1. View the asset’s metadata details.

Click on any table or column asset to open its metadata page.

#### Example

In the screenshots below, the **AWS_API_Key** column from the **customer_personal_data** table was successfully registered in Collibra based on the expression logic defined in the policy.

The hierarchy shown in **Collibra—EnterpriseCustomerDataPlatform → customer_profile_schema → pds_enriched_layer → customer_personal_data → AWS_API_Key**, matches the metadata returned in Graph Explorer, confirming that the correct asset was ingested.

The Description field on the Collibra column page reflects the value assigned by the expression rule, demonstrating that the logic executed as intended.

![Graph Explorer interface displaying data columns and their properties for customer profiles.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2025-12-04 at 11.12.12 AM.png)

![Overview of AWS API Key with descriptive statistics and metadata details displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2025-12-04 at 11.08.53 AM.png)
