---
title: "Consent"
slug: "consent-regular-node"
updated: 2026-02-12T05:53:18Z
published: 2026-02-12T05:53:18Z
canonical: "helpcenter.securiti.ai/consent-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Consent

The Consent workflow node manages and retrieves consent records from a specified consent offering. When integrated into workflows, it distributes consent data to downstream processes, ensuring accurate and up-to-date tracking of user permissions. It also lets you list all consents and fetch data from either a specific date or a custom time range.

#### Example use case

As an example, let’s create a workflow that records multiple consents. The process begins with a **Cron Trigger** workflow node, which initiates workflows (a series of automated actions) based on a specific schedule. Then, the Consent workflow node triggers to record multiple consents from the specified consent offering. Subsequently, the fetched consent data records are populated into the database using the Oracle workflow node.

This use case uses the following nodes:

- Cron Trigger node
- Consent node
- Oracle node

#### Recording multiple consents using Consent node

1. Add the Cron Trigger node to set the time such that the workflow is executed everyday. Set the **Mode** to everyday and set the time at which the workflow is set to execute every day, as shown below.

![Usecase-1-1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-63d3e266-abb0-ec83-c480-d2353ee0adf5.png)
2. Add a Consent node to choose the **Operation**, such as **List** for listing all consent. Set the **Delta Parameter** to select the timestamp filter. Set the date and time from when it records consent, and enable the **Delta Sync** toggle that triggers the last saved time pointer used to query the table. Enable the **Pagination** toggle to configure pagination and specify the number of pages, as shown below.

![Settings for data collection including date, pagination, and delta sync options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/consent-node-hc-updates.png)
3. Add Oracle node with the required datasource. Use the query, as shown below.

![Usecase-1-3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3f9914cf-8641-7f6b-77d6-fb1ef1fc09a5.png)
4. Connect the nodes and at the bottom of the workflow tab, click **Execute Workflow** to execute the workflow, as shown below.

![consent.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-be0f5b08-bb91-7305-f9b4-d4630989ba8c.png)

> [!NOTE]
> **Note**
> 
> Securiti treats the execution as successful even when no records are found, instead of showing an error.

#### Node configurations

| Parameters | Description |
| --- | --- |
| Operation | Operation to perform: - List all consents - Bulk create consents |
| Delta Parameter | To select timestamp filter: - Activity Timestamp - Collected Timestamp |
| From Date | To fetch record from the selected date to current time, in initial sync OR if delta sync is disabled. By default, data is fetched from the last 24 hours. > [!NOTE] > **Note** > > You must enable the **Pagination** toggle and use the **From Date** field to retrieve consent records beyond the last 30 days. |
| To Date | To fetch records till the selected time |
| Delta Sync (toggle) | Enable this toggle if you want to use the last saved timestamp of the last execution as the start time for the next execution. > [!NOTE] > **Note** > > Delta Sync only works with the Cron trigger enabled and active. |
| Pagination (toggle) | To specify the number of records to fetch per iteration in a single workflow execution. > [!NOTE] > **Note** > > You can use these parameters only when you enable the **Delta Sync** toggle. |
| Page Size |
| Import Consent | Specify the format either CSV file format or JSON format to import bulk consents. |
| Property Name | Specify the name of the binary property to which to write the data of the read file. |
| File Name | Specify the file name for the attachment, for instance `ucm_results.csv`. |
