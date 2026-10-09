---
title: "Registering metadata into the Enterprise Data Catalog"
slug: "registering-metadata-into-the-enterprise-data-catalog"
updated: 2026-09-08T16:38:16Z
published: 2026-09-08T21:00:16Z
canonical: "helpcenter.securiti.ai/registering-metadata-into-the-enterprise-data-catalog"
area: governance
modulo: enterprise-data-catalo
tipo: guia
data_captura: 2026-10-08
---

# Registering metadata into the Enterprise Data Catalog

You can register your data into the Enterprise Data Catalog and associate the relevant tags and glossary terms with the dataset.

> [!NOTE]
> **Important**
> 
> - If you ingest metadata from the same sources using different methods (For example, automatic registration and EDC ingestion), ensure that the URNs match by configuring parameters such as environment and platform instance in the ingestion recipe. Maintaining consistent URNs prevents data duplication, misclassification, and fragmentation, resulting in a more accurate and reliable data catalog.
> - Any updates to the content profiles or data element type attributes will automatically be reflected in the EDC.
> - Discovery scans take precedence over dataset import and EDC Ingestion. Re-running a discovery scan resets a dataset's metadata to what the scan detects, removing anything added through dataset import or EDC Ingestion.
> 
> For example, a discovery scan registers a dataset with two lineage relationships. You add one through dataset import and one through EDC Ingestion, giving the dataset four. Re-running the discovery scan leaves only the original two.
> 
> After re-running a discovery scan, re-run the dataset import and EDC Ingestion in their original order to restore the overwritten metadata.

To get started, use one of the following methods.

### Automatic registration

**Scenario**

As a data steward, you need to quickly catalog thousands of new datasets discovered in your environment. Manually adding each one isn’t practical. With EDC’s automatic registration, metadata from discovery scans flows directly into the catalog in bulk. This saves you time and ensures that your catalog stays up-to-date as new data sources emerge.

You can push the structured, unstructured (JSON and CSV file formats) and streaming datasets in bulk into the Enterprise Data Catalog. The data from the discovery scan goes directly into the data catalog.

The automatic registration process is part of the discovery scan, hence the [prerequisites](/v1/docs/trigger-nodes-discovery-scan) are the same as any discovery scan.

To register:

1. Open **Enterprise Data Catalog**, then choose **Settings > Scan Definitions**.

![automatic_registration_-_Scan_Definitions_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-14cd343e-61e4-daa4-e08a-641a25edcaf2.png)
2. Click **Create Discovery Scan** and fill in the details to suit.
3. In the responses section, enable **Register data assets into the Data Catalog** to register the data assets discovered as a part of the scan results and automatically add them to the Enterprise Data Catalog module.

![automatic_regiatration.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-946bbd1a-edf2-0ad5-37e2-35b703fac4ae.png)
4. Do one of the following:

In the case of structured data systems, you can see the following additional options to configure:

EDC refresh metadata is helpful in the following cases:

| EDC refresh metadata cases | Description |
| --- | --- |
| Dynamic metadata | Addresses cases where certain metadata (For example, host/IP) is not captured by a scan and may change over time. |
| Missed registration | Rectifies scenarios where data systems were not initially registered in the scan, and the need to register them arises later. |
| Accidental deletion | Recovers from accidental deletion of datasets in the Enterprise Data Catalog. |
  - Mark **Add and Update all selections** option to add all new tables and topics or update all tables and topics selections.
  - Mark **Add sections if not present** to add a new topic and table.
  - (Optional) Set a [default governance status](/v1/docs/governance-status-for-edc-entities) for all metadata at once.
  - Mark the **Add Dataset in lower case** checkbox to add the structured or streaming datasets to the data catalog in lowercase URNs.

> [!NOTE]
> **Note**
> 
> - If your datasets are case-insensitive and you are consuming metadata for this data system from another source (for example, using DH plugins), make sure that the URNs consumed from both sources are using the same case (upper or lower). Use the **Add Dataset in lower case** option to make sure of this. Otherwise, we recommend that you not use this option.
> - If you are ingesting datasets in case insensitive manner (without using double quotes while creating tables, schemas, columns, or databases, etc in the data system server for example snowflake), then it is recommended to mark the **Add Dataset in lower case** checkbox to ingest other DH plugin data i.e. assertions, tableau lineage.
> - If you are ingesting data in a case-sensitive manner (using double quotes while creating tables, schemas, columns, or database, etc in the data system server for example snowflake) then it is recommended not to mark the **Add Dataset in lower case** checkbox. You should not mark the **Add Dataset in lower case** checkbox when everything is in lowercase or in mixed case in the actual database server.
  - Mark the **Extract Lineage from SQL** checkbox to enable or disable the field data assets lineage to the data catalog. Enabling this option extracts the lineage from SQL objects included inside schemas or databases in scope.

> [!NOTE]
> **Note**
> 
> While configuring discovery scans, make sure you have selected the databases for which lineage needs to be viewed. By default, **All** is selected. In this case, if you mark the **Extract Lineage from the SQL** checkbox then lineage gets included from SQL objects for all the tables included in the selected database.
> 
> However, if you have selected specific databases for lineage along with specific tables in the discovery scan. In this case, if you mark the **Extract Lineage from the SQL** checkbox, this results in the ingestion of only the necessary tables essential for comprehensive lineage registration, along with the inclusion of the specifically chosen tables within the defined scope.
> 
> It is important to note that whenever you ingest lineage, a default schema is automatically created. This schema serves as a container for intermediate objects, such as view components, generated by the SQL parser.
  - Enable the **Always Execute Response** checkbox to refresh metadata in the Enterprise Data Catalog upon execution of the scan. Upon execution of the scan, all the metadata that is ingested in each scan run gets ingested into the Enterprise Data Catalog again. This feature lets you stay on top of dynamic data changes, ensuring your catalog remains accurate and reliable.

