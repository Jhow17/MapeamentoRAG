---
title: "Exporting and scheduling cookie consent reports and metrics"
slug: "exporting-and-scheduling-cookie-consent-reports-and-metrics"
updated: 2026-04-27T12:00:47Z
published: 2026-04-27T12:00:47Z
canonical: "helpcenter.securiti.ai/exporting-and-scheduling-cookie-consent-reports-and-metrics"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Exporting and scheduling cookie consent reports and metrics

Securiti lets you export cookie consent data and schedule consent metrics reports to support reporting, compliance, and analysis. You can:

- Export raw consent data for detailed analysis
- Schedule weekly consent metrics reports for selected recipients

## Exporting cookie consent data

Securiti sends exported data via email every Sunday to the cookie domain owner. The raw data includes the following properties for each consent:

- Client device family
- Client OS family
- Client user agent family
- Consent date
- Consent ID
- Consent status
- Cookie category
- Cookie category consented to
- Country code
- Device type
- Geolocation IP
- Implicit consent (T/F)
- Is active
- Location code
- Subject identity (UUID)
- User agent

To configure scheduled consent data export:

1. In Securiti, open **Cookie Consent Management**, and choose **Advanced** **Settings > Schedule Consent Report**.
2. On the **Schedule Consent Report** page, mark the **Send cookie consent reports to all cookie domain owner(s) on a weekly basis** radio button.
3. From the upper right of the page, click **Save**.

> [!NOTE]
> **Note**
> 
> Securiti automatically generates and sends weekly consent reports for all organizational units within your tenant every Sunday. The report name includes the organizational unit name.

## Scheduling a cookie report

To schedule a cookie report:

1. Open **Cookie Consent Management**, and choose **Advanced Settings > Schedule Consent Metrics Report**.
2. From the upper right side of the Consent Metrics page, click **+ Schedule Report**.
3. On the Schedule Report popup, fill the following details, then click **Schedule Report**:

| Setting | Description |
| --- | --- |
| Report title | Enter a descriptive title. |
| Cookie domain | Choose the cookie domain for which the report returns cookie consent metrics. |
| Country | Choose the country for which the report returns cookie consent metrics. |
| Recipients | Choose the recipients for the report. Securiti emails the report to the email address corresponding to their Securiti accounts. |

> [!NOTE]
> Note
> 
> Securiti adds an entry for the report to the Consent Metrics page, and emails the report to the recipients every week on Sunday.

## Deleting a scheduled cookie report

To delete a scheduled cookie report:

1. Open **Cookie Consent Management**, and choose **Advanced Settings > Schedule Consent Metrics Report**.
2. Go to the report you want to delete the scheduled report for, click **Options** (three dots) on the right side of the report, and select **Delete Scheduled Report**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Delete-Scheduled-Report.png)
3. On the **Delete Scheduled Report** popup, click **Yes, Delete Schedule** to delete your scheduled report, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Delete-Schedule-Report-popup.png)

## Cookie report analysis

Use the following table to understand the descriptions of the cookie report column headers:

| Column Header | Description |
| --- | --- |
| Cookie ID | Identifier assigned to the scanned cookie. |
| Cookie Name | Name of the scanned cookie. |
| Description | Description explaining the purpose of the scanned cookie explaining its purpose and why it was dropped by the organization. |
| Purpose | Explains the intention of the organization that dropped the cookie. |
| Cookie Category | Name of the cookie category to which the scanned cookie belongs. For instance, the cookie category could be **Advertising** or **Essential**. |
| Cookie Base Category | Name of the base cookie category. It can be: - Essential - Analytics & Customization - Advertising - Performance & Functionality - Unclassified - Social Networking |
| Category Description | Description of the base category to which the scanned cookie belongs. |
| Opt Out Text | Text against a cookie category when the data subject tries to opt out of a cookie category in the cookie preference center. |
| Domain ID | Identifier of the scanned domain on which the cookie scanner found the cookies attached in the cookie report. |
| Domain URL | URL of the scanned domain on which the cookie scanner found the cookies attached in the cookie report. |
| Expiry | Expiration date of the scanned cookie. |
| Country | Region from which the cookie is dropped. |
| Found on URL | URL of where the cookie is detected. |
| Initiator | Origin point of the cookie. |
| Initiator Type | Type of the origin point from where the cookie originates. It can be: - Script - Network - Webserver - Particular line on a page source |
| Cookie Provider | Entity that dropped the scanned cookie. |
| Policy URL | Policy URL of the organization that drops the scanned cookie. |
| Resource URL | Source location of the cookie. |
| Service | Name of the service provider responsible for dropping and managing the scanned cookie. |
| Cookie Type | Type of tracker. It can be: - Beacon - Cookie - Local storage item - Session storage item |
| First/Third Party | Indicates whether a cookie is classified as a first-party or third-party cookie, based on the domain that sets it. First-party cookies originate from the domain the data subject is visiting, while third-party cookies are set by a different domain. |

A web beacon is a small, usually transparent image embedded on a website or email that tracks the behavior of data subjects.

A small text file that is stored on a data subject's or website visitor's device (computer, smartphone, or tablet) by a domain (website). Cookies are used to collect information about the user's interactions with the website, such as preferences, login status, and browsing history. This information helps domains enhance user experience, perform analytics, and deliver personalized content and advertisements. Cookies can be categorized into various types, including Essential, Performance, Functionality, and targeting cookies, each serving different purposes in managing user consent and data privacy.

Local storage item stores the data in a persistent manner until the user manually clears the browser cache or until the web application clears the data.

Session storage item stores the data in a persistent manner only until the window or tab is closed.
