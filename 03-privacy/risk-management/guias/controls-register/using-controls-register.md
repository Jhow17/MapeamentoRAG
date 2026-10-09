---
title: "Using Controls Register"
slug: "using-controls-register"
updated: 2026-09-22T06:27:42Z
published: 2026-09-22T06:27:42Z
canonical: "helpcenter.securiti.ai/using-controls-register"
area: privacy
modulo: risk-management
tipo: guia
data_captura: 2026-10-08
---

# Using Controls Register

**Scenario**

As a Risk Manager, you need a single place to track every control your organization uses to manage risk, along with its implementation status and effectiveness. Without a centralized view, it's difficult to know which controls are overdue, which are expiring soon, or which risks still lack a control. By using the Controls Register, you get a full inventory of controls with status, effectiveness, and ownership visible at a glance, so you can prioritize follow-up before a control lapses or a risk goes unmanaged.

To access the Controls Register, on the Securiti homepage, under "Apps," select **Risk Management**, then **Controls > Controls Register**.

The list view shows every control in your organization. Quickly search for a control using the search bar by control ID, name, or description. Near the upper right corner, click **+ Add New Control** to create a new control directly from the register.

Use the Column Selector (grid icon) to arrange columns to suit. Available columns include control name, status, description, deadline, expiry date, effectiveness rating, linked compliance control, owners, and reviewers.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/controls_list.png)

## Control filters

You can filter controls by owner, reviewer, linked risk, linked compliance framework, linked compliance control, and tags. Create Saved Views to access your commonly used filters quickly.

## Control status filters

The filters below explain what each status means.

- `Not Implemented` - when a control is created and no implementation work has started.
- `In Progress` - when implementation work is underway.
- `In Review` - when the control is submitted for reviewer approval.
- `Implemented` - when the control is reviewed and approved.
- `Expired` - when the control's expiry date has passed.

## Importing and exporting controls

You can also import and export controls using the register.

1. Near the upper right corner of the page, click **Import** and select a CSV file to import controls. Click **Download CSV Template** first if you need the expected column format.
2. To export, mark the checkbox for your desired control(s) and click **Export**. You can export multiple controls at a time in CSV format. Securiti sends an email containing the download link.
3. To export evidence for a control, meaning its attachments, comments, and links bundled together, use “Associated Evidences” from the [control's details](/latest/docs/accessing-control-detail#associated-evidences1) page.

## Creating controls using the Controls Register

Securiti's Controls Register lets you create controls directly from the list page.

### Create control

To create a control from the register:

1. Near the upper right corner, click **+ Add New Control**.
2. On the "Add New Control" page, use the following fields to configure the control:
  1. Name - enter a name for the control.
  2. Framework - optionally link the control to one or more compliance frameworks, such as ISO 27001.
  3. Description - enter a description of what the control does and how it manages risk.
  4. Owner(s) - assign one or more owners from the list, or invite a guest user.
  5. Reviewer(s) - select reviewers if you want. Reviewers must already have an account.
  6. Status - select a desired status. Default status is “Not Implemented.”
  7. Effectiveness - rate the control's effectiveness. If your tenant uses Matrix risk settings, set both severity and likelihood values. If your tenant uses Linear risk settings, set a single risk score.
  8. Deadline - optionally set a target date for implementation.
  9. Expiry Date - optionally set when Securiti reasses or renews a control.
  10. Assign Tags - select and apply any tags you want. For more information, see [Tags management in assessments](/latest/docs/managing-assessment-tags).
3. Click **Add Control**

> [!NOTE]
> Note
> 
> This is one of two ways to create a control. You can also create one directly from a risk's details page, which links the new control to that risk automatically. See [Navigating risk details](/latest/docs/navigating-the-risk-details-page).

Proceed to [Accessing Control Detail](/latest/docs/accessing-control-detail).
