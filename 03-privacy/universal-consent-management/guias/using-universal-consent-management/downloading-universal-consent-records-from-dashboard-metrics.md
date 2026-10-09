---
title: "Downloading the universal consent records from the Dashboard and Metrics"
slug: "downloading-universal-consent-records-from-dashboard-metrics"
updated: 2026-09-01T08:00:26Z
published: 2026-09-01T08:00:26Z
canonical: "helpcenter.securiti.ai/downloading-universal-consent-records-from-dashboard-metrics"
area: privacy
modulo: universal-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Downloading the universal consent records from the Dashboard and Metrics

You can download universal consent records from the **Dashboard** and **Metrics** tabs in the Universal Consent Dashboard & Metrics experience. The available download options differ by tab, depending on whether you need record-level data or aggregated metrics.

## Downloading universal consent records from the Dashboard

To download the universal consent records:

1. In Securiti, open Universal Consent Management and choose Dashboard & Metrics. The **Dashboard** opens by default.
2. Near the upper right corner of the page, click the **+** (plus icon) and apply filters to suit.
3. In the upper right corner of the universal consent table, click **Download Records**, as shown below.

![Universal Consent Dashboard displaying consent records and options for managing data.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ucm_download_records_1.png)

> [!NOTE]
> Note
> 
> To prevent multiple report requests and reduce system strain, the **Download Records** button on the Universal Consent Dashboard page disables after a single click and only re-enables when you change the filters. Additionally, Securiti enforces a limit of **5 report requests per hour** for each Securiti user role.

Securiti schedules your download, and you receive an email containing the download link to your universal consent records.
4. Open your email associated with your Securiti tenant, and click **Download File** to download the `CSV` file containing consent records in your local machine, as shown below.

![Email notification for downloading the Universal Consent Report with details and download link.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ucm_download_records_2(1).png)

> [!NOTE]
> Note
> 
> The download link remains valid for 7 days.

## Analyzing the universal consent records report

Use the following table to understand the purpose of each column included in the exported report of universal consent records:

| Column header | Description |
| --- | --- |
| Subject Identity | Indicates the identifier associated with the data subject who provided consent. |
| Consent Status | Reflects whether the data subjects granted or declined the consent. |
| Consent Date | Shows the timestamp when the consent action was captured. |
| Consent Source | Indicates the consent source IDs. For instance, the ID is 10 for Forms and 22 for API. |
| Consent Source Name | Indicates the source through which the data subject provided consent. Such as Forms, Preference Center, or API. |
| Processing Purpose | Indicates the purpose for which personal data is processed based on the data subject’s consent. |
| Consent Purpose | Indicates the specific purpose selected by the data subject when providing consent. |
| Category Name | Indicates the high-level category under which the data subject provides consent for specific processing purposes. |
| GeoLocation IP | Indicates the approximate geographic location of the data subject based on the IP address captured at the time of consent. |
| Country Code | Shows the country code associated with the data subject’s location at the time consent was provided. |
| Consent Collected Date | Indicates the timestamp at which consent was recorded. |
| Derived Consent Rule | Indicates the rule that determines the final consent status based on Rules Matrix. |

## Downloading records of unique users from the Metrics

To download the unique users data:

1. In Securiti, open Universal Consent Management and choose Dashboard & Metrics. The Dashboard opens by default.
2. Near the top center of the Dashboard, select the Metrics tab.
3. Apply filters to scope the data as needed.
4. Near the upper right corner of the Unique Users widget, click **Download CSV**, as shown below.

![Dashboard displaying unique users and consent status metrics for data management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/umc_dashboard_download_csv.png)

Securiti schedules the export and sends an email to the email address associated with your Securiti tenant containing a secure download link.
5. Open the email and click **Download Report** to download the `CSV` file to your local machine, as shown below.

![Email notification for downloading the Universal Consent unique users report successfully generated.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/download_records_csv.png)
