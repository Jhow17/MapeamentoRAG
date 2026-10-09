---
title: "Navigating assessments dashboard"
slug: "navigating-the-assessment-metrics-dashboard"
updated: 2025-12-08T07:52:33Z
published: 2025-12-08T07:52:33Z
canonical: "helpcenter.securiti.ai/navigating-the-assessment-metrics-dashboard"
area: privacy
modulo: assessment-automation
tipo: guia
data_captura: 2026-10-08
---

# Navigating assessments dashboard

This topic provides you an overview of the Assessment Metrics Dashboard. Securiti roles such as Super Admin, Operator, and Module Owner can access the dashboard.

To access, in Securiti, open **Assessment Automation** and select **Assessments** **> Dashboard**. It consists of multiple widgets and when you click a data slice, Securiti redirects you to the assessments list sorted by the property, for example, “In Review.”

- **Assessment by Stage -** Shows data by different stage types including Not Started, In Progress, In Review, On Hold, Canceled, and Complete.

When [Two Step Review Workflow](/v1/docs/configuring-workflow-settings-custom-stages-in-assessments) is enabled, Securiti shows you the Primary Review and Secondary Review stages

> [!NOTE]
> **Note**
> 
> Securiti shows separate In Progress stages for Base Workflow and Two Step Review Workflows.
- **Overdue Assessments -** Shows data about assessments overdue but does not include information on On Hold and Canceled assessments.

> [!NOTE]
> **Note**
> 
> Clicking an overdue assessment opens its details view instead of overdue assessments list.
- **Assessments Created by Quarter -** Shows assessments data for up to four previous quarters. Securiti groups assessments by their created date.
- **Total Time Spent per Stage (In Days)** and **Average Time Spent per Stage (In Days) -** Shows data based on the total and average time spent by users in your organization on each assessment stage. These widgets don't include data for Canceled stage.

> [!NOTE]
> **Note**
> 
> Securiti shows *time spent data* once the dashboard is enabled for your tenant (if not already). All user interactions from that point on are included in this data; otherwise, the widgets will appear empty.
- **Assessments Created by Managing Organization -** Shows assessments data for multiple organizations using the same Securiti tenant.

![Screenshot_2025-07-09_at_2_08_24_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-be6bfdf6-6db5-8736-4533-bca790ac759e.png)

You can also apply filters on the dashboard similar to assessments list. The widgets are updated according to the applied assessment property. You can save views you frequently visit and access them via “Saved Views.”

> [!NOTE]
> **Note**
> 
> The applied filter on the assessments dashboard persists on the assessments list and vice versa.

For more information, see the following topics:

- [Using the Internal Assessments list view](/v1/docs/using-the-internal-assessments-list-view)
- [Assessments list Filter panel and Saved Views](/v1/docs/assessments-list-filter-panel-and-saved-views)

## Related

- [Configuring Workflow Settings (Custom Stages) in assessments](/configuring-workflow-settings-custom-stages-in-assessments.md)
- [Assessments list Filter panel and Saved Views](/assessments-list-filter-panel-and-saved-views.md)
- [Vendor Assessments list Filter panel and Saved Views](/vendor-assessments-list-filter-panel-and-saved-views.md)
