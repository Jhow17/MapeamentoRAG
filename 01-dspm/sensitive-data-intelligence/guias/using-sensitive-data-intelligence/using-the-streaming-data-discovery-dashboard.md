---
title: "Using the Streaming Data Discovery dashboard"
slug: "using-the-streaming-data-discovery-dashboard"
updated: 2026-02-13T08:14:49Z
published: 2026-02-13T08:14:49Z
canonical: "helpcenter.securiti.ai/using-the-streaming-data-discovery-dashboard"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Using the Streaming Data Discovery dashboard

The streaming data refers to a continuous flow of data that is generated and processed in real-time. This real-time aspect is crucial in scenarios where timely insights or actions are required. The Streaming Data Discovery dashboard gives you a detailed overview of your data assets and their categories.

### Prerequisites

In this dashboard, you can view the scan results and stats for complete discovery scans for streaming data systems.

### Summary of Streaming Data Discovery dashboard

The summary of important elements Securiti identifies after completing the discovery scan jobs:

- Counts for streaming topics, data element categories, and data element types distributed over different locations and data systems
- Counts for steaming partitions, brokers, consumers, schemas, and content profiles
- Sankey chart for the distribution of documents classified on the basis of:
  - Streaming topics and data element categories distributed across multi-cloud environments on global sites
  - Data systems distributed across different global locations
- Counts for each tabular view of fields, topics, and schemas
- Geographical view of streaming data centers located on various global sites, with the count for different stats
- Various widgets showing the counts for fields, topics, and schemas distributed over different global locations

### Using the Streaming Data Discovery dashboard

In Securiti open **Sensitive Data Intelligence,** then choose **Data Explorers > Streaming Data Discovery**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/StreamingDataDiscoverymenu.png)

This opens the Data Risk Explorer as shown below:

The tiles at the top of the page give you a numerical snapshot of your personal data metrics. The data is broken down into:

- Locations
- Data Systems
- Owners
- Topics
- Data Element Categories
- Data Element Types
- Partitions
- Brokers
- Consumers
- Schemas
- Masked Fields

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/streamingDDTopTiles.png)

The default view shows only the top row; click **Expand More** below the widgets to show the second row.

For larger counts for data elements, Securiti there is a count on each dashboard according to the standard units (SI) as below:

- Symbols for thousand, million, billion, and trillion are in lowercase (m, b, t), respectively.
- Symbols for greater numbers peta, exa, and zetta are in UPPERCASE (P, E, Z) respectively.

Below are the three tabs that show your data in tabular form in terms of fields, topics, and schemas.

![streaming_tabular_view.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ba8a5558-d2df-05ab-5b6c-286afe37fb35.png)

The **Fields** tab shows you a list of fields and their details.

| Column | Description |
| --- | --- |
| Data Element Type | The category of data element |
| Field Name | The field name detected in the data for scanning and classification |
| Confidence % | The predicted accuracy level of classification |
| Topic | The topic involved in the scan and classification |
| Data system | The data system and its instance are configured while creating the discovery scan |
| Masked | Whether masking is applied on the data or not, Y = Yes, N = No. |
| Owner | The account used to create the discovery scan. |
| Org Name | Shows the organization(s) you have selected. |

The **Topics** tab shows you a list of topics and their details.

| Column | Description |
| --- | --- |
| Topic Name | The topic scanned for classification |
| Schema | The number of schemas against the scanned topic |
| Data System | The data system and its instance are configured while creating the discovery scan |
| Message Rate | The message rate calculated during the scan |
| Last Scanned | The date and time of the last scan |
| Partitions | The number of partitions made for the consumers |
| Consumers | The number of consumers (both active and inactive) |
| Org Name | Shows the organization(s) you have selected. |

![Topic_Tab.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c70a3d44-b669-699e-07d1-f0ea79c48c54.png)

You can click on a topic to expand it to view the consumers and schemas in that topic. You can also use the search box for the consumer names by clicking **+ more**.

![Topic_Tab.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c70a3d44-b669-699e-07d1-f0ea79c48c54.png)

The **Schemas** tab shows you a list of schemas and their details.

| Column | Description |
| --- | --- |
| Schemas Namespace | The name of the schema |
| Topics with Classifications | The number of topics involved in classification for that schema |
| Value Type | The type of data in the schema |
| Data System | The data system and its instance configured while creating the discovery scan |
| Registry | Schema registry server URL |
| Org Name | Shows the organization(s) you have selected. |

![Schemas_Tab.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6feb8d9b-e301-dd66-c9ea-9feb9a83720d.png)

The **Distribution by Data Locations** shows you a visual overview of data by countries and different regions. It shows you the number of messages, topics, and data systems in each region. You can use the filter to display the required data.

![Map_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c5ee05c0-3592-446c-622c-78e6b59c6bfc.png)

The **Distribution by Data Element Type** shows you a list of data element types and information against each one in tabular form.

