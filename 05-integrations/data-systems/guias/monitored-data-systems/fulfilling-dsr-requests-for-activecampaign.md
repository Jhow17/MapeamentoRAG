---
title: "Fulfilling DSR requests for ActiveCampaign"
slug: "fulfilling-dsr-requests-for-activecampaign"
updated: 2025-10-30T18:59:29Z
published: 2025-11-03T06:13:35Z
canonical: "helpcenter.securiti.ai/fulfilling-dsr-requests-for-activecampaign"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Fulfilling DSR requests for ActiveCampaign

When Securiti accepts a DSR request, it creates a single task and subtask of the appropriate type for each ActiveCampaign data system instance in the Securiti platform.

The Securiti connector for ActiveCampaign supports the various DSR request types with varying degrees of automation as described in the table below.

| DSR Type | Automation |
| --- | --- |
| Access | **Automated** Securiti automatically extracts and attaches one or more Auto-generated PD reports showing all the personal data associated with the data subject. Verify that the data belongs to the data subject and that the processing record describes the processing, and if so, approve the subtask. See [Processing access request subtasks](/v1/docs/processing-access-request-subtasks) for more information. |
| Port | **Automated** Securiti automatically extracts and attaches one or more Auto-generated PD reports showing all the personal data associated with the data subject. Verify that the data belongs to the data subject and that the processing record describes the processing, and if so, approve the subtask. > [!NOTE] > **Note** > > For port requests, regulations don't require you to provide the context around which the data is processed within your organization. Therefore, port subtasks do not include a process record. See [Processing port request subtasks](/v1/docs/processing-port-request-subtasks) for more information. |
| Erasure | **Partially Automated** Securiti shows you a report or manifest that identifies the records or objects where it found personal data for the data subject. But unlike automated processing, Securiti does not erase the record. For each object, access the service or database to open and inspect the object that Securiti variables: Platform name identified. If it belongs to the data subject, delete it and verify the subtask. See [Processing erasure request subtasks](/v1/docs/processing-erasure-request-subtasks) for more information. |
| Rectification | **Manual** Securiti identifies the data system as a location that might contain personal data for the data subject. Since Securiti cannot access the data system, you must do so manually to check for the incorrect data identified by the data subject. Access the data system and search it for any records matching the data subject that contain the incorrect data. If you find such a record, correct it and verify the subtask. See [Processing rectification request subtasks](/v1/docs/processing-rectification-request-subtasks) for more information. |
| Objection | **Manual** Securiti identifies the data system as a location that might contain personal data for the data subject. But Securiti cannot access the data system and resolve the objection, so you must do so manually and check for any records associated with the data subject. Use your internal company processes to identify all groups processing the data subject’s personal data from that data system, and alert them to stop processing the data. Then approve the subtask. See [Processing objection request subtasks](/v1/docs/processing-objection-request-subtasks) for more information. |
| Restriction | **Manual** Securiti identifies the data system as a location that might contain personal data for the data subject. Since Securiti cannot access the data system, you must do so manually to check for any records associated with the data subject. Use your internal company processes to identify all groups processing the data subject’s personal data from that data system, and alert them to stop processing the data. Then approve the subtask. See [Processing restriction request subtasks](/v1/docs/processing-restriction-request-subtasks) for more information. |
| Confirmation | **Automated** Securiti automatically extracts and attaches one or more Auto-generated PD reports showing all the personal data associated with the data subject. Verify that the data belongs to the data subject and that the processing record describes the processing, and if so, approve the subtask. See [Processing confirmation request subtasks](/v1/docs/processing-confirmation-request-subtasks) for more information. |
| Do-Not-Sell | **Manual** Securiti identifies the data system as a location that might contain personal data for the data subject. Since Securiti cannot access the data system, you must do so manually to check for any records associated with the data subject. Use your internal company processes to identify all groups that might sell the data subject’s personal data from that data system and alert them to stop selling that data. Then approve the subtask.. See [Processing do-not-sell request subtasks](/v1/docs/processing-do-not-sell-or-share-request-subtasks) for more information. |
