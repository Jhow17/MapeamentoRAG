---
title: "Prerequisites for Amazon DocumentDB connector"
slug: "prerequisites-for-amazon-documentdb-connector"
updated: 2025-10-30T19:05:59Z
published: 2025-11-03T06:13:51Z
canonical: "helpcenter.securiti.ai/prerequisites-for-amazon-documentdb-connector"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Prerequisites for Amazon DocumentDB connector

Following prerequisites must be met before connecting Amazon DocumentDB with Securiti.

- A user with read-only access to all the databases is required.
- You must create an Amazon DocumentDB cluster to connect to Securiti.
- Ensure that you select an EC2 instance to authenticate your DocumentDB cluster with Securiti.
- You must create an EC2 instance or machine in the same Virtual Private Cloud (VPC) as the Amazon DocumentDB cluster. The EC2 instance must be configured to use the same VPC and security groups as the Amazon DocumentDB cluster.

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>

## Related

- [Create an application and obtain authentication credentials in Amazon DocumentDB](/create-an-application-and-obtain-authentication-credentials-in-amazon-documentdb.md)
