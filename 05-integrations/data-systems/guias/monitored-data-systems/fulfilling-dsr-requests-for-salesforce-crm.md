---
title: "Fulfilling DSR requests for Salesforce CRM"
slug: "fulfilling-dsr-requests-for-salesforce-crm"
updated: 2026-04-28T08:10:28Z
published: 2026-04-28T08:10:28Z
canonical: "helpcenter.securiti.ai/fulfilling-dsr-requests-for-salesforce-crm"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Fulfilling DSR requests for Salesforce CRM

This article covers the DSR privacy settings and supported DSR request types for Salesforce CRM

## DSR Privacy Settings

In the **Connectors** tab (for Classic UI), or in the **Privacy** tab (for New UI), configure the following settings for the **DSR Scan:**

| Parameter | Description |
| --- | --- |
| Include this instance in the DSR Workflow | Enable this option to include the respective data system in processing the DSR request. > [!WARNING] > **Important** > > For structured data system instances, Securiti creates subtasks in the DSR workbench. If no data is found during the data search, the subtasks are automatically deleted. |
| Allow Multi Column Join DSR | Enable this to combine data from multiple tables based on the values in more than one column. It enables AND condition in the DSR joins. |
| Require indices on primary identifier columns | Enable this if you require an index to exist on primary identifier columns, such as SSN or Email address, for any DSR to improve the speed of data retrieval operations. Enabling this option makes the DSR run more efficiently. |
| Guest Users | Enable this to automatically assign DSR subtasks created for the data system to guest users. See [Automatically assign DSR subtasks to guest users](/v1/docs/automatically-assigning-dsr-subtasks-to-guest-users), for more information |
| Guest User Guidance Text | Enter the guidance text for guest users to fulfil DSR requests. |
| Limit Guest access to specific DSR types | If selected, collaborators will automatically be assigned only to the requests of the selected DSR types |

## Supported DSR Types

When Securiti accepts a DSR request, it creates a single task, with subtasks of the appropriate DSR types for each Salesforce CRM Data system Instance in the Securiti platform.

The Securiti connector for Salesforce supports the various DSR request types with varying degrees of automation, as described in the Table below.

> [!NOTE]
> **Note**
> 
> The rows in the final CSV output with "NA" mentioned as PD type does not appear in the Structured Data Explorer. While rows with the PD type available show the populated data in the structured explorer for Salesforce data systems.

> [!WARNING]
> **Important**
> 
> When you search for an email after you initiate a DSR request in the Salesforce data system, ensure that you have marked the custom object as "searchable" by enabling the **Allow Search** checkbox in the Salesforce Object Manager. Otherwise, Securiti displays an error. See procedure below for more information.

You must set all custom objects as searchable to run DSR for Salesforce CRM, as search is disabled for new custom objects by default. To run DSR on custom objects.

1. Choose **Setup > Object Manager**.
2. Click **Edit** for your object.

![salesforce_objectmanager.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-25eea82e-57b2-168d-4811-14dfd6284713.png)
3. On the bottom of the page, under the **Search Status** area, mark the **Allow Search** checkbox.

![salesforce_crm_allowdsrsearch.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c559b910-c3cc-e84e-cc4d-49d8aa5ee37d.png)

| DSR Type | Automation |
| --- | --- |
| Access | **Automated** Securiti automatically extracts and attaches one or more Auto-generated PD reports showing all the personal data associated with the data subject. Verify that the data belongs to the data subject and that the processing record describes the processing, and if so, approve the subtask. See [Processing access request subtasks](/v1/docs/processing-access-request-subtasks) for more information. |
| Port | **Automated** Securiti automatically extracts and attaches one or more Auto-generated PD reports showing all the personal data associated with the data subject. Verify that the data belongs to the data subject and that the processing record describes the processing, and if so, approve the subtask. > [!NOTE] > **Note** > > For port requests, regulations don't require you to provide the context around which the data is processed within your organization. Therefore, port subtasks do not include a process record. See [Processing port request subtasks](/v1/docs/processing-port-request-subtasks) for more information. |
| Erasure | **Partially Automated** Securiti shows you a report or manifest that identifies the records or objects where it found personal data for the data subject. But unlike automated processing, Securiti does not erase the record. For each object, access the service or database to open and inspect the object that Securiti variables: Platform name identified. If it belongs to the data subject, delete it and verify the subtask. See [Processing erasure request subtasks](/v1/docs/processing-erasure-request-subtasks) for more information. |
| Rectification | **Partially Automated** Securiti shows you a report or manifest that identifies the records or objects where it found personal data for the data subject. But unlike automated processing, Securiti does not correct the record. For each object, access the service or database and open the object that Securiti identified. Inspect it for the incorrect data identified by the data subject, and if necessary, correct it and verify the subtask. See [Processing rectification request subtasks](/v1/docs/processing-rectification-request-subtasks) for more information. |
| Objection | **Partially Automated** The existence of the subtask indicates that Securiti found the data subject’s information within the data system. For some data system types, Securiti may also show you a manifest of the object or record where the data was found. For some data system types, Securiti may also show you a manifest of the object or record where the data was found. Use your internal company processes to identify all groups processing the data subject’s personal data from that data system, and alert them to stop processing the data. Then approve the subtask. See [Processing objection request subtasks](/v1/docs/processing-objection-request-subtasks) for more information. |
| Restriction | **Partially Automated** The existence of the subtask indicates that Securiti found the data subject’s information within the data system. For some data system types, Securiti may also show you a report or manifest of the object or record where the data was found. Use your internal company processes to identify all groups processing the data subject’s personal data from that data system, and alert them to stop processing the data. Then approve the subtask. See [Processing restriction request subtasks](/v1/docs/processing-restriction-request-subtasks) for more information. |
| Confirmation | **Partially Automated** Securiti shows you a report or manifest that identifies by object ID, object name, and object URI the objects where it found personal data for the data subject. For each object, access the service or database to open and inspect the object that Securiti identified. Verify that the personal data is indeed that of the data subject, verify that the processing record is correct, and approve the subtask. See [Processing confirmation request subtasks](/v1/docs/processing-confirmation-request-subtasks) for more information. |
| Do-Not-Sell | **Partially Automated** The existence of the subtask indicates that Securiti found the data subject’s information within the data system. For some data system types, Securiti may also show you a report or manifest of the object or record where the data was found. Use your internal company processes to identify all groups processing the data subject’s personal data from that data system, and alert them to stop selling that data. Then approve the subtask. See [Processing do-not-sell request subtasks](/v1/docs/processing-do-not-sell-or-share-request-subtasks) for more information. |
