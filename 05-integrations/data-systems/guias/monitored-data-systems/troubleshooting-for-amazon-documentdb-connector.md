---
title: "Troubleshooting for Amazon DocumentDB connector"
slug: "troubleshooting-for-amazon-documentdb-connector"
updated: 2025-10-30T19:06:33Z
published: 2025-11-03T06:13:51Z
canonical: "helpcenter.securiti.ai/troubleshooting-for-amazon-documentdb-connector"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Troubleshooting for Amazon DocumentDB connector

This section covers troubleshooting for the following issues when configuring Amazon DocumentDB data system connector.

#### Unable to connect to database

Perform troubleshooting for your connector, if you see the below error in the autodiagnostic report for your Amazon DocumentDB connector.

*No tables discovered (or) invalid database.*

Check for the following causes of error:

- Incorrect credentials for the Amazon DocumentDB cluster. Reconfigure the connector with correct credentials to resolve the error.
- **Use SSL** toggle is disabled for the connector but SSL is enabled for the Amazon DocumentDB cluster. Reconfigure the connector and enable the **Use SSL** toggle to resolve the error.
- Amazon DocumentDB cluster is being connected from outside the Virtual Private Cloud (VPC). Reconfigure the connector and provide EC2 machine SSH credentials that are on same the VPC as that of Amazon DocumentDB cluster, to resolve the error.

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>
