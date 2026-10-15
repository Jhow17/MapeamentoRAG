---
title: "Templates"
slug: "dqtemplates"
updated: 2026-07-18T10:31:07Z
published: 2026-07-18T10:31:07Z
canonical: "helpcenter.securiti.ai/dqtemplates"
stale: true
area: governance
modulo: enterprise-data-catalog
tipo: guia
data_captura: 2026-10-08
---

# Templates

### Templates overview

Templates provide the list of expectations available. They are grouped into expectation types to facilitate finding the type of data quality test that you require.

> [!NOTE]
> **Note**
> 
> - To perform actions on Data Quality Templates, enable the corresponding permission(s) for the required operation. Only the permission(s) associated with the action you intend to perform are required. For more information, see [EDC RBAC](/latest/docs/edc-rbac-permissions-and-roles).
>   - Create Data Quality Template
>   - Delete Data Quality Template
>   - Read Data Quality Template
>   - Update Data Quality Template
>   - Create Data Quality Template Type
>   - Delete Data Quality Template Type
>   - Read Data Quality Template Type
>   - Update Data Quality Template Type
> - Templates provide a list of expectations available. They are grouped into expectation types to facilitate finding the type of data quality test that you require.
> - You can use predefined templates from the Great Expectations community or create your own custom templates.
> - For predefined templates, you can edit only the metadata—name, description, tags, and list of resources—to help you identify and understand the template. Resources may include any supporting material that adds context or guidance for using the expectation effectively.
> - Custom expectation templates let you define custom SQL logic for asserting data quality during data loading and transformation. You can modify every parameter in the template, helping you detect data issues quickly and accurately.

#### Templates dashboard

The templates dashboard provides you with an overview of expectation types.

On the top right corner of the page, you can:

- Click **Expectations** to open the expectations gallery.

> [!NOTE]
> **Note**
> 
> You can also access the expectation gallery from the left navigation menu.
> 
> - Navigate to the **Expectations** icon and select **Expectations Gallery**.

- Click **Checkpoints** to open the checkpoint listing page.

> [!NOTE]
> **Note**
> 
> You can also access the checkpoint listing page from the left navigation menu.
> 
> - Navigate to the **Checkpoints** icon and select **Checkpoints Listing**.
- Click **+ Create Template** to create a custom template using SQL logic.

The left navigation section shows you the list of expectation types along with the count.

The first row shows you the template name along with its count and a search bar. The search bar lets you search for the created templates by their name or description.

#### Filtering templates

The following are the three ways to filter templates:

1. Menus

Select values from the following menus to filter specific templates:
  - Tags
    - Click the down arrow.
    - Select the operator from the menu.
    - Enter the tag name.
    - Click **Apply** to see the filtered template.
  - Data systems
    - Click the down arrow.
    - Select the operator from the menu.
    - Enter the data system name.
    - Click **Apply** to see the filtered template.
2. Search bar
  1. On the top right corner of the page, enter the name or description of the expectation type in the search bar.
  2. Select the required expectation type from the search list to open its detailed view.
3. Expectation types

You can directly select the expectation type from the left side navigation bar.

> [!NOTE]
> **Note**
> 
> You can use the search bar to filter the required expectation type.
  - Select any of the expectation types from the left menu to filter the templates that belong to the selected expectation type.

#### Exploring templates

You can search for the following expectation types in the templates dashboard.

- Column aggregates

Column aggregate templates are evaluated for a single column, and produce an aggregate Metric, such as a mean, standard deviation, number of unique values, column type, etc.
- Column maps

Column map templates are evaluated for a single column and ask a yes/no question for every row in that column. Based on the result, they calculate the percentage of rows that gave a positive answer.
- Column-pair maps

Column-pair map templates are evaluated for a pair of columns and ask a yes/no question about the row-wise relationship between those two columns. Based on the result, they calculate the percentage of rows that gave a positive answer.
- Multi-column match

