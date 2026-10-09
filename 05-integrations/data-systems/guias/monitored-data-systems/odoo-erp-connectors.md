---
title: "Odoo ERP"
slug: "odoo-erp-connectors"
status: "new"
updated: 2026-07-16T07:25:34Z
published: 2026-07-16T07:25:37Z
canonical: "helpcenter.securiti.ai/odoo-erp-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Odoo ERP

Odoo ERP falls under the category of Monitored, Structured data systems, as shown in the table below:

| **Data system type** | **Characteristics** |
| --- | --- |
| Monitored | Scanless data systems | Connect with data systems that respond to queries on specific elements of personal data. Because Securiti can query them in real-time as DSR requests come in, it doesn’t have to scan them ahead of time and establish an internal inventory of personal data. |
| Unstructured data systems | Connect with data systems that store unstructured data and must be periodically scanned for PI content. |
| Structured data systems | Connect with structured data systems that permit selective scanning to build identities from the records they contain, but also respond to queries on specific elements of personal data and can therefore support automation for DSR requests. |
| Streaming | Connect with streaming data systems to identify sensitive data upstream in the data pipeline, and optionally protect it via masking. |
| Unmonitored | Data systems that Securiti does not connect with and has no visibility into. You define these data systems as placeholders so that Securiti can alert subtask owners to check them for personal data when DSR requests come in. |
| User-defined | Connect with your proprietary data system using webhooks (reverse APIs) that your IT teams develop to interface with Securiti. |

To configure the Odoo ERP connector, perform the following procedures in sequence:

1. [Grant permissions and obtain credentials in Odoo ERP](/v1/docs/grant-permissions-and-obtain-credentials-in-odoo-erp).
2. [Activate the Odoo ERP connector in Securiti](/v1/docs/activate-the-odoo-erp-connector-in-securiti).
3. [Initiate Odoo ERP learning](/v1/docs/initiate-odoo-erp-learning).

See [Fulfilling DSR requests for Odoo ERP](/v1/docs/fulfilling-dsr-requests-for-odoo-erp) for more information about how Securiti uses the Odoo ERP data to respond to DSR requests.
