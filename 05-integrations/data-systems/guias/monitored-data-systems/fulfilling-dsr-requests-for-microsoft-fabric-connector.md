---
title: "Fulfilling DSR requests for Microsoft Fabric connector"
slug: "fulfilling-dsr-requests-for-microsoft-fabric-connector"
updated: 2026-02-08T13:42:52Z
published: 2026-02-09T20:00:06Z
canonical: "helpcenter.securiti.ai/fulfilling-dsr-requests-for-microsoft-fabric-connector"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Fulfilling DSR requests for Microsoft Fabric connector

This article covers the DSR privacy settings and supported DSR request types for Microsoft Fabric.

> [!WARNING]
> Important
> 
> If the new UI isn't available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements to activate it.

## DSR Privacy Settings

In the **Connectors** tab (for Classic UI), or in the **Privacy** tab (for New UI), configure the following settings for the **DSR Scan:**

| Parameter | Description |
| --- | --- |
| Include this instance in the DSR Workflow | Enabling this option includes the respective data system in processing the DSR request. > [!WARNING] > **Important** > > For unstructured data system instances, the DSR workbench creates subtasks only if data is found in the data search. If no data is found, tasks are not created. |
| Guest Users | Enable this to automatically assign DSR subtasks created for the data system to guest users. See [Automatically assign DSR subtasks to guest users](/v1/docs/automatically-assigning-dsr-subtasks-to-guest-users), for more information. |
| Guest User Guidance Text | Enter the guidance text for guest users to fulfil DSR requests. |
| Limit Guest access to specific DSR types | If selected, collaborators will automatically be assigned only to the requests of the selected DSR types |

## Supported DSR Types

When Securiti accepts a DSR request, it creates a single task, with subtasks of the appropriate DSR types for each Microsoft Fabric data system instances in the Securiti platform.

The Securiti connectors for Microsoft Fabric support the various DSR request types with varying degrees of automation, as described in the table below.

| DSR Type | Automation |
| --- | --- |
| Access | **Partially Automated** Securiti shows you a report or manifest that identifies the objects where it found personal data for the data subject. For each object, access the service or database to open and inspect the object that Securiti identified. Remove any extraneous sensitive data, verify that the processing record is correct, and approve the subtask. See [Processing access request subtasks](/v1/docs/processing-access-request-subtasks) for more information. |
| Port | **Partially Automated** Securiti shows you a report or manifest that identifies the objects where it found personal data for the data subject. For each object, access the service or database to open and inspect the object that Securiti name identified. Redact any extraneous sensitive data, attach the redacted data, and approve the subtask. > [!NOTE] > **Note** > > For port requests, regulations don't require you to provide the context around which the data is processed within your organization. Therefore port subtasks do not include a process record. See [Processing port request subtasks](/v1/docs/processing-port-request-subtasks) for more information. |
| Erasure | **Partially Automated** Securiti shows you a report or manifest that identifies the records or objects where it found personal data for the data subject. But unlike automated processing, Securiti does not erase the record. For each object, access the service or database to open and inspect the object that Securiti variables: Platform name identified. If it belongs to the data subject, delete it and verify the subtask. See [Processing erasure request subtasks](/v1/docs/processing-erasure-request-subtasks) for more information. |
| Rectification | **Partially Automated** Securiti shows you a report or manifest that identifies the records or objects where it found personal data for the data subject. But unlike automated processing, Securiti does not correct the record. For each object, access the service or database and open the object that Securiti identified. Inspect it for the incorrect data identified by the data subject, and if necessary, correct it and verify the subtask. See [Processing rectification request subtasks](/v1/docs/processing-rectification-request-subtasks) for more information. |
| Objection | **Partially Automated** The existence of the subtask indicates that Securiti found the data subject’s information within the data system. For some data system types, Securiti may also show you a manifest of the object or record where the data was found. For some data system types, Securiti may also show you a manifest of the object or record where the data was found. Use your internal company processes to identify all groups processing the data subject’s personal data from that data system, and alert them to stop processing the data. Then approve the subtask. See [Processing objection request subtasks](/v1/docs/processing-objection-request-subtasks) for more information. |
| Restriction | **Partially Automated** The existence of the subtask indicates that Securiti found the data subject’s information within the data system. For some data system types, Securiti may also show you a report or manifest of the object or record where the data was found. Use your internal company processes to identify all groups processing the data subject’s personal data from that data system, and alert them to stop processing the data. Then approve the subtask. See [Processing restriction request subtasks](/v1/docs/processing-restriction-request-subtasks) for more information. |
| Confirmation | **Partially Automated** Securiti shows you a report or manifest that identifies by object ID, object name, and object URI the objects where it found personal data for the data subject. For each object, access the service or database to open and inspect the object that Securiti identified. Verify that the personal data is indeed that of the data subject, verify that the processing record is correct, and approve the subtask. See [Processing confirmation request subtasks](/v1/docs/processing-confirmation-request-subtasks) for more information. |
| Do-Not-Sell | **Partially Automated** The existence of the subtask indicates that Securiti found the data subject’s information within the data system. For some data system types, Securiti may also show you a report or manifest of the object or record where the data was found. Use your internal company processes to identify all groups processing the data subject’s personal data from that data system, and alert them to stop selling that data. Then approve the subtask. See [Processing do-not-sell request subtasks](/v1/docs/processing-do-not-sell-or-share-request-subtasks) for more information. |
