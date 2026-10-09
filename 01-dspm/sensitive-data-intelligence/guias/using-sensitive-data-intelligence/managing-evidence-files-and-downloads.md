---
title: "Accessing evidence files in Securiti"
slug: "managing-evidence-files-and-downloads"
updated: 2026-07-17T08:49:41Z
published: 2026-07-20T21:00:00Z
canonical: "helpcenter.securiti.ai/managing-evidence-files-and-downloads"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Accessing evidence files in Securiti

Evidence files help you validate data classification results after discovery scans. Securiti stores these files in the Private Cloud Storage and retrieves them securely using signed URLs.

Evidence files contain specific data points that Securiti’s AI model evaluates to identify detections. Securiti downloads evidence files and sample data using time-limited, signed URLs for enhanced security. You use evidence files to:

- Validate detected data elements
- Confirm classification accuracy
- Review scan findings

This document explains how evidence files work for structured and unstructured data, the required permissions, and tenant-level controls.

## Prerequisites for evidence file access

Before you access evidence files, ensure the following requirements are met:

### 1. Configure Private Cloud Storage (PCS)

You must configure PCS for evidence to be stored and retrieved.

If PCS is not configured, Securiti cannot generate or retrieve evidence files. For more information, see [Configuring Private Cloud Storage (PCS).](/latest/docs/system-settings-configuring-private-cloud-storage)

### 2. Assign permissions for evidence access

Access to evidence files depends on role-based permissions. To access evidence, you must have the `View Data Evidence` or `View Evidence for Owned Connectors` permissions under the SDI module.

- Super Admin, Organization Admin, Module Owner and DPO roles receive `View Evidence for Owned Connectors` permission by default.
- Super Admin, SDI Classification Reviewer and SDI Evidence Analyst roles receive the `View Data Evidence` permission by default.
- Custom roles must be explicitly assigned this permission.
- If `View Evidence for Owned Connectors` permission is enabled only, then only the data system owners can access the evidence.

Without this permission, you cannot access evidence URLs. For more information, see [Sensitive Data Intelligence roles and permissions](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-roles-and-permissions).

### 3. Enable tenant-level controls for evidence access

Evidence downloads are governed by tenant-level settings in **System Settings**. To enable the settings to access evidence files:

1. In **Settings > Organizational > General**, scroll down to the **Tenant Security** section, as shown below.

![System settings for tenant security, including contact information and session timeout settings.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/evidence_tenantsecurity.png)
2. In the **Tenant Security** section, configure the following settings, as shown below:

| Setting | Description |
| --- | --- |
| Enforce Signed Headers for Evidence Validation | Enable the toggle to generate a random value used in the signed headers of the URLs used for evidence retrieval. When enabled: - Securiti validates evidence access using signed headers. - Direct browser downloads from PCS are blocked. - Only in-application validation is permitted. If you attempt to download evidence while signed headers are enforced, Securiti displays a message indicating that download is incompatible with PCS when signed headers are enabled. To enable direct downloads, you must disable signed headers. |
| Evidence Download | Enable the toggle to access evidence files from scans when needed. You cannot download the files if disabled. |

![System settings page displaying organizational options and evidence validation settings.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/evidence_tenantsettings.png)

### 4. Enable discovery scan setting for evidence download

For unstructured data systems, in **Discovery Scan > Advanced Settings**, you must enable the **Collect Evidence** option for your scan job. This option lets Securiti generate evidence files for the scan.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-YRRGOY6V.png)

## Accessing evidence files for structured data

You can download evidence files for your structured data, using a signed URL from the **Structured Data Discovery** dashboard. To download evidence files from Structured Data Discovery (SDD):

1. In Structured Data Discovery dashboard, click **+** from the top-level filter and select **Column** entity from the menu.
2. Select **Evidence file path** property and set it to **is not empty**, as shown below. Securiti displays all columns with evidence files.

![User interface for structured data discovery with filter options and data elements displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/sdd_evidencefile_property.png)
3. In the grid, click the download icon in the **Evidence file path** column, as shown below.

![Data discovery interface showing columns, evidence paths, and classification options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/sdd_evidencefile_download.png)

Securiti downloads the evidence file in JSON format in your **Downloads** folder.

### Previewing sample data in Structured Data Discovery

To preview sample data for structured data systems:

1. In the Structured Data Discovery dashboard, from the grid view, select an entity and click **Review Classification** as shown below.

