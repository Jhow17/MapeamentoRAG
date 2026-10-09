---
title: "HTML Extract"
slug: "html-extract-regular-node"
updated: 2026-01-16T06:12:40Z
published: 2026-01-16T06:12:40Z
canonical: "helpcenter.securiti.ai/html-extract-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# HTML Extract

An HTML Extract node in Securiti’s workflow automation refers to a node that is designed to extract specific information or data from an HTML document. Workflow automation tools are used to streamline and automate business processes, and the ability to extract data from HTML documents is important for tasks such as web scraping, data extraction, and content parsing.

Please refer to the [node configurations section](/v1/docs/html-extract) to understand the node working and properties.

#### Example use case

As an example, let’s create a use case that caters to an e-commerce company that aims to maintain competitive pricing for its products. To achieve this, the company uses a workflow that includes an HTML Extract node to regularly extract pricing information from competitors' websites. This data is then analyzed to adjust the company's pricing strategies accordingly.

The workflow starts with the **Cron node** that executes the workflow at the specified interval. The **HTTP request node** fetches the pricing of the competitors’ products, followed by the HTML extract node that extracts the information from the response. This information is then written into a file and sent over to the relevant teams that analyze the data via **Send Email** node.

The following nodes are used in this workflow:

1. [Cron Trigger Node](/v1/docs/cron)
2. [HTTP Request Node](/v1/docs/http-request)
3. HTML Extract Node
4. [Spreadsheet file Node](/v1/docs/spreadsheet-file)
5. [Send Email Node](/v1/docs/send-email)

#### Real-Time competitive pricing analysis

1. Start the workflow with a Cron Trigger node that executes the workflow at a set time, 12 hours in this case.
2. Add an HTTP Request node that fetches the data from the competitor’s website and attach the HTML Extract node to extract the HTML information from the response.

![Screenshot_2024-05-07_at_5_10_57_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-427700d1-8f7f-c5d6-faa7-d393f755f696.png)
3. Finally, add a Spreadsheet node and Send Email node to write the data into a spreadsheet and send the file as an attachment.
4. Connect the nodes and execute the workflow.

![Screenshot_2024-05-07_at_5_10_34_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-04528642-9f12-c28d-d6b9-3a8a8e7b9967.png)
5. Upon successful execution, the Workflow Node will provide a successful response. After the workflow runs successfully, you can access the results in two formats i.e. table view and JSON response

#### Node configurations

| Parameters |
| --- |
| Source data | Read the source data from either Binary or JSON |
| JSON Property | For source JSON, the name of the JSON property in which the HTML to extract data from is found. The property can contain either a string or an array of strings. |
| Binary Property | For source Binary, the name of the binary property in which the HTML to extract data from is found. |
| Extraction Values |
| Key | The key under which to save the extracted value |
| CSS Selector | The CSS Selector |
| Return Value | What kind of value to return |
| Attribute | Get an attribute value such as "class" from an element |
| HTML | Get the HTML that the element contains |
| Text | Get only the text content of the element |
| Value | Get the value of an input, select, or text area |
| Return array | Enable to return the values as an array so that if multiple values are found they also get returned separately. When enabled, the node returns all values as a single string. |
