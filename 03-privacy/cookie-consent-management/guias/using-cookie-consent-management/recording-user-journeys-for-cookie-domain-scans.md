---
title: "Recording user journeys for cookie domain scans"
slug: "recording-user-journeys-for-cookie-domain-scans"
updated: 2026-09-03T06:50:27Z
published: 2026-09-03T06:50:27Z
canonical: "helpcenter.securiti.ai/recording-user-journeys-for-cookie-domain-scans"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Recording user journeys for cookie domain scans

**Scenario**

As a Data Compliance Officer, you need to detect cookies and trackers that appear only after data subjects interact with specific sections of your website. For instance, on a flight booking website, trackers may load only after a data subject selects trip details, searches for flights, and proceeds through the booking flow. Standard scans may miss these interaction-based trackers. With Securiti’s user journey recording for cookie scans, you can replay recorded website interactions during scans to uncover cookies and trackers triggered throughout the user journey. This helps you improve detection accuracy and maintain more reliable compliance visibility across your website.

Securiti lets you upload Google Chrome DevTools journey recordings to improve cookie and tracker detection for websites that drop cookies only after specific user interactions. These interactions can include filling forms, selecting options, clicking buttons, or navigating through multiple pages of the website.

During a scan, Securiti runs the configured journeys once at the start of the scan and adds any detected cookies and trackers to the final scan results.

## When to use journey recordings

Use journey recordings when your website drops cookies or trackers only after a data subject completes specific actions, such as:

- Filling out a form
- Selecting menu options
- Clicking buttons
- Moving through booking, reservation, or checkout-style flows
- Navigating to pages that standard scans may not reach

## Best practices for recording journeys

Use the following best practices to reduce scan failures and improve detection accuracy:

| **Best practice** | Description |
| --- | --- |
| Keep recordings short | Keep each recording within 10 to 15 steps. Securiti counts actions such as clicking a button, filling a field, selecting a menu item, or navigating to another page as separate steps. |
| Avoid dynamic dates | Keep the default date when possible. Custom dates may become invalid in future scans, especially for booking or reservation flows. |
| Use dummy data | Enter dummy values instead of real personal, credential, or payment information. |
| Select broad booking options | For booking or reservation flows, select locations or destinations that are likely to return available results so the journey can continue successfully. |
| Avoid CAPTCHA-protected flows | Record journeys that do not trigger CAPTCHA challenges. The cookie scanner cannot solve CAPTCHAs during scan execution. |

## Procedure

Before uploading a form fill journey scan, record the user journey in Google Chrome DevTools and export it as a Securiti file. To learn how to record a user journey flow before using the Upload Form Fill Journey Scan feature, watch Google’s official [Record, Replay, and Measure User Flows](https://developer.chrome.com/docs/devtools/recorder) demo.

> [!CAUTION]
> Caution
> 
> You **must never use sensitive data**, such as personal information, credentials, or payment details, when recording these journeys. Chrome DevTools stores recorded journey inputs in the exported Securiti file.

To upload a form fill journey scan:

1. In Securiti, open **Cookie Consent Management**, and choose **Explorers > Domains**.
2. Click the domain for which you want to upload the journey recording.
3. Click the **Website Scan & Report** tab.
4. Near the upper right corner of the page, click **Edit**.
5. From the **Upload Form Fill Journey Scan** section, drag and drop the Securiti file into the upload area, or click **select Files to upload**, as shown below.

> [!NOTE]
> Note
> 
> You can upload up to five journey recording `JSON` files for each domain, with each file up to **5 MB**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Form-Fill-User-Journey(1).png)
6. (Optional) If the uploaded journey includes date-based values, click **Configure** next to the uploaded file, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Configure-Usere-Journey.png)
  1. On the **Configure User Journey Dates** popup, choose how Securiti should handle the date fields found in the selected journey, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Configure-User-Journey-Dates-popup.png) Use the following table to understand the available date configuration options:

| Date option | Description |
| --- | --- |
| Static date | To use the exact date recorded during the user journey, mark the **Static Date** radio button. > [!WARNING] > Important > > Use this option only if the date recorded remains valid when Securiti runs the scan. |
| Relative date | To use a date relative to the scan date, mark the **Relative Date** radio button. In the **Interval** text field, enter the number of days after the scan date that Securiti should use to calculate the end date, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Relative-Date-Set-Interval.png) |
  2. Near the bottom of the **Configure User Journey Dates** popup, click **Save**.
7. From the upper right corner of the page, click **Save**.

Securiti runs the configured journeys once at the start of the scan and adds any cookies and trackers that it detects to the final domain scan results. During scan execution, the **Live Scan Status** popup displays the uploaded journey recordings and their execution status, as shown below. The final scan report also includes journey-related details, such as whether Securiti found a cookie during a journey and the initiator type.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Live-Scan-Status.png)
