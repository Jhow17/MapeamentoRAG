---
title: "Using tags to organize and filter assessments"
slug: "managing-assessment-tags"
updated: 2026-04-27T07:36:32Z
published: 2026-04-27T07:36:32Z
canonical: "helpcenter.securiti.ai/managing-assessment-tags"
area: privacy
modulo: assessment-automation
tipo: guia
data_captura: 2026-10-08
---

# Using tags to organize and filter assessments

This topic explains how to apply structured tags to assessments and how to use those tags to filter and manage assessment lists.

Tags use predefined ‘key value’ pairs, such as Country = Germany or Business Unit = Marketing. They appear on both assessment details and list columns, and support filtering. The assessment owner or reviewer manages keys, and you can select values from a list or create them on the fly, depending on configuration.

## Viewing tags on an assessment

Open assessment details to access tags. Click **Tags** to:

- View all tags currently applied to the assessment.
- Add new tags using available keys and values.
- Remove tags that are no longer required.

## Adding a tag to an assessment

To add a tag:

1. Open the assessment you want to tag.
2. In the assessment toolbar, click **Tags > Configure Tags**.

![User interface displaying assessment sections, questions, and options for tagging and comments.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-01-05 at 1.10.03 PM.png)
3. Select a tag key from “Tag Types,” for example, ‘Country.’

![Tag management interface displaying options for adding and managing tags effectively.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-01-05 at 1.10.52 PM.png)
4. Enter or select a value.

![Tag management interface showing options to create and add new tags.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-01-05 at 1.11.19 PM.png)
5. Click **Save**

The tag is saved immediately and appears as “Assigned Tags” on the assessment. ![User interface displaying assigned tags and sections for a privacy assessment task.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-01-05 at 1.13.44 PM.png)

Observe these caveats:

- You can only create new tag keys from the assessment details page.
- Values containing disallowed special characters are rejected with a validation message.

![Tag management interface showing invalid tag type error for user input.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-01-05 at 1.15.35 PM.png)

## Removing a tag

To remove a tag:

1. On the “Tags Management” popup, locate the tag(s) you want to remove.
2. Clear the checkbox next to the tag.
3. Click **Save**

The tag is unassigned from the assessment, but remains available for other assessments if it’s still in use.

## Filtering assessments by tags

To filter assessments using one or more tags:

1. On the assessments list view, click the **+(filter)** icon.
2. From the properties, select **Tags**.
3. Choose a key and one or more values, then apply the filter.

You can combine multiple tag properties using “AND” logic, such as Country = USA and Risk Level = High. If no assessments match the selected tags, the list displays “No Data Available.”

![Internal assessments dashboard displaying tags and stages for assessment management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-01-05 at 1.33.47 PM.png)

> [!NOTE]
> Note
> 
> Applied filters presist between the assessment list view and the metrics dashboard.

## Tags in list view

- You can show or hide the Tags column in the assessments list via column selector.

![Dashboard displaying internal assessments with filters, tags, and completion status overview.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-01-05 at 1.37.32 PM.png)

Hover to view more tags in addition to the primary tag.

![Dashboard displaying internal assessments, highlighting tag management and assessment statistics.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-01-05 at 1.36.29 PM.png)
- Deleted keys or values continue to display correctly on older assessments for historical accuracy.

Securiti’s tagging interface supports large tag sets and high volumes, meaning assessments with many tags remain readable and responsive. Moreover, filtering remains fast even when tags are applied across large datasets.

For more information, see the following topics:

- [Assessments list - Filter panel and Saved Views](/latest/docs/assessments-list-filter-panel-and-saved-views)
- [Answering assessment questions in Securiti](/latest/docs/answering-assessment-questions-in-securiti)
- [Navigating the Assessment Metrics Dashboard](/latest/docs/navigating-the-assessment-metrics-dashboard)
