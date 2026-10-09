---
title: "Manually labeling files"
slug: "manually-labeling-files"
updated: 2026-07-30T14:56:19Z
published: 2026-07-30T14:56:19Z
canonical: "helpcenter.securiti.ai/manually-labeling-files"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Manually labeling files

Securiti lets you apply sensitivity labels to files on demand, without waiting for a Data Labeling policy to run automatically. This is useful when you configure a Data Labeling policy with **Auto Labeling** option disabled, which lets you to first review which files the policy would impact before applying any labels. Once you validate the results, you can go to the Data Remediation dashboard and use **Manually Label** to apply labels to the specific files you want.

For example, your organization wants to apply a Confidential label to all files containing personally identifiable information (PII) across your SharePoint data system. You create a Data Labeling policy with Auto Labeling disabled to first review which files the policy would impact before committing to any changes. After reviewing the scoped files in the Data Remediation dashboard and confirming the results look correct, you select the specific files you want to label and apply the Confidential sensitivity label manually.

> [!NOTE]
> Note
> 
> Manual labeling executes the same policy logic as auto-labeling. If you configure the policy to allow label overrides, manual labeling follows that behavior. If you do not allow overrides in the policy, manual labeling respects that restriction as well. Securiti records the manual labeling action in the **File History** in the Data Remediation dashboard, where you can see whether a label was applied through Auto Labeling or Manual Labeling. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-93G27A1H.png)

To manually label file(s):

1. Select the file(s) scoped by your selected Data Labeling policy from the Data Remediation dashboard, and click **Manually Label**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-AE9Y6MR4.png)
2. Mention the reason for manually labeling the file(s), and click **Manually Label File** to confirm, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-4AM6PSA0.png)
