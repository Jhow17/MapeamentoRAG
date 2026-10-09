---
title: "Classification validation and fine tuning for structured data"
slug: "classification-validation-and-fine-tuning-for-structured-data-1"
updated: 2026-09-29T10:06:34Z
published: 2026-09-29T11:23:43Z
canonical: "helpcenter.securiti.ai/classification-validation-and-fine-tuning-for-structured-data-1"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Classification validation and fine tuning for structured data

This section covers how to review and fine-tune classification results for structured data scans.

## Reviewing classification results

You can review classification results for structured data from **Structured Data Discovery** and **Scan Definition** pages.

### Structured Data Discovery

To validate results from the **Structured Data Discovery** dashboard, follow the steps below.

1. Navigate to the **Structured Data Discovery** dashboard. The left panel shows key entities, such as data elements identified, columns, tables, databases, and data systems along with their counts, as shown below.

![Overview of structured data discovery with database and column statistics displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/entitiesonstructureddatadiscovery_sdd.png)
2. Apply filters to view details for a specific structured data system, as shown below.

![Interface for structured data discovery with filter options and data elements listed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/applyfilters_structureddatadiscovery.png)
3. To review classification for a specific column, table, schema, or database, select it and choose **Review Classification** from the popup.

![Overview of structured data discovery with database and content profile statistics displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/reviewclassification_structureddatadiscovery(1).png)

> [!NOTE]
> Note
> 
> Using the default tenant configuration gives the most accurate classification (matching percentage). You can still compare the outcome against your original data if needed.
4. If the result isn't what you expected, edit the data element and choose the correct one from the **Data Element Type** column. For example, correcting a detection to the **Phone Number**.

![Selecting phone number options in a database management interface for data systems.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/correctingclassification_reviewclassification.png)
5. To validate the underlying sample data, click **View Sample Data**.

> [!WARNING]
> Important
> 
> You need the correct access permissions to view sample data, or you must be the discovery scan owner.

![Database column details showing business phone and associated data types.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/viewtablesampledata_reviewclassification.png)

> [!NOTE]
> Note
> 
> If you've configured Private Cloud Storage (PCS), the sample is stored there. Compare it against the expected result, then fine-tune the data elements to match exactly.

This opens the **Table Sample Data** page, as shown below.

![Sample data table displaying business information including phone numbers and addresses.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/tablesampledataview_reviewclassification.png)

### Scan Definitions

To validate results from the **Scan Definitions** dashboard, follow the steps below.

1. Under the **Scan Definitions** section, see details of your classification and discovery scan results, including evidence files. To review the classification evidence, log in to your data system's PCS to verify and compare the classification outcome with the source. For more information, see [Discovery Scans](/latest/docs/discovery-scans).
2. After you review the classification outcome from your data system console or cloud account, if you find any discrepancies in the identified data elements or content profiles, you can update or customize changes as described in [Fine-tuning classification and discovery scans](/latest/docs/classification-validation-and-fine-tuning-for-structured-data-1#finetuning-the-discovery-scan1).
3. Rescan your data after making the above changes.

## Fine-tuning the discovery scan

If review shows the scan needs adjustment, go back to its configuration and review **Data System Scope**, **Advanced Settings**, and **Sensitive Data**.

> [!WARNING]
> Important
> 
> Scan cannot be edited in **Scheduled**, **Running**, **Paused**, and **Pause** **Scheduled** state.

### Data system scope

To review and update the data system scope, follow the steps below:

1. Go to your discovery scan.
2. Confirm you've selected the correct data system instance.
3. Review the **Data System Scope** to confirm the databases, schemas, tables, and views are correct. If you don't have any to select, upload a CSV file of rows and columns instead.

![MongoDB data system selection interface with options for databases and regex patterns.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/datasystemscopeoptions_discoveryscan.png)

### Advanced settings

To review and update the advanced settings, follow the steps below:

1. Confirm the sample size is appropriate. For more information, see [Discovery scans for structured connectors](/latest/docs/creating-a-discovery-scan-for-structured-connectors).
2. To skip values such as `Unknown`, `NA`, `Null`, or `Not Available`, enable **Skip empty fields and fields below**.
3. Enable **Store Sample Data** to save your classification sample for later comparison.
4. If your scan needs to mask database columns and sync data system roles, enable both options.
5. If your data system has new tables, you haven't scanned yet, enable the option to **Include newly discovered tables and schemas into the scan scope**, as shown below.

![Advanced settings for data classification, including options for sampling and scanning data.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/advancedsettings_firstsetofoptions.png)
6. If your database columns contain only string data, enable the **Full Scan** option, if you haven't already.
7. Enable the options to include previously scanned columns/tables and retain manual classification results, if you want those preserved between scans, as shown below.

![Settings for data classification preferences and exact data matching options in a software interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/advancedsettings_secondsetofoptions.png)
8. If you have existing exact data profiles, enable the option to associate them with this scan, up to 100,000,000 rows deep.

### Sensitive data

To review and update the sensitive data settings, follow the steps below:

1. Review the data elements, content profiles, and exact data profiles selected, as shown below.

![List of selected localities and data element categories for sensitive data discovery.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/sensitivedataoptionsvalidation_discoveryscans.png)
2. Add or remove any as needed, including custom-created ones.

> [!NOTE]
> Note
> 
> If a resource wasn't activated, go to its configuration page and select it for this scan.
3. Rescan your data after making changes.

For more information, see [Fine-tuning classification resources](/latest/docs/fine-tuning-classification-resources).
