---
title: "Configuring rules in the DSR form"
slug: "configuring-rules-in-the-dsr-form"
updated: 2026-09-23T09:37:57Z
published: 2026-09-23T09:37:57Z
canonical: "helpcenter.securiti.ai/configuring-rules-in-the-dsr-form"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Configuring rules in the DSR form

Rules let you control which task templates apply to a DSR request. You can create rules and associate them with Task templates and workflows.

> [!NOTE]
> **Note**
> 
> - For the foreseeable future, both rules and **Automation** settings defined in the **Form Settings** tab are supported simultaneously.
> - If no rules are configured for the DSR form, when a request is received Securiti uses the Automation settings defined in the **Form Settings** tab to create tasks and subtasks.
> - If one or more Rule conditions are configured and met, Securiti follows those rules and ignores **Automation** settings defined in the **Form Settings** tab.
> - If Rule conditions are configured but none are met, Securiti does not fall back to the automation settings. Instead, it marks the DSR request as No User Found.

To create a Rule and associate task templates to it:

1. In the Data Subject Rights module, choose **Settings > Form Builder**.
2. Choose the form you want to use, or create a new one.
3. On the DSR form builder configure all relevant components and navigate to the **Rules** tab. On this tab, click **Add Rules**.

![Screenshot_2025-06-29_at_10_45_06_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6c466988-618b-a734-1c42-0d91672e74f5.png)
4. On the **Rule Details** page, enter the **Rule Name** and define the condition or Rule to determine which templates should be executed for DSR requests submitted through this form.

A Rule supports the following parameters:

| Parameters | Description |
| --- | --- |
| Request Type | Lets you trigger task templates or workflows based on the type of incoming request. This supports all request types(system or custom) configured in the DSR form. > [!NOTE] > **Note** > > If a Rule condition includes a custom request type, the original settings configured for that type (such as whether DSR Automation is enabled and whether tasks are created per Data System) are discarded. Tasks are instead created based on the Task template associated with the Rule. |
| Other | Selection | Lets you trigger the associated task templates or workflows based on the selected option(s) from a custom **dropdown** or **multi-select** field configured in the DSR form. **Examples** - If the field captures the type data subject and condition is: **is one of > Employee** Securiti triggers the mapped Task template or workflow when “ Employee” is selected in the form. - You can also select multiple values to include more options: **is one of > Employee, Customer, Other** In this case, Securiti triggers the template or workflow when the submitted value matches any of those options. |
| Checkbox | Lets you trigger the associated task templates or workflows based on the value of a custom checkbox field configured in the DSR form. Securiti checks whether the data subject marked/unmarked the checkbox field during form submission and triggers the mapped Task template or workflow accordingly. For instance, if the field is labeled “I agree the Terms and Conditions” and the condition is set to Checked, the Securiti triggers the associated automation. |
| Jurisdiction | You can use this condition only if the “Auto detect source country (based on source IP)” or “Auto detect subject residency (based on country/state field)” option is enabled in the Response section of the DSR form builder. ![Screenshot_2025-06-29_at_10_54_57_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ac4922b9-b013-4ca8-4461-e4ba276ac072.png) This lets you trigger the associated Task template or workflow based on the jurisdiction detected from the data subject’s IP address or the country and state fields they enter when submitting the DSR form. |
| Country | Lets you trigger a Task template or workflow based on the selected country in the published DSR form. If you select multiple countries in the condition, you cannot include a state parameter in the same Rule. |
| State | This parameter works in combination with the Country parameter. |
5. A Rule supports the following operators:

| Operators | Description |
| --- | --- |
| is_one_of | The condition passes if any submitted value in the DSR form matches a configured value. - For single-value fields (such as Request Type or Dropdown): The submitted value must exactly match one of the configured values. - For multi-value fields (such as Multi-select fields or multi-request types): The condition passes if at least one submitted value matches any configured value. **Example:** Condition: is_one_of (Access, Portability) The condition passes if the form submission includes Access, Portability, or both. |
| is_all_of | The condition passes only if **all configured values** are present in the submitted form value. - Applies to fields that support multiple values. - The submitted value may include extra values, but must contain all of the configured values. **Example:** Condition: is_all_of (Access, Port) The condition passes if the submission includes both Access and Port even if other values like Erasure are also selected. > [!NOTE] > **Note** > > Jurisdiction, Country and State parameters don’t support this operator. |
| is_not_one_of | The condition passes only if none of the submitted values match the configured values. - For single-value fields: The condition passes if the submitted value is not listed in the condition. - For multi-value fields: The condition fails if any submitted value matches a configured value. **Example:** Condition: is_not_one_of (Access, Port) - The condition fails if the DSR request includes Access or Portability. - It passes only if none of the submitted requests match those in the condition. |
6. Once you define the condition, if you want to assign DSR requests to users other than the default form owners, select users from the **DSR Assignees** menu. The list displays active users within the organization.

> [!NOTE]
> **Note**
> 
> Observe the following caveats:
> 
> - You must attach a Task template or workflow to the Rule when adding DSR request assignees. Otherwise, no task or Subtask is created in the workbench. When a form has a Rule configured, Securiti does not follow the **Automation** settings.
> - If two rules, Rule1 and Rule2, are configured for a form and Rule1 has assigned owners while Rule2 does not:
>   - If only Rule1 is satisfied, the owners defined in Rule1 are assigned as DSR request owners.
>   - If only Rule2 is satisfied, the form owners are assigned as DSR request owners.
>   - If both Rule1 and Rule2 are satisfied, only the owners from Rule1 are assigned as DSR request owners (form owners are not added as ticket owners).

Further, click **Add Template** to associate a template with the respective Rule. Choose templates from the list.

You can also turn on **Define Task Sequence** toggle to control the order in which the task templates associated with rules execute. For more information, see [Configuring sequential task processing in DSR forms](/latest/docs/configuring-sequential-task-processing-in-dsr-forms).

> [!WARNING]
> Important
> 
> If you have already selected task templates in the **Select Task Template** menu, enabling the **Define Task Sequence** toggle stops using them, and disabling it afterward does not restore them either. Disabling deletes all levels and their configured templates, along with the original templates selected before you enabled it. Before enabling this toggle, confirm you do not need to keep any templates already selected above it.

If you need to send triggers to particular workflows then click **Add Workflow** and choose workflow(s) from the menu that needs to be triggered when a DSR request is submitted. If no workflow is applicable across any rules for a given DSR request, Securiti sends triggers to all active workflows with the DSR trigger node for that DSR request.

> [!NOTE]
> **Note**
> 
> Observe the following caveats:
> 
> - Either a template or a workflow must be associated with each Rule.
> - Only active workflows are shown and can be selected in the menu.
> - The workflows must have DSR trigger nodes.

You can also mark the **Data Element Redaction** checkbox which data elements Robotic Automation redacts or leaves unredacted in the report generated for this rule's tasks. For more information, see [Filtering data elements in DSR attachments](/latest/docs/filtering-data-elements-in-dsr-attachments).
7. Once you are done with configuring all elements for a Rule, click **Create Rule**.

![Screenshot_2025-07-30_at_12_23_36_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a0987628-2590-08e1-ac85-06e79cf781a5(1).png)

> [!NOTE]
> **Note**
> 
> The DSR form must be published for these rules to take effect.

Once the DSR form is published, any incoming request that matches the configured rules automatically triggers task and Subtask creation in the DSR Workbench, based on the linked templates. For more information on how these tasks and subtasks are created, see [Task and Subtask creation based on task templates](/v1/docs/task-and-subtask-creation-based-on-task-templates).

You can also edit, clone or delete a Rule. To do so:

1. On the **Rules** tab, near the right corner of the Rule row, click options (three dots). Choose the operation you want to perform on the Rule.

![Screenshot_2025-06-29_at_1_30_04_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8f53a498-4497-e097-385e-4d26c2b20fbb.png)
2. Publish the DSR form for these rules to take into effect.

A predefined structure used to create tasks and subtasks in DSR workbench. It includes task details, optional data system associations, deadlines, automation settings, and subtasks. Task templates let you standardize and automate task creation across requests.