Multi-column templates are evaluated for a set of columns and ask a yes/no question about the row-wise relationship between those columns. Based on the result, they calculate the percentage of rows that gave a positive answer.
- Batch expectations

Batch expectation templates are evaluated for an entire Batch, and answer a semantic question about the Batch itself. For example, **expect_table_column_count_to_equal** and **expect_table_row_count_to_equal** answer how many columns and rows are in your Batch.
- Custom expectations

Custom expectation templates are user-defined and let you create reusable patterns to validate data quality during data loading and transformation. These templates function like custom unit tests for your data, helping you detect issues early and apply consistent checks across workflows. Read creating custom expectations for details.

> [!NOTE]
> **Note**
> 
> If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

- Click any expectation type to view the list of created templates that fall under the selected expectation type.

For each template, you can view the count of:
  - Tags
  - Created expectations
  - Data systems
- On the templates list, click the down arrow for any template you want to view the following details:
  - Matrics
  - Tags
  - Data systems
  - Arguments
  - Resources

#### Creating a custom expectation template

To create a custom expectation template:

1. On the Templates dashboard, in the upper right corner of the page, click **+ Create Template**.
2. On the **Create Template** page, add the following details:
  1. Name and description of the template.
  2. From the **Attributes** section:
    1. Click **Add Tags** to add tags for the template. Tags are user-defined labels that categorize or describe an expectation template. They help organize templates by grouping based on themes, purposes, or domains (for example, PII, null checks, financial data).
    2. Click **+ Add Resource** to add any external or internal reference materials linked to an expectation template. They provide additional context or guidance for understanding and applying the expectation correctly.
    3. From the **Add co-owners** menu, search or add the co-owner of the template.
    4. From the **Data System/Data Systems** menu, select the data system where the expectation templates are applied. Currently, only the following data systems are supported:
      - Amazon Redshift
      - Snowflake
      - Google BigQuery
      - MySQL
      - MSSQL
      - Postgres
  3. From the **Expectation Criteria** section:
    1. Click **+ Add Argument** to specify the criteria or conditions that the data is expected to meet or the desired outcomes of the data analysis.
      - On the **Add Argument** popup, specify:

> [!NOTE]
> **Important**
> 
> When defining Arguments for a Custom Expectation Template:
> 
> - You must include at least one argument of type Dataset (For example, dataset_arg_1, dataset_arg_2, etc.).
> - Every argument defined must be used somewhere in your SQL logic.
> - Arguments must be referenced inside angled brackets **<>** within SQL logic.

**Example**

![Arguments.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b2808b0c-fcdc-47a4-2352-10d635be41a2.png)

The input arguments make your expectation dynamic and reusable. In the above example, each argument is referenced in the SQL logic to define datasets, join keys, and thresholds.

| Argument | Type | Description |
| --- | --- | --- |
| arg_count_1 | Integer | Row count threshold for dataset 1. Used to validate if it exceeds a minimum count. |
| arg_count_2 | Integer | Row count threshold for dataset 2. Used to validate if it stays below a certain count. |
| dataset_arg_1_join_column | String | Join column name from dataset 1. |
| dataset_arg_2_join_column | String | Join column name from dataset 2. |
| dataset_arg_1 | Dataset | First dataset (aliased as fu in SQL). |
| dataset_arg_2 | Dataset | Second dataset (aliased as furp in SQL). |
        - Name
        - Type
        - Description
    2. Click **+ Add Metric** to define the compound attribute of data, such as the mean of a column.
      - On the **Add Metric** popup, specify:

> [!NOTE]
> **Important**
> 
> When defining Metrics for a Custom Expectation Template:
> 
> - Each **Metric** defined must produce a corresponding column in the SQL query’s final result set.
> - The column name in the SQL query output must exactly match the **Metric Name**.
> - The SQL logic must ensure that each metric returns one of two possible values:
>   - 'Pass’
>   - 'Fail'
> - This lets the system correctly determine if the template’s condition has passed or failed.

