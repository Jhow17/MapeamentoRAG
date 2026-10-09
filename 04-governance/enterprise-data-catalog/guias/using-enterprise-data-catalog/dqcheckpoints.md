---
title: "Checkpoints"
slug: "dqcheckpoints"
updated: 2026-07-18T12:40:10Z
published: 2026-07-18T12:40:10Z
canonical: "helpcenter.securiti.ai/dqcheckpoints"
stale: true
area: governance
modulo: enterprise-data-catalo
tipo: guia
data_captura: 2026-10-08
---

# Checkpoints

### Checkpoints overview

Checkpoints validate data, save validation results, run any actions you have specified, and finally, create a data doc with the results. Validation results are objects generated when data is validated against the set of expectations in the checkpoint. You can use a checkpoint to validate data in the future, and you can create and configure additional checkpoints for different business requirements.

Once you create your checkpoint, configure it, and specify the actions you want it to take based on the validation results, then all you need to do is run the checkpoint.

### Prerequisites

To perform actions on Data Quality Checkpoints, enable the corresponding permission(s) for the required operation. Only the permission(s) associated with the action you intend to perform are required. For more information, see [EDC RBAC](/latest/docs/edc-rbac-permissions-and-roles).

- Create Data Quality Checkpoint
- Delete Data Quality Checkpoint
- Execute Data Quality Checkpoint
- Read Data Quality Checkpoint
- Update Data Quality Checkpoint

#### Checkpoints dashboard

The checkpoints dashboard shows you the list of created checkpoints.

On the top right corner of the page, you can:

- Click **Expectations** to open the expectations gallery.

> [!NOTE]
> **Note**
> 
> You can also access the expectation gallery from the left navigation menu.
> 
> - Navigate to the **Expectations** icon and select **Expectations Gallery**.
> - Navigate to the **Expectations** icon and select **Templates** to open the templates dashboard.

- Click **Create Expectation** to create an expectation.

- The first row shows the search bar to filter the created checkpoint by its name. Under the search bar, you can filter the checkpoints **Last Expectation**, **Data Systems**, **Total Executions**, and **Owner**.
- At the right side of the search bar, the **Actions** button lets you delete checkpoints in bulk.
- Below the search options, the tiles show you the counts for the checkpoints created, total executions, and successful executions, along with their respective percentages.
- Below the count titles, you can view the list of created checkpoints.

#### Filtering checkpoints

The search bar lets you search for the created checkpoint by its name or description.

You can filter the specific checkpoint by applying filters on the following dropdown menus:

- Status
  1. Click the down arrow.
  2. Select the operator from the menu.
  3. Enter a status.
  4. Click **Apply** to see the filtered checkpoint.
- Last execution
  1. Click the down arrow.
  2. Enter a value or choose from the listed options.
  3. Select the operator (if any).
  4. Click **Apply** to see the filtered checkpoint.
- Data systems
  1. Click the down arrow.
  2. Enter a value or choose from the listed options.
  3. Select the operator (if any).
  4. Click **Apply** to see the filtered checkpoint.
- Total executions
  1. Click the down arrow.
  2. Enter the value.
  3. Click **Apply** to see the filtered checkpoint.
- Owner
  1. Click the down arrow.
  2. Enter a value or choose from the listed options.
  3. Select the operator (if any).
  4. Click **Apply** to see the filtered checkpoint.

#### Creating checkpoints

To create checkpoint:

1. From the top right corner of the page, click **Create Checkpoint**.
2. On the Create Checkpoint page, add the following details:
  1. Under the **General Information** section, specify the:
    - Unique name
    - Description
  2. Select the datasource from the **Datasource** menu. The menu shows the list of datasources that you have in the Enterprise Data Catalog.
  3. Once you select the datasource, you can view the list of applicable expectations in the **Expectations** menu.
3. Expectations section: The Expectation section contains two cards: one for linking system expectations, and another for linking custom expectations.
  - Click **System Expectations** to link expectations that were created using predefined templates provided by the platform.

You must associate your checkpoint to the expectation. For that, you can search for the expectation using the Expectation Name or through the search bar.
    1. Mark the checkbox(s) to select the required expectation(s) from the list.
    2. Once you hover on the expectation, on the right side of the page, a popup appears that shows details about the expectation.
    3. From the **Dataset** menu, you must specify the dataset. The dropdown shows you the list of only those datasets which are registered in the Enterprise Data Catalog.
  - Click **Custom Expectations** to link expectations that were built using custom SQL templates tailored to your specific data validation needs.

In the context of custom expectations, checkpoints bind logic-driven templates to real datasets and parameter values. They serve as automation tools for enforcing data quality rules, such as row counts, null checks, or joins, and produce metrics (like pass/fail) that indicate whether data meets defined conditions. Once configured, checkpoints can be run manually or on a recurring schedule to monitor data health.

Example

![Checkpoint_configuration.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3e5c72ca-f5e2-cc72-7d57-aaa3d7d69611.png)

In the above example, the selected expectation is named **Customer Volume Validation**, which is based on a custom SQL template designed to ensure that customer records meet specific volume thresholds after joining two datasets. The datasets are bound to the corresponding metrics so that the **Pass** or **Fail** results generated by the expectation are correctly reflected on the dataset page, enabling users to monitor data quality directly at the dataset level.

**Input configuration**

| Parameter | Value | Purpose |
| --- | --- | --- |
| arg_count_1 | 1000 | Minimum number of joined records required to pass **user_pass_fail**. |
| arg_count_2 | 5000 | Maximum number of joined records allowed to pass **furp_pass_fail**. |
| dataset_arg_1_join_column | customer_id | Join key from the first dataset, identifying unique customers. |
| dataset_arg_2_join_column | customer_id | Join key from the second dataset, matching the same customers. |

