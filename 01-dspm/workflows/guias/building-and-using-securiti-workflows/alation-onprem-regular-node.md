---
title: "Alation Onprem"
slug: "alation-onprem-regular-node"
updated: 2026-01-09T00:41:37Z
published: 2026-01-09T00:41:37Z
canonical: "helpcenter.securiti.ai/alation-onprem-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Alation Onprem

An Alation OnPrem node in Workflow Automation serves as an integration point with Alation's data cataloging capabilities, specifically tailored for on-premises deployments. Alation is a platform that offers data cataloging to organize data across various sources, enrich metadata, and enhance data governance practices. Integrating an Alation OnPrem node within a workflow provides several functions that streamline data management and utilization.

You can perform the following set of actions using the Alation OnPrem node in Securiti’s workflow module:

- Update custom fields on a table
- Update custom fields on a column

Refer to the [Node configurations section](/v1/docs/alation-onprem) to understand the node working and properties.

#### Example use case

As an example, let’s create a workflow that centers around integrating Alation OnPrem with a field classification system to streamline PII tagging and governance. It begins by scanning the database schema for potential Personally Identifiable Information (PII) such as names and email addresses. Based on the scan results, the workflow intelligently calls the Alation OnPrem node to update custom fields within your on-premises Alation data catalog.

Specifically, the Alation OnPrem nodes dynamically tag both tables and columns within Alation. Tables identified as containing PII are tagged with a **Custom Securiti Tag** with the value "Yes - Contains PII." Columns containing PII are marked with a "Securiti PD Attribute" custom field. Tables that do not contain PII receive a "Custom Securiti Tag'' with the value "No - Does not contain PII." This workflow automates and streamlines a crucial process within your data governance practices, enriching the metadata in your Alation OnPrem catalog for improved security and compliance.

This use case uses the following nodes:

1. [Field Classification Node](/v1/docs/field-classification)
2. [IF Node](/v1/docs/if)
3. Alation OnPrem Node

#### Integrating Field Classification with Alation OnPrem for Data Catalog Enrichment

1. Add Cron trigger node to start the workflow on the set time, for example every 24 hours.
2. Add Field Classification node and fetch the list of field classifications against the datasource name.
3. Add the IF node to evaluate if the field Classifications node output contains an indicator for PII.
4. Add the Alation OnPrem node at the end of the True branch to update column-level custom fields within the database in Alation, dynamically setting values based on whether the column was classified as containing PII.

![Screenshot_2024-04-22_at_3_59_57_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-720772d9-f42d-5ce8-c02e-4a1542b6bf61.png)
5. Connect the node and execute the Workflow.

![Screenshot_2024-04-22_at_3_59_42_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e80d18f8-c99a-5864-8e2f-2b759acf7290.png)
6. Once the workflow is executed, you can view the response in both JSON and table view.

#### Node configurations

| Parameters |
| --- |
| Privaci Datasystem | Choose the Alation datasystem from the menu. Refer to the Alation connector documentation to understand how to configure the data system. |
| Operation | Update Custom Field-Table | Updates a custom field in a table |
| Update Custom Field-Column | Updates a custom field in a column |
| Alation Datasource | Select the datasource in the Alation catalog to operate on. |
| Database | Select the database to perform the operation on. |
| Schema | Specify the database schema to perform the operation on. |
| Table | Specify the database table to perform the operation on. |
| Custom Field | Custom field to update |
| Custom Field Value | Value to use for custom field |
| Use Dynamic Labels | Choose whether to use dynamic labels or static values as labels |
| Column(s) | Columns to perform an operation on. Provide a comma-separated list of names to update multiple columns |

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.
