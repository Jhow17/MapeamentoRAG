---
title: "Summary of classification evidence for structured data"
slug: "summary-of-classification-evidence-for-structured-data"
description: "This section covers the summary of classification results for structured data"
updated: 2026-09-29T11:24:30Z
published: 2026-09-29T11:24:30Z
canonical: "helpcenter.securiti.ai/summary-of-classification-evidence-for-structured-data"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Summary of classification evidence for structured data

This section describes the JSON format used to represent discovery scan results for structured connectors. Each JSON payload includes metadata about the scanned tables and columns, detected data elements, confidence scores, associated classifications, and CLOB sample data.

The JSON output contains two types of records:

- Individual table scan results with detailed column information
- A summary record with aggregated statistics across all scanned tables

Securiti collects evidence context from large text fields, such as CLOB columns in databases. When Securiti identifies sensitive data in a CLOB column, it automatically gathers 150 characters of additional context before and after the detected value.

## Table scan results

Each table scan result provides detailed information about a specific database table, including all detected personal data elements and their corresponding column-level classifications.

| Field name | Data type | Description |
| --- | --- | --- |
| `payload_version` | String | Refers to the version identifier for the payload format. For example, **v1**. |
| `database` | String | Refers to the database that was scanned. For example, **Customer_DB**. |
| `schema` | String | Refers to the schema within the database. For example, **public**. |
| `table` | String | Refers to the full table path including database and schema. For example, **Customer_DB.public.Completename_AUS**. |
| `scanned_timestamp` | String | Refers to the timestamp when scanning was performed. For example, **2025-04-04T11:28:47Z**. |
| `total_pds` | Integer | Refers to the total count of personal data elements found in the table |
| `content_profiles` | Array[String] | Refers to the list of regulatory frameworks used for compliance assessment |
| `total_columns` | Integer | Refers to the total number of columns in the scanned table |
| `classified_columns` | Integer | Refers to the number of columns containing classified personal data |
| `total_clob_columns` | Integer | Refers to the number of Character Large Object (CLOB) columns in the table |
| `total_rows` | Integer | Refers to the total number of rows in the scanned table |
| `scanned_bytes` | Integer | Refers to the total number of scanned bytes |
| `columns` | Array[Objects] | Refers to the details about each column that contains personal data |
| `edm_profiles` | Object | Refers to the exact data profiles |
| `edm_profiles_count` | Integer | Refers to the number of exact data profiles |

### Non-CLOB column structure

Each column object in the `columns` array contains:

| Field name | Data type | Description |
| --- | --- | --- |
| `name` | String | Refers to the column name. For example, **Email**, **Name**, and **Address**. |
| `datatype` | String | Refers to the column data type. For example, **text**, **varchar**, and **BIGINT**. |
| `pd_count` | Integer | Refers to the total count of personal data elements detected in this column. |
| `sample_count` | Integer | Refers to the number of samples analyzed in this column. |
| `pds` | Array[Object] | Refers to the list of personal data types identified and their confidence scores. |

#### Personal data object structure

Each item in the `pds` array contains:

| Field name | Data type | Description |
| --- | --- | --- |
| `pd_count` | Integer | Refers to the occurrences of this data element |
| `confidence` | Float | Refers to the confidence score for the classification. Values range from 0.0 to 1.0. |
| `pd_type` | String | Refers to the data element type identified. For example, **NAME_FIRST** and **CONTACT_EMAIL**. |

### CLOB column structure (when present)

For CLOB (Character Large Object) columns, additional fields are included:

| Field name | Data type | Description |
| --- | --- | --- |
| `name` | String | Refers to the CLOB column. For example, **Email**, **Name**, and **Address**. |
| `data_type` | String | Refers to the data type of the column. For example, **text**, **varchar**, and **BIGINT**. |
| `pd_count` | Integer | Refers to the total count of data elements detected in this column. |
| `sample_count` | Integer | Refers to the number of samples analyzed in this column. |
| `pd_type` | Object | Refers to the data element types and their counts. |
| `pd_categories` | Object | Refers to the counts for data element categories. |
| `evidences` | Array[Object] | Refers to the detailed evidence of data element findings with context. |