![Overview of data classification with highlighted review classification option and column details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/sdd_reviewclassification.png)
2. In the **Review Classification** popup, from the right corner for your selected row, click the **Metadata Explorer** icon to open the metadata explorer.

![Metadata explorer icon in Review classification popup](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(281)(1).png)
3. From the dialog, click **Sample Data** to preview it, as shown below.

![View sample data in SDD](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(279)(1).png)

### Previewing sample data in Validation Workbench

You can also preview sample data from Validation Workbench.

To view sample data from Validation Workbench:

1. Open the Validation Workbench session for your structured data system.
2. In the **Structured Detections** grid, from the right corner of the data element’s row, click the **Table Sample Data** icon.

![Validation workbench displaying employee IDs and structured detection review options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/4.png)
3. In the **Table Sample Data** popup, view and cross-match the sample data of the complete table to which the selected column belongs.

> [!NOTE]
> Note
> 
> Securiti downloads the table sample data file to your machine with the following file name format:
> 
> `table_name.csv`
> 
> 
> 
> This file format ensures you can identify the source table in case of multiple sample data downloads.

![Table displaying employee IDs and sample data for reference and organization purposes.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/3.png)
4. To view sample data for the selected classification, from the right corner of the data element’s row, click the **Metadata Explorer** icon.

![metadata explorer icon in VWB](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/2.png)
5. In the **Metadata Explorer** dialog box, select the **Sample Data** tab, as shown below.

![sample data preview for a data element](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/1.png)

For more information, see [Viewing sample data in Validation Workbench for structured data](/latest/docs/validation-workbench-for-structured-data#viewing-metadata-and-sample-data-of-classifications).

## Accessing evidence files for unstructured data

You can access evidence files for your unstructured data, using a signed URL from the **Unstructured Data Scans** dashboard. To access evidence files from Unstructured Data Scans (UDS):

1. In Unstructured Data Scans dashboard, from the top-level filter, click **+.**
2. Select the **Files with Evidence property** and set it to **True**, as shown below.

![User interface displaying data scan options and filters for unstructured data analysis.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uds_evidencefile_property.png)
3. Scroll down to the **Files** grid, expand a file and click **View Evidence**, as shown below.

![Overview of a document with details about file ownership and scanning information.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uds_viewevidence.png)
4. In the **Highlights** popup, preview the evidence file data such as, content profiles, path, etc., as shown below.

> [!WARNING]
> Important
> 
> **Full Evidence Path** redirection is not supported for tenants using Azure-hosted Private Cloud Storage (PCS). This is a known limitation for Azure-based storage. As a workaround, we recommend that you use the **Download** option to access the evidence file.
5. Click **Download** the evidence file to your system, as shown below. The download uses a signed, time-limited URL.

![File summary showing download option and details for DOD_ID-ALLUSA-Draft.pdf document.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uds_evidencefile_download.png)

> [!NOTE]
> Note
> 
> The number of file records in the downloaded evidence file may be fewer than the number of files displaying detections. If this occurs, contact your Customer Success Manager or Account Representative to confirm whether your tenant meets the eligibility requirements for evidence file configuration.

### Previewing evidence file data in Validation Workbench

To view the evidence in the Validation Workbench:

1. From the main navigation left menu, hover over **Sensitive Data Intelligence** and select **Data Classification > Validation Workbench**.
2. From the left **Data Type** menu, select **Unstructured**.
3. Open an existing session or create a new one.
4. In your Validation Workbench session, for your files, click the **Metadata Explorer** icon to open the Metadata explorer.
5. Select the **Evidence** tab in the dialog and preview the evidence file data, as shown below.

![Review of unstructured data sources with highlighted loan application details and borrower information.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/viewevidence_vwb.png)

## Evidence file access using signed URLs

Securiti provides direct access to evidence stored in PCS via signed URLs for both structured and unstructured data. When you access an evidence file, Securiti generates a pre-signed URL which is scoped to a specific object in your PCS bucket. The evidence files are fetched directly from PCS, improving security.

The pre-signed URLs are time-limited and valid for 5 minutes for security purposes.

## Audit logging for evidence downloads

Pre-signed URLs generated for evidence file downloads are logged in the audit logs. The logs include the following parameters:

- Requesting user name
- Timestamp
- Action performed

This ensures traceability of all evidence access, as shown below.

![Audit logs showing user activities, including file downloads and session logins.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/evidencedownload_auditlog.png)

##
