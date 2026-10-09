---
title: "Understanding process records"
slug: "understanding-process-records"
updated: 2026-01-14T09:33:53Z
published: 2026-01-14T09:33:53Z
canonical: "helpcenter.securiti.ai/understanding-process-records"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Understanding process records

For **Access** and **Confirmation** DSR request types, the regulations require that you tell the data subjects what you do with their data and how you process it. Process records give you a convenient way to automate some or all of the work of delivering this information to the data subject. The processing record describes the context under which personal data is processed:

- Categories of personal data concerned
- Purposes of the processing
- Recipients or categories of recipients to whom the personal data have been or will be disclosed
- Envisaged period for which the personal data will be stored
- Legal basis for processing information
- Organizations managing the processing activities
- Source of information when data is not collected from the data subject
- Existence of automated decision-making, including profiling

For each data asset, you can associate one or more process records as described in [Editing a new or existing data asset](/v1/docs/creating-and-editing-processes). Each process record explains what records the data system contains and how you use those records. For more information on creating process records, see [Creating and editing processes](/v1/docs/creating-and-editing-processes).

> [!NOTE]
> **Note**
> 
> You must define values for the **Managing Organizations**, **Processing Entity**, **Processing Purpose**, **Lawful Basis for Processing** and **Automated Decision Making** in the **Basic Information** section while [creating a process](/v1/docs/creating-and-editing-processes) in the **Data Mapping** module. Also, make sure to add the **Retention Period** and **Data Elements and Types** when [creating a new data asset](/v1/docs/creating-and-editing-data-assets). Further, associate an asset with a process by [adding a process element](/v1/docs/creating-and-editing-processes). If you don't define these values, the selected process in the DSR workbench displays empty values.

When you process subtasks for DSR request types that require process information, you attach the process record for the data system where Securiti found an object containing personal data. The process record tells the data subject how their personal data was being used. For data assets with only one process record, that process record is the default for all access subtasks for that data system.

### Adding process records

When processing access subtasks, you can either choose an existing process record or create a new processing record from within the DSR. You create a new record if none of the current processing records addresses the way the personal data was being used or processed.

You can create a process record either from within the subtask or **Data Subject Rights** settings.

To create a process record from within the subtask:

1. If you have not done so, open the subtask created against the access request.
2. Go to the **Processing Details** and click Create **New Process Record**.

![Screenshot_2023-09-28_at_3_56_24_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2747a295-83f3-c7fc-2f48-1d2a1736dcc5.png)
3. Enter the details. Once you submit the subtask, the new record will be created in Process Records under the **Data Subject Rights** settings.

Similarly, to create a process record from **Data Subject Rights** settings:

1. In Securiti, click the jewel at the upper left corner of the page, then in the upper right corner choose **Dashboard View**.
2. On the bottom row of tiles, click **Settings**.
3. On the System Settings menu choose **Settings > Data Subject Rights > Process Records**.
4. On the top right side of the Process Records page, click **+ Add Process Record**.

| Process Records |
| --- |
| Name | Enter name for the process record. |
| Processing Entity | Enter entity name meant for the data subject in the report. |
| Processing Purpose | Choose the data processing purpose from the menu. |
| Data Element Types | Select one or more data element types. |
| Managing Organizations | Choose the organization involved in processing activities from the menu |
| Legal Basis for processing | Choose the legal basis for processing from the menu. |
| Recipients | Enter the name of recipients (or categories of recipients) to whom the personal data is disclosed. |
| Retention Duration | Enter the duration for which the data will be kept. **Formats example:** 10 Days, 10 Months, 10 Years |
| Logic involved | Enter logic name for the process record. |

> [!NOTE]
> **Note**
> 
> The menu values you see in menus while creating a new process record are sourced from the reference list defined in the Data Mapping module. For more information, see [Creating and customizing Data Mapping Automation reference lists](/v1/docs/creating-and-customizing-data-mapping-automation-reference-lists).