**Example**

![Metrics.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ad90e994-d944-95fe-67f8-9efcf719f7a8.png)

The metrics are the pass/fail outputs based on row count validations. In the above example, each metric returns Pass or Fail depending on the logic defined.

| Metric Name | Description |
| --- | --- |
| user_pass_fail | Passes if the row count of the joined data is greater than **arg_count_1**. |
| furp_pass_fail | Passes if the row count is less than **arg_count_2**. |
        - Name
        - Type
        - Description
    3. From the **SQL logic** section, define your own logic to create expectations to provide the flexibility to execute expectations that are not provided by the system yet.

![SQL_Logic.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e78a60e1-15e0-aebe-c9df-34a321d8e7d6.png)

In the above example, the SQL logic validates the row count of joined datasets against two thresholds. It returns pass/fail results based on whether those conditions are met.

Specifically, it does the following:

> [!NOTE]
> **Note**
> 
> - Click **Upload** to import a pre-written SQL script directly into the editor, so you don’t have to type it manually.
> - Click the copy icon to copy the SQL logic to your clipboard.
> - Click the download icon to save the SQL logic to your local device as a .sql file.
      - Joins **dataset_arg_1** and **dataset_arg_2** using the specified join columns.
      - Counts the number of resulting records.
      - Evaluates whether:

Each result returns either **Pass** or **Fail** based on these checks.
        - If the row count is greater than **arg_count_1**, it returns **Pass** in **user_pass_fail**; otherwise, **Fail**.
        - If the row count is less than **arg_count_2**, it returns **Pass** in **furp_pass_fail**; otherwise, **Fail**.
3. Click **Create Template**.

#### Visualizing custom expectation templates on the templates dashboard

Once the custom template is created, you can view it on the templates dashboard. Each custom template provides a quick overview that includes the following details:

- Tags – Labels associated with the template.
- Linked expectations – Number of expectations linked to this template.
- Connected data systems – Data systems tied to the template.
- Status – Indicates whether the template is valid or invalid.

> [!NOTE]
> **Note**
> 
> A template is considered **Valid** if the SQL logic defined during its creation is syntactically and semantically correct. It shows as **Invalid** if the SQL logic contains errors.

#### Managing templates

In the templates list, you can manage each template by clicking the down arrow next to it. This reveals available actions:

- Edit template – Modify the existing configuration or SQL logic.
- Delete template – Permanently remove the template.
- Clone template – Create a duplicate of the template for reuse or modification.

> [!NOTE]
> **Note**
> 
> Cloning lets you safely make changes to templates that are already linked to active expectations. This ensures that existing expectations remain unaffected while you create new versions of the template.
- View validation logs – Review logs related to the SQL logic validation process

#### Editing templates

> [!NOTE]
> **Note**
> 
> You can only edit the following details of the template:
> 
> - Name
> - Description
> - Tags
> - Resources

1. On the templates list, click **Options** (three dots).
2. On the **Edit Template** popup, you can update the following details:
  - Expectation name
  - Expectation description
  - Tags

> [!NOTE]
> **Note**
> 
> You can also create a new tag in the Tags field.
> 
> 1. Click **+Add a new tag**.
> 2. Add the details about the new tag.
> 3. Press **Enter** to save the tag.
    - In the search bar, type in the relevant tags to open the tags in the search list. The search bar only shows those tags that are defined in the Enterprise Data Catalog.
  - Resources
    1. Click **+Add Resource**.
    2. Add resource tile and resource link.
    3. Click **Save** to successfully add the resource.
3. Click **Save Template** once all the changes are updated to successfully update the template details.

> [!NOTE]
> **Note**
> 
> Unlike predefined expectation templates, custom expectation templates offer full flexibility; every parameter can be edited. This lets you tailor the configuration to your specific needs.
> 
> Once a custom expectation template has been created and validated, you can use it to create a dynamic and reusable expectation from the Expectations section.

####
