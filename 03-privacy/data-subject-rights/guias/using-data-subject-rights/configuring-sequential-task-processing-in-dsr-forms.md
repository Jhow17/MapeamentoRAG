---
title: "Configuring sequential task processing in DSR forms"
slug: "configuring-sequential-task-processing-in-dsr-forms"
updated: 2026-08-09T16:36:54Z
published: 2026-08-10T21:00:09Z
canonical: "helpcenter.securiti.ai/configuring-sequential-task-processing-in-dsr-forms"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Configuring sequential task processing in DSR forms

**Scenario**

As a Data Privacy Officer, you configure rules that map DSR conditions to task templates for teams handling identity checks, data retrieval, and legal review. Previously, every template tied to a rule fired together, so all tasks ran in parallel with no way to hold one back until another was resolved. With sequential task processing, you organize a rule's templates into up to 4 levels. Level 1 templates run first, and level 2 templates execute only once level 1's subtasks reach the status you define. For instance, you can set up legal review to start only after retrieval tasks come back approved across every data system. This lets you sequence work based on earlier results.

## Overview

Sequential task processing lets you control the order in which a rule's task templates execute, so later templates execute only once earlier ones reach a specific outcome. You can organize a rule's templates into up to 4 levels.

Level 1 has no dependency, since no level precedes it, so its templates execute once the rule's conditions are met and email verification is completed.

> [!NOTE]
> Note
> 
> If email verification isn't enabled on the form, level 1 templates execute as soon as the DSR request is created instead.

Each level after that depends on the level directly before it: level 2 templates execute based on the outcome of level 1 templates, level 3 templates execute based on the outcome of level 2 templates, and so on. Within a single level, the execution of different templates can depend on different templates from the level before, so each one executes independently once its own condition is met.

Each level supports up to 10 execution blocks, and each execution block can carry multiple nested rules, so a template's execution can depend on more than one condition at once. Defining a task sequence is optional per rule.

> [!NOTE]
> Note
> 
> A rule can also run without levels, in which case all of its templates execute together as they do today.

To define a task sequence for a rule:

1. While configuring a rule's [task templates section](/latest/docs/configuring-rules-in-the-dsr-form), enable the Define Task Sequence toggle.

![Interface showing task sequence setup with highlighted options for defining task templates.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-03 at 4.00.12 PM.png)
2. Under Level 1, click **Add Sequence Rule** (plus icon), then choose one or more task templates to execute from the Execute menu. You can add up to 10 execution blocks per level.

![Task sequence setup with multiple execution levels and templates for automation rules.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-03 at 4.06.40 PM.png)
3. Click **Add Level**, then under Level 2, click **Add** (plus icon) and choose templates to execute from the Execute menu.
4. In the IF row, choose one or more templates and mark the status that triggers this execution block. To add another condition to the same execution block, click the options icon (⋮) next to the **Execute** row and choose to add a nested rule. All conditions within a single execution block must be met for it to trigger, but each execution block in a level triggers independently of the others. For instance, an execution block can require both Data Retrieval to be approved and Legal Review to be approved before it executes, separate from any other execution block in that level.

![Details of task sequence rules with options to add nested rules and conditions.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-03 at 4.13.47 PM.png)
5. Repeat steps 3 and 4 to add up to 2 more levels (Level 3 and Level 4). Each level's execution blocks depend on the outcome of templates in the level directly before it.
6. Click **Create Rule**.

You can also associate a workflow with the Rule before creating it, if applicable to your form.

**Caveats:**

- At least one condition is required on every level except level 1.
- Duplicate execution blocks aren't allowed within the same level. An execution block is uniquely identified by the combination of the templates chosen in **Execute**, the templates chosen in the **IF** condition, and the status marked. If an execution block with that exact combination already exists in a level, you can't create another one in the same level. Similar execution blocks are allowed across different levels.
- If a form has both a sequential rule and a non-sequential rule, and a DSR request matches both, Securiti treats the entire DSR as sequential and treats every template configured in the non-sequential rule as level 1.
- Within a single IF condition, if you choose multiple templates, any one of them matching is enough to satisfy that condition (OR). Likewise, if you mark multiple statuses, any one of those statuses being met satisfies the condition (OR). This is separate from nested rules, where every nested rule must be met (AND).

