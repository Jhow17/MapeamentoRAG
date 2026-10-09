---
title: "Using Data Remediation Dashboards"
slug: "using-data-remediation-dashboards"
status: "update"
updated: 2026-09-22T12:07:18Z
published: 2026-09-22T12:07:18Z
canonical: "helpcenter.securiti.ai/using-data-remediation-dashboards"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Using Data Remediation Dashboards

**Scenario**

As a Data Security Officer, you are responsible for tracking and remediating sensitive files across your organization's data systems. Managing policy outcomes across Data Labeling, File Insights, File Quarantine, and File ROT policies through separate views makes it difficult to assess overall exposure and act quickly. With the Data Remediation dashboard, Securiti gives you a single interface to view, manage, and act on files flagged by all policy types, so you can identify issues faster, measure policy effectiveness, and maintain control over your sensitive data environment.

## Overview

The Data Remediation dashboard shows all files scoped by policies in the Sensitive Data Intelligence module. It provides a consolidated and actionable view of how policies affect files across your data environment.

The dashboard categorizes files into four distinct types:

- Data Labeling
- File Insights
- File Quarantine
- File ROT

This segregation helps you to clearly understand the impact of each policy type on your files and data systems.

> [!NOTE]
> Note
> 
> If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

## Accessing the Data Remediation dashboards

Securiti provides the following four dashboards under Data Remediation:

- Data Labeling
- File Insights
- File Quarantine
- File ROT

Each dashboard presents files, metrics, and actions relevant to the selected remediation type.

To access a remediation dashboard:

1. From the upper left corner, click the **Jewel** icon to open the main menu, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-TDITQW5T.png)
2. Under **Apps** section, select **Data Remediation**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-6X71EK5K.png)
3. In the **Data Remediation Explorers**, choose **Data Labeling**, **File Insights**, **File Quarantine**, or **File ROT**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-HTESXK4A.png)

- The selected dashboard loads with relevant file metrics and records.

## Using the policy filter on the Data Remediation dashboard

By default, the dashboard displays data for All Policies. You can filter results to a specific policy to analyze its scope and impact.

To select your desired policy:

1. Near the upper left corner, click the **Policy** dropdown and select your desired policy, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-NCLIOSS9.png)

- In File Quarantine and File ROT Remediation dashboards, you can also filter files by **Deleted Policies with Actions** to view files that were quarantined or reverted by policies that have been deleted, as shown below. Note that users with **Manage Owned** or **View Owned** policy permissions cannot access this view.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-57N6MQUY.png)
- Once you have selected your desired policy, you’ll see the policy scope and details grid, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-13WA0GCP.png)
- Click **<>** icon to view the applied policy scope in JSON format, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-I4FYUBKF.png)
  1. To copy the applied policy scope in JSON format, click **three dots (option)** and select **Copy JSON**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-02LW5BSZ.png)
  2. To download the applied policy scope in JSON format, click **three dots (option)** and select **Download JSON**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-DKBXKP0S.png)

## Viewing file statistics on the Data Remediation dashboard

Based on selected policy, the dashboard displays the following tiles:

| Policy | Title | Description |
| --- | --- | --- |
| All policies | Files | Displays the total number of files associated with the selected policy. |
| - File Quarantine - File ROT | Quarantined Files | Displays the total number of files quarantined under the policy. > [!NOTE] > Note > > You can also see Quarantined Files tile under in File Insights remediation dashboard. |
| Reverted Files | Displays the total number of files reverted under the policy. > [!NOTE] > Note > > You can also see Reverted Files tile in File Insights remediation dashboard. |
| File Insights | Quarantined By This Policy | Displays the total number of files quarantined under the selected policy. |
| Reverted By This Policy | Displays the total number of files reverted under the selected policy. |
| Data Labeling | Labeled Files | Displays the total number of files labeled under the policy. |
| Labeled by Securiti | Displays the total number of files labeled by Securiti. |
| Labeled by this Policy | Displays the total number of files labeled under the selected policy. |
| Externally Labeled | Displays the total number of files that have labels applied by an external system, such as a Data Labeling policy on Microsoft Purview. |

