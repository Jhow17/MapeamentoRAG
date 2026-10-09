---
title: "Alibaba Cloud OSS"
slug: "alibaba-cloud-oss-connectors-1"
status: "new"
updated: 2026-07-15T09:48:52Z
published: 2026-07-15T09:49:07Z
canonical: "helpcenter.securiti.ai/alibaba-cloud-oss-connectors-1"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Alibaba Cloud OSS

Alibaba Cloud OSS falls under the category of Monitored, unstructured data systems, as shown in the table below.

| **Data system type** | **Characteristics** |
| --- | --- |
| Monitored | Scanless data systems | Connect with data systems that respond to queries on specific elements of personal data. Because Securiti can query them in real-time as DSR requests come in, it doesn’t have to scan them ahead of time and establish an internal inventory of personal data. |
| Unstructured data systems | Connect with data systems that store unstructured data and must be periodically scanned for PI content. |
| Structured data systems | Connect with structured data systems that permit selective scanning to build identities from the records they contain, but also respond to queries on specific elements of personal data and can therefore support automation for DSR requests. |
| Streaming | Connect with streaming data systems to identify sensitive data upstream in the data pipeline, and optionally protect it via masking. |
| Unmonitored | Data systems that Securiti does not connect with and has no visibility into. You define these data systems as placeholders so that Securiti can alert subtask owners to check them for personal data when DSR requests come in. |
| User-defined | Connect with your proprietary data system using webhooks (reverse APIs) that your IT teams develop to interface with Securiti. |

## Steps to connect Alibaba Cloud OSS with Securiti

To configure the Alibaba Cloud OSS connector, perform the procedures in the following topics:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. [Acquire authentication credentials in Alibaba Cloud OSS](/latest/docs/acquire-authentication-credentials-in-alibaba-cloud-oss).
3. [Connecting Alibaba Cloud OSS with Securiti.](/latest/docs/connecting-alibaba-cloud-oss-with-securiti)
4. [Configure discovery scans for Alibaba Cloud OSS](/latest/docs/configure-discovery-scans-for-alibaba-cloud-oss)

### Additional resources

- [Fulfilling DSR requests in Alibaba OSS](/latest/docs/fulfilling-dsr-requests-in-alibaba-oss)

The cloud term typically refers to cloud computing. Cloud computing is a technology that allows users to access and use computing resources and services over the internet, often from remote data centers.

A collection of organized data or repositories and their corresponding management software, which could be IaaS, SaaS, or SQL. Data systems are configured in Securiti so that it can help you protect sensitive data and also locate personal data for data subjects who submit DSR requests. Data systems can be monitored, un-monitored, or user-defined. For each monitored or user-defined data system, you configure a connector that Securiti uses to interact with the data system.

Data systems which do not undergo scanning of data as Securiti can query them in real-time as DSR requests come in and respond to queries on specific elements of personal data.

An unstructured data systems refers to the systems that are used to store unstructured data. The most common examples of unstructured data include Microsoft OneDrive, Google Drive, AWS S3, and so on.

Personal Information. Sensitive information that pertains to an individual such as name, data of birth, phone number, etc.

Structured data systems refer to the systems that are used to store structured data in the form of databases, tables, and schemas. The most common examples of unstructured data include MySQL, Oracle, Snowflake, and so on.

Type of data that is transmitted continuously or in real-time. Examples of streaming data include website activity tracking, message, etc. Examples of Streaming data systems include, Kafka.

## Related

- [Acquire authentication credentials in Alibaba Cloud OSS](/acquire-authentication-credentials-in-alibaba-cloud-oss.md)
- [Configure discovery scans for Alibaba Cloud OSS](/configure-discovery-scans-for-alibaba-cloud-oss.md)
- [Fulfilling DSR requests in Alibaba OSS](/fulfilling-dsr-requests-in-alibaba-oss.md)
