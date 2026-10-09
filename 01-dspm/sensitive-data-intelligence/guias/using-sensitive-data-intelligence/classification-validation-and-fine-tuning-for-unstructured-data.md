---
title: "Classification validation and fine tuning for unstructured data"
slug: "classification-validation-and-fine-tuning-for-unstructured-data"
updated: 2026-09-29T11:22:46Z
published: 2026-09-29T11:22:46Z
canonical: "helpcenter.securiti.ai/classification-validation-and-fine-tuning-for-unstructured-data"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Classification validation and fine tuning for unstructured data

This section covers how to review and fine-tune classification results for unstructured data scans.

## Reviewing classification results

You can review classification results across **Unstructured Data Scans**, **File Cluster Analysis**, and **Scan Definitions** page.

### Unstructured Data Scans

To validate results from the **Unstructured Data Scans** dashboard, follow the steps below.

1. Select the scan from the **Scan** dropdown at the top, as shown below.
2. Use the filters on the top left of the dashboard to find relevant results, as shown below. The top row of widgets shows scanned files and volume, along with the count of detected data elements.

![Data scan interface showing properties and data system type selection options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/scanandapplyfilters_unstructureddatascans.png)

For example, to view results for Amazon S3, set **Data System Type** to **Amazon S3** and click **Apply**. This shows scan results, scanned documents, and detected data elements.
3. Scroll to the **Files** grid and expand an entry to see its detected data elements and content profiles. Click **View Evidence** to see the evidence Securiti collected for that scan job.

![Document showing data system details and discovery scans for consent procedures.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/viewevidence_unstructureddatascans.png)

> [!NOTE]
> Note
> 
> Evidence files are only available if you've configured Private Cloud Storage (PCS) and enabled **Collect Evidence** under Sensitive Data for the scan. If the PCS is not configured, the classification evidence is saved within your own SaaS cloud environment.
4. On the **Evidence Viewer** popup, click the evidence file link (copy the URL into your browser) to review the file from your PCS location.

![Evidence viewer displaying data elements and download option for medical consent document.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/downloadevidencefilelink_unstructureddatascans.png)

### File Cluster Analysis

To validate results from the **File Cluster Analysis** dashboard, follow the steps below.

> [!NOTE]
> Note
> 
> You can only view this dashboard if you enabled **Enable Similar Document Cluster Analysis** under **Advanced Settings** while configuring the discovery scan.

Navigate to the File Cluster Analysis dashboard. This page shows total clusters, duplicate documents, and data systems.

**Example**

1. Set **Contains Duplicates** to **True** and click **Apply**. Narrow further with **Data System Type**, as shown below. You can also click the cluster distribution box to filter by document count and resource size.

![Analysis of file clusters showing duplicates and data system types in a dashboard.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/applyfilters_fileclusteranalysis.png)
2. Scroll to **Cluster List** to see active clusters.
3. Click **Options** (three dots) on a cluster, then **View Files** to see its duplicates, as shown below.

![Overview of data clusters with highlighted option to view files and cluster details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/viewfilesoption_fileclusteranalysis(1).png)

### Scan Definitions

To validate results from the **Scan Definitions** dashboard, follow the steps below.

1. Under the **Scan Definitions** section, see details of your classification and discovery scan results, including evidence files. To review the classification evidence, log in to your data system's PCS to verify and compare the classification outcome with the source. For more information, see [Discovery Scans](/latest/docs/discovery-scans).
2. After you review the classification outcome from your data system console or cloud account, if you find any discrepancies in the identified data elements or content profiles, you can update or customize changes as described in [Fine-tuning classification and discovery scans](/latest/docs/classification-validation-and-fine-tuning-for-unstructured-data#finetuning-the-discovery-scan).
3. Rescan your data after making the above changes.

## Fine-tuning the discovery scan

If review shows the scan needs adjustment, go back to its configuration and review **Data System Scope and Scan Conditions**, **Advanced Settings**, and **Sensitive Data**.

### Data system scope and scan conditions

To review and update the data system scope and scan conditions, follow the steps below:

1. Open your discovery scan.
2. Confirm you've selected the correct data system instance.
3. Review the **Data System Scope** to confirm the files, documents, sites, libraries, folders, and other object categories you've chosen are correct, as shown below.

![Data system selection interface for SharePoint site collection and library management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/datasystemscope_unstructureddata.png)

> [!NOTE]
> Note
> 
> Scope options vary by data system. For example, Microsoft 365 SharePoint Online lets you choose sites, libraries, and folder paths.
4. Review the **Scan Conditions** to confirm the file or document types, extensions, sizes, files, and folder paths are correctly selected or unselected. For example, you might want to scan only Microsoft Word documents and exclude Microsoft PowerPoint documents.

> [!NOTE]
> Note
> 
> We recommend that you choose scan conditions carefully to avoid extra scanning time; specify only the conditions you need.

### Advanced settings

To review and update the advanced settings, follow the steps below:

1. Enable **Incremental Scan** to resume the scan from where it last completed, including any newly added documents, files, sites, libraries, or objects in the current scope. For more information, see [Discovery scans for unstructured connectors](/latest/docs/discovery-scans-for-unstructured-connectors).
2. Review the sampling settings if your discovery scans are taking longer than expected, and adjust to a smaller sample size for your unstructured data.
3. Enable or disable **Document metadata scan** as needed.

![Advanced settings for incremental scan and data collection options in a software interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/advancedsettings_firstsetofoptions_unstructureddatasystems.png)
4. If you enabled DSR automation for data element indexing but didn't need it, disable it now.
5. If your documents contain images or screenshots that need OCR, enable that option and use the optimized aspect ratio setting.
6. Enable or disable **Breach Impact Analysis** as needed. You need a separate scan for breach analysis on the same data system instance if you've enabled DSR automation for data element indexing.
7. Enable **Enable Similar Document Cluster Analysis** to let Securiti generate duplicate document clusters, viewable on the File Cluster Analysis dashboard.

![Settings for file text extraction and data subject requests in a software interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/advancedsettings_fileextractionoptions_unstructureddatasystems.png)

### Sensitive data

To review and update the sensitive data settings, follow the steps below:

1. Review the data elements, document categories, content profiles, and exact data profiles selected.
2. Add or remove any as needed, including custom-created ones, as shown below.

![Form for specifying sensitive data categories and document types in a user interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/sensitivedata_unstructureddatasystem.png)

> [!NOTE]
> Note
> 
> If a resource wasn't activated, open its configuration page and select it for this scan.
3. Rescan your data after making changes.

For more information, see [Fine-tuning classification resources](/latest/docs/fine-tuning-classification-resources).