#### CLOB evidence structure

The `evidences` array contains detailed findings with context:

| Field name | Data type | Description |
| --- | --- | --- |
| `row_id` | Object | Refers to the row ID containing the evidence > [!NOTE] > Note > > To populate `row_id` in evidence results for structured data, the scanned table must have a Primary Key (PK). If the table does not have a PK, the Evidence JSON will not include values under `row_id` during the initial discovery scan. In this case, Table Training will also show no Primary Key selected. To view row-level evidence `(row_id.fields)`, you must define and select a Primary Key for the table. |
| `pds` | Object | Refers to the data elements identified within this row, organized by type |

Each personal data finding includes:

| Field name | Data type | Description |
| --- | --- | --- |
| `offset` | Integer | Refers to the character offset of the finding in the CLOB data |
| `text` | String | Refers to the actual personal data text found |
| `context` | String | Refers to the surrounding context of the finding |

## Summary record

The final object in the JSONL file provides aggregated statistics across all scanned tables:

| Field name | Data type | Description |
| --- | --- | --- |
| `payload_version` | String | Refers to the version ID for the payload format |
| `end_time` | String | Refers to the timestamp when the scanning job is completed |
| `discovery_scan_id` | String | Refers to the discovery scan job ID |
| `job_id` | String | Refers to the unique scan job ID |
| `pd_categories` | Object | Refers to the counts of personal data elements by category |
| `pd_count` | Integer | Refers to the total count of all data elements detected |
| `pd_types` | Object | Refers to the count of each data element type detected across all tables |
| `scanned_bytes` | Integer | Refers to the total number of bytes scanned across all tables |
| `total_databases` | Integer | Refers to the number of databases scanned |
| `total_schemas` | Integer | Refers to the number of schemas scanned |
| `total_tables` | Integer | Refers to the number of tables scanned |
| `total_columns` | Integer | Refers to the total number of columns scanned |
| `total_clob_columns` | Integer | Refers to the total number of CLOB columns scanned |
| `total_classified_columns` | Integer | Refers to the total number of columns identified containing personal data |
| `total_rows` | Integer | Refers to the total number of rows scanned |
| `total_clob_rows` | Integer | Refers to the total number of CLOB rows scanned |
| `edm_profiles` | Object | Refers to the exact data profiles |
| `edm_profiles_count` | Integer | Refers to the number of exact data profiles |

## Sample JSON structures

Use the following table to understand the sample JSON structures:

