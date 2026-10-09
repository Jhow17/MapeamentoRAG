---
title: "Read PDF"
slug: "read-pdf-regular-node"
updated: 2025-10-30T19:07:29Z
published: 2025-11-03T07:40:59Z
canonical: "helpcenter.securiti.ai/read-pdf-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Read PDF

A Read PDF node in a Workflow is designed to automate the process of extracting text and sometimes other content from PDF files within a larger automated process. This node plays a crucial role in workflows that involve data ingestion, document processing, or information retrieval tasks where PDF documents are a primary source of data.

#### Example use case

As an example, let's create a Workflow that automates the extraction and analysis of financial reports stored as PDFs on Google Drive, converting them into structured data for further financial analysis and reporting. Let’s assume that a financial department stores monthly financial reports in PDF format on Google Drive. These reports need to be processed to extract key financial data, which is then analyzed to track financial health and inform decision-making.

A Google Drive node is triggered to run at a scheduled time each month after the financial reports are uploaded to a specific Google Drive folder. After the file is downloaded, the Read PDF node extracts the text from the PDF including all the financial data. The data is then converted into CSV format for further processing and analysis.

The following Nodes are used in this Workflow:

1. [Cron Node](/v1/docs/cron)
2. [Google Drive Node](/v1/docs/google-drive)
3. Read PDF Node
4. [Process CSV Node](/v1/docs/process-csv)

#### Automated financial report processing and analysis

1. Start the Workflow with the Cron trigger node on the set time, for example every 24 hours.
2. Add Google Drive node to fetch the PDF file stored on the drive.
3. Add the Read PDF node to read the content of the pdf file.

![Screenshot_2024-04-17_at_3_53_48_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bc4aa692-0c1a-9ccf-1038-47652ec792bb.png)
4. Finally, connect the Process CSV node to process the data fetched and create a CSV file from the data extracted from the PDF file.
5. Connect the Nodes and execute the Workflow.

![Screenshot_2024-04-17_at_3_53_27_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-48a37572-b831-64fc-5f83-1dc4d60701ac.png)
6. Once the Workflow is executed, you can view the response in both JSON and table view.

![Screenshot_2024-04-17_at_3_54_40_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5f17bd36-7a75-34fa-191a-f4d78f93f987.png)

#### Node configurations

| Parameters |
| --- |
| Binary Property | The name of the binary property from which to read the PDF file |

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.
