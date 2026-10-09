---
title: "Re-scanning DSR requests"
slug: "re-scanning-dsr-requests"
updated: 2026-08-12T07:32:38Z
published: 2026-08-12T07:32:38Z
canonical: "helpcenter.securiti.ai/re-scanning-dsr-requests"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Re-scanning DSR requests

Securiti lets you rescan data systems for personal data related to DSR requests. Doing so refreshes all subtasks, and adds new ones as necessary. Securiti also removes any subtasks for which data has been removed. For existing subtasks previously marked Approved, Securiti returns them to Review state if new data is found, such as new or updated files for access or port requests. You can manually re-scan individual DSR requests, and you can also schedule all DSR requests for regular re-scanning.

### Manually re-scanning a DSR request

You can manually re-scan specific DSR requests when you know or suspect that new personal data has become available in the time since Securiti accepted the DSR request. You might do this if, for example, you have added new data systems, or added new objects or tables to existing data systems. You can re-scan any DSR request that has not already been published.

To re-scan a DSR request:

1. In Securiti choose **Data Subject Rights > DSR Dashboard**.
2. Locate the DSR request you want to re-scan, and at it’s right edge choose **Options** (three dots)**> Re-scan DSR**.

Or from the DSR workbench, at the upper right corner, choose **Rescan > Rescan DSR**.

> [!NOTE]
> **Note**
> 
> When the [task setting](/v1/docs/configuring-dsr-task-settings) to retain subtasks changes from "true" to "false", rescanning behaves differently based on connector type. For unstructured and hybrid connectors, subtasks in the “no data found” state are deleted and only recreated if new data is found. For structured connectors, the original “no data found” subtask remains, and a new subtask is added if data is available.

### Scheduling re-scanning for all open DSR requests

You can configure Securiti to regularly re-scan all DSR requests for new PD added to your data systems since the request was submitted:

1. In the Data Subject Rights module, choose **Settings > DSR Settings**.
2. Scroll to the DSR Re-Scan Policy section, then click **Edit** (pencil icon).

![Settings page showing DSR reports and re-scan policy options with disabled features.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-12 at 12.30.02 PM.png)
3. Mark the checkbox for **Auto Refresh DSR every...** and choose a refresh interval from the menu as shown below. Once done, click **Save.**

![Settings page showing DSR report options and auto-refresh policy for data requests.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-12 at 12.31.21 PM.png)

> [!NOTE]
> **Note**
> 
> Securiti lets the following roles in your Securiti tenant schedule rescan for DSR requests:
> 
> - Super Admin
> - DPO
> - Org Admins
> - Module Owners
> - Operator

### Rescanning custom request types

When you rescan a custom DSR request, Securiti reviews the latest configuration for that request type. It updates all existing subtasks and creates any new ones based on the [current setup](/v1/docs/creating-a-custom-request-type).

> [!NOTE]
> **Note**
> 
> When a data subject submits a single DSR that includes multiple request types - both system supported and custom ones, a specific process follows. Securiti re-scans the system supported request in the same manner as it does currently. For custom requests, Securiti first verifies the [current configuration](/v1/docs/configuring-dsr-request-types) and re-scans the custom request based on its latest setup. For instance if data subject submits access and custom one as part of a DSR request:

Below are some of the examples:

#### Example 1: Transitioning from Task per ds enabled to disabled

At the time of DSR request submission:

- **Configuration:**
  - **DSR Automation:** Disabled
  - **Task per Data System:** Enabled
- **DSR workbench behavior on submission:**

Securiti creates tasks and subtasks for each data system involved in DSR processing. Since Securiti cannot access these data systems as no automation is involved, you can manually check for the data subject's personal data in them. Upload any found data as a document and verify by marking the checkbox next to it.

![Screenshot_2025-08-09_at_7_25_08_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-141c7c12-6ecb-897c-70eb-03f6bfa8ce89.png)

After submission (before rescan):

- **Configuration changes:**
  - **DSR Automation:** Disabled
  - **Task per Data System:** Disabled
- **DSR workbench behavior on rescanning:**

Securiti deletes all existing tasks and subtasks except those in the approved or declined state and creates a new task with a subtask in the DSR workbench. The new task is not linked to any data system and is named after the custom request type.

![Screenshot_2025-08-09_at_8_16_37_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-607860d5-e8c5-1595-7092-7f5fd31b14b0.png)

#### Example 2: Transition from DSR automation disabled to enabled

At the time of DSR request submission:

- **Configuration:**
  - **DSR Automation:** Disabled
  - **Task per Data System:** Enabled (manually)
- **DSR workbench behavior on submission:**

Securiti creates tasks and subtasks for each data system involved in DSR processing. Since Securiti cannot access these data systems as no automation is involved, you can manually check for the data subject's personal data in them. Upload any found data as a document and verify by marking the checkbox next to it.

![Rescan_3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e34ad4a3-0fcb-4d74-20fe-7eca4bdf7d6b.png)

After submission (before rescan):

- **Configuration changes:**
  - **DSR Automation:** Enabled
  - **Task per Data System:** Enabled (by default)
- **DSR workbench behavior on rescanning:**

Securiti executes automation on data systems in a manner consistent with system request types, thereby instantiating discrete tasks and subtasks for each respective system within the DSR workbench. Additionally, each task may include attached files (both structured and unstructured) containing relevant data subject information. Securiti skips creating tasks for data systems that do not contain any data related to the DSR request.

