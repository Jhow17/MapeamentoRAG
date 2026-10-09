---
title: "Granting DB permissions for Oracle Autonomous Data Warehouse"
slug: "granting-db-permissions-for-oracle-autonomous-data-warehouse"
updated: 2025-10-31T07:14:59Z
published: 2025-11-03T07:44:50Z
canonical: "helpcenter.securiti.ai/granting-db-permissions-for-oracle-autonomous-data-warehouse"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Granting DB permissions for Oracle Autonomous Data Warehouse

Do the following to grant Oracle Autonomous Data Warehouse Connector Database Permissions.

1. ```
CREATE USER testuser IDENTIFIED BY “password”;
GRANT CREATE SESSION TO testuser;

GRANT CONNECT TO testuser;
GRANT DWROLE TO testuser;
GRANT UNLIMITED TABLESPACE TO testuser;
```
2. Proceed to [Acquire authentication credentials in Oracle Autonomous Data Warehouse](/v1/docs/acquire-authentication-credentials-in-oracle-autonomous-data-warehouse).

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>
