---
title: "Universal Consent Management API reference"
slug: "universal-consent-management-api-reference"
description: "Universal Consent Management REST APIs for consent collection, ingestion, retrieval, and deletion. Manage consent records, purposes, sources, preference centers, bulk uploads, and consent status. /privaci/v1/consentapi/"
tags: ["API Documentation", "Consent Management", "Consent Records"]
updated: 2026-07-20T08:38:51Z
published: 2026-07-20T08:38:51Z
canonical: "helpcenter.securiti.ai/universal-consent-management-api-reference"
area: privacy
modulo: universal-consent-management
tipo: api
data_captura: 2026-10-08
---

# Universal Consent Management API reference

The [Universal Consent Management APIs](https://securiti-doc-router.securiti.ai/modules/universal-consent/apidocs/index.html) let you collect and manage consent records through API-based ingestion, fetch consent records, and delete consent records. You can also manage processing purposes, consent purposes, custom parameters, API consent sources, and generate success page magic links.

This API documentation includes operations such as:

- Manage consent records:
  - Upload individual consent records
  - Upload consent records in bulk using **JSON** or **CSV** data
  - Upload consent records with **Custom Parameters**
  - Upload consent records via **Rules Matrix**
  - Fetch all uploaded consent records
  - Fetch consent records by UUID
  - Fetch latest consent status by **UUID** and **Preference Center ID**
  - Fetch latest user consent using customizable filters
  - Delete consent records
  - Cancel an ongoing consent deletion process
- Create, fetch, update, or delete:
  - **Processing Purposes** by name or ID
  - **Consent Purposes** by name or ID
  - **Processing Purpose Categories**
  - **Custom Parameters**
  - **Consent API Sources**
- Generate:
  - **Universal Preference Center** magic links
  - **Consent Success Page** links

Use the [Universal Consent Management REST API documentation](https://securiti-doc-router.securiti.ai/modules/universal-consent/apidocs/index.html) to explore and test the APIs, review `HTTP` endpoints, sample API request and response body schemas, query parameters, path parameters, and authentication methods. You can also access **Postman Collection** to review, and test API responses before integration.

Universally Unique Identifier (UUID) is an alphanumeric string that is used to identify information in computer systems. For instance, they are often used to identify rows of data within a database table, with each row assigned a specific UUID.