![Distribution_Data_Element_Type.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-24e9193b-0771-b7d0-ee0f-fd6af470d963.png)

The **Distribution by Data Systems** shows you a list of data systems and information against each one in tabular form.

![Distribution_Data_Systems.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f7fa4549-b27e-afc4-284d-e587dc7a2d3e.png)

> [!NOTE]
> **Note**
> 
> - Your dashboard might appear blank or sparsely populated until you configure your data system connectors and data classification settings.
> - For the Kafka streaming data system:
>   - If your processing rate comes out to be zero after the scan, it might be due to no offset change. If you observe this, you can keep the message flow continuous during the scan or feed the messages in burst mode instead of pushing them all together.
>   - The scan stops automatically under the following conditions:
>     - The scan runs for a few minutes if the detected messages are not enough for classification or are less than 21k.
>     - The scan stops in less than 10 minutes if the detected messages are > 21k.

As with all Securiti dashboards, you can also use the Filter panel to filter the view and home in on specific data. See [Filtering pages and dashboards](https://helpcenter.securiti.ai/v1/docs/filtering-securiti-pages-and-dashboards) for more information.

> [!NOTE]
> **Note**
> 
> You can resize the width of columns under each widget of your Streaming Data Discovery dashboard. Move the cursor to the edge of the column, then click and hold the left mouse button. Further, drag the cursor to the left or right to adjust the width of the column and release the mouse button.

#### Exporting Streaming Data Discovery dashboard to PDF

You can export the entire content of the Streaming Data Discovery dashboard to a PDF file. If you want to limit the content of the export or are interested in exporting a specific part of the dashboard, use the filter panel.

- To export the dashboard data to a PDF file, click **Export PDF** from the top right side of the dashboard. Securiti exports everything that you include from the filter panel. Securiti sends you an email when the PDF is available to download.

#### Exporting Fields, Topics, and Schemas to a CSV file

This section describes how to export the list of Fields, Topics, and Schemas tabs to a CSV file. To do so:

1. Select the topic(s) from the left side of the list and click **Export CSV**. To export the entire list of Fields or Schemas tab, click **Export CSV**.

Securiti exports everything that you include from the filter panel.

![streaming_csv.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-81a435a7-2100-ed80-6ad5-aa97381c9ce1.png)
2. To limit the export content, use the filter panel. Securiti sends you an email when the CSV is available to download. This file might be in .Zip or .GZ format.

You can choose the relevant option according to your environment from **System Settings** > **Organizational** > **General**.

![compressedFormats.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a0f79009-5c75-47e9-0edf-f6be33446cf4.png)

#### Registering data system names to lowercase URNs in the data catalog

You can register the data systems, datasets, tables, and columns in lowercase Uniform Resource Names (URNs) in the data catalog. To do so:

1. In **Sensitive Data Intelligence**, choose **Data Explorers** > **Streaming Data Discovery**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/StreamingDataDiscoverymenu.png)
2. Scroll down to the tabular view of streaming data and select the **Topics** tab.
3. Select the desired topic from the list.
4. Mark **Add or Update all selections** option to add a new topic or update all topic selections, or mark **Add sections if not present** to add a new topic.
5. Mark the **Add Dataset in lower case** checkbox to convert the streaming dataset names to the data catalog in lowercase Uniform Resource Names (URNs).

> [!WARNING]
> **Important**
> 
> Make sure to keep the following points in mind while registering the data systems, datasets, tables, and columns to the data catalog in lowercase URNs:
> 
> - If you want to avoid discovering duplicate URNs in the data catalog, always remember the **Add Dataset in lower case** checkbox option used in the **Responses** area of discovery scan jobs. In case you enabled it in the discovery scan, enable this option from the structured or streaming data discovery dashboard as well.
> - If you have not enabled the **Add Dataset in lower case** checkbox option from the discovery scan job, you don't need to enable it from the structured or streaming data discovery dashboard as well.
> - To avoid discovering duplicate URNs, you must recall the option used in the older discovery scan job for this particular dataset. In case you do not remember that, follow the steps below:
>   1. Grab the data system name from the streaming or structured dashboard.
>   2. Go to the data systems, search for that data system, and open its instance.
>   3. Click the corresponding discovery scan job to open it, check the option from the **Responses** area, and note this option to enable it from the structured or streaming data discovery dashboard.
> - To avoid any mistakes, before running the discovery scan job, you can always enable or disable the **Add Dataset in lower case** option in the discovery scan, depending on your requirements. If you mistakenly enable or disable it in the discovery scan, you can always enable or disable it only if the job was never run.
> - If you enable the **Add Dataset in lower case** option, run the discovery scan job, and later decide to disable it, you must delete the first job and create a new job. The same is true vice versa.
6. (Optional) In the **Responses** area, to extract your schema in CSV or JSON format and register it to the Enterprise Data Catalog, mark the **Extract and register schema** checkbox.

## Related

- [Viewing scan results](/viewing-discovery-scan-results.md)
