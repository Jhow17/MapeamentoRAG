---
title: "Troubleshooting Data Labeling policies"
slug: "troubleshooting-data-labeling-policies"
updated: 2026-08-26T08:02:37Z
published: 2026-08-31T21:00:01Z
canonical: "helpcenter.securiti.ai/troubleshooting-data-labeling-policies"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Troubleshooting Data Labeling policies

This article covers the possible issues that can occur when using Data Labeling policies to apply sensitivity labels to files. For more information, see [Using Data Labeling Policies](/latest/docs/using-data-labeling-policies).

## Policy logs are not generated and labeling activity is empty

Data Labeling policies run only on files that match the content profile defined in the policy. If a file does not contain the specified content profile, the policy does not trigger a labeling action, and no labeling activity or policy log is generated for that file. If Auto Labeling is disabled on the policy, labeling does not run even when a file meets the content profile criteria. Enable Auto Labeling and confirm the content profile matches the target files before troubleshooting further.

## Labeling fails for a Box file in the recycle bin

When you run a Data Labeling policy on a Box file in the recycle bin, the labeling operation fails and the policy logs display the `PATH_CREATION_FAILED` error. This occurs because Box lets Securiti download files from the recycle bin but prevents uploading or overwriting them. As a result, Securiti can download the file for labeling but cannot upload the labeled file back to Box. To apply the sensitivity label, restore the file from the recycle bin and run the Data Labeling policy again.

## Sensitivity labels are not visible during policy creation

Sensitivity labels do not appear during policy creation if the label source is not properly configured or synced.

- **Microsoft Purview**: Confirm the Purview connector is authenticated and that sensitivity labels have synced successfully.
- **Google Drive**: Enable Google data labeling in the Permissions tab of the data system.

## Unable to verify whether a label is applied to a file

Securiti stores sensitivity labels in a file's metadata, and the applied label may not always display in the Securiti UI. To confirm whether a label has been applied, review the file's metadata directly in the source system.

## Only one Google Drive data system is visible during policy creation

Securiti displays Google Drive data systems at the workspace level rather than per account. If multiple Google Drive accounts belong to the same workspace, only one Google Drive data system appears during policy creation. This is expected behavior. Securiti supports and displays only one Google Drive data system per workspace. To view multiple Google Drive data systems, connect separate Google Drive workspaces.

## A file's labeling history is empty

If a file's labeling activity shows Labeling Completed but its labeling history is empty, the file was labeled by a findings-based policy. Securiti has since moved to a no-findings model, and history from existing findings-based policies was not migrated. As a result, the labeling history for these files appears empty.

## Labels applied from a different Azure tenant are not visible in Microsoft

If you onboard your Microsoft Purview connector from one Azure tenant, for example, dev and apply labeling policies to files hosted in another Azure tenant, for example, Production SharePoint, the labels may not appear in the Microsoft suite.

In this case, Securiti successfully writes the sensitivity label to the file's metadata and shows **Labeling Completed**. However, Microsoft services such as SharePoint and Microsoft 365 apps do not display the label, because the label originates from a different Azure tenant. Sensitivity labels are tenant-scoped and must belong to the same Azure tenant as the target SharePoint environment for Microsoft to recognize them.

To verify whether labeling succeeded in this scenario, review the file's metadata properties directly in SharePoint or the source system.

## Protected sensitivity labeling fails when a file is open

If a file is open when the `assignSensitivityLabel` API attempts to apply a protected sensitivity label, the API request can remain in a running state and eventually fail due to a timeout. To avoid this issue, close the file before applying the protected sensitivity label, whether the file is open in a browser tab or in Microsoft Office 365 for desktop. Otherwise, the operation may fail after reaching the maximum retry limit.

## A previous sensitivity label is restored after removing a protected sensitivity label

For some file formats, such as Microsoft Visio files, removing a protected Microsoft Purview Information Protection (MIP) sensitivity label may restore the previously applied unprotected sensitivity label as **Externally Labeled**. As a result, the file remains labeled. To completely remove the sensitivity label from the file, remove the restored unprotected sensitivity label as well.
