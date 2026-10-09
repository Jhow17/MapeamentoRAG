---
title: "Data quality"
slug: "data-quality-framework"
status: "update"
updated: 2026-07-21T11:09:47Z
published: 2026-07-21T11:09:52Z
canonical: "helpcenter.securiti.ai/data-quality-framework"
stale: true
area: governance
modulo: enterprise-data-catalo
tipo: guia
data_captura: 2026-10-08
---

# Data quality

**Scenario**

As a data steward, you need to ensure your organization's datasets are accurate before they feed into key analytics dashboards. Manually reviewing tables often misses hidden anomalies and leads to poor decisions. With Securiti's Data Quality Framework, you define data type and range checks across multiple data systems. Now, errors surface early, giving you confidence in your data and enabling reliable business insights.

Data quality helps ensure that your data meets specific standards, [expectations](/v1/docs/dqexpectations), and criteria, thereby improving data reliability and trustworthiness.

Securiti’s Data quality capabilities provide a data validation and testing framework for ensuring the quality and integrity of your data. It lets you define and validate expectations about your data and helps you set up various types of validations or expectations, such as data type checks, value range checks, and more. It also helps you catch errors and anomalies early in your data pipelines, preventing downstream problems and ensuring that your data is trustworthy for analysis and decision-making.

### Prerequisites

- You must make sure the datasets to be tested are registered in the Enterprise Data Catalog.
- You must have an active [pod](/latest/docs/securiti-pods-and-elastic-pods) to execute the checkpoints.
- Users configured while connector activation must have **SELECT** access to tables to be tested. Access policies in tables may impact tests (For example if there is masking in columns or row-level access policies). So you must have at least select access but also must have access to all possible restrictions.

### Scope

You can check the quality and integrity of the following data systems in the data quality framework:

- Snowflake

> [!NOTE]
> **Note**
> 
> To successfully execute data quality checks, use **Basic Authentication**, **OAuth 2.0** authentication or **Key Pair Authentication** to activate and connect to the Snowflake data system.
- Amazon Redshift
- Snowflake
- Google BigQuery
- MySQL
- MSSQL
- Postgres
- Apache Trino

> [!NOTE]
> **Note**
> 
> You must mark the **Add Dataset in Lowercase** checkbox if you want to ingest data quality results properly for the Snowflake data system. For the rest of the data systems you must unmark the **Add Dataset in Lowercase** checkbox.

### Opening data quality

To open data quality:

- In Securiti, open **Enterprise Data Catalog**, then choose **Data Catalog > Data Quality** to open the Templates page.

![Data_Quality_-_Opening_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-797f8630-87f7-873b-c990-4cb88bf43ce4.png)
- Or you can access the **Templates** from the hamburger menu. Open **Enterprise Data Catalog**, click the **hamburger menu > Data Quality** to open the **Templates** page.

## Related

- [Data quality findings](/data-quality-findings.md)
