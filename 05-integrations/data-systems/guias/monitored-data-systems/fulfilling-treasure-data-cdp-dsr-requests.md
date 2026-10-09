---
title: "Fulfilling Treasure Data CDP DSR requests"
slug: "fulfilling-treasure-data-cdp-dsr-requests"
updated: 2026-06-28T14:23:22Z
published: 2026-06-28T14:23:22Z
canonical: "helpcenter.securiti.ai/fulfilling-treasure-data-cdp-dsr-requests"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Fulfilling Treasure Data CDP DSR requests

This article covers the DSR privacy settings and supported DSR request types for Treasure Data CDP.

## DSR Privacy Settings

In the **Privacy** tab, configure the following settings for the **DSR Scan:**

| Parameter | Description |
| --- | --- |
| Include this instance in the DSR Workflow | To include the respective data system in processing the DSR request, enable this option. > [!WARNING] > **Important** > > For structured data system instances, Securiti creates subtasks in the DSR workbench. If no data is found during the data search, the subtasks are automatically deleted. |
| Allow Multi Column Join DSR | Enable this to combine data from multiple tables based on the values in more than one column. It enables AND condition in the DSR joins. |
| Require indices on primary identifier columns | Enable this if you require an index to exist on primary identifier columns such as SSN or Email address, for any DSR to improve the speed of data retrieval operations. Enabling this option makes the DSR run more efficiently. |
| Require database indexes for SQL table joins | Enable this option to limit the joins in the generated SQL queries to only tables that have indexes on joined columns. |
| Maximum depth for SQL table relations | This is the maximum depth to which relations between tables will be considered for JOIN clauses in the SQL queries generated for DSR automation. Lowering the depth speeds up automation and eases the load on the database server. Configure this value to suit. |
| Guest Users | Enable this to automatically assign DSR subtasks created for the data system to guest users. See [Automatically assign DSR subtasks to guest users](/v1/docs/automatically-assigning-dsr-subtasks-to-guest-users), for more information. |
| Guest User Guidance Text | Enter the guidance text for guest users to fulfill DSR requests. |
| Limit Guest access to specific DSR types | Enable this toggle to assign only specific DSR types to the collaborators. |

## Supported DSR Types

When Securiti accepts a DSR request, it creates a single task, with subtasks of the appropriate DSR types for each Treasure Data CDP Data system Instance in the Securiti platform.

The Securiti Connector for Treasure Data CDP supports the various DSR request types with varying degrees of automation as described in the Table below.

| DSR Type | Automation |
| --- | --- |
| Access | **Automated** Securiti automatically extracts and attaches one or more Auto-generated PD reports showing all the personal data associated with the data subject. Verify that the data belongs to the data subject and that the processing record describes the processing, and if so, approve the subtask. See [Processing access request subtasks](/v1/docs/processing-access-request-subtasks) for more information. |
