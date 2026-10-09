---
title: "Fulfilling DSR requests for Workday"
slug: "fulfilling-dsr-requests-for-workday"
updated: 2026-07-31T14:05:22Z
published: 2026-07-31T14:05:22Z
canonical: "helpcenter.securiti.ai/fulfilling-dsr-requests-for-workday"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Fulfilling DSR requests for Workday

## DSR scan configuration

In the **Privacy** tab, configure the following settings for the **DSR Scan:**

| Parameter | Description |
| --- | --- |
| Include this instance in the DSR Workflow | Enabling this option includes the respective data system in processing the DSR request. > [!WARNING] > **Important** > > For unstructured data system instances, the DSR workbench creates subtasks only if data is found in the data search. If no data is found, tasks are not created. |
| Guest Users | Enable this to automatically assign DSR subtasks created for the data system to guest users. See [Automatically assign DSR subtasks to guest users](/v1/docs/automatically-assigning-dsr-subtasks-to-guest-users), for more information. |
| Guest User Guidance Text | Enter the guidance text for guest users to fulfil DSR requests. |
| Limit Guest access to specific DSR types | If selected, collaborators will automatically be assigned only to the requests of the selected DSR types |

## Supported DSR types

When Securiti accepts a DSR request, it creates a single task, with subtasks of the appropriate DSR types for each Workday Data system Instance in the Securiti platform.

> [!WARNING]
> Important
> 
> Securiti only retrieves structured data for Workday connector’s DSR requests.

The Securiti Connector for Workday supports the various DSR request types with varying degrees of automation described in the Table below.

| DSR Type | Automation |
| --- | --- |
| Access | **Automated** Securiti automatically extracts and attaches one or more Auto-generated PD reports showing all the personal data associated with the data subject. Verify that the data belongs to the data subject and that the processing record describes the processing, and if so, approve the subtask. See [Processing access request subtasks](/v1/docs/processing-access-request-subtasks) for more information. |
| Port | **Automated** Securiti automatically extracts and attaches one or more Auto-generated PD reports showing all the personal data associated with the data subject. Verify that the data belongs to the data subject and that the processing record describes the processing, and if so, approve the subtask. > [!NOTE] > **Note** > > For port requests, regulations don't require you to provide the context around which the data is processed within your organization. Therefore, port subtasks do not include a process record. See [Processing port request subtasks](/v1/docs/processing-port-request-subtasks) for more information. |
