---
title: "Fulfilling DSR requests for Segment"
slug: "fulfilling-dsr-requests-for-segment"
updated: 2026-06-20T09:41:19Z
published: 2026-06-20T09:41:19Z
canonical: "helpcenter.securiti.ai/fulfilling-dsr-requests-for-segment"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Fulfilling DSR requests for Segment

This article covers the DSR privacy settings and supported DSR request types for Segment.

## DSR Privacy Settings

In the **Privacy** tab, configure the following settings for the **DSR Scan:**

| Parameter | Description |
| --- | --- |
| Include this instance in the DSR Workflow | Enabling this option includes the respective data system in processing the DSR request. > [!WARNING] > **Important** > > For unstructured data system instances, the DSR workbench creates subtasks only if data is found in the data search. If no data is found, tasks are not created. |
| Guest Users | Enable this to automatically assign DSR subtasks created for the data system to guest users. See [Automatically assign DSR subtasks to guest users](/v1/docs/automatically-assigning-dsr-subtasks-to-guest-users), for more information. |
| Guest User Guidance Text | Enter the guidance text for guest users to fulfil DSR requests. |
| Limit Guest access to specific DSR types | If selected, collaborators will automatically be assigned only to the requests of the selected DSR types |

## Supported DSR Types

When Securiti accepts a DSR request, it creates a single task, with subtasks of the appropriate DSR types for each Segment Data system Instance in the Securiti platform.

The Securiti Connector for Segment supports the various DSR request types with varying degrees of automation described in the Table below.

| DSR Type | Automation |
| --- | --- |
| Access | **Manual** Securiti identifies the data system as a location that might contain personal data for the data subject. Access the data system and search it for any personal data of the data subject. If you find any, you upload a document containing it, verify that the processing record is correct, and approve the subtask. See [Processing access request subtasks](/v1/docs/processing-access-request-subtasks) for more information. |
| Port | **Manual** Securiti identifies the data system as a location that might contain personal data for the data subject. Access the data system and search it for any personal data of the data subject. If you find any, upload a document containing it and approve the subtask. > [!NOTE] > **Note**: > > For port requests, regulations don't require you to provide the context around which the data is processed within your organization. Therefore port subtasks do not include a process record. See [Processing port request subtasks](/v1/docs/processing-port-request-subtasks) for more information. |
| Erasure | **Automated** Securiti first initiates an access request to test whether the data system contains instances of the specified identity. If so, it then initiates the erasure request and shows you a report that tells you whether it erased the personal data automatically. It may indicate that erasure is scheduled, but has not yet taken place. Verify that the personal data has been erased, and if so, approve the subtask. See [Processing erasure request subtasks](/v1/docs/processing-erasure-request-subtasks) for more information. |
| Rectification | **Manual** Securiti identifies the data system as a location that might contain personal data for the data subject. Since Securiti cannot access the data system, you must do so manually to check for the incorrect data identified by the data subject. Access the data system and search it for any records matching the data subject that contain the incorrect data. If you find such a record, correct it and verify the subtask. See [Processing rectification request subtasks](/v1/docs/processing-rectification-request-subtasks) for more information. |
| Objection | **Manual** Securiti identifies the data system as a location that might contain personal data for the data subject. But Securiti cannot access the data system and resolve the objection, so you must do so manually and check for any records associated with the data subject. Use your internal company processes to identify all groups processing the data subject’s personal data from that data system, and alert them to stop processing the data. Then approve the subtask. See [Processing objection request subtasks](/v1/docs/processing-objection-request-subtasks) for more information. |
| Restriction | **Manual** Securiti identifies the data system as a location that might contain personal data for the data subject. Since Securiti cannot access the data system, you must do so manually to check for the incorrect data identified by the data subject. Access the data system and search it for any records matching the data subject that contain the incorrect data. If you find such a record, correct it and verify the subtask. See [Processing rectification request subtasks](/v1/docs/processing-rectification-request-subtasks) for more information. |
| Confirmation | **Manual** Securiti identifies the data system as a location that might contain personal data for the data subject. Access the data system and search it for any personal data of the data subject. If you find any, verify that the processing record is correct, and approve the subtask. See [Processing confirmation request subtasks](/v1/docs/processing-confirmation-request-subtasks) for more information. |
| Do-Not-Sell | **Manual** Securiti identifies the data system as a location that might contain personal data for the data subject. Since Securiti cannot access the data system, you must do so manually to check for any records associated with the data subject. Use your internal company processes to identify all groups that might sell the data subject’s personal data from that data system and alert them to stop selling that data. Then approve the subtask.. See [Processing do-not-sell request subtasks](/v1/docs/processing-do-not-sell-or-share-request-subtasks) for more information. |
| Disclose subprocessors | **Manual** Securiti identifies the data system as a location that might contain personal data for the data subject. Access the data system and search it for any personal data of the data subject. If you find any, verify that the data belongs to the data subject. If so, use the Identify Sub-Processors tools to build a list of subprocessors with whom your organization has shared the personal data of the data subject. Then approve the subtask. See [Processing disclosure of subprocessor subtasks](/v1/docs/processing-disclosure-of-subprocessors-tasks) for more information. ### |