- By default, Securiti shows statistics for all policies, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-PVTH0EKK.png)

## Filtering files in the Data Remediation dashboard

Filtering properties help you narrow the scope of files in the Data Remediation dashboard so you can quickly identify files that require attention. You can apply filtering properties across multiple nodes and navigate between them without losing your selections. For example, you can apply the **Sensitivity Labels**, **Broadly Shared**, and **Processing Status** filtering properties to identify publicly accessible files that contain sensitive data and have a **Quarantine Failed** status. This helps you identify affected files across multiple locations and take targeted remediation actions while preserving your applied filtering properties.

You can filter files using the following filtering properties.

| Properties | Description |
| --- | --- |
| Account Name | Displays the name of the account associated with the file. |
| Action | Displays the remediation or policy action taken on the file. |
| Broadly Shared | Displays if the file is public or not. |
| Checksum | Displays the file's unique digital fingerprint for data integrity verification. |
| Cluster Name | Displays the cluster name where the file resides. |
| Container Name | Displays the name of the storage container where the file is stored. |
| Content Profiles | Displays the content profiles associated with the file. |
| Data Element | Displays the data elements detected in the file. |
| Data Labeling Policy ID | Displays the policy ID that applies the sensitivity label to the file. It also identifies externally labeled files, where an external source applies the sensitivity label instead of Securiti. |
| Data Source | Displays the data source in the Securiti portal. |
| Data Source Execution IDs | Displays the execution identifiers associated with data source processing jobs. |
| Data System Type | Displays the type of data system the file belongs to. |
| Data System URN | Displays the unique resource name (URN) identifying the specific data system. |
| Destination Path | Displays the path location where the file is moved after quarantine. |
| Discovery Scan IDs | Displays the unique identifiers of discovery scan jobs(s) that found or classified the file. Displays the identifiers of discovery scans that detected the file. |
| Discovery Scan Job IDs | Displays the unique identifiers of discovery scan jobs(s) that found or classified the file. |
| Document Type | Displays the type or format classification of the file content. |
| Error Reason | Displays the reason a file encountered an error during quarantine or processing. |
| Errored | Displays True if file encountered an error and False if not. |
| Evidence File Path | Displays the evidence path that contains audit or proof-of-action data for the file. |
| File Created Time | Displays the original creation timestamp of the file. |
| File Format | Displays the file’s format or extension type. |
| File Modified time | Displays the timestamp indicating when the file was last modified. > [!NOTE] > Note > > For some files, the **File Modified Time** may be earlier than the **File Created Time**. This occurs when the source data system assigns a new creation time to the file while preserving its original modification time. This behavior can occur when you: > > - Copy a file to another location. > - Restore a file from a backup. > - Extract a file from an archive. > - Install a file as part of software. |
| File Name | Displays the full name of the file, including its extension. |
| File Owner | Displays the name or ID of the user who owns or uploaded the file. |
| File Record Creation Time | Displays when the file record was created. |
| File Record Updated Time | Displays when the file record was last updated. |
| File Size | Displays the size of the file in bytes, KiB, MiB, or GiB. |
| File Status | Displays the current status of the file within the system. |
| First Scan Time | Displays when the file was first discovered or scanned by the system. |
| Graph Node ID | Displays the unique identifier in the Data Command Graph. |
| Groups | Displays user or access groups associated with the file. |
| Labeling Activity | Displays the most recent labeling operation performed on the file. Securiti populates the **Labeling Activity** field when a Data Labeling policy runs. The following Labeling Activity statuses are supported: - Labeling Completed - Labeling Failed - Processing Labeling - Remove Completed - Remove Failed - Remove Skipped - Skipped Labeling For **Labeling Failed** labeling activity, hover over the status to view the most recent error log message. To investigate the failure further, click **View Audit Log** in the tooltip to view the relevant activity logs. For more information about the **Labeling Activity** statuses and their corresponding execution results, see [Understanding Data Labeling execution results](https://helpcenter.securiti.ai/docs/using-data-remediation-dashboards#understanding-data-labeling-execution-results). > [!NOTE] > Note > > - The tooltip is available only when a **Data Labeling Policy ID** is associated with the failed labeling activity. > - When you click **View Audit Log** option, Securiti takes you to the **Policy Activity** page. If Policy Activity is not enabled for your tenant, Securiti takes you to the **Policy Logs** instead. > - Securiti records labeling history only for successful labeling activities. For failed or skipped activities, you can view detailed execution information in the **Policy Logs**. Securiti displays the 10 most recent Data Labeling history records for each file. > > ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-4B11LCSV.png) > - When a policy execution fails, the **Labeling Activity** field displays **Labeling Failed**, and Securiti does not populate the file's labeling history. To reflect the file's current labels, Securiti retrieves the existing labels directly from the file during policy execution and displays them in the **Sensitivity Labels** field with the **(external)** suffix. The suffix indicates that the labels come from the data system rather than from Securiti. This approach keeps the **Sensitivity Labels** field aligned with the file's actual sensitivity labels even when the policy execution fails. |
| Labeling Policy ID | Displays the ID of the labeling policy applied. > [!NOTE] > Note > > Labeling Policy ID filter is only available in Data Labeling remediation dashboard. |
| Last Access Time | Displays when the file was last accessed or opened. |
| Last Execution Result | Displays the outcome of the most recent execution of the file. For more information about the **Last Execution Result** values and what each value indicates, see [Understanding Data Labeling execution results](https://helpcenter.securiti.ai/docs/using-data-remediation-dashboards#understanding-data-labeling-execution-results). > [!NOTE] > Note > > - The **Last Execution Result** field is populated only after you run new policies or re-run existing policies. By default, existing policies do not have values in this column. > - Pod version 1.142 or later is required for the **Last Execution Result** field to be populated. |
| Last Scan Time | Displays the most recent time the file was scanned. |
| Mime Type | Displays the MIME type indicating the file’s content type. |
| O365 ID | Displays the unique identifier of the file in Office 365 environments. |
| Object Type | Displays the data object classification. |
| Pipeline ID | Displays the identifier of the policy or remediation pipeline processing the file. |
| Policy Label Name | Displays the name of the applied policy label. This field is populated when the data labeling policy is executed. > [!NOTE] > Note > > Policy Label Name filter will be deprecated in upcoming releases. |
| Policy Label UUID | Displays the UUID associated with the policy label. This field is populated when the data labeling policy is executed. |
| Processing Status | Displays the current processing state of the file. The following are the possible processing statuses: - Processing Quarantine - Processing Revert - Quarantine Completed - Revert Completed - Quarantine Failed - Revert Failed For **Quarantine Failed** and **Revert Failed** processing statuses, hover over the status to view the most recent error log message. To investigate the failure further, click **View Audit Log** in the tooltip to view the relevant activity logs. > [!NOTE] > Note > > - The tooltip is available only when a **Processing Policy ID** is associated with the failed remediation action. > - When you click **View Audit Log** option, Securiti takes you to the **Policy Activity** page. If Policy Activity is not enabled for your tenant, Securiti takes you to the **Policy Logs** instead. |
| Processing Policy ID | Displays the policy ID that is currently acting on the file or most recently completed an action on it. > [!NOTE] > Note > > Processing Policy ID filter is not available in Data Labeling remediation dashboard. |
| Protected by Label | Displays whether the file is protected with a protected Microsoft Purview Information Protection (MIP) sensitivity label. |
| Public | Displays if the file is publicly accessible. |
| Quarantine Data System ID | Displays the destination data system ID where the file was quarantined. > [!NOTE] > Note > > Quarantine Data System ID filter is not available in Data Labeling remediation dashboard. |
| Quarantine Destination ID | Displays the ID of the central quarantine destination where the quarantined file is stored. > [!NOTE] > Note > > Quarantine Destination ID filter is not available in Data Labeling remediation dashboard. |
| Quarantined File Name | Displays the file name assigned to the quarantined file. If the destination data system does not support characters in the original file name, or if the complete destination path exceeds the destination data system's supported path length, Securiti stores the file using a compatible or hashed file name and displays the updated file name. |
| Quarantine Hashed Directory Path | Displays the hashed directory path assigned to the quarantined file. Securiti stores the file using a hashed directory path when the complete destination path exceeds the destination data system's supported path length or when the destination system does not support characters in the original path. > [!NOTE] > Note > > - When hashing is triggered, Securiti hashes both the directory path and the corresponding file name. > - Files from the same source directory may be stored in different destination directories if only some files exceed the destination data system's supported path length. > - Use the **Resource Path** and **Destination Path** filtering properties in the File Quarantine Remediation dashboard to locate quarantined files. |
| Quarantine Policy Path | Displays the quarantine policy path. > [!NOTE] > Note > > Quarantine Policy Path filter is only available in File Insights remediation dashboard. |
| Quarantine Processing Status | Displays the processing status of the quarantine action. > [!NOTE] > Note > > Quarantine Processing Status filter is only available in File Insights remediation dashboard. |
| Quarantined At | Displays the date and time when the file was quarantined. > [!NOTE] > Note > > Quarantine At filter is not available in Data Labeling remediation dashboard. |
| Quarantined By Policy ID | Displays the policy ID that quarantined the file. > [!NOTE] > Note > > Quarantine By Policy ID filter is not available in Data Labeling remediation dashboard. |
| Quarantine/Revert Error Code | Displays the error code associated with the most recent failed quarantine or revert operation. > [!WARNING] > Important > > Files are processed in batches during quarantine and revert operations. If Securiti encounters an error while processing a file in a batch, it stops processing the remaining files in that batch because they are expected to fail for the same reason. In this case, only the file that encountered the error displays the corresponding error code in the **Quarantine/Revert Error Code** property. The remaining files in the batch are marked as **Quarantine Failed**, but the **Quarantine/Revert Error Code** property remains empty because no quarantine or revert operation was attempted on those files. > > This behavior applies to the following error codes: > > - AUTHENTICATION_FAILED > - ACCESS_DENIED > - SESSION_EXPIRED > - CONTAINER_NOT_FOUND > - INSUFFICIENT_SPACE > - CONFIGURATION_ERROR |
| Remediation | Displays the remediation status of the file. This filter supports the following values: - Excluded - Deleted - Excluded (Global) > [!NOTE] > Note > > Remediation filter is not available in File Insights remediation dashboard. |
| Resource Path | Displays the complete path or location of the file in its data system. |
| Reverted At | Displays the timestamp indicating when the file was reverted. > [!NOTE] > Note > > Reverted at filter is not available in Data Labeling and File Insights remediation dashboard. |
| Sensitivity Labels | Displays the labels currently applied to the file. For each sensitivity label, the Policy ID of the policy that applied the label is shown when you hover over the label. Moreover, the term **External** is shown if a label was discovered on the file but was not applied by Securiti. You can also view the **Sensitivity Labels** property in the Graph Explorer. This field is populated when a label is detected on the file during the discovery scan or when a label is applied through a policy. For more information, see [Using Data Labeling Policies](/latest/docs/using-data-labeling-policies). > [!NOTE] > Note > > - The Sensitivity Labels filter is only available in the Data Labeling remediation dashboard. > - In case of Microsoft Purview, a file can have only one sensitive label, and in case of Google Drive, a file can have up to five sensitivity labels. |
| Skip Reason | Displays the reason a file was skipped during a discovery scan. |
| Skipped | Displays if the file was skipped during a discovery scan. |
| Super Groups | Displays parent or inherited access groups. |
| Target Label | Displays the label that the policy attempts to apply during its most recent run. You can also view Target Labels even before policy execution to preview how files will be labeled, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-L68XS0JC.png) > [!NOTE] > Note > > - Target Label filter is only available in Data Labeling remediation dashboard. > - Target Labels are visible regardless of whether auto-labeling is enabled or disabled. |
| Top Level Directory | Displays the root directory or primary folder where the file resides. |
| Version Of | Displays the relationship or parent version if the file is a versioned copy. |

To apply filters:

1. Click the **+** (plus icon) to view the available filtering properties, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-F7TSW7XP.png)
2. Apply one or more filtering properties. For example, set `Sensitivity Labels = SensitiveLabel100` and `File Format = Presentation` , then click **Apply** to identify presentation files that contain the specified sensitivity label, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-ADPXOTK6.png)
3. To apply filtering properties directly from the entity grid, use the inline **+** (plus icon) or **-** (minus icon) controls to add or remove specific values. For example, add the file name **hospital_stats.tif** to the applied filtering properties, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-H2C69G8L.png)
4. Click **Clear** to remove all applied filtering properties, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-J2PZZRHB.png)

