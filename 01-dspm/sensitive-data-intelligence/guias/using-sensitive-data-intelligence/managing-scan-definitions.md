---
title: "Managing scan definitions"
slug: "managing-scan-definitions"
updated: 2026-09-29T11:28:40Z
published: 2026-09-29T11:28:40Z
canonical: "helpcenter.securiti.ai/managing-scan-definitions"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Managing scan definitions

This section describes how you can pause, delete, and reassign a discovery scan.

### Pausing or resuming a discovery scan

This section describes how you can pause a discovery scan that is already in progress. You can also resume the paused scans. From the **Discovery Scans** page, choose Options (three dots) for a scan in a running state and click **Pause** for any running scan.

> [!WARNING]
> Important
> 
> Pausing a discovery scan happens in two steps, it does not stop immediately. The system first prepares the scan to pause (Pause Scheduled), then completes the pause once all activity is safely stopped (Paused).
> 
> **Pause Scheduled**
> 
> When you pause a discovery scan, the scan enters **Pause Scheduled**. At this stage, the system signals all parts of the scan to finish their current work. Any active tasks are saved so the scan can resume without data loss.
> 
> **Paused**
> 
> After all pending tasks are wrapped up, the scan moves into the **Paused** state. No new tasks run until the scan resumes. You might see logs of scanning operation even after the scan state was successfully paused. This happens as the **Pods** has already downloaded a large list of files and is processing internally based on content classification.
> 
> **Rare delay cases**
> 
> In rare cases, the system might take extra time to pause. This can happen when the scan is working through a very large or complex data that needs to finish its current action before stopping.

> [!NOTE]
> **Note**
> 
> You can pause and resume scan jobs based on the following conditions:
> 
> - On-demand pause is only available for manual scan jobs when they are in progress or running.
> - You can resume the discovery scan job only when the scan is paused.
> - You cannot pause or resume the scans for any scheduled jobs for which you set the schedules.
> - You cannot pause or resume the scans for which you have defined the exclusion intervals.

#### Supported data systems for pause and resume

The following table lists the data systems supported for pausing and resuming discovery scans.

| Structured | Unstructured |
| --- | --- |
| Amazon Aurora for PostgreSQL | Alibaba Cloud OSS |
| Amazon RDS MariaDB | Amazon S3 |
| Amazon RDS for MySQL | Asana Enterprise |
| Amazon RDS for PostgreSQL | Azure Blob Storage |
| Apache Hive | Azure Files |
| Azure Synapse | Box |
| Databricks | Citrix ShareFile |
| Domo | Dropbox |
| Google Cloud SQL for MySQL | G Suite Gmail (Attachments) |
| Google Cloud SQL for PostgreSQL | G Suite Google Drive |
| Google Cloud SQL for SQL Server | Google Cloud Storage |
| HP NonStopSQL | HDFS |
| IBM Netezza | Jira Software Data Center |
| InterSystem Cache | Jira Software |
| MariaDB | Microsoft 365 OneDrive |
| MySQL | Microsoft 365 Outlook (Attachments) |
| PostgreSQL | Microsoft 365 SharePoint Online |
| PowerBI Service | Microsoft Teams |
| SAP SuccessFactors | NFS |
| SQL Server | OpenText Content Server |
| Salesforce (Legacy) | Oracle HCM |
| Salesforce Customer Data Platform | Oracle Object Storage |
| ServiceNow Tables | SFTP |
| Snowflake | SMB |
| Zendesk | Salesforce CRM |
|  | Securiti for Box |
|  | Slack Enterprise |
|  | Slack Pro |
|  | Tableau Server |
|  | Zendesk Support |

### Deleting and reassigning a discovery scan

You can delete the primary scans that are no longer required.

From an entry on the **Discovery Scans** page, choose Options (three dots) and click **Delete**.

![DeleteScan.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bf5fe6c3-23d1-4b42-5040-e241189f0671.png)

> [!NOTE]
> **Note**
> 
> To delete a discovery scan, you must be the discovery scan owner.

Choose one of the options from:

- To delete the primary scan, click **Delete Anyway**. This removes the primary scan created for the current data system.
- To reassign another scan as a primary to your current scan and delete the current primary scan, click **Re-assign & Delete**.

![deleteAnyway.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2a99a1e6-0262-d138-18ca-aafc4df70006.png)

#### Canceling a running discovery scan

- On the **Discovery Scans List** page, from an in-progress scan entry, choose the Options (three dots) and choose **Cancel**.
  - The following cancel scan modal appears if all data sources have been marked as completed. To cancel the discovery scan, click **Cancel Scan**.

![DScancel_modal.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9aa02a9a-33c3-898a-7d32-3bc667457b58.png)
  - The following modal appears if all data sources have not been marked as completed. To cancel the discovery scan, click **Cancel Scan**.

![cancelDSModal.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4d94bc24-9d79-8b66-fe51-73aee54c128c.png)

This section describes how you can manage a scan definition. The supported actions include pausing, resuming, canceling, reassigning, and deleting a scan definition.

