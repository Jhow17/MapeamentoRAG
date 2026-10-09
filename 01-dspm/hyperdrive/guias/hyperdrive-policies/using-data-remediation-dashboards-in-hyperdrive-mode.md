---
title: "Using Data Remediation dashboards in Hyperdrive mode"
slug: "using-data-remediation-dashboards-in-hyperdrive-mode"
status: "new"
updated: 2026-09-22T03:53:24Z
published: 2026-09-22T03:53:24Z
canonical: "helpcenter.securiti.ai/using-data-remediation-dashboards-in-hyperdrive-mode"
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Using Data Remediation dashboards in Hyperdrive mode

The Data Remediation dashboards provide a centralized view of files scoped by the following policies in Sensitive Data Intelligence:

- Data Labeling
- File Insights
- File Quarantine
- File ROT

You can use these dashboards to review policy outcomes, investigate files, and perform remediation actions from a single interface. For more information, see [Using Data Remediation Dashboards](/latest/docs/using-data-remediation-dashboards).

## Remediation actions

The Data Remediation dashboards support different remediation actions based on the policy type, as described in the following table:

| Policy | Remediation action | Description |
| --- | --- | --- |
| Data Labeling | Manually Label | Lets you manually apply sensitivity labels to files within the scope of the selected Data Labeling policy. For more information, see [Manually labeling files](/latest/docs/manually-labeling-files). |
| Remove Label | Lets you remove specific or all sensitivity labels from files within the scope of the selected Data Labeling policy. For more information, see [Removing labels from files.](/latest/docs/removing-labels-from-files) |
| File Quarantine | Quarantine | Lets you isolate files from their original location to restrict access and prevent further exposure. For more information, see [Quarantining files](/latest/docs/quarantining-files-from-the-data-remediation-dashboard). |
| Revert | Lets you restore quarantined files to their original location. For more information, see [Reverting files](/latest/docs/reverting-files-from-the-data-remediation-dashboard). |
| All Policies | Remediate | Lets you exclude files from further policy evaluation or mark them as deleted. For more information, see [Remediating files](/latest/docs/remediating-files-from-the-data-remediation-dashboard). |
| Remove Remediation | Lets you reverse previously applied remediation and restore files to active policy evaluation. For more information, see [Removing remediation](/latest/docs/removing-remediation-from-files). |

## Next steps

To learn more about investigating policy outcomes, monitoring policy activity, managing policies, and troubleshooting remediation actions, see the following articles:

- [Accessing evidence files for policies](/latest/docs/111)
- [Viewing policies in the reporting dashboard](/latest/docs/111-1)
- [Accessing policy logs from the Data Remediation dashboard](/latest/docs/111-2)
- [Updating policies from the Data Remediation dashboard](/latest/docs/111-3)
- [Troubleshooting for data remediation actions](/latest/docs/troubleshooting-data-remediation-dashboards)