#### Example 3: Re-scanning multi-DSR request

When a data subject submits a single DSR that includes multiple request types - both system supported and custom ones, a specific process follows. Securiti re-scans the system supported request in the same manner as it does today. For custom requests, Securiti first verifies the current configuration and re-scans the custom request based on its latest setup. For instance if data subject submits access and custom one as part of a DSR request:

**At the time of submission:**

- **Configuration of custom request type:**
  - **DSR Automation:** Disabled
  - **Task per Data System:** Enabled

Both options are enabled by default for access type and you cannot update them.
- **DSR workbench behavior on submission:**

Securiti generates tasks and subtasks for both request types for each data system involved in DSR processing. Further, Securiti executes automation for access requests and attaches relevant files (structured and unstructured) as needed. If a system has no related data subject’s data, Securiti skips task creation.

Regarding the “custom one” as no automation is involved in this case so Securiti creates a single task and a subtask per system. Your manual verification is required to check for the data subject's personal data. Any findings must be uploaded as a document and confirmed via a checkbox.

![Screenshot_2025-01-07_at_12_24_08_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9511aecc-598f-661f-7bd5-2e3758a2b0d7.png)

**After submission (before rescan):**

- **Configuration of custom request type:**
  - **DSR Automation:** Disabled
  - **Task per** **Data System**: Disabled

Both options are enabled by default for access request type and you cannot update them.
- **DSR workbench behavior on rescanning:**

For access, Securiti re-scans the request in the same manner as it does today. Meanwhile for “custom one”, Securiti deletes all existing tasks and subtasks except those in the approved or declined state and creates a new task with a Subtask in the DSR workbench. The new task is not linked to any data system and is named after the custom request type.

![Screenshot_2025-08-09_at_9_19_40_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a02e4352-0216-4642-963f-0de5bfbc1010.png)

### Rescan behavior for tasks and subtasks created from task templates

When a DSR request is re-scanned,Securiti checks for updates in the associated task templates and takes action based on configuration changes. The following behaviors are supported:

#### Case 1: Change in associated data system of a template

If a task template originally linked to a data system instance is later updated to remove that data system, Securiti:

- Deletes the existing tasks and subtasks created for that data system instance from that template.
- May create a new task and a subtask without any data system association if there are no other data systems associated with that template..

> [!NOTE]
> **Note**
> 
> This behavior applies only if the subtask is in the **Review**, **Error**, or In Progress state as subtasks in completed (approved, declined, No Data Found) status are not rescanned.

#### Case 2: Deletion of the task template

If a task template was active when the DSR request was created but is later deleted:

- A full or partial rescan does not modify tasks or subtasks previously created from that template.

#### Case 3: Change in subtask naming settings

If subtask name-related settings are changed after the DSR request is created and a rescan is triggered:

- Securiti creates a new subtask based on the updated subtask template configuration.
- The original subtask remains unchanged.

**Example:**

- A subtask template is initially configured to use default subtask naming when the DSR request is created.
- Later, the subtask template name is updated, and the setting is changed to use the subtask template name instead.
- After a rescan, Securiti adds a new subtask using the updated name. The original subtask remains with its original name.

#### Case 4: Rescan behavior after subtask template deletion

Deleting a subtask template after a DSR request is created does not automatically remove the subtasks that were generated from it in the workbench. If a rescan is performed, Securiti retains those existing subtasks, even if their original template has been deleted. However, any new data from the rescan is linked only to subtasks that are based on currently active subtask templates. This means the original subtask remains in the workbench without receiving updated data, and new subtasks may be created from any subtask templates that were added after the DSR request was created.

#### Case 5: Rule evaluation on receiving additional information

When additional information is submitted for a DSR request via a supplemental form, Securiti checks whether any fields used in rule conditions have been updated.

Securiti follows this behavior:

- If a rule condition is met (even if it was false at the time of the original request), Securiti creates a new task and subtasks based on the newly matched rule.
- If the conditional fields remain unchanged, previously created tasks and subtasks remain unchanged.
- If only one rule is configured in the form for a task template, and that rule no longer matches due to additional information submitted through a supplemental form, Securiti does not delete the task or any associated subtasks previously created.

> [!NOTE]
> **Note**
> 
> If automation is enabled for the associated data systems, Securiti rescans those systems using any new personal identifiers provided in the supplemental form and updates the workbench accordingly.

#### Case 6: Rescanning a sequential DSR request

When you rescan a sequential DSR request, Securiti shows a Select a Level popup where you choose the level to restart the rescan from.

- Securiti deletes all levels from the selected level onward and re-evaluates conditions to recreate eligible tasks, based on the current status of the level before it.
- If multiple rules qualify for the DSR request, Securiti deletes tasks from all qualifying rules at the selected level.

![User interface displaying task selection and confirmation for data subject rights access.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-04 at 7.55.14 AM.png)

For more information, see [Configuring sequential task processing in the DSR form](/latest/docs/configuring-sequential-task-processing-in-dsr-forms).

---

### FAQs

#### 1. How can I confirm that the rescan has initiated for DSR requests?

To check if rescan has initiated for a DSR request, go to the Audit Logs of that request and type "rescan" in the search field. If the DSR has started, you will see the message "Rescan got initiated for DSR XXX."

## Related

- [Partial re-scanning in DSR](/partial-re-scanning-in-dsr.md)
