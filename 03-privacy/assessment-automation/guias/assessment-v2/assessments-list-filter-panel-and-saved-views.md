---
title: "Assessments list Filter panel and Saved Views"
slug: "assessments-list-filter-panel-and-saved-views"
updated: 2026-04-27T07:39:14Z
published: 2026-04-27T07:39:14Z
canonical: "helpcenter.securiti.ai/assessments-list-filter-panel-and-saved-views"
area: privacy
modulo: assessment-automation
tipo: guia
data_captura: 2026-10-08
---

# Assessments list Filter panel and Saved Views

**Scenario**

As a Data Compliance Officer on the legal team, you need to stay ahead of overdue assessments. Manually scanning long lists wastes time and risks missing critical deadlines. Using filters, you instantly surface overdue assessments across teams or regions. This helps you focus your attention, prioritize high-risk items, and take quick action to drive timely completion.

Securiti lets you apply filters to sort assessments you want. Also, you can save those filters and group them under different categories for easy access later.

> [!WARNING]
> **Important**
> 
> Before selecting a property from the Filter panel, ensure you're applying the filter while logged in to Securiti. For example, if you choose the property Awaiting Question Approval as *true*, the list refreshes to show any Assessments with questions that a reviewer is yet to approve. Securiti shows the said information based on the tenant you're logged in.
> 
> If you're logged in with the credentials of, say, a support user instead, the Awaiting Question Approval filter may not return the correct assessments list. To prevent errors, we recommend accessing filters with the same account you use for answering or reviewing the assessment.

Use the following procedure for filtering options:

1. From the Securiti title, choose **Assessment Automation**.
2. On the Internal Assessments list view, in the upper left corner, click the **+** icon to open the Filter panel.
3. Under **Properties**, choose your desired property that you want to filter by and on the right side, mark the checkbox for the views you want included.

For example, select "Assessment Category > Data Maps." The page refreshes to show you information on data mapping assessments. The filter properties include such as:

![Screenshot_2024-06-25_at_6_17_17_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0e3297b9-5698-d826-bc2f-b5e7d973560b.png)

> [!NOTE]
> **Note**
> 
> Securiti shows you operator chips for different filters.
  - Assessment Category
  - Assessment ID
  - Assessment Title
  - Risk Count
  - Risk Owner
  - Risk Rating
  - Tags
  - Tag Type
  - Source Type
  - Stage type

> [!NOTE]
> **Note**
> 
> Stage type also filters assessments with [Two Step Review Workflow](/v1/docs/configuring-workflow-settings-custom-stages-in-assessments). The filter tracks by assessment stages such as In Progress, In Review, etc. not by stage labels.
4. Click **Apply**

> [!NOTE]
> **Note**
> 
> If you exit without saving, Securiti notifies you have unapplied filters.

> [!WARNING]
> **Important**
> 
> All filters, for example, Managing Organization works at an assessment level. If you have an assessment containing Managing Organization questions i.e. Dropdown or Dropdown Mutliselect, applying the filter does not return any assessments. Instead you must specify an organization from the Managing Organization menu under assessment details. Now when you filter based on Managing Organization, Securiti shows you relevant assessments on the list view.

To create and manage “Saved Views”:

1. On the Internal Assessments list view, near the upper right corner, click **Save View**.
2. Securiti opens up the Save View pane. Create a group, for example, *Assessments*, and enter a name for your view. Optionally, add some description if you want.

![Screenshot_2024-03-27_at_12_08_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-de6c887d-e928-2000-76d4-d9e71cede776.png)
3. Click **Save**
4. (Optional) If you previously applied a filter and modified it, clicking Save View asks you whether to:
  1. Save with Changes
  2. Save as a New View
  3. Revert Changes

![Screenshot_2024-05-10_at_3_53_55_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8f75a225-801f-494a-cb81-20d35bbe8d6d.png)
5. Similarly, near the upper right corner, click **Saved Views** which opens up a list showing your saved filters on the left.

![Screenshot_2024-03-27_at_12_24_08_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0f19a6f5-fe68-9edb-bb91-def397a5c0a6.png)

To clear your selections, in the upper right corner, click **Clear Search**.

For more information, see the following topics:

- [Using the Internal Assessments list view](/v1/docs/using-the-internal-assessments-list-view)
- [Assessments list (Search and exports)](/v1/docs/assessments-list-search-and-exports)

## Related

- [Navigating assessments dashboard](/navigating-the-assessment-metrics-dashboard.md)
- [Vendor Assessments list Filter panel and Saved Views](/vendor-assessments-list-filter-panel-and-saved-views.md)
