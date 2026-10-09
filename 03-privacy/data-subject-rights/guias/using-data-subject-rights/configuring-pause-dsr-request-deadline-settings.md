---
title: "Configuring pause DSR deadline settings"
slug: "configuring-pause-dsr-request-deadline-settings"
updated: 2026-08-12T07:02:15Z
published: 2026-08-12T07:02:15Z
canonical: "helpcenter.securiti.ai/configuring-pause-dsr-request-deadline-settings"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Configuring pause DSR deadline settings

**Scenario**

As a Data Privacy Officer, you manage DSRs with strict regulatory deadlines. Some requests arrive with unclear scope or missing details, and work cannot proceed. Manual tracking risks overdue requests. Using the pausing deadline functionality, you can pause the DSR to stop the clock and notify the data subject with the reason and expected delay. When ready, the deadline recalculates accurately. You maintain compliance, clarity, and accountability.

### Introduction

You can pause a DSR deadline when more information or action is needed before proceeding. You can pause for identity verification, clarification of request scope, or any custom reason that fits your process. You can also notify the data subject about why their request is being paused. This helps you manage complex or incomplete DSRs without missing compliance deadlines, ensuring accuracy and accountability in request handling.

> [!WARNING]
> Important
> 
> Pausing a DSR deadline may not be permitted under certain regulations. Using this functionality in those jurisdictions may result in non-compliance. You are responsible for ensuring that pausing is used only where allowed.

You can configure pausing request deadline settings at the tenant level and then use the functionality directly from the DSR Workbench.

> [!NOTE]
> Note
> 
> Before enabling this setting, review the following behavior and scope:
> 
> - This setting applies at the tenant level and is not configured per regulation or per form.
> - When enabled, pausing is allowed for all requests submitted through all DSR forms in the tenant.
> - By default, pausing DSR deadlines is disabled.
> - Only Securiti super admins can enable this setting. All other roles have read-only access.
> - If the setting is enabled and a DSR deadline is paused, that paused deadline can still be resumed even if the tenant-level setting is later disabled. However, once the setting is disabled, deadlines for new or other active DSRs cannot be paused.

1. In the Data Subject Rights module, choose **Settings > DSR Settings**.
2. Under the DSR Deadline section, click **Edit** (pencil icon) on the right side to open the settings in edit mode as shown below.

![Settings for DSR deadlines and retention policies, highlighting disallowed actions.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-12 at 11.58.06 AM.png)
3. Mark the Allow Pause for DSR deadline checkbox and click Save.

![Settings page showing DSR deadline options and retention policy details for data management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-12 at 12.00.21 PM.png)

Once done, you can open the DSR in the DSR workbench and pause the DSR deadline. For more information, see [Pausing and resuming DSR deadline](/latest/docs/pausing-and-resuming-dsr-deadline).