### Understanding Data Labeling execution results

When you run a Data Labeling policy, you can use the **Labeling Activity** and **Last Execution Result** fields in the Data Labeling Remediation dashboard to understand the outcome of the labeling operation.

The **Labeling Activity** field shows the status of the labeling operation, such as **Labeling Completed**, **Labeling Failed**, or **Skipped Labeling**, while the **Last Execution Result** field shows the result of the labeling operation and helps you understand why Securiti skips or fails to label a file.

The following table describes the possible **Last Execution Result** values for each **Labeling Activity** status:

| Labeling Activity | Last Execution Result | Description |
| --- | --- | --- |
| Labeling Completed | Success | Securiti labels the file successfully. |
| Skipped Labeling | File Format Not Supported | Securiti skips labeling because the file format does not support labeling. |
| No New Label or Custom Attribute | Securiti skips labeling because there is no new label or custom attribute to apply to the file. |
| Label Already Exists on File | Securiti skips labeling because the label that the policy attempts to apply already exists on the file. |
| Override Disabled | Securiti skips labeling because label override is disabled. |
| Lower Sensitivity | Securiti skips labeling because the label that the policy attempts to apply has a lower sensitivity than the existing label. |
| Manual Label | Securiti skips labeling because the existing label was manually applied. |
| Appliance Version Not Supported | Securiti skips labeling because the appliance version does not support the labeling operation. |
| Protected Labeling Not Supported | Securiti skips labeling because protected labeling is not supported for the file or data system. |
| Requires Protected Label | Securiti skips labeling because the labeling operation requires a protected label. |
| Labeling Failed | File Not Found | Securiti fails to label the file because it cannot find the file. |
| Failed to Download File | Securiti fails to label the file because it cannot download the file for Microsoft Purview Information Protection (MIP) labeling. |
| Failed to Upload File | Securiti fails to label the file because it cannot upload the labeled file. |
| Failed to Extract File Label | Securiti fails to label the file because it cannot retrieve the existing label from the file. |
| Internal Server Error | Securiti fails to label the file because of an internal server error. |
| Mandatory File Parameters Missing | Securiti fails to label the file because one or more required file parameters are missing. |
| Malformed File Format | Securiti fails to label the file because the file format is malformed. |
| Missing Shared Drive ID | Securiti fails to label the file because the Google Shared Drive ID is missing. |
| Shared Drive Owner Not Found | Securiti fails to label the file because it cannot identify the owner of the Google Shared Drive. |
| Data System Ineligible for Labeling | Securiti fails to label the file because the data system is not eligible for labeling. |
| Failed to Fetch Data System | Securiti fails to label the file because it cannot retrieve the data system information. |
| Connector Type Not Supported | Securiti fails to label the file because the connector type does not support labeling. |
| Failed to Resolve Source Mount Path | Securiti fails to label the file because it cannot resolve the source mount path. |
| Failed to Resolve Connector Account | Securiti fails to label the file because it cannot resolve the connector account. |
| Missing Workspace Data Source ID | Securiti fails to label the file because the workspace data source ID is missing. |
| Failed to Fetch Google Credentials | Securiti fails to label the file because it cannot retrieve the required Google credentials. |
| Failed to Fetch Google Label Service | Securiti fails to label the file because it cannot access the Google label service. |
| Failed to Fetch Google Drive Labels | Securiti fails to label the file because it cannot retrieve the available Google Drive labels. |
| Remove Skipped | Label Not Found on File | Securiti skips label removal because it cannot find the label on the file. |