> [!NOTE]
> **Note**
> 
> The second way to refresh the metadata in the Enterprise Data Catalog is from the **Discovery Scans List** page.
> 
> - On the **Discovery Scans List** page, click **Options** (three dots) > **EDC** **Refresh** to refresh content. The EDC refresh capability is only for structured datasets.

In the case of unstructured data systems, you can see the following additional option to configure:

- Mark the **Extract and register schema** to extract your structured schema in CSV, TSV, or JSON formats to register them into the Enterprise Data Catalog.
- Mark the **Register all unstructured datasets** to extract schema for all unstructured files and register them into the Enterprise Data Catalog.

> [!NOTE]
> **Note**
> 
> If you select both checkboxes i.e. **Extract and register schema** and **Register all unstructured datasets**, the process will first register structured schemas in CSV, TSV, or JSON formats. After that, all unstructured files, including images, videos, PDFs, and text files, will be ingested into the EDC.
- From the **Set Environment** menu, select the suitable environment.

This selection lets you select environments for the objects to be registered in the EDC. With this capability, you can easily distinguish and manage metadata across various environments, such as Production or QA.

Below is a list of available environment variables, along with their descriptions to help you make the best selection:

| Value | Description |
| --- | --- |
| PROD | Designates production fabrics. |
| PROD-Hidden | Designates hidden production fabrics. Maintains original production behavior, displaying PROD metadata in the URN but hiding the environment in breadcrumbs. |
| DEV | Designates development fabrics. |
| TEST | Designates testing fabrics. |
| QA | Designates quality assurance fabrics. |
| UAT | Designates user acceptance testing fabrics. |
| EI | Designates early integration fabrics. |
| PRE | Designates pre-production fabrics. |
| STG | Designates staging fabrics. |
| NON_PROD | Designates non-production fabrics. |
| CORP | Designates corporation fabrics. |

1. (Optional) Add relevant descriptions and links. You can also associate tags, glossary terms, domains (subdomains), and owners to the dataset. Make sure that you have created relevant domains (subdomains), owners, and terms ahead of configuring a scan. By doing this, you will have assets in the Enterprise Data Catalog already assigned to the correct domain and owner.

> [!NOTE]
> **Note**
> 
> In the **Owners** menu, you can select both legacy owners and [custom ownership types](/latest/docs/edcownership).

1. Scroll to the top and on the top right corner of the page and click **Finish and Activate** button.
2. From the **Discovery Scans List** page, select the **Scan Now** option to run the discovery scan.

> [!NOTE]
> **Note**
> 
> You can view the datasets in the Enterprise Data Catalog as soon as their data classification is completed. You don't have to wait for the scan job to complete to see the results in the Enterprise Data Catalog.

> [!NOTE]
> **Note**
> 
> There are a few restrictions when creating an URN. Column names are encoded if they contain any of the following reserved characters:
> 
> - Commas "," are reserved characters in URN fields.
> - Parentheses "( , )" are reserved characters in URN fields.
> 
> **Example**: Schema Field Name **tran)saction_date** will be encoded as **tran%29saction_date**.

> [!NOTE]
> **Note**
> 
> - If you [delete a discovery scan](/v1/docs/pausing-reassigning-and-deleting-a-discovery-scan) or [purge data systems](/latest/docs/managing-data-system-connectors) selected for ingestion, EDC also removes the datasets ingested from those sources.

### Manual registration

**Scenario**

As a data steward, you’re preparing datasets for a new analytics project. Some datasets contain incomplete or sensitive information not ready for broad use. With manual registration, you carefully select only the validated and approved datasets to add to the catalog. This prevents premature exposure of unverified data and ensures analysts work with trusted, approved information.

With manual registration of data, you can select the specific datasets to add them to the data catalog. You can also add dataset details like descriptions, links, and tags.

As a prerequisite, you must have Sensitive Data Intelligence data metadata in the explorers to initiate the manual registration process.

- To register the structured datasets into the data catalog:
  1. Open **Sensitive Data Intelligence**, then choose **Structured Data Discovery** to open the structured data explorer.
  2. Click to the **Tables**, **Schemas** or **Databases** tabs under the data graph. Select the tables/schemas or databases to register data from, and click **Register with Data Catalog**. For details, read Step 4

![manual_regiatration.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2119311f-c75e-9a5f-3756-f2f314dd4dc7.png)
  3. Fill in the details to suit. Click **Save and Register with Data Catalog**.
- To register the streaming datasets into the Enterprise Data Catalog:
  1. Open **Sensitive Data Intelligence**, then choose **Streaming Data** **Discovery**.
  2. Go to the **Topic** column under the data graph. Select the topic to register data from, and click **Register with Data Catalog**.
  3. Fill in the details to suit. Click **Save and Register with Data Catalog**.

> [!NOTE]
> **Note**
> 
> There are a few restrictions when creating an URN. Column names are encoded if they contain any of the following reserved characters.
> 
> - Commas "," are reserved characters in URN fields.
> - Parentheses "( , )" are reserved characters in URN fields.
> 
> **Example**: Schema Field Name **tran)saction_date** will be encoded as **tran%29saction_date**.

### EDC ingestion

EDC ingestion lets you configure, and execute metadata ingestion using third-party connectors developed by the DataHub community using the Enterprise Data Catalog user interface. For details, refer to [EDC ingestion documentation](/v1/docs/edc-ingestion).

An Enterprise Data Catalog (EDC) is a centralized inventory and metadata management tool for an organization's data assets. It helps organizations manage and govern their data by providing a comprehensive view of data sources, data lineage, data definitions, data usage, and data quality.
