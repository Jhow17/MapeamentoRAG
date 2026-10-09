---
title: "Downloading the Legacy cookie consent records"
slug: "downloading-the-cookie-consent-records"
updated: 2026-09-03T06:37:01Z
published: 2026-09-03T06:37:01Z
canonical: "helpcenter.securiti.ai/downloading-the-cookie-consent-records"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Downloading the Legacy cookie consent records

You can download legacy cookie consent data from the Consent Records table on the Cookie Consent Legacy Dashboard which provides record-level consent information captured through cookie banners and preference centers. Securiti sends you an email containing the download link to the `CSV` file.

> [!NOTE]
> **Note**
> 
> The contents of the file reflects the filters applied at the time of the download.

To download the cookie consent records:

1. In Securiti, open **Cookie Consent Management** and choose **Legacy** **Cookie Consent Data**.
2. Near the upper right corner of the page, click **Filter**, and apply filters to suit.
3. From the upper right corner of the **Consent Records** table, click **Download** icon.

> [!NOTE]
> **Note**
> 
> To prevent multiple report requests and reduce system strain, the **Download Records** button on the Cookie Consent Legacy Dashboard disables after a single click and only re-enables when you change the filters. Additionally, Securiti enforces a limit of **5 report requests per hour** for each Securiti user role.
4. Securiti schedules your download, and you receive an email containing the download link to your cookie consent records.
5. Open your email associated with your Securiti tenant, and click **Download File** to download the `CSV` file containing consent records in your local machine.

> [!NOTE]
> **Note**
> 
> The download link remains valid for **7 days**.

### Analyzing the cookie consent records report

Use the following table to understand the purpose of each column included in the exported report of cookie consent records:

| Column header | Description |
| --- | --- |
| Subject Identity | Indicates the identifier associated with the data subject who provided consent. |
| Cookie Category | Specifies the classification of the cookie, such as Essential, Analytics, Advertising, etc. |
| Consent Status | Reflects whether the data subject accepted or rejected cookies in that cookie category. |
|  | States whether the consent was implicitly inferred or explicitly given. |
| Consent Date | Records the timestamp when the consent action was captured. |
| Location Code | Provides the location code based on the data subject's IP-derived region. |
| Country Code | Indicates the country code such as `US`, `FR`, etc., derived from the data subject's location. |
| User Agent | Captures the complete user agent string of the web browser used by the data subject. |
| Device Type | Describes the type of device used, such as Desktop, Mobile, or Tablet. |
| Consent Id | A unique identifier generated for the specific consent record. |
| Is Active | Indicates whether the consent record is currently valid (true/false). |
| Client User Agent Family | Specifies the web browser family such as Chrome, Firefox, Safari, etc. used to provide consent. |
| Client OS Family | Denotes the operating system family such as Windows, macOS, Android, etc. of the device. |
| GPC Signal | Shows whether the Global Privacy Control (GPC) signal was detected during consent capture. |
| GeoLocation Info | Provides additional geolocation information, if available, for the data subject. |
| Domain Group | Identifies the group (category) to which the domain belongs, for organizational purposes. |

The Global Privacy Control (GPC) is a browser-based global opt-out tool that lets the Internet users signal their opt-out consent settings to websites, advertisers, and publishers on the world wide web. Some global privacy laws, such as the CPRA, require covered entities to mandatorily detect and honor users’ GPC signal. The Cookie Consent Management module lets you configure cookie banners and preference centers with GPC to ensure detection of the GPC signals on the web browsers of your data subjects to honor their opt-out cookie preferences

Signal means any signal defined by the IAB EU TCF v2.2 **Policies** or **Specifications** sent by a CMP to **Vendors**, usually on behalf of a **Publisher**. This includes information about the transparency, consent, and/or objection status of a Vendor and/or Purpose, the opt-in status of a Special Feature, and Publisher restrictions.

## Related

- [Filtering cookie consent records from the Legacy dashboard](/filtering-cookie-consent.md)
- [Collecting cookie consent](/collecting-cookie-consent.md)
