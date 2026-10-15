---
title: "Expectations"
slug: "dqexpectations"
updated: 2026-07-18T10:35:53Z
published: 2026-07-18T10:35:53Z
canonical: "helpcenter.securiti.ai/dqexpectations"
stale: true
area: governance
modulo: enterprise-data-catalog
tipo: guia
data_captura: 2026-10-08
---

# Expectations

### Expectations overview

Expectations are basically unit tests for your data. With expectations, you can assert what you expect from the data you load and transform, and catch data issues.

Expectations are verifiable assertions about data. They enhance communication about your data and improve the quality for data applications. They help you take the implicit assumptions about your data and make them explicit. Using Expectations helps reduce trips to domain experts and avoids leaving insights about data on the cutting room floor.

You can also create expectations to suit your specific data quality requirements. By defining and validating these expectations, you can ensure the integrity, quality, and consistency of your data throughout its lifecycle.

### Prerequisites

To perform actions on Data Quality Expectations, enable the corresponding permission(s) for the required operation. Only the permission(s) associated with the action you intend to perform are required. For more information, see [EDC RBAC](/latest/docs/edc-rbac-permissions-and-roles).

- Create Data Quality Expectation
- Delete Data Quality Expectation
- Read Data Quality Expectation
- Update Data Quality Expectation

#### Expectations dashboard

The expectations dashboard shows you the list of created expectations.

On the top right corner of the page, you can:

- Click **Templates** to open the templates gallery.

> [!NOTE]
> **Note**
> 
> You can also access templates from the left navigation menu.
> 
> - Navigate to the **Expectations** icon and select **Templates**.

- Click **Checkpoints** to open the checkpoints listing.
  - You can also access checkpoint listing page from the left navigation menu.
    - Navigate to the **Checkpoints** icon and select **Checkpoints Listing**.
- Click **Create Expectation** to open the create expectation page.

The first row shows the count of created expectations and passed expectations.

#### Filtering expectations

The search bar lets you search for the created expectation by its name or description. You can also select values from the following menus to filter specific templates:

- Passed checkpoints
  1. Click the down arrow.
  2. Select the operator from the menu.
  3. Enter a numeric value.
  4. Click Apply to see the filtered expectations.
- Data systems
  1. Click the down arrow.
  2. Select the operator from the menu.
  3. Enter a value.
  4. Click Apply to see the filtered expectations.

You can view the following details of each listed expectation:

- Passed checkpoints
- Data system
- Last modified
- Owner

#### Create expectation

To create an expectation, you must specify the template and a unique name to the expectation.

1. Open the **Expectations** page.
2. On the upper right corner of the page, click **Create Expectation**.
3. On the **Create Expectation** page, from the **Expectation Template** menu, to select the template, search with key words or:
  1. Select the **parent template type**.
  2. Select the **template**. The rightmost panel displays the details of the template you selected.
  3. Click **Apply** to select the template.
4. In the **Name** field, enter the unique expectation name.

Enter the following fields to configure the Argument.

Arguments are the input parameters or conditions you provide when defining an expectation. They specify the criteria or conditions that data must meet to be considered valid.
5. Enter the following fields to configure the **Argument**.

When creating expectations for data, you use the following fields to specify the criteria that your data must meet. This helps to ensure the quality and reliability of your dataset.

> [!NOTE]
> **Note**
> 
> Each template type has a unique set of argument parameters. Find a comprehensive list of all the possible parameters in the table provided below.