## Pausing or resuming a scan definition

You can pause a scan definition that is already in progress and resume a paused scan definition. From the **Scan Definitions** page, click the **More Actions** (three dots icon) for a scan definition in a running state, then click **Pause Scan**, as shown below.

![Overview of scan definitions, showing active and inactive scans with their statuses.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/pausingascanjob_scandefinitions.png)

Pausing a scan definition happens in two steps rather than stopping immediately. Use the following table to understand these scan definition states:

| Pause actions | Description |
| --- | --- |
| Pause Scheduled | When you pause a scan definition, it enters the **Pause Scheduled** state. At this stage, the system signals all parts of the scan to finish their current work. Any active tasks are saved so the scan definition can resume without data loss. |
| Paused | After all pending tasks are wrapped up, the scan definition moves into the **Paused** state. No new tasks run until the scan definition resumes. You might still see scanning activity in the logs even after the scan definition's state shows as successfully paused. This happens because the system has already downloaded a large batch of files before the pause took effect, and is still processing them internally based on content classification. > [!NOTE] > Note > > In rare cases, the system might take extra time to pause. This can happen when the scan definition is working through a very large or complex dataset that needs to finish its current action before stopping. |

> [!NOTE]
> **Note**
> 
> You can pause and resume scan jobs based on the following conditions:
> 
> - On-demand pause is only available for manual scan jobs when they are in progress or running.
> - You can resume a scan definition's job only when the scan definition is paused.
> - You cannot pause or resume scans for any scheduled jobs for which you set the schedules.
> - You cannot pause or resume scans for which you have defined exclusion intervals.

### Supported data systems for pause and resume

The following data systems support pausing and resuming a scan definition.

#### Structured data systems

- Amazon Aurora for PostgreSQL
- Amazon RDS MariaDB
- Amazon RDS for MySQL
- Amazon RDS for PostgreSQL
- Apache Hive
- Azure Synapse
- Databricks
- Domo
- Google Cloud SQL for MySQL
- Google Cloud SQL for PostgreSQL
- Google Cloud SQL for SQL Server
- HP NonStopSQL
- IBM Netezza
- InterSystem Cache
- MariaDB
- MySQL
- PostgreSQL
- PowerBI Service
- SAP SuccessFactors
- SQL Server
- Salesforce (Legacy)
- Salesforce Customer Data Platform
- ServiceNow Tables
- Snowflake
- Zendesk

#### Unstructured data systems

- Alibaba Cloud OSS
- Amazon S3
- Asana Enterprise
- Azure Blob Storage
- Azure Files
- Box
- Citrix ShareFile
- Dropbox
- G Suite Gmail (Attachments)
- G Suite Google Drive
- Google Cloud Storage
- HDFS
- Jira Software Data Center
- Jira Software
- Microsoft 365 OneDrive
- Microsoft 365 Outlook (Attachments)
- Microsoft 365 SharePoint Online
- Microsoft Teams
- NFS
- OpenText Content Server
- Oracle HCM
- Oracle Object Storage
- SFTP
- SMB
- Salesforce CRM
- Securiti for Box
- Slack Enterprise
- Slack Pro
- Tableau Server
- Zendesk Support

## Canceling a running scan definition

You can cancel a scan definition that is currently running. On the **Scan Definitions** page, from an in-progress scan definition entry, click the **More Actions** (three dots icon), then click **Cancel**, as shown below.

![Overview of scan definitions with active and completed scans listed in a table.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/cancelscan_scandefinitions(1).png)

The confirmation popup that appears depends on whether all data sources in the scan definition have been marked as completed. Use the following table to understand the confirmation popup for each status:

| Status | Description |
| --- | --- |
| All the data sources have been marked as completed | The popup mentions that the job status will be updated shortly, as shown below. To cancel the discovery scan, click **Cancel Scan**. ![DScancel_popup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9aa02a9a-33c3-898a-7d32-3bc667457b58.png) |
| All the data sources have not been marked as completed | The popup confirms the cancellation of the job status, as shown below. To cancel the discovery scan, click **Cancel Scan**. ![cancelDSpopup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4d94bc24-9d79-8b66-fe51-73aee54c128c.png) |

## Deleting and reassigning a scan definition

You can delete a primary scan definition that is no longer required.

From an entry on the **Scan Definitions** page, click the **More Actions** (three dots icon), then click **Delete**, as shown below.

![Overview of scan definitions with active and completed scans.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/deletescan_scandefinitions(2).png)

> [!NOTE]
> **Note**
> 
> To delete a scan definition, you must be the scan definition owner.

When you delete a primary scan definition, a confirmation popup appears. Choose one of the following two options based on your requirements:

- To delete the primary scan definition, click **Delete Anyway**. This removes the primary scan definition created for the current data system.
- To reassign another scan definition as the primary and delete the current primary scan definition, click **Re-assign & Delete**.

For more information, see [Discovery scan FAQs](/latest/docs/discovery-scan-faqs).

## Related

- [Discovery scans](/discovery-scans.md)
