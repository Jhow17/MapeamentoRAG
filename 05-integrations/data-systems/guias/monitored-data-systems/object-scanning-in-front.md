---
title: "Object scanning in Front"
slug: "object-scanning-in-front"
updated: 2026-07-20T12:23:01Z
published: 2026-07-20T21:00:00Z
canonical: "helpcenter.securiti.ai/object-scanning-in-front"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Object scanning in Front

The Front connector scans multiple objects for both structured and unstructured data.

## Structured data objects

The connector scans the structured data in Front for the following objects:

- Teammates
- Contacts

> [!NOTE]
> Note
> 
> When you delete a teammate or contact, make sure you delete private data and conversations associated with them.
> 
> Structured data scanning requires [table training](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems).

## Unstructured data objects

The connector scans the unstructured data in Front for the following objects:

- Comments
- Messages
- Attachments

> [!NOTE]
> Note
> 
> Connector scans update and delete events only for the conversations. It does not apply to messages, comments, and attachments.
