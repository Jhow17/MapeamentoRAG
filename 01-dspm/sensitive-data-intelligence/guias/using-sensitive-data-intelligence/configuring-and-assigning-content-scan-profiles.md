---
title: "Configuring and assigning content scan profiles"
slug: "configuring-and-assigning-content-scan-profiles"
updated: 2026-04-27T10:44:31Z
published: 2026-04-27T21:00:23Z
canonical: "helpcenter.securiti.ai/configuring-and-assigning-content-scan-profiles"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Configuring and assigning content scan profiles

You can configure scan profiles to improve scanning performance by excluding files that are unlikely to contain personal data.

Securiti has one default scan policy. By default, this policy applies to all applicable unstructured data systems. You can create additional content scan profiles and assign them to specific connectors. When a connector scans a data system, it excludes all these files identified by the scan profile.

> [!NOTE]
> **Note**
> 
> - Scan Profiles only apply to unstructured data system connector types that do not support discovery scans.
>   - To view a full list of data systems that Securiti support discovery scans, see [Supported data systems for discovery scans](/v1/docs/supported-data-systems-for-discovery-scans).
> - If a data system is being scanned using a discovery scan, then the scan scope, file exclusions, etc., in the discovery scan are used. To learn more about discovery scans, see [Discovery scans](/v1/docs/discovery-scans).

### Prerequisites

1. In the case of self-hosted data systems, you must [activate a Pod or an elastic Pod](/v1/docs/pods-cluster-version-v128-and-later).
2. Configure and [activate the connector for the data system](/v1/docs/managing-data-system-connectors).

### Creating a custom scan profile

To create a custom scan profile:

1. From the main menu, choose Sensitive Data Intelligence > Discovery Scans > **Scan Profiles**. It shows the Scan Profiles page as shown below:

![Securiti dashboard displaying sensitive data intelligence and scan profiles options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-20 at 7.05.55 PM.png)
2. Near the top of the **Scan Profiles** list, along the left edge of the page, click **+** to create a new scan profile.

The new scan profile is a clone of the default scan policy, which you cannot edit.
3. From the menu at the top, choose an organization for which you want to configure the scan profile.
4. Near the upper left corner of the workspace, enter a name for the scan policy.
5. In the **File Types to Exclude from Content Scan** area, click the **System Categories** tab and use the tools to enable or disable scanning of broad file type categories such as word processing or spreadsheets.

![Settings for scan profiles, including exclusions for various file types and categories.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-20 at 7.03.21 PM.png)

Activating the toggle enables the exclusion of the corresponding file type category. Categories without toggles are always excluded.
6. (Optional) Click the **Custom Categories** tab and use the tools there to associate custom categories as described in [Configuring custom scan categories](/v1/docs/configuring-custom-scan-categories).
7. Use the tools in the **File Size Exclusion** area to configure maximum file sizes above which Securiti does not scan the file.

At the top of the area, configure the overall file size limit that applies to all files. Below that, configure maximum sizes for specific file categories on the System Categories and Custom Categories tabs.

![Settings for scan profiles including file size exclusions and categories for scanning.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-20 at 7.04.34 PM.png)
8. profiUse the **File Age** tools to set the retention time for files. You can specify the number of days to exclude files before and after certain days.
9. Use the File Name Exclusion tools to define names and name patterns for files you want to exclude, but which do not belong to any file type categories.

Some examples of file exclusion statements:

| something_*.txt | Excludes all text file types with names that start with **something_*<any_text>*.txt** |
| --- | --- |
| *_something.txt | Excludes all text file types with names that end with ***<any_text>*_something.txt** |
| *_something_*.txt | Excludes all txt file types with names which contain ***<any_text>*_something_*<any_text>*.txt** |
| config.* | Excludes all file types with the name **config** |
10. Use the **Advanced Profiles** tools to customize the following scanning optimizations that Securiti uses:
  - Fast scanning of applicable file types (you can select this option to optimize the scanning process)
  - Download optimization (you can select this option to optimize the download process)
  - Scan document metadata (you can select this option to scan document metadata such as document creation date, edit date, created by, file type, and so on).
  - Extract text from images using OCR technology (you can enable this option to extract text from images using OCR technology and include that text for scanning)
11. Near the top of the page, click **Save** to save your changes.

### Assigning a custom content scan policy to an unstructured data system instance

To assign a custom content scan policy to an unstructured data system:

1. In Securiti, open **Data Systems**.
2. Choose any unstructured data system and navigate to the **Connector** tab.
3. Choose **Discovery Scans > Scan Profiles**.
4. In the **Content Scan Policy** area, use the **Content Scan Policy** menu to choose the content scan policy for the data system instance.

![contentScanPolicy.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9e9315d2-00f6-efba-bed7-7381f3b1e258(1).png)
5. Near the upper right corner of the page, click **Save**.

## Related

- [Discovery scans](/discovery-scans.md)
- [Configuring custom scan categories](/configuring-custom-scan-categories.md)
