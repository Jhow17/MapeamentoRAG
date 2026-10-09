---
title: "Pipeline Status"
slug: "pipeline-status"
updated: 2025-12-09T09:18:36Z
published: 2025-12-09T09:18:36Z
canonical: "helpcenter.securiti.ai/pipeline-status"
area: gencore-ai
modulo: gencore-ai
tipo: guia
data_captura: 2026-10-08
---

# Pipeline Status

When you run your pipeline, you can view the status of the files that are ingested into the pipeline.

![Overview of files ingested with their statuses and details in a data management system.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/pipeline status for IE.png)

- You can search for the files through the **Search** box.
- You can filter the files as follows:

| Filter | Description |
| --- | --- |
| Name | Enter the keywords or phrases to narrow down specific files. |
| File formats | Search for and select the types of files. |
| File Size | Enter the file size to refine the list of files based on their size. |
| Status | Select the status of the file as **Error** and **Scanned**. |
| Ingested date | Select the date the file is ingested. |
- The widgets display the following information:

| Widget | Description |
| --- | --- |
| Total Files | This widget displays the total number of files ingested. |
| Files with Issues | This displays the number of files that have issues. |
- The files are listed with the following attributes:

| Attribute | Description |
| --- | --- |
| Name | The name of the file. |
| Data source | The source the file is ingested from. |
| Data system type | The provider of the data system. |
| Data system | The data system from which the file is ingested. |
| File format | The format of the ingested file. |
| File size | The size of the ingested file. |
| Sensitive data | Number of sensitive data elements in the file. |
| Status | The status of the file as Error or Scanned. |
| Ingested on | The date the file is ingested on. |
- You can sort the list of files based on **Name**, **File size** and **Ingested on**.

#### Viewing the ingested files details

To view the ingested data, click a file to open the **Instance Explorer**.

![pipeline instance explorer in Status](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/pipeline status - IE.png)

In the **Inspector** tab, the instance explorer shows the pipeline's lineage and relationships in detail. This includes:

- How each element connects to other elements
- The number of elements for each entity such as account detail, data sources, file types, pipeline nodes, policies, location and users

![Inspector tab of instance explorer](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/phishing inspector.png)

When you click an entity in the diagram, its details appear in a table. For example, clicking IaaS Cloud shows information like Hosting, Region Count, Data System Count, and Account Count.

![Overview of IaaS Cloud services including AWS, GCP, and Microsoft Azure details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/iaascloud element status.png)

In the **Preview** tab, you see the preview of the ingested file.

![file without masking](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/file without masking.png)

In case masking is applied, this tab displays the masked version of the file.

![Employee information table displaying names, ages, occupations, and membership dates of staff.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/masked file.png)

A set of criteria that focuses your view by eliminating elements that fall outside the scope of interest. When you filter Securiti pages and dashboards, you choose criteria in the filter panel to reduce the number of elements Securiti displays to just those of interest.

File format refers to the different types of files, which have different extensions and file types. Securiti performs the classification of several file types relevant to your data systems. The most common of them are:

- .doc
- .docx
- .xls
- .xlsx
- .ppt
- .pptx
- .conf
- .cf
- .txt
- .c
- .cpp
- .java
- .xml
- .html

## Related

- [Creating a new pipeline](/creating-a-new-pipeline.md)
- [Pipeline Builder](/pipeline-builder.md)
- [Using GenAI pipelines](/using-genai-pipelines.md)
