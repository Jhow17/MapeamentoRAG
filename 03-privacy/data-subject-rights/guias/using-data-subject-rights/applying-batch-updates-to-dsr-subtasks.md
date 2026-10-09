---
title: "Applying batch updates to DSR subtasks"
slug: "applying-batch-updates-to-dsr-subtasks"
updated: 2026-04-05T12:47:23Z
published: 2026-04-06T21:00:01Z
canonical: "helpcenter.securiti.ai/applying-batch-updates-to-dsr-subtasks"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Applying batch updates to DSR subtasks

You can use batch update tools in the DSR workbench to do any or all of the following to the subtasks of a DSR request for which you are a co-owner. This feature is useful in cases where you have a workflow that assigns all subtasks to a central user, perhaps a DPO, who must reassign them after verification:

- Update the ownership of some or all subtasks of a DSR request
- Select a process for the processing record field
- Set the response status to Approve, Declined, or No Data

1. In Securiti, open a DSR request for which you are a co-owner, then click the **Batch Update** tab.
2. Expand the **Tasks & Subtasks** area and use the tools there to choose which tasks and subtasks the batch update applies to. For each data system, you can select specific subtasks for the update, as shown below.

![RN_batch_update11.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-34c1d776-6850-f73c-c89a-74bd2b7b0912.png)
3. Expand the **Subtask** **Fields** area and use the tools there to reassign ownership and fill in process information, as shown below. The available processes are those you have defined using the Data Mapping Automation tools.

![RN_batch_update12.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b77e246e-3f6d-ddb2-dd27-d77cfed4f052.png)
4. Expand the **Subtask Response Status** area and use the tools there to choose the status to apply to the selected subtasks, as shown below.

![RN_batch_update13.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9b07ed9e-781b-dbc4-00e4-7053199647cb.png)
5. When you are done, at the bottom of the tab click **Apply Update**.

> [!WARNING]
> Important
> 
> When you customize subtask instructions, batch update behavior depends on how those instructions are configured. For more information, see [Customizing Subtask Instructions](/latest/docs/customizing-subtask-instructions).
> 
> Observe the following caveats:
> 
> - When you apply a batch update for processing details, Securiti updates only those subtasks where processing details are enabled. Subtasks without this instruction remain unchanged.
> - For checkbox-based instructions, Securiti automatically marks them as complete when you set the subtask status to Approve. This includes actions such as confirming opt-out of sale or confirming data element presence.
> - If you configure subtask instructions as mandatory, such as uploading attachments or adding notes, you cannot complete the subtask until you provide the required input.
> - If a batch update fails, Securiti does not show the failure in the UI. Instead, it sends an email with details about the affected subtasks and the reason for failure.
