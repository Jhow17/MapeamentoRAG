---
title: "Fulfilling DSR requests for Zendesk"
slug: "fulfilling-dsr-requests-for-zendesk-self-hosted"
updated: 2026-06-27T08:17:00Z
published: 2026-06-27T08:17:00Z
canonical: "helpcenter.securiti.ai/fulfilling-dsr-requests-for-zendesk-self-hosted"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Fulfilling DSR requests for Zendesk

This article covers the DSR privacy settings and supported DSR request types for Zendesk.

## DSR Privacy Settings

In the **Privacy** tab, configure the following settings for the **DSR Scan:**

| **Parameter** | **Description** |
| --- | --- |
| Include this instance in the DSR Workflow | Enable this option to include the respective data system in processing the DSR request. > [!WARNING] > **Important** > > For structured data system instances, Securiti creates subtasks in the DSR workbench. If no data is found during the data search, the subtasks are automatically deleted. |
| Allow Multi Column Join DSR | Enable this to combine data from multiple tables based on the values in more than one column. It enables AND condition in the DSR joins |
| Guest Users | Enable this to automatically assign DSR subtasks created for the data system to guest users. See [Automatically assign DSR subtasks to guest users](https://portal.us.document360.io/v1/docs/automatically-assigning-dsr-subtasks-to-guest-users), for more information. |
| Guest User Guidance Text | Enter the guidance text for guest users to fulfill DSR requests. |
| Limit Guest access to specific DSR types | If selected, collaborators will automatically be assigned only to the requests of the selected DSR types |

## Supported DSR Types

When Securiti accepts a DSR request, it creates a single task, with subtasks of the appropriate DSR types for each Zendesk (Self-hosted) Data system Instance in the Securiti platform.

The Securiti Connector for Zendesk (Self-hosted) supports the various DSR request types with varying degrees of automation described in the Table below.

| DSR Type | Automation |
| --- | --- |
| Access | **Automated** Securiti automatically extracts and attaches one or more Auto-generated PD reports showing all the personal data associated with the data subject. Verify that the data belongs to the data subject and that the processing record describes the processing, and if so, approve the subtask. See [Processing access request subtasks](/v1/docs/processing-access-request-subtasks) for more information. |
| Erasure | **Automated** Securiti first initiates an access request to test whether the data system contains instances of the specified identity. If so, it then initiates the erasure request and shows you a report that tells you whether it erased the personal data automatically. It may indicate that erasure is scheduled, but has not yet taken place. Verify that the personal data has been erased, and if so, approve the subtask. See [Processing erasure request subtasks](/v1/docs/processing-erasure-request-subtasks) for more information. |
