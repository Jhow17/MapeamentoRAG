---
title: "Date & Time"
slug: "date-time-regular-node"
updated: 2026-02-12T05:58:07Z
published: 2026-02-12T05:58:07Z
canonical: "helpcenter.securiti.ai/date-time-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Date & Time

The Date and Time node in Securiti’s workflow automation module allows you to manipulate and transform date and time information with ease. This node is designed to change the format of date and time data to better suit your specific needs, making it an essential component for customizing timestamps and streamlining time-related processes within your workflows.

Within your workflows, the Date and Time node serves a multitude of purposes. It allows you to seamlessly convert date formats, perform time zone conversions, and extract specific elements from timestamps. Additionally, you can employ it to create conditional actions based on date and time conditions or to ensure smooth data integration with external systems that require precise date and time formatting.

See the [Node Configuration section](/v1/docs/date-time) to understand the node properties and their examples.

#### Example use case

Let’s create a sample workflow that fetches a list of assessments along with their details such as created_at, modified_at etc. The purpose of this workflow is to get the timestamp of the assessment creation and convert it into a readable format for data collection.

The workflow begins with an **Assessment node** that lists all the assessment details from a specific date till the current date. The **Date and Time node** converts the value of the “created_at” field from the response and converts the value into the readable custom format. The **Spreadsheet File** node then writes the values to a file.

#### Converting Date and Time to a Custom Format for Data collection

1. Begin the workflow by adding the Assessments Node to fetch the list of assessments from the said date till the current date.
2. Add the Date and Time node to format the date and add the value, property name and format. In this specific case, we are using the custom format to convert the value to “hh:mm:ss” format.

![date-and-time-2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9e2c949b-694e-6096-5827-99965520f933.png)
3. Add the Spreadsheet File node to write the data to a spreadsheet file.
4. Connect the nodes to execute the workflow.

![date-and-time-1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-391c44e8-761c-c250-34c5-094154050f61.png)
5. Upon successful execution, the Date and Time node will provide a successful response. After the workflow runs successfully, you can access the results in two formats i.e. table view and JSON response.

![date-and-time-3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e90ed465-21a7-0212-2454-555a3ab1816f.png)

#### Node configuration

| Parameters |
| --- |
| Action | Format a date | This option formats a date in the selected format. |
| Value | Specify the value of the date that needs conversion. |
| Property name | Specify the name of the property to which the converted date is written, for example, date data. *This is an optional field.* |
| Custom format | Enable this toggle if you want to specify a predefined custom format. |
| To format | Specify the desired format in which the date and time is required. |
| MM/DD/YYYY | Example: 09/04/1986 |
| YYYY/MM/DD | Example: 1986/04/09 |
| MMMM DD YYYY | Example: April 09 1986 |
| MM-DD-YYYY | Example: 09-04-1986 |
| YYYY-DD-DD | Example: 1986-04-09 |
| Options | From format | Specify the input format if the format is not recognized. |
| from timezone | Specify the timezone to convert the time from. |
| to timezone | Specify the timezone to convert the time to. |
