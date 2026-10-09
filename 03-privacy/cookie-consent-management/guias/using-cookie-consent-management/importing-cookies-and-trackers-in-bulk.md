---
title: "Importing cookies and trackers in bulk"
slug: "importing-cookies-and-trackers-in-bulk"
updated: 2025-11-20T08:01:01Z
published: 2025-11-20T08:01:01Z
canonical: "helpcenter.securiti.ai/importing-cookies-and-trackers-in-bulk"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Importing cookies and trackers in bulk

**Scenario**

As a consent admin, you manage cookie data for dozens of domains. Manually adding each tracker one by one slows you down and increases the chance of errors. With Securiti’s bulk import feature in the Cookie and Tracker Library, you just have to fill out a simple CSV template and upload it directly into the Cookie and Tracker Library. You populate your inventory in minutes, improving efficiency and ensuring comprehensive coverage across all domains.

## Overview

Securiti’s bulk import feature in the Cookie and Tracker Library helps you save time and reduce manual effort when managing cookies and trackers across domains. Instead of adding entries one by one, you can download the CSV file template, fill it with details of multiple cookies and tracking technologies, and upload it back to the library. This eliminates the need to add each entry manually and lets you manage large volumes of cookie data more efficiently. This feature helps improve data consistency, and helps maintain a centralized, up-to-date library for all existing domains in your Securiti tenant.

> [!NOTE]
> Note
> 
> Only the following Securiti user roles in your organization can import cookies or trackers in bulk:
> 
> - Super Admin
> - Org Admin
> - Module Owner

## Procedure

To import cookies and trackers in bulk:

1. In Securiti, open Cookie Consent Management, and choose **Cookie Consent Configurations > Cookie & Tracker Library**.
2. On the Cookie & Tracker Library page, from the upper right corner, click **More Options**, and select, **Import Trackers**.
3. On the **Import Trackers** popup, click **Download .CSV Template** to download the CSV template to your local machine.
4. Navigate to the **Downloads** folder on your local machine, and open the `import_trackers_template.csv` file in any spreadsheet tool.
5. Fill out the details for each cookie or tracker in the CSV file. Provide values for the following fields:

| Field | Description |
| --- | --- |
| Cookie Name | Name of the cookie or tracking technology. |
| Description | A brief explanation of what the cookie or tracker does. |
| Purpose | The reason for using the cookie, such as analytics, advertising, or functionality. |
| Category | The classification of the cookie, such as Essential, Analytics, or Social Networking, etc. |
| Domain URL | The domain where the cookie is set. |
| Found on URL | The specific page or URL where the cookie was detected. |
| Country | The country where the cookie is typically set or used. |
| Expiry or Duration | How long the cookie stays on the data subject’s browser, such as Session or 1 year. |
| Initiator | The source or component that triggered the cookie, such as Google Analytics or Meta Pixel. |
| Initiator Type | The type of initiator, such as Script, Image, or Inline. |
| Cookie Provider | The organization or service that owns the cookie. |
| Policy URL | A link to the provider’s privacy or cookie policy. |
| Resource URL | The location of the script or element responsible for setting the cookie. |
| Service | The broader service the cookie is part of, such as YouTube or Hotjar. |
| Cookie Type | The technical type of cookie, such as First-party or Third-party. |
6. Once done, save the changes to your CSV file.
7. On the **Import Trackers** popup, in the **File Description** text field, enter an appropriate description for the CSV file.
8. In the section below the File Description field, drag and drop the CSV file from your local machine or click **Or Select File to Upload**, and choose the CSV file.
9. Once the file is uploaded, from the **Choose to Override or Ignore Duplicate Entries** section, click one of the following cards to suit, as shown below:
10. | Card | Description |
| --- | --- |
| Ignore Duplicate Tracker(s) | Securiti retains the existing cookie and tracker entries in the library and skips the versions from your uploaded CSV file. |
| Override Existing Tracker(s) | Securiti replaces the existing cookie and tracker entries in the library with the versions from your uploaded CSV file. |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Import-Trackers-popup.png)
11. Once done, near the bottom of the popup, click **Import**. Securiti immediately starts importing cookies and trackers into the library. The process may take a few minutes depending on the number of entries in the file.
12. Once the import is complete, Securiti shows the **Import Status** popup. From this popup, you can view the outcome of the import process, including how many trackers were **Imported**, **Aborted**, or **Errored**, as shown below.
  1. If any trackers failed to upload, click **Download Failed Trackers File** to download the file and review the reasons for the import failure.
  2. If the import was successful, near the bottom of the popup, click **Dismiss** to close it.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Import-Status-popup.png)

> [!NOTE]
> Note
> 
> Securiti also sends you an email containing the file with failed or errored trackers.
