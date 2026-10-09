---
title: "Managing tags in Securiti"
slug: "managing-tags-in-securiti-2"
updated: 2026-09-17T16:11:28Z
published: 2026-09-17T16:11:28Z
canonical: "helpcenter.securiti.ai/managing-tags-in-securiti-2"
area: platform
modulo: system-settings
tipo: guia
data_captura: 2026-10-08
---

# Managing tags in Securiti

Securiti provides a centralized **Tag Management** page where you can create and manage reusable tags for objects in Securiti platform. You can organize tags into categories and use them consistently across the platform. Tags help you classify, filter, and govern assets in Securiti.

To access the **Tag Management** page:

1. At the top left corner of the platform, click the **Jewel** icon.
2. From the Platform Services section in the new navigation, click **Settings**.
3. From the **Settings** menu, choose **Tag Management** > **Tags.**

## Understanding the Tags page

The **Tags** page provides the following capabilities:

- Summary metrics for **Total Tag Categories** and **Total Tags**
- A search bar to search tags by name, category, or keyword.
- An organized list view with rows representing tag categories.

Each row in the list represents a tag category. Under each category, Securiti displays:

- The number of tags within the category
- The individual tag values as label chips
- An expand or collapse arrow to view or hide the tag values for each category

![Overview of tag management settings with categories and total tags displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/tag_management(1).png)

## Creating a custom tag

> [!NOTE]
> Note
> 
> Only a Super Admin can create new tags from the **Tag Management** page in **Settings**. Users with any other role, including custom roles granted the `Manage Tags` or `View All Tags` permissions, cannot access this page. These permissions currently apply only to applying or removing existing tags from assets on the Inventory page. Securiti does not let you view tags if these permissions are not enabled.
> 
> For more information, see [Applying tags to graph objects](/latest/docs/applying-tags-to-assets-in-inventory).

To create a custom tag:

1. From the upper right corner of the page, click **Create Custom Tag**.
2. In the **Create Custom Tag** page, in the **General Information** section, specify the following:

![Tag management interface displaying options for creating and categorizing AWS assets.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/tags_createcustomtag_page.png)
  - **Tag Name**: Enter a clear and meaningful name for your tag, such as “AWS assets”.
  - **Category**: Select a category for your tag or create one, as shown below.
  - (Optional) **Description**: Enter a description about your custom tag.
3. Click **Create Tag**

![Creating a new tag for AWS assets in the Tag Management section.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/tags_createtag.png)

Once created, the tag becomes available for use in the other pages, such as the Inventory dashboard.
