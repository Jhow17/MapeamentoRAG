---
title: "DSR Automation in data system connectors"
slug: "dsr-automation-in-data-system-connectors"
updated: 2025-11-03T19:58:19Z
published: 2025-11-03T19:58:19Z
canonical: "helpcenter.securiti.ai/dsr-automation-in-data-system-connectors"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# DSR Automation in data system connectors

Securiti supports Data Subject Rights (DSR) automation for the following Data system Connector types:

| Data system types | Description |
| --- | --- |
| Monitored data systems | Securiti supports the Integration with the monitored data systems. You can connect with the data systems at Data system connectors. In monitored systems, DSR is performed to search the Data system Instance for the subject’s data and include it in the DSR Forms. To learn more, refer to [DSR Automation in Monitored data systems](/v1/docs/dsr-automation-in-data-system-connectors). |
| Unmonitored data systems | Securiti does not support connectors for some of your data systems, you can create new or add existing unmonitored data systems in the Data Mapping Automation module and include them in the DSR Workflow. To learn more about creating and editing assets in unmonitored data systems, refer to [Configuring unmonitored data systems](/v1/docs/configuring-unmonitored-data-systems) |
| User-defined data systems | Securiti does not support connectors for these data systems and uses OpenGDPR APIs to fetch Data Subject’s data for the user-defined data systems. You can set up the user-defined data systems manually. Further, add these data systems to the DSR Workflow by checking the **Include this Instance in DSR Workflow** checkbox in the **Permission** tab of the Data system configurations. For more information, refer to [User-Defined (Webhooks) connectors](/v1/docs/user-defined-webhooks-connectors) |

### DSR Automation in Monitored data systems

DSR Automation lets you search for the data subject’s data automatically within your structured and Unstructured data systems as a data subject submits a request. DSR Automation is performed using the following methods for structured and Unstructured data systems

To include your Data system Instance in DSR Automation:

1. Go to the **Permissions** tab for your Data system Instance in the **Data Systems** module.
2. In the **DSR Scan** section of the **Permissions** tab, mark the **Include this Instance in the DSR Workflow** checkbox.

![workflow-option.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2c8714e4-9c97-d73b-c405-90037b3edc6d.png)

Enabling the option allows Securiti to search the Data system Instance for data subject’s data and includes it in the DSR Forms, allowing you to select it as one of the systems to include or exclude for data scanning. To learn about data systems inclusion and exclusion for data scanning, refer to [Creating and Publishing DSR request forms.](/v1/docs/creating-and-publishing-dsr-request-forms)

> [!NOTE]
> **Note**
> 
> - Securiti performs a DSR scan on all the Data system instances with this option enabled in case no Data system is added explicitly in the DSR form.
> - You must configure additional settings for your structured and Unstructured data systems to perform DSR Automation. See the below sections for more information.

### DSR Automation in structured data systems

Securiti searches the data stored in the [structured data systems](/v1/docs/supported-data-system-connectors-in-securiti) using SQL queries or search APIs, depending on whether the Data system supports API based or query-based DSR Automation.Supported Data system connectors in Securiti

#### Enabling DSR automation in structured data systems

Securiti lets you enable the DSR Automation Connector Activation process. Once you have marked the checkbox for **Include this Instance in the DSR Workflow**, configure the following settings to suit.

| Parameter | Description |
| --- | --- |
| Allow Multi-Column Join DSR | Enable this option to include multiple matching columns of two joining tables in the DSR query generation process. For example, if there are common fields, such as email address and phone number, in joining tables, then all of those columns are joined while searching and linking the Data system’s data. |
| Require indices on primary identifier columns | Enable this option if you require an index to be created on primary identifier columns such as SSN or Email address. This will improve the speed of data retrieval operations. |
| Require Database indexes for SQL Table Joins | Enable this option to limit the Joins in the generated SQL queries to only tables that have indexes on joined columns. Enabling this option helps you reduce the load on the Database server and make the DSR Automation performant. |
| Maximum depth for SQL Table relations | Set the value for the maximum depth to which relations between tables will be considered for JOIN clauses in the SQL queries generated for DSR Automation. Lowering the depth speeds up automation and eases the load on the Database server. |

