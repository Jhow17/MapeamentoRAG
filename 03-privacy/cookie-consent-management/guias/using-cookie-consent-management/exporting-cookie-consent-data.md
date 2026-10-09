---
title: "Exporting cookie consent data"
slug: "exporting-cookie-consent-data"
updated: 2026-08-28T07:55:39Z
published: 2026-08-28T07:55:39Z
canonical: "helpcenter.securiti.ai/exporting-cookie-consent-data"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Exporting cookie consent data

**Scenario**

As a Data Privacy Officer, you receive a regulatory request to provide cookie consent records for data subjects in France for the month of March. Pulling this data manually from logs is slow and increases the risk of missing or incomplete records. With Securiti’s Export Consent Data functionality, you can select a custom date range and extract consent data specific to that period. It lets you generate a complete, time-bound report that captures consent status, timestamps, and data subject interactions. This helps you respond quickly to audits, demonstrate compliance with confidence, and avoid delays caused by manual data collection.

Securiti lets you export cookie consent data directly from the management portal using a selected date range. This capability simplifies data extraction for reporting, compliance, and operational use while improving reliability and reducing manual effort.

Use the following table to understand the available capabilities:

| Capability | Description |
| --- | --- |
| Date range selection | Exports consent data for any selected historical date range. |
| Large data handling | Splits large datasets into multiple `CSV` files and bundles them into a single `ZIP` file. |
| Email delivery | Sends an email notification with the subject “Your Consent Data Export is Ready” along with download links or a no-data notification. |
| Retry mechanism | Re-runs failed export attempts automatically and marks the job as failed with a reason if the retry is unsuccessful. |
| Job status tracking | Tracks export status as In Progress, Completed, or Failed. |
| Audit logging | Maintains the export operations in Securiti’s audit logs. |

> [!NOTE]
> **Note**
> 
> - Securiti only lets Super Admin user roles to initiate consent data exports.
> - Securiti processes one export request at a time per organization and includes data from all organizational units by default.
> - Consent data is exportable starting from 2020.
> - Securiti retains exported data for 30 days, after which it automatically deletes it.

## Procedure

To export Cookie Consent data:

1. In Securiti, open Cookie Consent Management, and choose **Explorers > Export Consent Data**.
2. On the Export Consent Data page, from the upper right corner, click **Export**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Export-button.png)
3. On the **Export** popup, set the data range using the date picker, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Set-Date-Range.png)
4. Once done, near the bottom of the popup, click **Export**. You can track the export status as In Progress, Completed, or Failed, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Export-Status.png)
5. Once the export completes, check your email for a notification from Securiti. The email includes secure download links or notifies you if no data is available for the selected date range, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Export-Email.png)

## Consent data fields

Use the following table to understand the fields included in the exported consent data:

| Field | Description |
| --- | --- |
| Domain ID | Identifier of the domain where consent was captured. |
| Domain URL | Website URL where consent was collected. |
| Subject identity | Unique identifier (UUID) for the data subject. |
| Consent status | Indicates whether consent is granted or declined. |
| IP address | IP address of the data subject. |
| Country | Country associated with the request. |
| Cookie category | Cookie category associated with the consent. |
| Consent given date | Date when the data subject provided consent. |
| Consent storage date | Date when C stored the consent record. |
| Implicit consent | Indicates whether consent was captured implicitly ("True" or "False"). |
| GPC signal | Indicates whether a Global Privacy Control (GPC) signal was detected ("True" or "False"). |
| User agent | Browser or client information. |
| Device type | Type of device used by the data subject. |
| Operating system | Operating system of the device. |
| Consent captured on | Source or context where consent was captured (if available). |
| Organization unit ID | Identifier of the organizational unit. |
| Organization unit name | Name of the organizational unit. |

> [!NOTE]
> Note
> 
> Securiti may leave some fields empty depending on the data available at the time of consent capture.

## Exporting consent data from completed jobs

To export consent records from the existing completed jobs:

1. In Securiti, open Cookie Consent Management, and choose the **Explorers > Export Consent Data**.
2. To the right of the jobs table, next to the **Updated On** column, click **Download**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Export-Data-Existing-Job.png)

Securiti processes the export of consent records again and sends you via email.

> [!NOTE]
> Note
> 
> Securiti updates the **Updated On** column after you initiate the re-export.

## Using top-level filter

The top-level filter lets you combine different properties of the export jobs and apply filters accordingly. It works from the top down and determines the result values in the grid view.

To use the top-level filter:

1. From the upper left corner of the Export Consent Data dashboard, click **+**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Filters-Icon.png)
2. From the filters panel, apply one or more filters using the following properties.

| Property | Description |
| --- | --- |
| Created On | Filters export jobs by date range. Use **between** to select a date range. |
| Created By | Filters export jobs by the user who created them. Use **is one of** to select one or more users from the provided list or use the search option. |
| Status | Filters export jobs by job status, such as **In Progress**, **Completed**, or **Failed**. Use **is one of** to select one or more consent states or use the search option. |
| Updated On | Filters export jobs by the export job’s last updated time. For instance, when you initiate a re-export job, the **Updated On** date changes to the current date. Use **between** to select a date range. |
3. Once you set all required properties, from the bottom of the filter panel, click **Apply**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Apply-filters.png)

Securiti builds a query based on your selected properties and displays the filtered results.
4. (Optional) To clear the filter, from the upper right corner, click **Clear Search**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Clear-Search.png)

The Global Privacy Control (GPC) is a browser-based global opt-out tool that lets the Internet users signal their opt-out consent settings to websites, advertisers, and publishers on the world wide web. Some global privacy laws, such as the CPRA, require covered entities to mandatorily detect and honor users’ GPC signal. The Cookie Consent Management module lets you configure cookie banners and preference centers with GPC to ensure detection of the GPC signals on the web browsers of your data subjects to honor their opt-out cookie preferences
