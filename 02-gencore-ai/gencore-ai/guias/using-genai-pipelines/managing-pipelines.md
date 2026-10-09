---
title: "Managing pipelines"
slug: "managing-pipelines"
updated: 2025-12-09T09:18:47Z
published: 2025-12-09T09:18:47Z
canonical: "helpcenter.securiti.ai/managing-pipelines"
area: gencore-ai
modulo: gencore-ai
tipo: guia
data_captura: 2026-10-08
---

# Managing pipelines

To manage pipelines, make use of the following options listed in the **Options** (three-dot menu) to the right side of a pipeline:

![132_RAG_pipeline_options_labelled.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-23ce60bc-7aed-673b-1e67-5c442e1e9760(1).png)

### Edit a pipeline

To edit a pipeline:

1. Click **Edit**. The **Edit** popup displays.

![132_RAG_pipeline_options_Edit.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8a20fabb-322d-e200-43b8-c4293b8e6603(1).png)
2. Update the title and/or description for your pipeline.
3. Click **Update**.

### View Audit Logs

To view audit logs for a pipeline, click **Audit Log**. Securiti displays the **Audit Logs** page.

![132_RAG_pipeline_options_Audit_Log.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-177b019b-bda3-8b6b-d204-1cecec02b7fd(1).png)

### Clone a pipeline

To clone a pipeline:

1. Click **Clone**.

![132_RAG_pipeline_options_Clone.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-cbe9076c-8af1-3490-a1a3-afae112c7ba0(1).png)
2. Provide a title and description for the cloned pipeline.
3. Click **Clone**.

If the pipeline you clone has custom files as a source, the custom files are not cloned in the process. You must upload the custom files in the cloned pipeline.

![Cone_pipeline_message.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f9e34a05-9d4d-5e9f-8945-da7859d585ee(2).png)

### Purge a pipeline

To purge a pipeline:

1. Click **Purge**. A confirmation popup displays.

![132_RAG_pipeline_Purge.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-dce3fabf-7be1-56a4-0342-51cf8d7ebe1c(1).png)
2. To confirm purging the pipeline, click **Purge**. To cancel, click **Cancel**.

### Cancel pipeline execution

To cancel the execution of a pipeline, click **Cancel**.

### Delete a pipeline

You can delete a singe pipeline or multiple pipelines in bullk.

- To delete a single pipeline:
  1. Click **Delete**. A confirmation popup displays.

![132_RAG_pipeline_Delete.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b7ea2ff6-b1eb-d71a-88a4-0031ad62af4c(1).png)
  2. To confirm deleting the pipeline, click **Delete**. To cancel, click **Cancel**.
- To delete pipelines in bulk:

> [!NOTE]
> **Note**
> 
> While deleting pipelines, please note:
> 
> - Pipelines in the Loading state cannot be deleted.
> - Super admins can delete any pipeline.
> - Regular users can only delete pipelines they own. If a user attempts to delete a pipeline created by another user, an error response displays.
  1. Select the pipelines you want to delete. A popup displays showing the number of pipelines selected and a **Delete** button.

![Bulk delete for GenAI pipelines](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Bulk delete popup.png)
  2. Click **Delete**.

![Bulk delete popup button for GenAI pipelines](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Bulk delete popup button.png)
  3. On the popup confirming the delete action, click **Delete Pipelines**.

![Bulk_delete_confirmation_Labelled.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0141d19b-97bd-c0d9-0fa2-562952d5bf9e(1).png)

### Audit Logs

The Audit Log page for a pipeline displays the creation and activity details logged for the pipeline.

![Audit log displaying changes and execution states for various pipelines and users.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Audit Log page.png)

- You can filter the logs by the following parameters:
  - **Time**: The time the activity was done. You can define settings as follows:
    1. Select **Before** or **After**.
    2. Select **Date**.
    3. Click **Apply**.
  - **Entry Type**: The type of entry. You cans select from the following and click **Apply**:
    - Changed
    - Execution
  - **User**: The user carrying out the activity. You can define settings as follows:
    1. Define parameter from the following:
      - Equals: The result must be equal to the parameter entered.
      - Not equals: The result must not be equal to the parameter entered.
      - Is one of: The result must be one of the parameters entered. You can type multiple parameters. To enter a parameter, type the parameter value and press Enter. Add more parameters if required.
    2. Select user ID. You can select multiple user IDs.
    3. Click **Apply**.
  - **Activity**: The type of activity carried out for the pipeline. You can select from the following and click **Apply**:
    - Clone
    - Create
    - Delete
    - Deleted Failure
    - Disable
    - Enable
    - Error
    - Update
  - **Message**: The message explaining the details of the activity.
    1. Define parameter from the following:
      - Equals: The result must be equal to the parameter entered.
      - Not equals: The result must not be equal to the parameter entered.
      - Is one of: The result must be one of the parameters entered. You can type multiple parameters. To enter a parameter, type the parameter value and press Enter. Add more parameters if required.
      - Contains: The result must contain the parameter.
    2. Enter keyword or phrase.
    3. Click **Apply**.
- You can sort the logs as follows:
  - Time
  - User
  - Activity

## Related

- [Using GenAI pipelines](/using-genai-pipelines.md)
