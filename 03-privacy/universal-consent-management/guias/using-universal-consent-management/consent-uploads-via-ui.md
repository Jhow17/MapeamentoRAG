---
title: "Consent uploads via UI"
slug: "consent-uploads-via-ui"
updated: 2026-09-21T07:37:47Z
published: 2026-09-21T21:00:01Z
canonical: "helpcenter.securiti.ai/consent-uploads-via-ui"
area: privacy
modulo: universal-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Consent uploads via UI

**Scenario**

As a Data Privacy Officer, you often receive large files of historical consent records from legacy systems during platform migrations. Importing these records into a new system while preserving consent history can be difficult and time-consuming. Without an efficient process, important consent details may be lost or inconsistently recorded.

With Securiti’s Consent Uploads, you can upload a CSV or JSON file containing thousands of consent records in a single step. For instance, during a migration from a legacy CRM, you upload a file with 50,000 historical consent entries at once instead of processing them individually. This speeds up migration, preserves historical consent records, and helps maintain a complete audit trail.

Securiti lets you import your consent records in bulk directly from the UI. This functionality is also available via API. You can now upload your consent records via the CSV or JSON file of up to maximum a 5 MB. To upload your consents in bulk:

1. In Securiti, open **Universal Consent Management** and choose **Universal Consent > Consent Bulk Imports**.
2. Near the upper right corner of the page, click **+ Import Consents** as shown below.

![Creating-Import-Consents.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5661c07e-1f62-cf73-709c-78479b6633a9.png)
3. On the **Import Consents** popup, click either **.JSON** or **.CSV** to download the corresponding file template, as shown below. Open the downloaded template and populate it with your consent records appropriately.

![Import-Consents-Download-Templates.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-74252443-34d3-550d-952a-fa40f4c1da46.png)

> [!WARNING]
> **Important**
> 
> - When populating the downloaded CSV template, you must add either consent purpose ID or consent purpose name. Similarly, you must add either processing purpose ID or processing name. Adding both is not required.
> - CSV template also supports **uuids** column where you can add multiple UUID values as a JSON string such as `{"client_id": "g-0009364", "email_address": "abcd@example.com"}`.
> - When populating the downloaded CSV template, you must add either **uuid** or **uuids** column because only one is required. Securiti ignores the value of uuid when you provide values for both columns because **uuids** take precedence over **uuid**.
> - Securiti returns an error if a `custom_parameters` value exceeds **10 KB** when you upload consent records using **JSON** or **CSV** files or the **Universal Consent APIs**.
> 
> ![Consent upload dashboard showing processed and errored records with relevant job IDs.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ucm_custom_parameters(3).png)
4. Enter the description for your consent records in the **Description** field and upload your JSON or CSV file by either dragging and dropping or by selecting the file from your local machine as shown below.

![Import-Consents-Description.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-50864e84-7741-ddea-0683-ad71ee4433de.png)
5. Near the bottom of the popup, click **Import** to bulk import your consent records in the system.
6. Securiti validates the syntax and semantics of your uploaded files and displays an error message on the console if the type of data you entered in the JSON/CSV file is incorrect or missing as shown below.

![Import-Consents-Error.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-63bb6319-2f97-4618-b4e6-807b788a92f4.png)

> [!WARNING]
> Important
> 
> For bulk uploads via **JSON** or **CSV** files, Securiti does not derive the `WITHDRAWN` consent status based on the data subject’s existing consent status. For instance, if the existing status is `GRANTED` and the **JSON** or **CSV** file specifies `DECLINED`, Securiti updates the status to `DECLINED`, not `WITHDRAWN`.

You can check the status of any of your uploaded consents by clicking the **Metadata Explorer** icon. In case of consent records failure, Securiti shows you the metrics of successfully uploaded and failed consent records, as shown below.

![Metadata-Explorer.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a56acbe3-192c-812e-7918-2b9351381cc9.png)

You can also download the consent records with errors by clicking the **Options** (three dots) and then **Download Error Report**. Based on the uploaded data format, it downloads a JSON or CSV file containing only the records with errors, as shown below.

![Download-Consent-Error-Report.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-93d4b92d-44bf-173b-7e48-efbcd8ffb4a5.png)

