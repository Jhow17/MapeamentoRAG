---
title: "Configuring custom scan categories"
slug: "configuring-custom-scan-categories"
updated: 2026-04-27T10:40:06Z
published: 2026-04-27T21:00:23Z
canonical: "helpcenter.securiti.ai/configuring-custom-scan-categories"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Configuring custom scan categories

Custom scan categories are sets of file types and file naming patterns that you can associate with content scan profiles as described in [Configuring and assigning content scan profiles](https://helpcenter.securiti.ai/docs/configuring-and-assigning-content-scan-profiles). Because they are separate from the scan policies, you can easily reuse them in multiple scan profiles.

### Creating a custom scan category

1. In the main menu, click **Settings** and choose **General**.

![Settings menu showing various options including General, Users, and Audit Logs.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-17 at 2.09.06 PM.png)
2. Choose **Data Classification > Custom Scan Categories**.

![Custom scan categories settings with options to exclude file types and patterns.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-17 at 2.09.45 PM.png)
3. Near the upper right corner of the left panel, click the plus sign (**+**).

![Custom scan categories settings with options to exclude file types and patterns.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-17 at 2.09.59 PM.png)
4. If you have selected multiple organizations, choose the relevant organization from the **Select Organization** menu.
5. Near the upper left corner of the **Custom Categories** area, edit the text in the name box to give your new custom scan category a convenient name, as shown below.

![Custom scan category creation interface with options for file types and patterns.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-17 at 2.10.40 PM.png)
6. Use the tools in the **File Types to Exclude** and **File Name Patterns to Exclude** areas to build lists of file name extensions and file naming patterns to exclude.

To add an extension or pattern, type it in the text box, then click the checkmark.

![Settings for custom scan categories, including file types and patterns to exclude.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-17 at 2.12.24 PM.png)
7. Near the upper right corner of the Custom Categories area, click **Save**.

### Associating one or more custom scan categories with a content scan profile

1. In Securiti, click **Settings**, then choose **Data Classification> Scan Profiles**.
2. In the **Scan Profiles** list, click the scan profile to which you want to associate the custom scan category.
3. Near the upper right corner of the card for the scan policy, click **Edit** (pencil icon), as shown below.

![Settings for scan profiles including file types and categories for data classification.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-17 at 2.14.20 PM.png)
4. Under the section of **File Types to Exclude** **from the Content Scan,** enter the required custom scan category, as shown below.

![Settings for Excel File Scan Profiles with highlighted Computer-Aided Design option.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-17 at 3.08.14 PM.png)

> [!NOTE]
> **Note**
> 
> You can filter the list on the menu by typing ahead in the search box.

After adding the custom category, it appears below the **Custom Categories** tab, as shown below.

![Scan profiles settings showing excluded file types for Computer-Aided Design.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-17 at 3.08.54 PM.png)

Repeat this step as necessary to associate additional custom scan categories to the scan profile.
5. (Optional) To review the file types and naming patterns for a custom scan category, as shown below, click the down arrow near the right edge of the panel.

![Scan profiles settings showing excluded file types for data classification management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-17 at 3.09.08 PM.png)
6. Near the upper right corner of the page, click **Save** to save your changes to the custom content scan policy.

### Deleting a custom scan category

> [!NOTE]
> **Note**
> 
> You can only delete custom scan categories that are not associated with any content scan profiles. The easiest way to tell whether a custom scan category has any such associations is to try deleting it. If delete is disabled, you must identify and remove such associations before deleting the custom scan category.

1. In Securiti, click **Settings** and choose **Data Classification > Custom Scan Categories**.
2. In the Scan Categories list near the left side of the page, find the custom scan category you want to delete and choose **Options > Delete**.
  - If delete is enabled, you're done.
  - If delete is disabled, it is because the custom scan category is associated with a content scan profile. Proceed to the next steps.
3. In Securiti, click **Settings** and choose **Data Classification** > **Content Scan Profiles**.
4. For each entry in the Scan Profiles list on the left side of the page, except the default policy:
  1. Click the profile.
  2. In the **File Types to Exclude from Content Scan** area, click the **Custom Categories** tab and check whether the profile has the custom scan category you are trying to delete.
  3. If the profile does have the custom scan category you are trying to delete, near the upper right corner of the page, click **Edit** (pencil icon).
  4. On the **Custom Categories** tab, next to the custom scan category, click **Delete** to remove it from the profile.
5. Repeat Steps 1 and 2.

## Related

- [Configuring and assigning content scan profiles](/configuring-and-assigning-content-scan-profiles.md)
