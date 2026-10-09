---
title: "Remediating files"
slug: "remediating-files-from-the-data-remediation-dashboard"
updated: 2026-07-30T14:46:34Z
published: 2026-07-30T14:46:34Z
canonical: "helpcenter.securiti.ai/remediating-files-from-the-data-remediation-dashboard"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Remediating files

Remediation lets you take a definitive action on files that have been reviewed and assessed, either by excluding them from further policy evaluation or marking them as deleted. This helps you keep the dashboard focused on active violations and reduces noise from files that have already been addressed.

For example, a policy flags a set of internal template files as sensitive because they contain placeholder data resembling PII. After reviewing them, you confirm these files are non-sensitive and do not require ongoing monitoring. You can select all flagged template files and mark them as excluded from the relevant policies, preventing them from appearing as violations in future policy runs.

To remediate file(s):

1. Select the file(s), and click **Remediate**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-OXD09ADD.png)
2. Choose one of the following remediation types:

| Type of Remediation | Description |
| --- | --- |
| Excluded | Excludes files from evaluation under the selected policy. If you select **Exclude from all policies**, exclusion behavior depends on where the action is performed: • Files marked as excluded from the File Insights, File Quarantine, or File ROT Remediation dashboards are excluded from evaluation across all three policies. • Files marked as excluded from the Data Labelling remediation dashboard are excluded from evaluation across data labeling policy. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-YYOHSB4A.png) |
| Deleted | Marks files as deleted and excludes them from evaluation across all policies. > [!NOTE] > Note > > This option only updates the file’s remediation status in Securiti. It does not delete the file from the graph. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-FU7BD7GF.png) |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-VYXOTXXF.png)

> [!NOTE]
> Note
> 
> When you revert a remediated file, Securiti records the corresponding reverse action in the file history. If you remediate the file using **Excluded**, the file history shows the action as **Included**. If you remediate the file using **Deleted**, the file history shows the action as **Restored**, as shown below.
> 
> ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-1785422626673.png)
3. Mention the reason for remediating file(s), and click **Remediate Files**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-BZGX2NCV.png)
