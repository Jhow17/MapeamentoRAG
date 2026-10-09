---
title: "Setting up data systems for DSR automation"
slug: "setting-up-data-systems-for-dsr-automation"
updated: 2026-09-22T08:49:26Z
published: 2026-09-22T08:49:26Z
canonical: "helpcenter.securiti.ai/setting-up-data-systems-for-dsr-automation"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Setting up data systems for DSR automation

DSR Automation refers to an advanced technology that facilitates intelligent search capabilities to find data for data subjects, enabling automation in cloud and self-hosted data systems. The result is a reduction in the time required to handle DSR requests, accompanied by an improvement in the precision and quality of the outcomes.

> [!NOTE]
> **Note**
> 
> You must purchase licenses to use DSR Automation. The number of licenses required depends on the number of instances where data of the data subject is stored and needs to be searched automatically upon the submission of a DSR request.

Setting up the DSR Automation process spans across both **Data Subject Rights** and **Data Systems and Connectors** modules.

> [!WARNING]
> **Important**
> 
> The individual setting up DSR Automation settings within the **Data Subject Rights** module may be different from the one setting up connectors and DSR Automation settings within data systems. Therefore, these individuals need to coordinate to ensure a smooth setup process.

To setup the DSR Automation:

### Set up a DSR form and identify data systems for DSR automation

To setup the DSR form:

1. In the Data Subject Rights module, identify your DSR form requirements and create and publish the necessary DSR forms. For more information, see [Creating and publishing DSR request forms](/v1/docs/creating-and-publishing-dsr-request-forms).
2. To uniquely identify a data subject within your systems, you typically need to collect certain data such as email address. In some use cases, identifying data subjects may require additional identifiers such as a phone number or address.

Once you have decided on the identifier fields in the DSR form, you should mark these fields as data subject identifiers while configuring the DSR form. For more information, see [Configuring DSR request forms for multiple identifiers](/v1/docs/configuring-dsr-request-forms-for-multiple-identifiers).

This action informs DSR Automation that these are identifier fields for searching data of a specific data subject. Within the same DSR form setting, you also need to set up the Data Element Types as shown [here](/v1/docs/configuring-dsr-request-forms-for-multiple-identifiers).

> [!NOTE]
> **Note**
> 
> Record these exact DS Identifiers and "Data Element Types," as you will need them later while setting up DSR Automation for Structured Data Systems.
3. Ask appropriate technical contact within your data teams to identify all the data systems storing data of data subjects. Securiti supports connectors for many structured and unstructured data systems. For more information, see [a list of supported data system connectors.](/v1/docs/supported-data-system-connectors-in-securiti) These technical individuals set up data system records, instances and connectors for data systems. For more information, see the [Configuring connectors for monitored data systems](/v1/docs/configuring-connectors-for-monitored-data-systems).

![Setting_up_data_systems_for_DSR_automation.svg](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-732f9647-536b-f9ce-e188-b62ae1efc355.svg)

### DSR automation for unstructured data systems

In unstructured data systems, DSR Automation is supported either using "Full Scan'' or "API". To see the DSR Automation methods for each unstructured data system, refer to [supported data system connectors](/v1/docs/supported-data-system-connectors-in-securiti).

1. If the DSR Automation is supported using “Full Scan”:
  - You must set up at least one discovery scan job for the respective data system.
  - Discovery Scans build an index of primary data elements such as email, SSN, passport number etc. that is stored in Securiti cloud.
  - While creating a discovery scan, you must enable the “Enable Data Subject Requests (DSR) Automation on this Data” option. For more information, see [Discovery scans for unstructured data systems.](/v1/docs/discovery-scans)

![ds_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2cc22f7e-5901-3af8-3972-fb7d097cd0ef.png)
2. If DSR Automation is supported using "APIs," set up the necessary permissions for your API user in the connector setup.
3. Once done, in the **Permissions** tab of Data System configurations, mark “Include this instance in the DSR Workflow” checkbox.

![ds2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-02b90cb5-76cc-bc5c-d487-1c4659c21689.png)

For more information, refer to the [configuration of the respective data system](/v1/docs/configuring-connectors-for-monitored-data-systems).

### DSR automation for structured data systems

Securiti searches the data stored in the [structured data systems](/v1/docs/supported-data-system-connectors-in-securiti) using SQL queries or search APIs depending on whether the data system supports API based or query based DSR Automation. For more information, [see a list of supported data system connectors](/v1/docs/supported-data-system-connectors-in-securiti).

Once the discovery scan or legacy scan is completed for the respective structured data systems, you need to enable several other settings for these systems to search for the data subject’s data. You can find these settings under [Table Training](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems).

