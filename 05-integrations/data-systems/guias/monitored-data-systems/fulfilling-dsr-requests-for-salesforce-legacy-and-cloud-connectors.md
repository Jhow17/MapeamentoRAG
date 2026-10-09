---
title: "Fulfilling DSR requests for Salesforce"
slug: "fulfilling-dsr-requests-for-salesforce-legacy-and-cloud-connectors"
updated: 2026-03-10T05:41:21Z
published: 2026-03-10T05:41:21Z
canonical: "helpcenter.securiti.ai/fulfilling-dsr-requests-for-salesforce-legacy-and-cloud-connectors"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Fulfilling DSR requests for Salesforce

This article covers the DSR privacy settings and supported DSR request types for Salesforce (Legacy) and Securiti Hosted.

## Privacy Platform Integrations settings

Configure the following on the **Privacy** tab under the **Privacy Platform Integration** section:

**Enable Privacy Platform Integration**: Enable the toggle to include the Data system Instance for Integration in the Privacy **Platform Integrations**. For more information, see [Using the Privacy Platform Integrations](/v1/docs/configuring-salesforce-integration-in-securiti).

> [!NOTE]
> **Important**
> 
> **Privacy Integrations Framework** is available by subscription only. Contact [support@securiti.ai](http://support@securiti.ai) to enable it for your tenant.

Once the toggle is enabled, Scoping Metadata Sync starts for the Data system Instance. After the sync completes, the Data system Instance can be used in the Privacy **Platform Integrations**.

> [!NOTE]
> **Note**
> 
> - Once enabled, the **Enable Privacy Platform Integration** toggle cannot be disabled.
> - Scoping Metadata Sync runs every 7 days after completion. Additionally, it runs every 15 minutes to detect any new Data system instances.
> - Securiti does not let you deactivate and purge a Data system Instance that is used in Privacy **Platform Integrations**

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

When Securiti accepts a DSR request, it creates a single task, with subtasks of the appropriate DSR types for each Salesforce Data system Instance in the Securiti platform.

The Securiti Connector for Salesforce supports the various DSR request types with varying degrees of automation, as described in the Table below.

> [!NOTE]
> **Note**
> 
> The rows in the final CSV output with "NA" mentioned as PD type does not appear in the Structured Data Explorer. While rows with the PD type available show the populated data in the structured explorer for Salesforce data systems.

> [!WARNING]
> **Important**
> 
> When you search for an email after you initiate a DSR request in the Salesforce Data system, ensure that you have marked the custom object as "searchable" by enabling the **Allow Search** checkbox in the Salesforce Object Manager. Otherwise, Securiti displays an error.

| DSR Type | Automation |
| --- | --- |
| Access | **Automated** Securiti automatically extracts and attaches one or more Auto-generated PD reports showing all the personal data associated with the data subject. Verify that the data belongs to the data subject and that the processing record describes the processing, and if so, approve the subtask. See [Processing access request subtasks](/v1/docs/processing-access-request-subtasks) for more information. |
| Port | **Automated** Securiti automatically extracts and attaches one or more Auto-generated PD reports showing all the personal data associated with the data subject. Verify that the data belongs to the data subject and that the processing record describes the processing, and if so, approve the subtask. > [!NOTE] > **Note** > > For port requests, regulations don't require you to provide the context around which the data is processed within your organization. Therefore, port subtasks do not include a process record. See [Processing port request subtasks](/v1/docs/processing-port-request-subtasks) for more information. |
| Erasure | **Partially Automated** Securiti shows you a report or manifest that identifies the records or objects where it found personal data for the data subject. But unlike automated processing, Securiti does not erase the record. For each object, access the service or database to open and inspect the object that Securiti variables: Platform name identified. If it belongs to the data subject, delete it and verify the subtask. See [Processing erasure request subtasks](/v1/docs/processing-erasure-request-subtasks) for more information. |
| Rectification | **Partially Automated** Securiti shows you a report or manifest that identifies the records or objects where it found personal data for the data subject. But unlike automated processing, Securiti does not correct the record. For each object, access the service or database and open the object that Securiti identified. Inspect it for the incorrect data identified by the data subject, and if necessary, correct it and verify the subtask. See [Processing rectification request subtasks](/v1/docs/processing-rectification-request-subtasks) for more information. |
| Objection | **Partially Automated** The existence of the subtask indicates that Securiti found the data subject’s information within the data system. For some data system types, Securiti may also show you a manifest of the object or record where the data was found. For some data system types, Securiti may also show you a manifest of the object or record where the data was found. Use your internal company processes to identify all groups processing the data subject’s personal data from that data system, and alert them to stop processing the data. Then approve the subtask. See [Processing objection request subtasks](/v1/docs/processing-objection-request-subtasks) for more information. |
| Restriction | **Partially Automated** Securiti shows you a report or manifest that identifies the records or objects where it found personal data for the data subject. But unlike automated processing, Securiti does not correct the record. For each object, access the service or database and open the object that Securiti identified. Inspect it for the incorrect data identified by the data subject, and if necessary, correct it and verify the subtask. See [Processing rectification request subtasks](/v1/docs/processing-rectification-request-subtasks) for more information. |
| Confirmation | **Partially Automated** Securiti shows you a report or manifest that identifies by object ID, object name, and object URI the objects where it found personal data for the data subject. For each object, access the service or database to open and inspect the object that Securiti identified. Verify that the personal data is indeed that of the data subject, verify that the processing record is correct, and approve the subtask. See [Processing confirmation request subtasks](/v1/docs/processing-confirmation-request-subtasks) for more information. |
| Do-Not-Sell | **Partially Automated** Securiti shows you a report or manifest that identifies by object ID, object name, and object URI the objects where it found personal data for the data subject. For each object, access the service or database to open and inspect the object that Securiti identified. Verify that the personal data is indeed that of the data subject, verify that the processing record is correct, and approve the subtask. See [Processing confirmation request subtasks](/v1/docs/processing-confirmation-request-subtasks) for more information. |