### Processing sequential DSR requests in the workbench

Once a request is submitted using a form where sequential task processing is enabled, a few behaviors apply to that request that don't apply to a standard request while processing it in the [DSR workbench](/latest/docs/dsr-workbench-overview).

#### Filtering by rule and level

For sequential DSR requests, you can also filter tasks and subtasks by the rule and level they belong to, from both the Worklist and Batch Update tabs. This filtering option isn't available for standard DSR requests.

To filter tasks and subtasks in the **Worklist** tab:

1. Near the **Tasks** column, click Apply **Filters** (funnel icon).
2. In the **Filters** popup, choose a rule from the **Rule Name** menu, choose a level from the **Task Level** menu, or mark **Show only Active Subtasks** to hide subtasks already in a completed status. Once done, click **Apply**.

![Dashboard displaying DSR access request details and task management options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-03 at 8.12.11 PM(1).png)

- The **Rule Name** menu shows every published rule configured on the form used to raise the DSR request, including rules that didn't result in task creation for this request. Choosing a rule with no matching tasks returns an empty list.
- The **Task Level** menu shows Level 1 through Level 4. Choosing a level with no tasks or subtasks returns an empty list.

> [!NOTE]
> Note
> 
> Level 1 execution isn't limited to a sequential rule's own level 1 tasks. Two other cases also land at level 1:
> 
> - Tasks created from a workflow. These appear under the Workflow task in the Rule Name menu.
> 
> ![Dashboard displaying DSR access request with filters and subtasks for data management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-03 at 8.19.11 PM(1).png)
> - Tasks created from a non-sequential rule, when the same form also has a sequential rule that matches the DSR request. Securiti treats every template in that non-sequential rule as level 1.

#### Level progression timing

Securiti checks an execution block's condition against the status of specific subtasks created from templates in the level before it. Even if that condition is already met, the next level doesn't execute until automation finishes for every task in the previous level.

- For structured data systems, Securiti creates tasks and subtasks before automation or scan completes. A subtask owner can approve or decline manually while the Automation bar is still in progress. Even if every subtask in the level already matches the status an execution block requires, Securiti waits for the Automation bar to reach full progress before executing the next level.

![DSR access request dashboard showing task details and automation progress for a user.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-03 at 9.54.17 PM.png)
- For unstructured data systems, this timing gap doesn't come up. Securiti creates a task and subtasks only once automation has already found and attached data.

> [!NOTE]
> Note
> 
> You can configure an execution block to trigger when a subtask reaches Error, the same as any other status. This lets you design a level for handling failures, such as escalating to manual review, instead of only building around Approved, Declined, or No Data found outcomes.

#### Force-timeout on level progression

If a task's automation and creation is stuck for too long, Securiti eventually moves the DSR forward instead of leaving it blocked indefinitely.

If automation on a task remains incomplete for 5 days, Securiti forces the Automation bar to complete. Once the Automation bar completes, whether naturally or through this force-timeout, Securiti evaluates the subtask's existing status against the next level's execution blocks and triggers a match if one exists.

For instance, say an execution block is configured so that Task B executes when Task A's subtask is approved. The subtask owner approves Task A's subtask while automation on Task A is still in progress. Task B does not execute yet, since Securiti still waits for the Automation bar to reach full progress. If automation on Task A remains stuck for 5 days, Securiti forces the Automation bar to complete. Since Task A's subtask is already approved, Securiti executes Task B at that point.

#### Editing subtasks after the next level has triggered

You can still update a subtask's status after Securiti has already executed the next level based on it.

- If you update the subtask to the same status as before, Securiti does not trigger the next level a second time, since the corresponding task already exists.
- If you update the subtask to a different status, and a separate execution block's condition matches that new status, Securiti triggers that execution block's task as well.

For example, say Task A's subtask is approved, which triggers Task B. A separate execution block is configured to trigger Task C when Task A's subtask is declined. If you update Task A's subtask back to approved, Securiti does not create Task B a second time. If you instead update Task A's subtask to declined, Securiti triggers Task C. Task B is not deleted.
