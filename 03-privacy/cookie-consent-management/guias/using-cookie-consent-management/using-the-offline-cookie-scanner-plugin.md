---
title: "Using the offline cookie scanner plugin"
slug: "using-the-offline-cookie-scanner-plugin"
updated: 2026-09-22T19:59:27Z
published: 2026-09-22T19:59:27Z
canonical: "helpcenter.securiti.ai/using-the-offline-cookie-scanner-plugin"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Using the offline cookie scanner plugin

Securiti provides a Google Chrome web browser plugin that lets you scan webpages for cookies. The offline cookie scanner plugin generates a `JSON` file that you can upload to Securiti instead of running an online cookie scan. You can use the offline cookie scanner for websites or specific webpages that are difficult to scan with Securiti’s online scanner, such as webpages protected by complex authentication flows.

## Installing the web browser plugin

To download and install the web browser plugin:

1. On the Chrome Web Store, navigate to the [Veeam (Securiti.AI) Cookie Scanner](https://chromewebstore.google.com/detail/veeam-securitiai-cookie-s/kgleeojgabnjeebilliignebkdeajibe) listing.

> [!WARNING]
> Important
> 
> This plugin is not publicly available. You can download and install it only through the link provided in step 1 of this procedure.
2. From the upper right corner, click **Add to Chrome**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Add-to-Chrome-button.png)
3. From the **Add “Veeam (Securiti.AI) Cookie Scanner”** popup, click **Add extension**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Add-extension-button.png)
4. From the **Extensions** menu in Google Chrome, pin **Veeam (Securiti.AI) Cookie Scanner**. After you pin the extension, the extension icon appears in the upper right corner of Google Chrome, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Extension-in-Google-Chrome.png)

## Scanning website pages for cookies

To use the web browser plugin to scan for cookies:

1. Navigate to the webpage you want to scan for cookies.
2. Near the upper right corner of the web browser, click **Extensions** (puzzle piece icon), and choose **Securiti Cookie Scanner** from the available extensions.
3. On the **Securiti** **Cookie Scanner** popup, click **Play** icon (right arrow).

![Screenshot_2022-08-10_at_12_22_46_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e2a93f34-2e62-4810-162a-4a7be7211485.png)
4. Navigate to any webpage on the website for which you want to scan for cookies.
5. When you are done, re-open the Securiti Cookie Scanner, and click **Stop** (two vertical lines).
6. Click **Download JSON**, as shown below.

![Screenshot_2022-08-10_at_12_24_38_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-59619fa3-9ec3-2813-d51d-15aa8a298a38.png)

Rename the `JSON` file if you want. The offline cookie scanner plugin also lets you download a `JSON` file with empty values even when it did not find any cookies, local storage, or session storage items during the scan.

This `JSON` file contains all the information such as the scan start time, scan end time, details of cookies such as cookie classification types (first-party or third-party), local storage items, and session storage items that the offline scanner found on your domain.

## Uploading offline cookie scanner results to Securiti

To upload the results of the scan to Securiti:

1. In Securiti, open Cookie Consent Management, and choose **Explorers > Domains**.
2. Select the domain for the website you scanned.

> [!NOTE]
> Note
> 
> If the domain does not exist, create a new domain first.
3. On the **Website Scan & Report** tab, click the **Import Offline Scanner Output**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Import-Offline-Scanner-Output.png)
4. Select how Securiti should import the offline cookie scanner results, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Add-to-scan-results.png) Use the following table to understand the available import options:

| Option | Description |
| --- | --- |
| Override scan results | Replaces the previous scan results with the imported offline cookie scanner results. |
| Add to scan results | Adds the imported offline scanner results to the existing scan results. |
5. Drag and drop the `JSON` file that you downloaded from the Securiti offline cookie scanner plugin, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Upload-file.png)
6. Review and categorize the detected cookies.
7. Deploy the cookie policy.
