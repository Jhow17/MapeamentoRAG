---
title: "Configuring instant content classification"
slug: "configuring-instant-content-classification-en"
updated: 2026-09-29T11:27:32Z
published: 2026-09-29T11:27:32Z
canonical: "helpcenter.securiti.ai/configuring-instant-content-classification-en"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Configuring instant content classification

Instant content classification lets you quickly test the accuracy of classification results before running an exhaustive scan. You can specify data elements, content profiles, and document types to initiate the scan and view results in the **Classification Results** tab.

> [!NOTE]
> **Note**
> 
> - Instant classification functions similarly to a normal discovery scan, identifying sensitive information and then returning the results once the classification is complete.
> - You can upload document files up to 50 MB. You must have the following roles to access the instant classification feature:
>   - Super Admin
>   - Organization Admin
>   - Operator

If your files in instant classification contain images to scan, Securiti applies the same settings described in discovery scans.

For discovery scans, the default settings typically scan only very high-resolution images on the first page of a PDF. To improve OCR processing, see [Discovery scans for unstructured connectors](/latest/docs/discovery-scans-for-unstructured-connectors).

If you run a new classification scan job, it overwrites the old scan results.

## Using the instant classification

To use the instant classification:

1. Open **Sensitive Data Intelligence**, and choose **Discovery Scans > Instant Classify**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(351).png)
2. From the **Organization** menu, choose an organization for which you want to configure the instant classification, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(352).png)
3. Use the tools on the page to upload a `CSV` file that you want to use for instant classification, and click **Next - Define Scope**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(353).png)
4. On the **Data Scope** tab, choose the desired data element categories, file categories, and content profiles, as shown below.

> [!NOTE]
> Note
> 
> You must have activated a pod to perform the scanning.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/sdiInstantClassifyDefineScope.png)

> [!NOTE]
> Note
> 
> When you choose a content profile, Securiti automatically selects dependent data elements and file categories.
5. Turn on the **Generate Scan Results** toggle to generate scan results, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(354).png)
6. Click the **Classification Results** tab to view the data elements that Securiti discovered, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(359).png)

## Canceling the classification

Click **Cancel** to cancel the classification jobs that are in progress or scheduled, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(356).png)

## Deleting the instant classification results

Click **Delete Classification** to delete the classification jobs that are complete, failed, or canceled, once you've reviewed them, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(355).png)

## Downloading the instant classification results

Click **Download Scan Results** to download the scan results.

> [!NOTE]
> Note
> 
> You can generate and download the scan results if you have enabled private cloud storage.

## Related

- [Discovery scans](/discovery-scans.md)
