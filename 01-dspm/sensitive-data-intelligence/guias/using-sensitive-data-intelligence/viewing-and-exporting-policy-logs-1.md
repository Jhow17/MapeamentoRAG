---
title: "Viewing and exporting policy logs"
slug: "viewing-and-exporting-policy-logs-1"
updated: 2026-07-21T04:23:48Z
published: 2026-07-21T04:23:48Z
canonical: "helpcenter.securiti.ai/viewing-and-exporting-policy-logs-1"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Viewing and exporting policy logs

Securiti generates the File ROT policy logs to capture details of quarantine actions and related issues.

To view and export the policy logs:

1. From the File ROT **Policies** page, click options (three dots) and select **View**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-695MYXUZ.png)
2. From the upper-right corner of the policy details page, click **Policy Logs**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-W95NZGJN.png)
3. Filter logs by the following properties, as shown below.

| Properties | Description |
| --- | --- |
| Data System Type | Lets you filter the logs based on the type of data system where the file is located. For example, `G Suite Google Drive` |
| Data System Name | Lets you filter the logs based on the name of the data system from which the log entry is generated. For example,`John Testing` |
| Log Level | Lets you filter the logs based on the log level of the log entry. The following log levels are supported: - **Informational**: Informational logs are recorded when a quarantine or revert operation is skipped for an expected reason, such as when a datasource is not found in the quarantine-enabled datasources or when a batch revert is skipped for a set of documents. - **Error**: Error logs are recorded when a quarantine or revert operation fails due to an issue such as an internal server error, inability to load or validate the destination configuration, or when a datasource is not configured for quarantine operations. |
| File Name | Lets you filter the logs based on the name of the file associated with the log entry. For example,`John.json` |
| Folder Path | Lets you filter logs based on the folder path where the file is stored within the selected data system. |
| Timestamp | Lets you filter logs based on the exact date and time when the policy log entry was recorded. For example,`22 Jan, 2026 7:08 pm` |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-0ALYL7L8.png)
4. Click **Export** to generate a CSV file, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-OUH8AT1T.png)

Securiti sends an email with the download link when the CSV file is ready. You can also download the file from Securiti's my-downloads page.
