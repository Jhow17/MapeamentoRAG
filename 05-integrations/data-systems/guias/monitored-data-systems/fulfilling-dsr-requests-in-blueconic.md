---
title: "Fulfilling DSR requests in Blueconic"
slug: "fulfilling-dsr-requests-in-blueconic"
updated: 2026-06-10T18:45:27Z
published: 2026-06-10T18:45:27Z
canonical: "helpcenter.securiti.ai/fulfilling-dsr-requests-in-blueconic"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Fulfilling DSR requests in Blueconic

This article covers the DSR privacy settings and supported DSR request types for Blueconic.

## DSR Privacy Settings

In the **Privacy** tab, configure the following settings for the **DSR Scan:**

> [!WARNING]
> **Important**
> 
> Blueconic (Securiti Cloud) is a scanless connector where DSR Automation is performed using smart search APIs. Scanless connectors do not support data or DSR scans.

| Parameter | Description |
| --- | --- |
| Include this instance in the DSR Workflow | Enabling this option includes the respective data system in processing the DSR request. > [!WARNING] > **Important** > > For unstructured data system instances, the DSR workbench creates subtasks only if data is found in the data search. If no data is found, tasks are not created. |
| Guest Users | Enable this to automatically assign DSR subtasks created for the data system to guest users. See [Automatically assign DSR subtasks to guest users](/v1/docs/automatically-assigning-dsr-subtasks-to-guest-users), for more information. |
| Guest User Guidance Text | Enter the guidance text for guest users to fulfil DSR requests. |
| Limit Guest access to specific DSR types | If selected, collaborators will automatically be assigned only to the requests of the selected DSR types |

## Supported DSR Types

When Securiti accepts a DSR request, it creates a single task, with subtasks of the appropriate DSR types for each Blueconic data system instance in the Securiti platform.

The Securiti connector for Blueconic supports the various DSR request types with varying degrees of automation as described in the table below.

| DSR Type | Automation |
| --- | --- |
| Access | **Automated** Securiti automatically extracts and attaches one or more Auto-generated PD reports showing all the personal data associated with the data subject. Verify that the data belongs to the data subject and that the processing record describes the processing, and if so, approve the subtask. See [Processing access request subtasks](/v1/docs/processing-access-request-subtasks) for more information. |
| Port | **Automated** Securiti automatically extracts and attaches one or more Auto-generated PD reports showing all the personal data associated with the data subject. Verify that the data belongs to the data subject and that the processing record describes the processing, and if so, approve the subtask. > [!NOTE] > **Note** > > For port requests, regulations don't require you to provide the context around which the data is processed within your organization. Therefore, port subtasks do not include a process record. See [Processing port request subtasks](/v1/docs/processing-port-request-subtasks) for more information. |
| Erasure | **Automated** Securiti first initiates an access request to test whether the data system contains instances of the specified identity. If so, it then initiates the erasure request and shows you a report that tells you whether it erased the personal data automatically. It may indicate that erasure is scheduled, but has not yet taken place. Verify that the personal data has been erased, and if so, approve the subtask. See [Processing erasure request subtasks](/v1/docs/processing-erasure-request-subtasks) for more information. |
