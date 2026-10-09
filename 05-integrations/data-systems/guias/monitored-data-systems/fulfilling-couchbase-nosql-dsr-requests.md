---
title: "Fulfilling Couchbase NoSQL DSR requests"
slug: "fulfilling-couchbase-nosql-dsr-requests"
status: "new"
updated: 2026-07-30T10:26:19Z
published: 2026-07-30T10:26:19Z
canonical: "helpcenter.securiti.ai/fulfilling-couchbase-nosql-dsr-requests"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Fulfilling Couchbase NoSQL DSR requests

This article covers the DSR privacy settings and supported DSR request types for couchbase NoSQL.

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

When Securiti accepts a DSR request, it creates a single task and subtask report of the appropriate type for each Couchbase data system instance in the Securiti platform.

The Securiti connector for Couchbase supports all six DSR request types with varying degrees of automation as shown in the following table. Follow the links for specific information about how Securiti handles the request.

| Request type | Automation |
| --- | --- |
| [Access](/v1/docs/couchbase-nosql-access-requests) | Partial |
| [Port](/v1/docs/couchbase-nosql-port-requests) | Partial |
| [Erase](/v1/docs/couchbase-nosql-erasure-requests) | Partial |
| [Rectify](/v1/docs/couchbase-nosql-rectification-requests) | Partial |
| [Object](/v1/docs/couchbase-nosql-objection-requests) | Partial |
| [Restrict](/v1/docs/couchbase-nosql-restriction-requests) | Partial |
