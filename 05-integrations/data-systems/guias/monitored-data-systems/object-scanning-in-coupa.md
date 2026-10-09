---
title: "Object scanning in Coupa"
slug: "object-scanning-in-coupa"
updated: 2025-10-30T19:47:53Z
published: 2025-11-03T06:14:10Z
canonical: "helpcenter.securiti.ai/object-scanning-in-coupa"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Object scanning in Coupa

The Coupa connector scans multiple objects for both structured and unstructured data. The connector scans the structured data in Coupa for the following objects:

- Users (list of Coupa users)
- Suppliers (list of suppliers and their PD information)
- Invoices
- Requisitions
- Announcements
- Items
- Inventory transactions
- Purchase orders
- Quote requests
- Quote responses
- Order pads
- Projects
- Addresses
- Accounts
- ASN headers
- Approvals
- Contracts
- Coupa Pay statements
- Coupa Pay payments
- Data file sources
- Expense reports
- Comments

Structured data scanning requires [table training](/v1/docs/table-training-for-structured-and-hybrid-data-systems).

Only *attachments* are scanned as unstructured data.

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>
