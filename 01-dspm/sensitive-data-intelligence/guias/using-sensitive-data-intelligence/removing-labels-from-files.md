---
title: "Removing labels from files"
slug: "removing-labels-from-files"
status: "update"
updated: 2026-09-16T10:22:15Z
published: 2026-09-16T10:22:15Z
canonical: "helpcenter.securiti.ai/removing-labels-from-files"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Removing labels from files

Securiti lets you remove sensitivity labels from files that no longer require a particular label. This helps you maintain accurate classification across your data environment and ensure Securiti treats files under the correct sensitivity level.

For example, your organization runs a Data Labeling policy that applies a Confidential label to files containing PII. After the policy runs, a subsequent review confirms that some labeled files no longer require the Confidential label. You can select those files from the Data Remediation dashboard and remove the label.

> [!NOTE]
> Note
> 
> To use the **Remove Label** option for Microsoft Purview Information Protection sensitivity labels, you must use pod version 1.147.0 or above.

To remove label(s) from file(s):

1. Select the file(s) scoped under the selected Data Labeling policy from the Data Remediation dashboard, and click **Remove Labels**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-HF50X196.png)
2. From the **Remove Labels** popup, select one of the following options:

| Option | Description |
| --- | --- |
| Remove selected labels | Select **Remove selected labels** option to remove specific labels, such as **ConsumerLabel46 (170)** from the selected files. Also, mention the reason for removing the label(s) from the file(s). ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-07-30 at 7.58.16 PM.png) |
| Remove all | Select **R****emove all** option to remove all labels from the selected files. Also, mention the reason for removing the label(s) from the file(s). ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-07-30 at 7.58.46 PM.png) |

> [!NOTE]
> Note
> 
> - The label removal behavior varies by data system type. Google Drive supports multiple labels per file, so you can remove one or more labels in a single operation. Microsoft Purview Information Protection (MIP) supports a single label per file, so removing the label leaves the file unlabeled.
> - In Google Drive, when you select a label to remove, Securiti matches files based only on the **Label Name**. Securiti does not consider the **Field Name** or its value during label removal.
> - When you remove a label from a file, Securiti excludes the file from future scheduled auto-labeling runs, even if the file is rescanned. If you manually apply a label to the file, it returns to the normal labeling workflow, and Securiti can relabel it during future scheduled runs if the file is rescanned.
3. Click **Remove Labels from Files** to confirm, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-H1X22LRY.png)