| Input fields | Description |
| --- | --- |
| Column | Name of the column in your dataset for which you want to define an expectation. Column name indicates which data you are setting the expectation for. |
| Column_A | The first column name. |
| Column_B | The second column name. |
| Min_value | Minimum allowable value. |
| Average | Expected average (mean) value for the specified column. This means that you anticipate the column's average to be close to the value you provide. |
| Or_equal | Typically used in conjunction with other fields, like min_value. When it is set to **True**, it means that the specified condition should be considered met. if the value is equal to the boundary value. |
| Start_datetime | This field specifies an expected start datetime. This could be the earliest date or time you expect to find in the specified column. |
| Column_set | It defines expectations that involve multiple columns simultaneously, which can be useful for complex data validation. |
| Quantile_ranges | Key **\quantiles\** is an increasingly ordered list of desired quantile values (i.e. floats). Key **\value_ranges\** is a list of 2-value lists that specify a lower and upper bound (inclusive) for the corresponding quantile (with [min, max] ordering). The length of the \quantiles\ list and the \value_ranges\ list must be equal. - Click **Upload** to upload the Quantiles in a formatted JSON file. Click **Copy code** to copy the Quantile_ranges code. |
| Value_pairs_set | All the valid pairs to be matched. |
| Regex_list | This field lists the regular expressions used for pattern matching or validation. For example, **\b[A-Za-z]\b**. |
| Regex | The regular expression of the column entries should match. |
| Other_table_name | The name of the other table. |
| Like_pattern | The like pattern expression the column entries should match. |
| Strftime_format | A strftime format string to use for matching. |
| Strict_min | If **True**, the minimal column minimum must be strictly larger than min_value, default=**False**. |
| Strict_max | If **True**, the minimum proportion of unique values must be strictly larger than min_value, default=**False**. |
| Value | The expected number of rows. |
| Max_value | The maximum value allowed. |
| Partition_object | The expected partition object. |
| Threshold | A maximum Z-score threshold. All column Z-scores that are lower than this threshold will be evaluated successfully. |
| Like_pattern_list | The list of like pattern expressions the column entries should match. |
| Value_set | A list of potential values to match. |
| Allow_relative_error | Whether to allow relative error in quantile communications on backends that support or require it. |
| Json_schema | The JSON schema in string form to match. |
| Sum_total | Expected sum of columns. |
| Column_list | Set of columns to be checked. |
| Exact_match | Whether the list of columns must exactly match the observed columns. |

#### Creating an expectation using a custom template

On the Create Expectation pop-up, configure the following details:

1. From the **Expectation Template** menu, select the pre-defined template that outlines the structure and validation logic for the expectation.

> [!NOTE]
> **Note**
> 
> Once a template is selected, the **Arguments** and **SQL Logic** sections automatically appear. The **SQL Logic** section is populated with the logic defined during the creation of the custom template. This logic is displayed for reference only and cannot be edited on the **Create Expectation** page. The **Arguments** section lets you input specific values for the parameters used in the logic.
2. In the **Name** field, enter a clear name for the expectation.
3. In the **Arguments** section, provide valid values for each parameter. These arguments are dynamic inputs used within the SQL logic.

Example

Based on the SQL logic defined above, here are some example values you can use for the arguments:

| Argument | Example input |
| --- | --- |
| arg_count_1 | 10000 |
| arg_count_2 | 50000 |
| dataset_arg_1_join_column | user_id |
| dataset_arg_2_join_column | user_id |
4. From the **SQL Logic** section, double-check the logic.
5. Click **Create Expectation**.

Your expectation now appears on the **Expectations Dashboard**, where it can be monitored, managed, and scheduled for execution as part of your data quality workflows.

#### Edit expectation

To edit expectation:

1. Choose the expectation from the expectation list that you want to edit.
2. Click **Options** (three dots).
3. On the **Edit Expectation** page, edit the details to suit.
4. Click **Edit Expectation** to save changes.

#### Delete expectation

To delete a single expectation:

- From the expectations list, choose **Options** (three dots) > **Delete**.

To delete the multiple expectations:

1. On the expectations list, mark the checkboxes for the expectations you want to delete.
2. At the bottom-middle of the page, a pop-up shows up - click the delete button.
3. On the confirmation popup, click **Delete Expectation**.

> [!NOTE]
> **Note**
> 
> You cannot delete expectations that have inherent dependencies on associated checkpoints. If you try to delete such expectations, a popup warns you that these expectations are linked to associated checkpoints. It also shows a list of the specific checkpoints associated with each expectation.

####
