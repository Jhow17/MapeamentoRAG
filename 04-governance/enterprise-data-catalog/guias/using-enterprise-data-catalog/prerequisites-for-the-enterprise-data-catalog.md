---
title: "Prerequisites for the Enterprise Data Catalog"
slug: "prerequisites-for-the-enterprise-data-catalog"
updated: 2026-07-22T13:13:24Z
published: 2026-07-22T13:13:24Z
canonical: "helpcenter.securiti.ai/prerequisites-for-the-enterprise-data-catalog"
stale: true
area: governance
modulo: enterprise-data-catalog
tipo: guia
data_captura: 2026-10-08
---

# Prerequisites for the Enterprise Data Catalog

- You must integrate your cloud account into Securiti.
- You must have an Enterprise Data Catalog subscription. In the Enterprise Data Catalog, if you want to group data by Domain, you must create a domain before ingestion of the dataset to avoid assigning them manually later.
- For the business metadata, that is glossaries, you must document what glossaries are required and if needed map to datasets, technical metadata. Moreover, you must also document any special access restrictions to the metadata in order to create the necessary metadata policies.
- You must have a subscription for the [Sensitive Data Intelligence](/latest/docs/using-sensitive-data-intelligence) module to perform the following actions:
  - Configure data systems.
  - Configure the discovery scan and enable the Register data assets into the Data Catalog toggle. You can configure this section as per your needs.
  - Run a fresh scan to add the datasets to the EDC.
- You must configure [private cloud storage](/latest/docs/private-cloud-storage) to successfully implement inferred lineage and bulk load capabilities for both datasets and glossary terms.

Domain is a logical or thematic grouping of related data assets. Domains are used to categorize and organize data assets based on their subject matter or the business context they belong to. For example, you might have a Finance domain that includes data related to financial transactions, reports, and analysis, or a Human Resources domain that encompasses data related to employee information, payroll, and HR processes.
