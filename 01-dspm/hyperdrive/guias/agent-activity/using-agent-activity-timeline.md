---
title: "Using Agent Activity Timeline"
slug: "using-agent-activity-timeline"
updated: 2026-09-23T11:50:36Z
published: 2026-09-23T11:50:36Z
canonical: "helpcenter.securiti.ai/using-agent-activity-timeline"
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Using Agent Activity Timeline

## Overview

The Agent Activity Timeline is a dedicated page that displays activity events in chronological order across your connected data systems. It visually represents actions such as access, modification, and deletion, letting you identify bursts of operations or suspicious patterns at a glance.

You can use the Timeline page to:

- Observe patterns such as spikes in access, modification, sharing, or deletion activity.
- Identify concentrated bursts of actions that may indicate automated behavior or potential risk.
- Correlate activity with restore points to determine whether recovery options exist before a destructive event.
- Compare activity across agents, data systems, and files within the same time window.
- Undo a single AI-driven action, or revert all changes made after a selected restore point.

> [!NOTE]
> Note
> 
> The Timeline view is also available in Instance Explorer for an individual instance. On an instance's **Activity Log** results, click **Timeline** to switch from the tabular **Activity Logs** view. The dedicated Timeline page does not replace that view.

## Accessing the Agent Activity Timeline

To open the Agent Activity Timeline:

1. In Securiti, from the left navigation menu, click the Jewel icon and select **Agent Activity**.
2. From the **Dashboards** menu, select **Timeline**, as shown below.

![Navigation menu showing Agent Activity and highlighted Timeline option for user selection.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/timeline_nav.png)

## Understanding the Timeline page

The Timeline page includes the following components:

- **Agent** and **Data System** filters at the top of the page, which scope the timeline to a specific AI agent or data system. Both are set to **All** by default.

> [!WARNING]
> Important
> 
> The **Agent** menu is scoped to agents that have performed at least one recorded activity and that carry a visible Agent tag. If an agent is missing from the menu, verify the following:
> 
> - The agent has performed a recorded activity within the selected time span. Widen the span using the **All** option and check again.
> - Activity Analysis has completed for the data system the agent acts on. Until it does, the agent has no recorded activity to display.
> - The application carrying the agent has a visible Agent tag.
> 
> An agent that has never performed a recorded activity does not appear in the menu, even though it exists in your tenant.
- An activity-type legend, which lists the action types present in the current scope. The types include:
  - Access
  - Create
  - Modify
  - Move
  - Search
  - Share
  - Unshare
  - Delete

Each type has its own color, and the legend displays only the types found in the selected scope.

- A granularity indicator, such as **Showing activities per hour**, which reflects the current zoom level.
- A time-range selector in the upper-right corner, with the options **1D**, **1W**, **1M**, and **All**.
- Swimlane rows, grouped by entity type, which show when each action occurred.
- A window pan control at the bottom of the page, which controls the time span the timeline displays.

### Reading the swimlane rows

Each horizontal row represents one entity involved in the recorded activity. Rows are grouped and color-coded by entity type, so that you can see who performed an action, what it affected, and when it occurred. The rows are arranged as follows:

1. Actor-level rows, such as **Agent**, appear at the top. Markers clustered close together on an agent row indicate that the agent performed several actions in a short time frame.
2. Resource-level rows, such as **Files** or **Data Systems**, appear beneath the actor. A **Modify** marker on both the agent row and a file row at the same timestamp indicates that the agent modified that file at that time.
3. Recovery rows, specifically **Restore Points**, appear at the bottom. Restore points appear as green markers with a vertical line running through all rows above them.

To focus the timeline on one entity, click its row label in the left column, such as a specific agent or file.

Hover over any activity marker to view the action performed, the time, and the resource name, as shown below.

![Agent activity timeline showing access, modification, and sharing events over specific dates.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/timeline_eventdetails.png)

### Adjusting the time span

The window pan control at the bottom of the page displays the full activity history as a density chart, with a highlighted window marking the span currently shown in the timeline above.

- To move through time without changing the span, drag the window left or right.
- To widen or narrow the span, drag either edge of the window.
- To jump to a preset span, use the **1D**, **1W**, **1M**, or **All** selector in the upper-right corner.

The timeline above updates as you drag, and the granularity indicator changes to match the new span, as shown below.

![Agent activity timeline displaying access, modification, and sharing statistics over time.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/timeline_windowpane.png)

### Undoing a single AI action

Undo reverses one action performed on one file. Use it when an agent has made a specific change that you want to reverse without rolling back everything that followed.

> [!NOTE]
> Note
> 
> Undo and revert are available only when a single AI agent is selected in the **Agent** filter. The multi-agent view supports monitoring and investigation only.

1. In the **Agent** filter, select a single AI agent.
2. On the agent row or a file row, click the marker for the action you want to reverse, such as a yellow **Modify** marker.
3. Click **Undo**, as shown below.

![Agent activity timeline showing file deletion and undo options for patient form.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/timeline_undooption.png)
4. In the **Confirm Undo** popup, verify the file listed under **File**, as shown below.
5. Click **Undo** to reverse the action, or click **Cancel** to close the popup without changes.

![Confirmation dialog for undoing deletion of a patient form document in the system.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/timeline_undopopup.png)

Securiti reverses the selected action on that file using the underlying backup service. Other actions in the same time window are not affected.

### Reverting to a restore point

Reverting rolls back every change an agent made after a selected backup snapshot. Use it when the scope of unwanted changes is wider than a single file.

Each green marker in the **Restore Points** row represents a backup snapshot captured at a specific time.

1. In the **Agent** filter, select a single AI agent.
2. In the **Restore Points** row, locate a restore point that falls before the unwanted modifications or deletions.
3. Click the restore point marker.
4. Click **Revert**, as shown below.

![Agent activity timeline showing file modifications and a revert option for backup points.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/timeline_revertoption.png)
5. In the **Confirm Revert** popup, review the files listed under **Files**, as shown below. The heading displays the total number of files in scope.
6. Click **Confirm Revert** to start the rollback, or click **Cancel** to close the popup without changes.

![Confirmation dialog for reverting changes in the agent activity timeline interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/timeline_revertpopup.png)

After you confirm the revert:

- All files that the AI agent modified after the selected restore point are restored to their previous versions.
- Current versions of the affected files are replaced with the versions from the selected backup snapshot.
- Securiti starts the restore process using the underlying backup service.

> [!NOTE]
> Note
> 
> Securiti lets you identify restore points and revert affected files only when it is integrated with a supported backup system, such as Veeam Data Cloud. Without that integration, the Timeline page still provides full investigative and monitoring capability. For more information, see [Veeam Data Cloud integration documentation](/latest/docs/veeam-data-cloud-integration).
