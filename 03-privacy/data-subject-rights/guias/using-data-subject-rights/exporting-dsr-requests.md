---
title: "Exporting DSR requests"
slug: "exporting-dsr-requests"
updated: 2025-10-31T14:19:00Z
published: 2025-11-03T06:20:26Z
canonical: "helpcenter.securiti.ai/exporting-dsr-requests"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Exporting DSR requests

You can export multiple DSR requests to files. Securiti compiles the requested DSRs into a password-protected zip file containing a CSV file and emails you a link to the file so you can download it. The email includes the password for the zip file. Download the file within seven days; the link expires after that. You can narrow down the specific DSR requests for export by applying different filters.

> [!NOTE]
> **Note**
> 
> The following roles in your Securiti tenant can export DSR requests:
> 
> - Super Admin
> - Organization Admin
> - Operator
> - Module Owner
> - DPO

1. In the Data Subject Rights module, choose **Data Subject Rights > DSR Dashboard.**
2. On the **DSR Requests** list, mark the checkbox next to the DSR requests you want to export.

A popup appears showing the number of requests you have selected. To export all DSR requests present in the selected organization, mark **Select all [total number of DSRs]** **DSR Requests** checkbox and click **Export**.

![export_selective_DSR_requests.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-73bb0c4d-1c4b-05ec-3827-2330274c0a59.png)
3. Use the tools on the next popup to customize the export as shown below, then click **Export**.

![export_popup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-893eb673-5208-b87e-5402-a7eca6e570fc.png)

This sends you an email containing the link to the DSR requests report and the password to access that report. Clicking the Download File link in the email downloads the file on your device. The email includes the 32-character password to access the file.

> [!NOTE]
> **Note**
> 
> If you are a Windows user, you must use third-party tools like 7-Zip, WinRAR, and WinZip to access the exported DSR requests. If encryption is disabled, you can freely download the exported CSV file without the need for a passkey. For more information on encryption standards, see [Configuring DSR encryption standards](/v1/docs/configuring-dsr-encryption-standards)

The DSR Dashboard page displays 25 DSR requests with pagination set at 25 requests per page. To export all DSR requests on the particular page; on the DSR Requests list, mark the checkbox next to the DSR ID column header and repeat the same process. You can also clear the selected DSR requests by clicking **Clear Selection** on the popup.

![Export_from_page.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-372553d9-5a5c-4e80-213e-d94fa3a8e769.png)

Similarly, to export DSR requests from multiple pages, scroll down to the bottom of the page and click the navigation arrow. Again mark the checkbox next to the DSR ID column header to select all DSR requests on the particular page and click **Export** on the popup.

Further, to export specific requests, narrow them down using DSR filters and repeat the same process.

![filter_export.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-60d969de-d24d-4514-ca71-560f3ead8108.png)

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>
