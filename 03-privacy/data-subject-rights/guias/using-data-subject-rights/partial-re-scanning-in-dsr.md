---
title: "Partial re-scanning in DSR"
slug: "partial-re-scanning-in-dsr"
updated: 2026-08-09T17:45:22Z
published: 2026-08-10T21:00:09Z
canonical: "helpcenter.securiti.ai/partial-re-scanning-in-dsr"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Partial re-scanning in DSR

**Scenario**

As a Data Security Officer, you are responsible for reviewing large volumes of DSR tasks. Re-running automation and rescanning all the data systems involved for the entire request takes more time and resources. With partial rescans, you selectively reprocess only the tasks or data systems that need attention. This improves efficiency and helps you maintain performance while keeping requests accurate and up to date.

## Overview

You can partially rescan DS requests to reduce automation time and improve resource efficiency. This lets you target specific tasks and data systems that need re-scanning. You can rescan one or more tasks after they are created, whether through DSR Automation, workflow or via API, as long as a Data System is associated with the task. You can re-scan any DSR request that has not already been published.

> [!NOTE]
> **Note**
> 
> To partially rescan tasks created via a workflow, confirm that the data systems for those tasks are part of DSR Automation. Check if the "Include this instance in the DSR workflow" checkbox is enabled in the **Permissions** tab of the relevant data systems.
> 
> ![Screenshot_2025-01-24_at_2_01_39_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ff9da8d6-4e07-09d4-79f6-afb262c1dde5.png)

You can either initiate partial rescan from the **DSR Dashboard** or from within the **DSR Workbench.**

To re-scan selective tasks:

1. In Securiti choose **Data Subject Rights > DSR Dashboard**.
2. Locate the DSR request you want to re-scan, and at its right edge choose **Options (three dots) > Select Tasks for Rescan.**

Or open the DSR request in the DSR Workbench and at the upper right corner of the screen choose **Rescan > Rescan Tasks.**
3. On the Rescan Tasks page, you can search tasks by name or filtering by status (In Progress or Completed), then select the ones to re-scan. Once done, click **Rescan**.

![Screenshot_2025-08-06_at_11_30_03_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-fcc16b50-d78a-4eed-82b0-b917182bc2dc.png)

> [!NOTE]
> **Note**
> 
> You cannot run multiple rescans in parallel. Each rescan must complete before the next one can begin. For custom request types, when you update a request type setting and partially scan a DSR, the rescan uses the old setting from the time the DSR request was submitted, not the latest one.

Once rescanning completes, Securiti updates the tasks and subtasks in the DSR workbench along with **Data Subject Explorer** with any new data found during the scan.

Once partial rescan completes, Securiti triggers the 'Tasks Creation Completed' signal to the workflow. This is the same action it takes during a standard DSR creation or full DSR rescan. As a result, any workflows automatically execute if they are set to listen for this specific event or related ones.

### Rescanning a sequential DSR request

A DSR request submitted through a form with sequential task processing enabled behaves differently during a partial rescan. For more information on sequential task processing, see [Configuring sequential task processing in the DSR form](/latest/docs/configuring-sequential-task-processing-in-dsr-forms).

Like the Worklist and Batch Update tabs, the Rescan Tasks popup lets you filter by **Rule Name**, **Level ID**, and **Status** before selecting which tasks to rescan.

![Task management interface showing completed and in-progress tasks for data access requests.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-04 at 8.11.30 AM.png)

A partial rescan doesn't delete or recreate tasks, it reruns automation on the subtasks you select. If new data is found, an already-approved or already-declined subtask returns to Review status, requiring the subtask owner to review and resubmit it.

For instance, say a rule has an execution block that triggers Task B when Task A is approved, and a separate execution block that triggers Task C when Task A is declined. Task A's subtasks were originally approved, which already triggered Task B. You partially rescan Task A:

- If the subtask owner reviews the new data and approves Task A again, the same outcome as before, Securiti does not create Task B a second time, since it already exists.
- If the subtask owner instead declines Task A this time, a different outcome, Securiti creates Task C as well, since that execution block's condition is now met. Task B is not deleted, both Task B and Task C now exist.
- If automation itself resolves Task A to No Data found on the rescan, and a third execution block is configured to trigger on No Data found, Securiti creates that execution block's task too. No Data found subtasks are never suppressed on a sequential DSR request, so this status remains available for execution blocks to evaluate against.