**Dataset mapping**

| Dataset role | Description |
| --- | --- |
| dataset_arg_1 | - Select any dataset from the **dataset_arg_1** menu. For example, **HuzDBOne.HuzDBOne.Customer,PROD**. |
| dataset_arg_2 | - Select any dataset from the **dataset_arg_1** menu. For example, **HuzDBOne.HuzDBOne.CustomerTestDetails,PROD**. |

The selected datasets are joined on the **customer_id** field to analyze the volume of customer engagement data relative to customer master data.

**Metrics**

Once this checkpoint is executed, it validates whether the volume of customer engagement data, when joined with the customer master table, falls within the defined threshold range.
    - From the **Expectation** menu, select the expectation and configure the checkpoint with real datasets and parameters.
    - From the **Metric** menu, select the metric values as described below:

| Metric | Description |
| --- | --- |
| user_pass_fail | Passes if the resulting join yields more than 1,000 records. |
| furp_pass_fail | Passes if the resulting join yields fewer than 5,000 records. |
4. From the **Schedule** section, you can schedule checkpoints to let them execute automatically at specified times without manual intervention. This ensures consistent data quality checks and enhances the reliability of your data processes.
  - Select **Run Manually** to activate, deactivate, and start the execution manually at any time.
  - Select **Run on Periodic Schedule** to set execution timings based on a user-defined schedule. Set the specific time for your scan, choose Daily, Weekly, or Monthly from the **Periodic Schedule Frequency**, and specify any time of the day, week, or month.
    - You can also select **Custom Cron** from the **Periodic Schedule Frequency** to schedule tasks in Unix-like operating systems.
    - Enter the expression in the [Cron Expression Builder](https://crontab.guru/). You can get assistance from the expression builder to create the expression.
5. Click **Create Checkpoint**.

#### Executing checkpoints

- Choose the checkpoint from the checkpoints list. Click the play icon to execute the checkpoint. The execution process may take a few minutes depending on the number and complexity of expectations included as well as the amount of data to be tested.

You can easily check the status of the executed checkpoints, which can be in one of the following states:

| Status | Description |
| --- | --- |
| Submitted | The menu icon is disabled and you cannot view the checkpoint details. |
| Running | The menu icon is disabled and you cannot view the checkpoint details. |
| Completed | The menu icon is enabled and you can view the checkpoint details. |
| Failed | The menu icon is enabled and you can view the checkpoint details. |

> [!NOTE]
> Note
> 
> Datasets ingested through [Sensitive Data Intelligence](/v1/docs/discovery-scans) can execute data quality checkpoints without any issues. However, when datasets are ingested via [EDC ingestion](/v1/docs/edc-ingestion), the data quality checkpoint fails during execution.

#### 

#### Exploring checkpoints

You can view the following details of each checkpoint in the list:

- Checkpoint name
- Last execution
- Last run
- Data system
- Total executions
- Next scheduled run
- owner

#### Expanded view

- From the checkpoints list, click the down arrow for the checkpoint for which you want to view the following details:
  - Execution ID (You can copy the execution ID by clicking the copy icon located to the right of the execution ID)
  - Status
  - Start time
  - End time
  - Passed expectations
  - Failed expectations
- Click **Options** (three dots) to perform the following actions per execution:
  - Click **View Data Docs** to view the data docs.

Data Docs translate expectations, validation results, and other metadata in human-readable documentation. This automatically compiling your data documentation from your data tests keeps your documentation current.
  - Click **Download Log** to download logs in the **.txt** format.

The log file contains crucial information about the execution, including any errors encountered during execution, successful execution logs, and details on how the execution was processed. These logs serve as a valuable resource for tracking and analyzing the performance and outcomes of executed tasks within the framework.
  - Click **Delete Execution** to delete the execution.
- Click checkpoint metadata explorer to view the detailed metadata for each checkpoint.
- After the successful execution of the checkpoint, view its details in the dataset under the **Validation** tab.
  1. Open **Enterprise Data Catalog**, then choose **Datasets**.
  2. Click on the data system folder and subfolders to open the dataset for which you need to view the validation details.
  3. On the dataset page, click the **Validation** tab to view the details about passed and failed expectations.
    - Click the down arrow to view the expectation details.

#### Edit checkpoint

To edit checkpoint:

1. Choose the checkpoint from the checkpoints list that you want to edit.
2. Click **Options** (three dots).
3. On the **Edit Checkpoint** page, edit the details to suit.
4. Click **Edit Checkpoint** to save changes.

#### Delete checkpoint

To delete a single checkpoint:

1. From the checkpoints list, choose **Options** (three dots) **> Delete**.
2. On the confirmation popup, click **Delete Checkpoint**.
  - Mark the checkbox to keep the associated data docs.

![DQ_-_Data_docs_checkbox.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-411e8411-ed98-1a6a-6e4f-b87e39364aa4.png)

To delete multiple checkpoints:

You can select more than one checkpoint for deletion by selecting checkboxes.

1. On the checkpoints list, mark the checkboxes for the multiple checkpoints you want to delete.
2. Click the delete button in the pop-up that appears at the bottom-middle of the page.
3. On the confirmation popup, click **Delete Checkpoint**.
  - Mark the checkbox to keep the associated data docs.

> [!NOTE]
> **Note**
> 
> You can also delete multiple checkpoints using the **Actions** button located to the right of the search bar.
> 
> 1. Click **Actions > Delete**.
> 2. Mark the checkboxes you want to delete.
> 3. Click the delete button in the pop-up that appears at the bottom-middle of the page.
> 4. On the confirmation popup, click **Delete Checkpoint**.
>   - Mark the checkbox to keep the associated data docs.
