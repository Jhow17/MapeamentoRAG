---
title: "Data and AI Security Overview dashboard"
slug: "data-and-ai-security-overview"
updated: 2026-08-18T14:17:48Z
published: 2026-08-18T14:17:48Z
canonical: "helpcenter.securiti.ai/data-and-ai-security-overview"
area: dspm
modulo: graph-reporting-dashboards
tipo: guia
data_captura: 2026-10-06
---

# Data and AI Security Overview dashboard

The Data and AI Security Overview dashboard provides a unified view of your data security posture across connected systems, AI models, and data sources. With this dashboard, security and compliance teams can assess overall data and AI risk posture, enforce governance controls, and maintain compliance readiness across the data estate.

The dashboard lets you:

- Track posture scores across frameworks and compliance categories
- Visualize trends in data exposure, access controls, and AI model deployment
- Identify security gaps and prioritize remediation actions across environments

![Overview of data security findings, highlighting risk severity and asset posture scores.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/dataandaisecurityoverview_dashboard.png)

The table below provides an overview of the predefined widgets in the **Data and AI Security Overview** dashboard.

| Widget title | Widget type | Description |
| --- | --- | --- |
| Security Findings Type | Grid | Displays an overview of security findings by type (e.g., Cross Border Findings, Security Posture Findings, and Compliance Test Findings), helping to categorize the nature of risks. |
| Security Findings By Risk Severity | Chart | Displays the security findings by their severity (Very High, High, Medium, Low), enabling quick prioritization based on risk. |
| Asset Risk Score | Chart | Displays the Risk Score over time in a line chart, providing insights into the overall risk level for assets in your environment |
| Asset Posture Score by Framework Category | Grid | Displays security posture score for framework categories and the number of passed tests for each category. |
| Open Very High & High Findings | Chart | Displays the number of open very high and high findings in the security posture, helping to identify critical areas requiring attention. |
| Data Location | Map | Displays a global map view indicating the geographic locations of your data across different cloud providers (AWS, Azure, GCP, OCI), helping with compliance and data residency requirements. |
| AI Models and Agents | Grid | Displays a list of AI models and agents in your environment, detailing the hosting platform, AI models, data systems, and related files. |
| AI Platforms | Grid | Displays AI platforms like AWS Sagemaker, including key metrics on connected data systems, AI models, and misconfigurations. |
| Sensitive Data Elements | Grid | Displays sensitive data elements (e.g., name, location, contact info), providing insights into how much sensitive data is stored across different data systems, tables, and files. |
| Top 20 Roles with access to Sensitive Data | Grid | Displays the top 20 roles (e.g., SYSADMIN, ACCOUNTADMIN) with access to sensitive data, helping identify potential data exposure at the role level. |
| Top 20 Groups with access to Sensitive Data | Grid | Displays the top 20 user groups that have access to sensitive data, helping assess the risk exposure based on group-level access permissions. |
| Public Cloud Data | Grid | Displays a summary of data across public cloud environments (AWS, Azure, GCP, OCI), showing key metrics like data systems, tables, files, data volume, and sensitive data elements. |
| SaaS Cloud Data | Grid | Displays data for various SaaS applications (e.g., Salesforce, Microsoft 365), detailing file counts, data volumes, and sensitive data elements to monitor SaaS application security. |
| Private Cloud Data | Grid | Displays data stored in private cloud environments (e.g., PostgreSQL, MongoDB), offering visibility into sensitive data elements, data systems, and misconfigurations. |
| Object and File Storage Data | Grid | Displays data from object and file storage systems (e.g., Google Cloud Storage, Amazon S3, Oracle Object Storage), showing metrics on file volumes and sensitive data. |
| Data Warehouse | Grid | Displays data warehouse environments (e.g., Google BigQuery, SQL Server, MySQL), offering insights into the number of data systems, tables, scanned tables, columns, and sensitive data elements. |
