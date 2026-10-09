---
title: "Alation"
slug: "alation-regular-node"
updated: 2026-02-12T14:34:30Z
published: 2026-02-12T14:34:30Z
canonical: "helpcenter.securiti.ai/alation-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Alation

Alation is a data catalog platform designed to assist organizations in effectively managing and deriving value from their data. It serves as a centralized repository for data assets, offering metadata and context to enhance data discovery. The platform supports data governance initiatives by enabling the definition and enforcement of data policies, including tracking data lineage and ensuring compliance.

Using the Alation node in Securiti’s workflow Automation module, you can perform the following actions:

- Update custom fields on a table
- Update custom fields on a column

Refer to the [Node configurations section](/v1/docs/acquire-authentication-credentials-in-alation) to understand the node working and properties.

#### Prerequisites

You must have valid credentials set for Alation to use the Alation node. Refer to the [setting up credentials section](/v1/docs/acquire-authentication-credentials-in-alation) to understand how to configure the required credentials.

#### Example use case

As an example, this workflow centers around integrating Alation node with a field classification system to streamline PII tagging and governance. It starts by scanning the database schema for potential Personally Identifiable Information (PII) like names and email addresses. Based on the scan results, the workflow intelligently calls Alation nodes to update custom fields within your Alation data catalog.

Specifically, the Alation nodes dynamically tag both tables and columns within Alation. Tables identified as containing PII receive a "Custom Securiti Tag'' with the value "Yes - Contains PII." Columns containing PII are marked with a "Securiti PD Attribute" custom field. Tables without PII get a "Custom Securiti Tag'' with the value "No - Does not contain PII." This workflow automates and streamlines an essential process within your data governance practices, enriching Alation metadata for improved security and compliance.

This use case uses the following nodes:

- [Field Classification Node](/v1/docs/field-classification)
- [IF Node](/v1/docs/if)
- Alation Node

#### Integrating Field Classification with Alation for Data Catalog Enrichment

1. Add Cron trigger node to start the Workflow on the set time, for example every 24 hours.
2. Add Field Classification node and fetch the list of field classifications against the datasource name.
3. Add the IF node to evaluate if the field Classifications node output contains an indicator for PII.
4. Add the Alation node at the end of the True branch to update column-level custom fields within the database in Alation, dynamically setting values based on whether the column was classified as containing PII.

![Screenshot_2024-03-05_at_7_05_58_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e7b5bd2e-e7d2-2a77-c410-364cecc7611d.png)
5. Connect the node and execute the Workflow.

![Screenshot_2024-03-04_at_3_33_40_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-77c11bb1-7035-10e7-dfb5-3de524072fbd.png)
6. Upon successful execution, the Workflow node will provide a successful response. You can access the results in two formats i.e. table view and JSON response

#### Node configurations

| Parameters |
| --- |
| Alation API | Choose credentials for an Alation instance, or create new credentials. Refer to the [setting up credentials section](/v1/docs/acquire-authentication-credentials-in-alation) to understand how. |
| Authentication | Basic Auth | Use basic authentication method to setup credentials. |
| API Key | Use API Key authentication method to setup credentials. |
| Operation | Update Custom Field-Table | Updates a custom field on a table |
| Update Custom Field-Column | Updates a custom field on a column |
| Alation Data System | Select the data system in the Alation catalog to operate on |
| Database | Select the database to perform the operation on |
| Schema | Select the database schema to perform the operation on |
| Table | Specify the database table to perform the operation on |
| Custom Field | Specify the custom field to update |
| Custom Field Value | Specify the value to use for custom field |
| Use Dynamic Labels | Choose whether to use dynamic labels or static values as labels |
| Column(s) | Columns to perform operation on. Provide comma-separated list of names to update multiple columns |
| Column PD Map | For dynamic labels, provide a column-to-PD map. The map must be a valid JSON object containing column name as keys and list of PD as value, for example: ```json {"column":["Email","US SSN"]} ``` |

#### Setting up credentials

Use the following credentials to set up credentials for Alation.

| Parameters | Description |
| --- | --- |
| Credentials Name | Provide a valid name of the credentials. Use a name that makes it clear to what exactly the access is given. For example, for credentials of an email account, the name can be the email address itself. |
| Username | Specify the username of the user on Alation. |
| Password | Specify the password associated with the user on Alation. |
| Base URL | Specify the base URL for Alation to connect to Alation, for example, *https://securiti.alation.com* |
| API Key | Specify API Key for Alation. |

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.