> [!NOTE]
> **Note**
> 
> If the data is processed without any errors, the error report option appears disabled in the menu.

You can also delete any uploaded consent job through the **Options** (three dots) button at the far right side of any record, and then by clicking the **Yes, Delete** confirmation popup, as shown below.

![Delete-Consent-Uploads.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-07395ba5-f505-8fe3-384f-21aceb491c26.png)

> [!NOTE]
> **Note**
> 
> - You can only delete import jobs with **Processed** status. Securiti only deletes the consent jobs and not the actual consent records from the system currently.
> - Securiti automatically deletes the succeeded or failed consent import jobs after 30 days, and staled jobs after 60 days from its database.

## Consent validation rules for CSV uploads

When you upload a CSV file containing the consent records, Securiti validates that `granted` and `consent_status` are aligned before processing any records.

> [!NOTE]
> Note
> 
> The `consent_status` field is optional for more granular consent status. Securiti processes the CSV file even when the `consent_status` field is empty.

If `granted = TRUE`, Securiti expects a `GRANTED` state, so it accepts `GRANTED` or an empty value which defaults to `GRANTED`. If it receives `DECLINED`, `WITHDRAWN`, `PENDING`, or any unsupported value, it treats this as a mismatch.

Use the following table to understand the validation rule when `granted = TRUE`.

| `granted` | `consent_status` | Derived Consent |
| --- | --- | --- |
| `TRUE` | `GRANTED` | `GRANTED` |
| `TRUE` | `DECLINED` | - |
| `TRUE` | `WITHDRAWN` | - |
| `TRUE` | `PENDING` | - |
| `TRUE` | Empty | `GRANTED` |
| `TRUE` | Unsupported value | - |

Similarly when `granted = FALSE`, Securiti expects a non granted state, so it accepts `DECLINED`, `WITHDRAWN`, or `PENDING` and defaults an empty value to `DECLINED`. However, if it receives `GRANTED` or an unsupported value, it marks this as inconsistent.

Use the following table to understand the validation rule when `granted = FALSE`.

| `granted` | `consent_status` | Derived Consent |
| --- | --- | --- |
| `FALSE` | `GRANTED` | - |
| `FALSE` | `DECLINED` | `DECLINED` |
| `FALSE` | `WITHDRAWN` | `WITHDRAWN` |
| `FALSE` | `PENDING` | `PENDING` |
| `FALSE` | Empty | `DECLINED` |
| `FALSE` | Unsupported value | `NO CONSENT` |

> [!NOTE]
> Note
> 
> If `granted` and `consent_status` do not align, Securiti does not process the affected records and raises a misalignment of values error to ensure only valid and consistent consent data is ingested, as shown below.
> 
> ![Dashboard displaying consent uploads with job statuses and error notifications for processing.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/csv_upload_error.png)

## Filtering consent uploads

You can also use the top-level filter to narrow down specific consent upload jobs. In the upper-left corner of the Consent Uploads page, click the **+** to open the top-level filter, as shown below.

![Filter-Consent-Uploads.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b87e1f4c-599d-7583-6b17-d60e1760ba5b.png)

You can filter consent uploads based on the following properties:

| Property | Description |
| --- | --- |
| Job ID | Lets you filter consent uploads that contain a specific keyword in the Job ID. |
| Date Created | Lets you filter consent uploads based on their creation date. |

Select your filtering criteria, then click **Apply** to filter the results.

![Apply-Top-Level-Filter.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4ba0f229-e9c5-8bdc-d25e-7c0be43f541c.png)

You can clear a specific filter by clicking the **Options** (three dots) menu next to it, or clear all filters at once by clicking the **Clear Search** button, as shown below.

![Clear-Filters.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-02de75cf-6918-ff00-c804-819b4a40c85c.png)

Universally Unique Identifier (UUID) is an alphanumeric string that is used to identify information in computer systems. For instance, they are often used to identify rows of data within a database table, with each row assigned a specific UUID.

## Related

- [Collecting form consent](/collecting-form-consent.md)
- [Building a universal preference center](/building-a-universal-preference-center.md)