## Searching files on the Data Remediation dashboard

When working with large datasets, you need a quick way to find a **specific file**. Use the search bar to locate files by name and focus on the records that matter.

- Use the search bar to locate files by name, for example file name **person_1.txt**, as shown below.

> [!NOTE]
> Note
> 
> Applying a search or changing a filter clears your current file selection. To avoid losing your selection, set your filters first to narrow down the files you want, and then select the files and perform your bulk actions.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-D39ZRMUJ.png)

## Viewing files hierarchy in the Data Remediation dashboard

When a policy identifies hundreds of affected files across nested folders, locating the appropriate folder and selecting individual files for remediation can be time-consuming. The **Folder Browser** lets you view the files hierarchy within the scope of the selected policy, locate the folder that contains the affected files, and apply supported remediation actions to all files in that folder. This helps you remediate large volumes of sensitive data while reducing the manual effort.

> [!NOTE]
> Note
> 
> If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

To remediate files at the folder level:

1. Enable the **Folder Browser** toggle, as shown below.

> [!NOTE]
> Note
> 
> The **Folder Browser** displays up to 10 files and 10 subfolders within each folder. To view additional files, use the entity grid.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-EZWLWTHR.png)
2. Browse the folder hierarchy, and select the folder that contains the files you want to remediate, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-V6H9QFTZ.png)
3. Apply one of the following remediation actions, as shown below. Securiti applies the selected remediation action to all files in the selected folder.

