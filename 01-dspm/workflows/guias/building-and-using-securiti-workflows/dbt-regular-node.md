---
title: "DBT"
slug: "dbt-regular-node"
updated: 2026-01-09T09:53:11Z
published: 2026-01-09T09:53:11Z
canonical: "helpcenter.securiti.ai/dbt-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# DBT

DBT (Data Build Tool) node for the Data Catalog module.

| Parameters |
| --- |
| Active DataSources | DataSource name configured on Privaci Datasources page |
| Config Files Properties | Binary property name from the preceding node for Configuration files (Manifest, Catalog, Sources) to read data from |
| Load Schemas (Toggle) | Populates data in the fields (columns) of the data set |
| Mark DataSet Status (Toggle) | Makes field a part of the dataset and soft deletes the data from the UI and does not display data in tables on UI |
| DataSet Tags | Applies to all | DataSet tags are applied to all the data |
| Apply by dataset urn pattern | Regex matches the asset’s urn |
| Apply by schema field pattern | Regex matches the field |
| Dataset Tag | Select multiple tags against the urn pattern or schema field pattern |
| Glossary Terms | Applies to all | Glossary terms are applied to all the data |
| Apply by dataset urn pattern | Regex matches the asset’s urn |
| Apply by schema field pattern | Regex matches the field |
| Glossary Term | Select one or more glossary terms to apply to the data set |
| DataSet Term | Select multiple terms against the urn pattern |
| Ownership | Assign ownership to all |
| Assign ownership by dataset urn pattern |
| Remove Default Ownership (Toggle) | Removes the default applied ownership from the data set |
| DataSet Owners | Select DataSet owners from the menu |
| Catalog Groups | Select Groups from the menu |
| Ownership Type | Select the type of ownership: - Technical Owner - Business Owner |
| Property Name | Add the name of the property |
| Property Value | Add the value of the parameter |
| URN Pattern | Add DataSet URN pattern. URN regex pattern example: **.*example1.*** |
| Field Pattern | Add DataSet Schema Field pattern. Schema field pattern example: **.*example1.*** |
