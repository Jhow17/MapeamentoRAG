---
title: "EDC-specific Data command graph dashboard"
slug: "edc-specific-data-command-graph-dashboard"
updated: 2026-07-17T11:49:42Z
published: 2026-07-17T11:49:42Z
canonical: "helpcenter.securiti.ai/edc-specific-data-command-graph-dashboard"
stale: true
area: governance
modulo: enterprise-data-catalo
tipo: guia
data_captura: 2026-10-08
---

# EDC-specific Data command graph dashboard

**Scenario**

As a data steward, you need a clear view of how metadata entities relate to ensure data quality and governance. Manually navigating expectations, glossary terms, and domains is time-consuming and fragmented. The EDC-specific data command graph dashboard lets you filter and visualize these relationships in a single graph, helping you identify gaps, streamline audits, and manage responsibilities more efficiently.

The data command graph dashboard for the Enterprise Data Catalog module provides a module-specific inventory of select entities, also known as a sub-graph. It displays your data in the form of a circular graph and metric widgets at the top of the page.

> [!NOTE]
> **Note**
> 
> If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

Access data command graph:

- In Securiti, open **Enterprise Data Catalog** module, and from the left panel choose **Dashboard** > **DataCommand Graph** to access the data command graph.

![DCG.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-10f5b0af-183d-c436-63b3-a06eec01a0eb.png)

The data command graph circular graph displays an EDC's entities and their connections along with the metadata count. It lets you view rich context for any entity including tags, glossary terms, databases etc. You can visualize your data at the granular level and apply filters on aggregates of entity types and all their relationship types.

### Dashboard

The top row of the dashboard is the filter bar where you can apply entity-level and attribute-level filters to view valuable information. The second row displays the module-specific statistics of data as metrics. Near the left side of the page is the Saved Views panel that shows you the list of all your saved views.

You can apply filters across entities to quickly view the graphical representation of the underlying data. [Click here](/v1/docs/using-the-app-specific-inventories) to learn more about filters and graphical representation.

The Enterprise Data Catalog Command Graph and Graph Explorer present you the following nodes:

| Node | Description |
| --- | --- |
| Assertion | An assertion is a data quality rule on a data object or data field. |
| Chart | A chart is a widget such as a pie chart, bar chart or a data table and is used to illustrate important characteristics of a data set. |
| Dashboard | A dashboard is a collection of chart objects. |
| Data domain | Data domains are used to group metadata from an organizational point of view. Data domains help to expedite ownership assignment as well as to find SMEs. |
| Data flow | Documents the orchestration of data flows. |
| Data job | An instance of a job execution within a data flow. It captures the metadata of a job such as data transformation. |
| Data process | The execution states and results of an instance of a data job or job flow. |
| Data product | Represents a data product within the EDC. |
| Glossary node | Glossary nodes are used to build taxonomies and hierarchies and contain groupings of glossary terms. |
| Glossary term | Glossary Terms represent business metadata and are used to aggregate business context for technical metadata. |
| Responsibility | Responsibility indicates the responsibility a user has on an asset. |
| Tags | Tags are free-form text labels that allow users to group objects for search, filtering and use. |
| Expectation template | Stores predefined expectation rules that can be reused. Instead of creating a new expectation each time, you can apply templates for consistency and efficiency. **Example**: Expect_column_values_to_not_be_null **Description**: It ensures that column values are not null across different datasets. |
| Expectation | Defines data quality rules or conditions that data must meet. **Example**: column not null: ID **Description**: It states that the ID column must not contain null values. |
| Checkpoint | Acts as a control point where data quality checks are applied. It defines when and where data quality validation should take place within the data flow. **Example**: customer_data_quality_check **Description**: Ensures that critical columns in the customer dataset do not contain null values. |
| Checkpoint execution | Executes the checkpoint to run data quality validations. It checks the data at a specific point and records the results. **Example**: customer_data_quality_check_execution_01 **Description**: Executes the **customer_data_quality_check** checkpoint to validate null values in the **Customer_ID** column. |
| Expectation execution | Executes the expectation rules against the data. It evaluates whether the data meets the defined expectations and reports the results. **Example**: customer_id_null_check_execution_01 **Description**: Executes the expectation **column_not_null: ID** to validate the **Customer_ID** column. |

> [!NOTE]
> **Note**
> 
> If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to determine if this feature is included in your subscription and if your tenant meets the requirements to use this functionality.

For more information, see [Graph explorer](/v1/docs/using-graph-explorer).

Refer to loosely defined terms that can be applied to data assets and other catalog entities. These tags make it easier to organize and search for specific assets within the Enterprise Data Catalog.
