---
title: "Core concepts"
slug: "core-concepts"
updated: 2026-01-07T12:30:53Z
published: 2026-01-07T12:30:53Z
canonical: "helpcenter.securiti.ai/core-concepts"
area: governance
modulo: enterprise-data-catalog
tipo: guia
data_captura: 2026-10-08
---

# Core concepts

Enterprise Data Catalog module is where data users can come to find data and get answers to questions about the data. The metadata is stored using a data model using the following abstractions:

| Name | Description |
| --- | --- |
| Entities | An Entity is the primary node in the metadata graph. For example, an instance of a dataset or a glossary term is an entity. An entity is made up of a type (for example dataset), a unique identifier (for example an URN), and groups of metadata attributes (for example documents) which we call aspects. |
| Aspects | An aspect is a collection of attributes that describes a particular facet of an entity. They are the smallest atomic unit of writing in the Enterprise Data Catalog. That is, multiple aspects associated with the same Entity can be updated independently. Aspect can be shared across entities, for example **Ownership** is an aspect that is reused across all the Entities that have owners. Common aspects include: - [Ownership](https://github.com/datahub-project/datahub/blob/master/metadata-models/src/main/pegasus/com/linkedin/common/Ownership.pdl): Captures the users and groups who own an entity. - [GlobalTags](https://github.com/datahub-project/datahub/blob/master/metadata-models/src/main/pegasus/com/linkedin/common/GlobalTags.pdl): Captures references to the tags associated with an entity. - [GlossaryTerms](https://github.com/datahub-project/datahub/blob/master/metadata-models/src/main/pegasus/com/linkedin/common/GlossaryTerms.pdl): Captures references to the glossary terms associated with an entity. - [InstitutionalMemory](https://github.com/datahub-project/datahub/blob/master/metadata-models/src/main/pegasus/com/linkedin/common/InstitutionalMemory.pdl): Captures internal company documents associated with an entity (for example links). - [Status](https://github.com/datahub-project/datahub/blob/master/metadata-models/src/main/pegasus/com/linkedin/common/Status.pdl): Captures the **deletion** status of an entity, that is whether it should be soft-deleted. - [SubTypes](https://github.com/datahub-project/datahub/blob/master/metadata-models/src/main/pegasus/com/linkedin/common/SubTypes.pdl): Captures one or more **subtypes** of a more generic entity type. Specific subtypes can imply that certain additional aspects are present for a given entity. |
| Relationships | A relationship represents a named edge between 2 entities. Relationships permit edges to be traversed bi-directionally. For example, a **Chart** may refer to a **CorpUser** as its owner via a relationship named **OwnedBy**. |
| Identifiers (Keys & URNs) | A key is a special type of aspect that contains the fields that uniquely identify an individual entity. Key aspects can be serialized into URNs, which represent a stringified form of the key fields used for primary-key lookup. Moreover, URNs can be converted back into key aspect structs, making key aspects a type of **virtual** aspect. Key aspects provide a mechanism to easily read fields comprising the primary key, which are usually generally useful like dataset names, platform names etc. URNs provide a friendly handle by which entities can be queried without requiring a fully materialized struct. |

The Enterprise Data Catalog module helps you store two types of metadata:

| Metadata type | Metadata | Description |
| --- | --- | --- |
| Technical metadata - This is metadata observed by the connectors and scanners. Includes metadata that describes data systems structures such as names of databases, schemas and the datasets stored in them (tables, views, topics, files). | Relationship | It is the information between those objects (For example, Database >Schema >Table). |
| Metadata about the schema of datasets | These are attributes (field or/and column) names and properties such as data types and keys. |
| Lineage | It is the relationships between data objects (datasets and/or fields and/or columns) that indicate data movement. We have the following types of lineage: - Design lineage This Lineage is documented in objects like procedures or scripts or ETL jobs. This lineage can be extracted by parsing SQL code or obtaining source/target relationships from APIs. - Execution lineage This lineage is documented in system logs or artifacts produced after the execution of a job. It is lineage produced by executing a script/job as described above or by other documented or undocumented processes. This lineage is what plugins capture by parsing logs and artifacts (DBT, Snowflake, BigQuery, Spark). |
| Profiling | The Enterprise Data Catalog module helps you store and report profiling metrics in time series. Profiles can be provided to the Enterprise Data Catalog using plugins that support this feature. |
| Business metadata - The business metadata add context and meaning to the technical metadata | Ownership | It is typically a technical owner or data steward. Ownership is documented in the catalog so that you can find, ask questions and request access to data as part of the business tasks. |
| Classification | These are the data element labels that are obtained from the scans. It should be based on centrally defined corporate ontologies and taxonomies. Data discovery is one of the most important tasks that business metadata can support using attributes to classify the data source. The list of classifiers used in the Sensitive Data Intelligence module are listed in the Glossary under Data Classification. |
| Domain | These are descriptions and documentation that can be added to technical metadata to add context and help with understanding. |
| Relationships to glossaries | - Terms Relating technical metadata to terms helps to centralize and aggregate context on it. By doing this, a data steward can maintain documentation in one place (business term) instead of maintaining the same documentation in multiple places (attributes). - Policies The data policies can be documented in the catalog and then related to the proper metadata to help data users understand how data can be used. |

An entity is a specific and distinguishable object in the Enterprise Data Catalog. It could represent various things like datasets or glossary terms.

A URN, or Uniform Resource Name, is a Uniform Resource Identifier (URI) that is used to uniquely identify a resource, but without specifying its location or how to access it.

Aspect refers to a collection of attributes that describes a particular facet of an entity. It is a way to look at and understand the various characteristics or sets of attributes of data objects. To put it simply, an aspect in Enterprise Data Catalog is a way of describing a particular aspect of your data, such as its quality, lineage, usage, or metadata.

Data Lineage involves tracking the end-to-end flow and transformation of data through various pipeline stages. It visually represents data's journey from origin to destination, crucial for:

- Understanding impact: You can comprehend the impact of changes on downstream processes and analyses.
- Data quality assurance: It ensures transparency into processes affecting data, supporting data quality.

Data classification is a process of organizing and categorizing data for its improved understanding and efficient use. A typical data classification tool first discovers personal and sensitive data across on-premises, private, and multi-cloud environments to classify data elements, such as Date of Birth, Name, Address, or SSN.

Domain is a logical or thematic grouping of related data assets. Domains are used to categorize and organize data assets based on their subject matter or the business context they belong to. For example, you might have a Finance domain that includes data related to financial transactions, reports, and analysis, or a Human Resources domain that encompasses data related to employee information, payroll, and HR processes.