| Policy | Remediation action | Description |
| --- | --- | --- |
| Data Labeling | Manually Label | Lets you apply sensitivity labels to files in the selected folder that are within the scope of the Data Labeling policy. |
| Remove Label | Lets you remove specific or all sensitivity labels from files in the selected folder that are within the scope of the Data Labeling policy. |
| File Quarantine | Quarantine | Lets you isolate files in the selected folder from their original location to restrict access and prevent further exposure. |
| Revert | Lets you restore quarantined files in the selected folder to their original location. |
| All Policies | Remediate | Lets you exclude files in the selected folder from further policy evaluation or mark them as deleted to remove them from active violations. |
| Remove Remediation | Lets you reverse previously applied remediation and restore files in the selected folder to active policy evaluation. |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-ZRQTO8M5.png)

## Refreshing the Data Remediation dashboard data

To ensure you are always working with the most current file and policy information, you can manually reload the dashboard at any time.

- Click **Refresh** to reload dashboard data, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-H6JI3R1S.png)

## Grouping files by owner on the Data Remediation dashboard

When remediating policy violations, knowing who owns the affected files helps you assign accountability and coordinate cleanup efforts. Use Group by Owner to organize files under their respective owners for a clearer view of ownership distribution.

- Select **Group by Owner** to group files by file owner. For example, here all of 10,000 files are grouped under the owner **SYSTEM**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-SKPEF4ZG.png)

## Merging applied filters with policy scope on the Data Remediation dashboard

You can merge applied filters into the scope of the selected policy. Once merged, the policy reruns automatically if it is active.

To merge applied filter(s) with the scope:

1. Click **Merge with Scope,** as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-817OC0S7.png)
2. In the confirmation dialog, click **Yes, Merge**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-THAJF8QM.png)

• The merged filters appear in the policy scope, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-A5A8WC5U.png)

## Customizing visible columns on the Data Remediation dashboard

By default, the dashboard displays a limited set of columns. You can customize the grid to show only the columns relevant to your analysis.

To view columns of your choice:

1. Click the **column selector**, as shown below.![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-TDGKKJYB.png)
2. Select or deselect columns as needed, and click **Apply** to update the grid view, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-WHDWJKOS.png)