1. For each table, verify primary identifiers, primary keys, classified data element types, and Reference Columns.
  - To custom mark primary keys, primary identifiers and data elements:
    - For each table in the structured data system, click Edit at the upper right corner of the Table training page, identify the Primary Key(s) for each table and mark its PK checkbox. DSR Automation uses this information to correctly query the table and any related tables for personal data when it collects information to fulfill DSR requests. For more information, see [verifying primary keys](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems).
    - Further, identify the Primary Identifiers that uniquely identify a data subject as described [here](/v1/docs/table-training-for-structured-and-hybrid-data-systems). These Primary Identifiers need to match the one collected while setting up the fields on DSR form as described [here.](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems)

> [!NOTE]
> **Note**
> 
> By default, email address is set as the Primary Identifier on the DSR form.

Once you have identified the primary identifier columns for the table, mark Primary Identifier checkbox for each. For more information, see [verifying primary identifiers](/v1/docs/table-training-for-structured-and-hybrid-data-systems).
    - Moreover for each table in the structured data system, setup Data Element Types as described [here](/v1/docs/managing-data-system-connectors). These Data Element Types need to match the one you configured in the DSR Form. For all tables, identify the joins (foreign key links) that relate the table to any other tables. Securiti uses this information to correctly query the table and any related tables for personal data when it collects information to fulfill DSR requests. For more information, see [Verifying and configuring joins](/latest/docs/verifying-and-configuring-joins).

![ds_4.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e5f9a7f7-db8e-070a-9177-8a7d834b295c.png)
2. (Optional) While configuring connectors for structured data systems, use the options in the **Permissions** tab to control or customize data searches. To learn about each option and determine if you need to enable them for your structured data systems, refer to the [connector activation section](/latest/docs/microsoft-sql-server-connectors) for respective structured data systems.

![ds_5.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-68a88854-978d-d0df-b00c-8202adcba068.png)
3. Once done with all the above settings, in the **Permissions** tab of data system configurations, mark “Include this instance in the DSR Workflow” checkbox.

![ds_6.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8d507c15-967a-1640-0c3f-58b037e46fd4.png)

### DSR automation for unmonitored data systems

- If Securiti doesn’t support connectors for some of your data systems, you can create new or add existing unmonitored data systems in the Data Mapping module and include them in the DSR workflow. For this purpose, you need to subscribe to the Data Mapping module. For more information, see [Configuring unmonitored data systems](/v1/docs/configuring-unmonitored-data-systems).

![ds_8.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c965b47b-fac4-79df-dc83-01d0fca9fb85.png)
- In the **DSR Workbench**, Securiti creates a task for an unmonitored system, but no data is searched automatically. So if the respective unmonitored Data System contains the data subject’s data, you can upload it manually.

### DSR Automation for user-defined data systems

If you can't find connectors for some data systems but they support APIs to fetch data subject’s data, you can set up a user-defined system.

Once you have authenticated and activated these data systems, add them in the DSR workflow by marking **Include this instance in DSR workflow** checkbox in the **Permission** tab of the data system configurations. For more information, see [Configuring user-defined (Webhooks) connectors](/v1/docs/user-defined-webhooks-connectors)

### DSR Automation for scanless data systems

Securiti doesn't scan scanless data systems ahead of time. Instead, it queries them in real-time as DSR requests come in, eliminating the need to establish an internal inventory of personal data.

Once you have authenticated and activated these data systems, add them in the DSR workflow by marking "Include this instance in DSR workflow" checkbox in the Permission tab of the data system configurations. For more information, see [Configuring the Auth0 connector](/v1/docs/auth0-connectors).

### Inclusion of data systems in DSR Form

Once you configure the required data systems and set up DSR Automation, these systems will appear in the DSR form configuration.You can choose which data systems to include or exclude in the DSR request handling process.

![ds_10.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ebb33888-c21e-0576-0e05-1d2df42c7afd.png)

For more details on inclusion or exclusion of data systems, see [Creating and publishing DSR request forms](/v1/docs/creating-and-publishing-dsr-request-forms).

---

### FAQ

#### 1. How does DSR automation for self-hosted connectors work when the pod is off, and how does it recover when turned back on? Is there a retry or time limit before rescanning?

If the pod is off when a DSR request is received, the DSR Automation fails, and the DSR workbench shows an error in the subtask created against that Data System.

![Screenshot_2025-02-21_at_5_11_19_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2239ca56-5b36-84b9-84bd-79e565963059.png)

There is no automatic retry. Once the pod is back up, you can manually rescan the Subtask to retrieve the results. There’s no time limit for rescanning the same DSR request. The only conditions are that the DSR should not be published and no other scan for that DSR request is in progress.

## Related

- [Using Robotic Automation setup dashboard](/using-robotic-automation-setup-dashboard.md)
