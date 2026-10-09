---
title: "Viewing and exporting policy logs"
slug: "viewing-data-labeling-policy-logs"
updated: 2026-07-30T12:51:12Z
published: 2026-07-30T12:51:12Z
canonical: "helpcenter.securiti.ai/viewing-data-labeling-policy-logs"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Viewing and exporting policy logs

Securiti generates the Data Labeling policy logs to capture details of labeling actions and related issues.

> [!NOTE]
> Note
> 
> You see entries in the Policy Logs only when a file is not labeled. This can happen when one of these conditions occur:
> 
> - The file is not labeled because of an error.
> - The file format is not supported.
> - The file is already labeled and the **Override already applied label** is not selected.

To view and export the policy logs:

1. From the Data Labeling **Policies** page, click options (three dots) and select **View**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-2ELEGIC7.png)
2. From the upper-right corner of the policy details page, click **Policy Logs**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-2BL9CH3B.png)
3. Filter logs by the following properties, as shown below.

| Properties | Description |
| --- | --- |
| Data System Type | Lets you filter the logs based on the type of data system where the file is located. For example, `Microsoft 365 SharePoint Online` |
| Data System Name | Lets you filter the logs based on the name of the data system from which the log entry is generated. For example,`John Testing` |
| Log Level | Lets you filter the logs based on the log level of the log entry. The following log levels are supported: • **Informational:** Informational logs are recorded when a labeling operation is skipped for an expected reason, such as an unsupported file format, an existing label that takes precedence, a manually applied label, or when override is not enabled. • **Error:** Error logs are recorded when a labeling operation fails due to an issue such as a failed download or upload, inability to extract or assign labels, a malformed file, or an unresolvable label state. |
| File Name | Lets you filter the logs based on the name of the file associated with the log entry. For example,`John.json` |
| Current Label | Lets you filter the logs based on the label currently applied to the file at the time of the log entry. |
| Original Label | Lets you filter the logs based on the label applied to the file before any policy or remediation action. |
| Timestamp | Lets you filter logs based on the exact date and time when the policy log entry was recorded. For example,`22 Jan, 2026 7:08 pm` |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-LKD49223.png)
4. Click **Export** to generate a CSV file, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-44V9QAPR.png)

Securiti sends an email with the download link when the CSV file is ready. You can also download the file from Securiti's my-downloads page.
