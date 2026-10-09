---
title: "Data Remediation"
slug: "data-remediation-system-dashboards"
status: "update"
updated: 2026-09-17T07:33:15Z
published: 2026-09-17T07:33:15Z
canonical: "helpcenter.securiti.ai/data-remediation-system-dashboards"
area: dspm
modulo: graph-reporting-dashboards
tipo: guia
data_captura: 2026-10-06
---

# Data Remediation

The Data Remediation system dashboards provide visibility into obsolete and potentially risky files across your data systems. Use these dashboards to review policy outcomes, monitor remediation activity, and identify files for review or cleanup.

The **Data Remediation** dashboard category includes the following dashboards:

| Dashboard | Description |
| --- | --- |
| File Insight | Lets you review obsolete files that File Insights policies identify across your data systems. |
| File Quarantine | Lets you review files that File Quarantine policies identify across your data systems. |
| File ROT | Lets you review Redundant, Obsolete, or Trivial (ROT) files that File ROT policies identify across your data systems. |

- Use the policy filter at the top of each dashboard to filter data by a specific policy, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-SJS82EUV.png)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-KBLNNYLF.png)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-BXMA6C8P.png)
- After you select a policy, the dashboard displays insights in the following widgets:

| Widget Name | Widget Type | Description |
| --- | --- | --- |
| Obsolete Data | Metric | Displays the total number and volume of obsolete files for the selected policy. |
| Processed Data Trend | Trend Chart | Displays the weekly trend of files processed for the selected policy. |
| Processed Data | Metric | Displays the total number and volume of quarantined and reverted files. |
| Top Obsolete Data Sources | Grid | Displays the data systems with the greatest number of obsolete files and the file count for each. |
| Data Posture Score | Trend Chart | Displays the data posture score over time based on the severity and impact of applied policies. |
| Obsolete Files by file format | Treemap | Displays the number of obsolete files grouped by file format. |
| Quarantined Files | Grid | Displays quarantined files and details such as the file name, source data system, resource path, file owner, and resource URL. |
| Reverted Files | Grid | Displays reverted files and details such as the file name, source data system, resource path, file owner, and resource URL. |
