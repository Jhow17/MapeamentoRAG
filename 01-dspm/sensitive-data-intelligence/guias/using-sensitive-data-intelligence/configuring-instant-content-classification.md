---
title: "Configuring instant content classification"
slug: "configuring-instant-content-classification"
updated: 2026-04-27T10:40:52Z
published: 2026-04-27T21:00:23Z
canonical: "helpcenter.securiti.ai/configuring-instant-content-classification"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Configuring instant content classification

Instant content classification lets you quickly test the accuracy of classification results before running an exhaustive scan. You can use documents for quick classification to check the accuracy of the classification before you plan to run larger scans. You can specify data elements, content profiles, and file types to initiate the scan and view results in the **Classification** **Results** tab.

> [!NOTE]
> **Note**
> 
> - Instant classification functions similarly to a normal discovery scan, identifying sensitive information and then returning the results once the classification is complete.
> - You can upload document files up to 50 MB. You must have the following roles to access the instant classification feature:
>   - Super Admin
>   - Organization Admin
>   - Operator

### OCR Images Scanning in Instant Classification

If you have images to scan from files in instant classification, the same settings are applied as described in discovery scans.

For discovery scans, the default settings typically scan only very high-resolution images on the first page of a PDF. To improve OCR processing, see [Discovery scans for unstructured data systems](/v1/docs/discovery-scans).

If you run a new classification scan job, it overwrites the old scan results.

### Using the instant classification

To use the instant classification:

1. In the **Sensitive Data Intelligence**, choose **Discovery Scans > Instant Classify**.

![Securiti dashboard showing Sensitive Data Intelligence and Instant Classify options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-20 at 6.32.58 PM(1).png)
2. From the **Organization** menu, choose an organization for which you want to configure the instant classification.

![User interface showing file upload and organization selection in data classification settings.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-20 at 6.45.09 PM.png)
3. Use the tools on the page to upload the file that you want to use for instant classification, and click **Next - Define Scope**. ![User interface showing file upload success and next steps in data classification process.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-20 at 6.34.25 PM(1).png)
4. On the **Data Scope** tab, choose the desired data element categories, file categories, and content profiles.

> [!NOTE]
> Note
> 
> You must have activated a pod to perform the scanning.

![User interface for data classification with highlighted 'Define Scope' section.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-20 at 6.38.55 PM.png)
5. Turn on the **Generate Scan Results** toggle to enable generating scan results.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-CZSB6286.png)
6. Click the **Classification** **Results** tab to view the data elements that Securiti discovered.

![Instant Classify interface showing classification results for a financial document upload.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-20 at 6.41.16 PM.png)

### Canceling the classification

Click **Cancel** to cancel the classification jobs that are in progress or scheduled.

![Classification results for a financial document with options to download or delete.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-20 at 6.43.00 PM.png)

### Deleting the instant classification results

Click **Delete Classification** to delete the classification jobs that are complete, failed, or canceled after you look at them.

![Instant Classify results showing file details and options for classification management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-20 at 6.43.17 PM.png)

### Downloading the instant classification results

Click **Download Scan Results** to download the scan results.

> [!NOTE]
> **Note**
> 
> You can generate and download the scan results if you have enabled private cloud storage.

## Related

- [Viewing scan results](/viewing-discovery-scan-results.md)
- [Discovery scans](/discovery-scans.md)