In addition to the above settings for your Data system, configure the following for the Table training of your Data system Instance.

1. Near the top right corner of your activated Data system Instance, click **Table Training**.

![Table-training-finalp.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a95ff27d-8cc9-2985-de9d-ae13637f77ad.png)
2. On the top right corner of the **Table training** page your structured Data system, click **Edit Mode**.

![Edit-mode-finalp.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-526719dc-04a0-d261-e90a-5acf0bcd5870.png)
3. In the **Edit mode**, perform the following actions for your data Table training:
  1. Verify and identify the Primary key(s) (PK) by marking the checkbox for your identifier in the **PK** Column of the Table. See [Verifying Primary Keys](/v1/docs/table-training-for-structured-and-hybrid-data-systems), for more information.

![PK-column-finalp.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6693ec60-6290-3310-1902-ec7290b4646d.png)

This information is used to correctly query the Table and any related tables for personal data when information is collected during the automation to fulfill DSR requests.
  2. Identify the Primary Identifiers (PI) that uniquely identify a data subject by marking the checkbox for your identifier in the **PI** Column of the Table.

![PI-column-finalp.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-cf92bdf1-036d-d4a4-7b01-64ee38ac2056.png)

These Primary Identifiers are used to match the data collected within the DSR with the DS Identifiers in the DSR form. See the topics below for more information.
    - [Verifying primary identifiers](/v1/docs/table-training-for-structured-and-hybrid-data-systems)
    - [Configuring DSR request forms for enhanced DSR requests](/modules/data-subject-rights/en/dsr-target/using-enhanced-dsr-request-processing/configuring-dsr-request-forms-for-enhanced-dsr-requests.html#UUID-8c23967e-866c-4fbd-f2d4-79dd2d733de4).
  3. Set up the Data element types to process the DSR request. See [Verifying data element types](/v1/docs/table-training-for-structured-and-hybrid-data-systems), for more information.

The Data element types need to match the values marked as **Data element Type** in the DSR form.

![Data-element-types.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ec8ddcf2-4b68-79e4-b7e6-cc9eeb5760ff.png)
  4. Identify the common Personal Data fields across all tables. These are used to correctly query tables for personal data when DSR Automation collects information to fulfill DSR requests. For more information, see [Verifying and configuring joins](/v1/docs/verifying-and-configuring-joins).

![reference-column-final.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-79ec0028-0dc9-eaac-f201-496fd71c3093.png)

### DSR Automation in unstructured data systems

Securiti uses a full scan or search APIs to search data in [Unstructured data systems](/v1/docs/supported-data-system-connectors-in-securiti). In full scan DSR Automation for Unstructured data systems, a Discovery scan is used to scan and index all the personal data stored in a Data system. Securiti's Cloud stores this index data and uses it to identify the subject’s data upon the submission of a DSR.Supported Data system connectors in Securiti

#### Enabling DSR automation in unstructured data systems

Securiti lets you enable the DSR Automation Connector Activation process. Once you have marked the checkbox for **Include this Instance in the DSR Workflow**, configure the following setting for at least one Discovery scan for data systems supporting full scan.

Unstructured data systems supporting full scan must have at least one Discovery scan configured for DSR Automation. To include a Discovery scan in DSR Automation, perform the following steps:

1. In the **Discovery Scans** page, select the scan you want to include in the DSR Automation process.
2. In the **Advanced Settings** section, enable the **Data Subjects Requests (DSR) Automation on this data** toggle.

![workflow.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8c2cdc56-bb55-932d-7cc4-b44e8116d521.png)

Discovery scan builds an index of primary data elements such as email, SSN, passport number, etc., and stores it in Securiti Cloud. Examples of such data systems include Amazon S3 and NFS.

> [!NOTE]
> **Important**
> 
> Securiti does not create any index for personal data and no data is returned for DSR Automation if this option is disabled in Discovery scan.

To learn more about DSR Automation Workflow and processing, refer to [Using Data Subject Rights](/v1/docs/using-data-subject-rights-1).

## Related

- [Supported data system connectors in Securiti](/supported-data-system-connectors-in-securiti.md)