| Condition | JSON structure |
| --- | --- |
| Individual table scan results with Non-CLOB Column | `{ "payload_version": "v1", "database": "Customer_DB", "schema": "public", "table": "Customer_DB.public.account_table", "scanned_timestamp": "2025-04-04T11:28:47Z", "total_pds": 160, "content_profiles": [ &nbsp; "SA_PDPL_STRUCTURED", &nbsp; "CPRA", &nbsp; "QA_PDPPL_STRUCTURED", &nbsp; "AU_PA_STRUCTURED" ], "total_columns": 14, "classified_columns": 4, "total_clob_columns": 0, "total_rows": 20, "scanned_bytes": 4623, "columns": [ &nbsp; { &nbsp; &nbsp; "name": "NAME", &nbsp; &nbsp; "datatype": "text", &nbsp; &nbsp; "pd_count": 40, &nbsp; &nbsp; "sample_count": 20, &nbsp; &nbsp; "pds": [ &nbsp; &nbsp; &nbsp; { &nbsp; &nbsp; &nbsp; &nbsp; "pd_count": 20, &nbsp; &nbsp; &nbsp; &nbsp; "confidence": 0.92688704, &nbsp; &nbsp; &nbsp; &nbsp; "pd_type": "NAME_LAST" &nbsp; &nbsp; &nbsp; }, &nbsp; &nbsp; &nbsp; { &nbsp; &nbsp; &nbsp; &nbsp; "pd_count": 20, &nbsp; &nbsp; &nbsp; &nbsp; "confidence": 0.93098986, &nbsp; &nbsp; &nbsp; &nbsp; "pd_type": "NAME_FIRST" &nbsp; &nbsp; &nbsp; } &nbsp; &nbsp; ] &nbsp; }, &nbsp; { &nbsp; &nbsp; "name": "email", &nbsp; &nbsp; "datatype": "varchar", &nbsp; &nbsp; "pd_count": 20, &nbsp; &nbsp; "sample_count": 20, &nbsp; &nbsp; "pds": [ &nbsp; &nbsp; &nbsp; { &nbsp; &nbsp; &nbsp; &nbsp; "pd_count": 20, &nbsp; &nbsp; &nbsp; &nbsp; "confidence": 0.99, &nbsp; &nbsp; &nbsp; &nbsp; "pd_type": "CONTACT_EMAIL" &nbsp; &nbsp; &nbsp; } &nbsp; &nbsp; ] &nbsp; } ], "edm_profiles": {}, "edm_profiles_count": 0}` |
| Individual table scan results with CLOB Column | `{ "payload_version": "v1", "database": "main", "schema": "largedata", "table": "main.largedata.automation_clob_100_k_rows_25_columns_0009", "scanned_timestamp": "2025-04-03T11:45:38Z", "total_pds": 1800601, "content_profiles": [ &nbsp; "SA_PDPL_STRUCTURED", &nbsp; "CPRA", &nbsp; "TH_PDPA_STRUCTURED" ], "total_columns": 25, "classified_columns": 18, "total_clob_columns": 1, "total_rows": 100000, "scanned_bytes": 231755, "columns": [ &nbsp; { &nbsp; &nbsp; "name": "Clobdata", &nbsp; &nbsp; "datatype": "STRING", &nbsp; &nbsp; "pd_type": { &nbsp; &nbsp; &nbsp; "CONTACT_EMAIL": 21, &nbsp; &nbsp; &nbsp; "CONTACT_PHONE": 29, &nbsp; &nbsp; &nbsp; "DEMOGRAPHIC_AGE": 7, &nbsp; &nbsp; &nbsp; "DEMOGRAPHIC_DOB": 26, &nbsp; &nbsp; &nbsp; "DEMOGRAPHIC_SEX_OR_GENDER": 21, &nbsp; &nbsp; &nbsp; "FINANCIAL_BANK_ACCOUNT": 18, &nbsp; &nbsp; &nbsp; "FINANCIAL_BANK_ROUTING": 26, &nbsp; &nbsp; &nbsp; "FINANCIAL_CC_ACCOUNT": 4, &nbsp; &nbsp; &nbsp; "GEO_CITY_NAME": 36, &nbsp; &nbsp; &nbsp; "GEO_COUNTRY": 42 &nbsp; &nbsp; }, &nbsp; &nbsp; "pd_categories": { &nbsp; &nbsp; &nbsp; "CONTACT": 50, &nbsp; &nbsp; &nbsp; "FINANCIAL": 48, &nbsp; &nbsp; &nbsp; "GOVERNMENT_IDENTIFIERS": 113, &nbsp; &nbsp; &nbsp; "LOCATION": 164, &nbsp; &nbsp; &nbsp; "NAME": 172, &nbsp; &nbsp; &nbsp; "PHYSICAL_ATTRIBUTES": 28, &nbsp; &nbsp; &nbsp; "SOCIAL": 26 &nbsp; &nbsp; }, &nbsp; &nbsp; "pd_count": 601, &nbsp; &nbsp; "evidences": [ &nbsp; &nbsp; &nbsp; { &nbsp; &nbsp; &nbsp; &nbsp; "row_id": { &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; "fields": { &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; "Email": "paxmal@earthlink.net" &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; }, &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; "object": "automation_clob_100_k_rows_25_columns_0009" &nbsp; &nbsp; &nbsp; &nbsp; }, &nbsp; &nbsp; &nbsp; &nbsp; "pds": { &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; "Bank Account Number": [ &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; { &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; "offset": 457, &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; "text": "78745020562966", &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; "context": "78745020562966" &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; } &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; ], &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; "Email Address": [ &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; { &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; "offset": 75, &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; "text": "paxmal@earthlink.net", &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; "context": "paxmal@earthlink.net" &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; } &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; ], &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; "Date of Birth": [ &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; { &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; "offset": 56, &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; "text": "10/15/2001", &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; "context": "10/15/2001" &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; } &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; ] &nbsp; &nbsp; &nbsp; &nbsp; } &nbsp; &nbsp; &nbsp; } &nbsp; &nbsp; ] &nbsp; }, &nbsp; { &nbsp; &nbsp; "name": "Email", &nbsp; &nbsp; "datatype": "STRING", &nbsp; &nbsp; "pd_count": 100000, &nbsp; &nbsp; "sample_count": 100, &nbsp; &nbsp; "pds": [ &nbsp; &nbsp; &nbsp; { &nbsp; &nbsp; &nbsp; &nbsp; "pd_count": 100000, &nbsp; &nbsp; &nbsp; &nbsp; "confidence": 0.99, &nbsp; &nbsp; &nbsp; &nbsp; "pd_type": "CONTACT_EMAIL" &nbsp; &nbsp; &nbsp; } &nbsp; &nbsp; ] &nbsp; } ]}` |
| A summary record with aggregated statistics across all scanned tables | `{ "payload_version": "v1", "end_time": "2025-04-04T11:45:02Z", "discovery_scan_id": "2", "job_id": "428f922f-4330-4c4f-82b9-db8427663fa0", "pd_categories": { &nbsp; "AUTHENTICATION": 3, &nbsp; "CONTACT": 2, &nbsp; "LOCATION": 6, &nbsp; "NAME": 137, &nbsp; "PHYSICAL_ATTRIBUTES": 1, &nbsp; "SOCIAL": 1 }, "pd_count": 6841, "pd_types": { &nbsp; "AUTH_ACCESS_DATE": 20, &nbsp; "AUTH_AWS_API_KEY": 20, &nbsp; "AUTH_AZURE_API_KEY": 20, &nbsp; "CONTACT_EMAIL": 24, &nbsp; "DEMOGRAPHIC_DOB": 19, &nbsp; "DEMOGRAPHIC_SEX_OR_GENDER": 19, &nbsp; "GEO_CITY_NAME": 19, &nbsp; "GEO_COUNTRY": 19, &nbsp; "GEO_POSTAL_CODE": 20, &nbsp; "GEO_PROVINCE": 39, &nbsp; "GEO_STREET_NAME": 19, &nbsp; "NAME_FIRST": 2942, &nbsp; "NAME_LAST": 2942, &nbsp; "NAME_PART": 719 }, "scanned_bytes": 213725, "total_databases": 1, "total_schemas": 2, "total_tables": 6, "total_columns": 117, "total_clob_columns": 0, "total_classified_columns": 65, "total_rows": 410597, "total_clob_rows": 410597, "edm_profiles": {}, "edm_profiles_count": 0}` |
| Consolidating all objects to create a summary file | `[{ "payload_version": "v1", "database": "Customer_DB", "schema": "public", "table": "Customer_DB.public.account_table", "scanned_timestamp": "2025-04-04T11:28:47Z", "total_pds": 160, "content_profiles": [ &nbsp; "SA_PDPL_STRUCTURED", &nbsp; "CPRA", &nbsp; "QA_PDPPL_STRUCTURED", &nbsp; "AU_PA_STRUCTURED" ], "total_columns": 14, "classified_columns": 4, "total_clob_columns": 0, "total_rows": 20, "scanned_bytes": 4623, "columns": [ &nbsp; { &nbsp; &nbsp; "name": "NAME", &nbsp; &nbsp; "datatype": "text", &nbsp; &nbsp; "pd_count": 40, &nbsp; &nbsp; "sample_count": 20, &nbsp; &nbsp; "pds": [ &nbsp; &nbsp; &nbsp; { &nbsp; &nbsp; &nbsp; &nbsp; "pd_count": 20, &nbsp; &nbsp; &nbsp; &nbsp; "confidence": 0.92688704, &nbsp; &nbsp; &nbsp; &nbsp; "pd_type": "NAME_LAST" &nbsp; &nbsp; &nbsp; }, &nbsp; &nbsp; &nbsp; { &nbsp; &nbsp; &nbsp; &nbsp; "pd_count": 20, &nbsp; &nbsp; &nbsp; &nbsp; "confidence": 0.93098986, &nbsp; &nbsp; &nbsp; &nbsp; "pd_type": "NAME_FIRST" &nbsp; &nbsp; &nbsp; } &nbsp; &nbsp; ] &nbsp; }, &nbsp; { &nbsp; &nbsp; "name": "email", &nbsp; &nbsp; "datatype": "varchar", &nbsp; &nbsp; "pd_count": 20, &nbsp; &nbsp; "sample_count": 20, &nbsp; &nbsp; "pds": [ &nbsp; &nbsp; &nbsp; { &nbsp; &nbsp; &nbsp; &nbsp; "pd_count": 20, &nbsp; &nbsp; &nbsp; &nbsp; "confidence": 0.99, &nbsp; &nbsp; &nbsp; &nbsp; "pd_type": "CONTACT_EMAIL" &nbsp; &nbsp; &nbsp; } &nbsp; &nbsp; ] &nbsp; } ], "edm_profiles": {}, "edm_profiles_count": 0},{ "payload_version": "v1", "database": "main", "schema": "largedata", "table": "main.largedata.automation_clob_100_k_rows_25_columns_0009", "scanned_timestamp": "2025-04-03T11:45:38Z", "total_pds": 1800601, "content_profiles": [ &nbsp; "SA_PDPL_STRUCTURED", &nbsp; "CPRA", &nbsp; "TH_PDPA_STRUCTURED" ], "total_columns": 25, "classified_columns": 18, "total_clob_columns": 1, "total_rows": 100000, "scanned_bytes": 231755, "columns": [ &nbsp; { &nbsp; &nbsp; "name": "Clobdata", &nbsp; &nbsp; "datatype": "STRING", &nbsp; &nbsp; "pd_type": { &nbsp; &nbsp; &nbsp; "CONTACT_EMAIL": 21, &nbsp; &nbsp; &nbsp; "CONTACT_PHONE": 29, &nbsp; &nbsp; &nbsp; "DEMOGRAPHIC_AGE": 7, &nbsp; &nbsp; &nbsp; "DEMOGRAPHIC_DOB": 26, &nbsp; &nbsp; &nbsp; "DEMOGRAPHIC_SEX_OR_GENDER": 21, &nbsp; &nbsp; &nbsp; "FINANCIAL_BANK_ACCOUNT": 18, &nbsp; &nbsp; &nbsp; "FINANCIAL_BANK_ROUTING": 26, &nbsp; &nbsp; &nbsp; "FINANCIAL_CC_ACCOUNT": 4, &nbsp; &nbsp; &nbsp; "GEO_CITY_NAME": 36, &nbsp; &nbsp; &nbsp; "GEO_COUNTRY": 42 &nbsp; &nbsp; }, &nbsp; &nbsp; "pd_categories": { &nbsp; &nbsp; &nbsp; "CONTACT": 50, &nbsp; &nbsp; &nbsp; "FINANCIAL": 48, &nbsp; &nbsp; &nbsp; "GOVERNMENT_IDENTIFIERS": 113, &nbsp; &nbsp; &nbsp; "LOCATION": 164, &nbsp; &nbsp; &nbsp; "NAME": 172, &nbsp; &nbsp; &nbsp; "PHYSICAL_ATTRIBUTES": 28, &nbsp; &nbsp; &nbsp; "SOCIAL": 26 &nbsp; &nbsp; }, &nbsp; &nbsp; "pd_count": 601, &nbsp; &nbsp; "evidences": [ &nbsp; &nbsp; &nbsp; { &nbsp; &nbsp; &nbsp; &nbsp; "row_id": { &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; "fields": { &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; "Email": "paxmal@earthlink.net" &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; }, &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; "object": "automation_clob_100_k_rows_25_columns_0009" &nbsp; &nbsp; &nbsp; &nbsp; }, &nbsp; &nbsp; &nbsp; &nbsp; "pds": { &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; "Bank Account Number": [ &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; { &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; "offset": 457, &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; "text": "78745020562966", &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; "context": "78745020562966" &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; } &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; ], &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; "Email Address": [ &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; { &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; "offset": 75, &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; "text": "paxmal@earthlink.net", &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; "context": "paxmal@earthlink.net" &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; } &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; ], &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; "Date of Birth": [ &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; { &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; "offset": 56, &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; "text": "10/15/2001", &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; "context": "10/15/2001" &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; } &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; ] &nbsp; &nbsp; &nbsp; &nbsp; } &nbsp; &nbsp; &nbsp; } &nbsp; &nbsp; ] &nbsp; }, &nbsp; { &nbsp; &nbsp; "name": "Email", &nbsp; &nbsp; "datatype": "STRING", &nbsp; &nbsp; "pd_count": 100000, &nbsp; &nbsp; "sample_count": 100, &nbsp; &nbsp; "pds": [ &nbsp; &nbsp; &nbsp; { &nbsp; &nbsp; &nbsp; &nbsp; "pd_count": 100000, &nbsp; &nbsp; &nbsp; &nbsp; "confidence": 0.99, &nbsp; &nbsp; &nbsp; &nbsp; "pd_type": "CONTACT_EMAIL" &nbsp; &nbsp; &nbsp; } &nbsp; &nbsp; ] &nbsp; } ]},{ "payload_version": "v1", "end_time": "2025-04-04T11:45:02Z", "discovery_scan_id": "2", "job_id": "428f922f-4330-4c4f-82b9-db8427663fa0", "pd_categories": { &nbsp; "AUTHENTICATION": 3, &nbsp; "CONTACT": 2, &nbsp; "LOCATION": 6, &nbsp; "NAME": 137, &nbsp; "PHYSICAL_ATTRIBUTES": 1, &nbsp; "SOCIAL": 1 }, "pd_count": 6841, "pd_types": { &nbsp; "AUTH_ACCESS_DATE": 20, &nbsp; "AUTH_AWS_API_KEY": 20, &nbsp; "AUTH_AZURE_API_KEY": 20, &nbsp; "CONTACT_EMAIL": 24, &nbsp; "DEMOGRAPHIC_DOB": 19, &nbsp; "DEMOGRAPHIC_SEX_OR_GENDER": 19, &nbsp; "GEO_CITY_NAME": 19, &nbsp; "GEO_COUNTRY": 19, &nbsp; "GEO_POSTAL_CODE": 20, &nbsp; "GEO_PROVINCE": 39, &nbsp; "GEO_STREET_NAME": 19, &nbsp; "NAME_FIRST": 2942, &nbsp; "NAME_LAST": 2942, &nbsp; "NAME_PART": 719 }, "scanned_bytes": 213725, "total_databases": 1, "total_schemas": 2, "total_tables": 6, "total_columns": 117, "total_clob_columns": 0, "total_classified_columns": 65, "total_rows": 410597, "total_clob_rows": 410597, "edm_profiles": {}, "edm_profiles_count": 0}]` |

For more information, see [Supported data systems for discovery scans](/latest/docs/supported-data-systems-for-discovery-scans).

## Related

- [Discovery scans](/discovery-scans.md)
- [Structured Data Discovery New Experience dashboard](/structured-data-discovery-new-experience.md)
