---
title: "IAM Metadata Sources"
slug: "iam-metadata-sources"
updated: 2026-03-31T09:42:16Z
published: 2026-04-06T21:00:01Z
canonical: "helpcenter.securiti.ai/iam-metadata-sources"
stale: true
area: dspm
modulo: data-access-governance
tipo: guia
data_captura: 2026-10-06
---

# IAM Metadata Sources

To configure IAM Metadata Sources :

1. In Securiti, open **Data Access Governance,** from the left menu bar, click **Settings**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled(14).png)
2. Click **IAM Metadata Sources**. This opens the IAM Metadata Sources page.
3. Near the upper right corner of the page, click **+New IAM Metadata Source**.
4. On the **New IAM Metadata Source** popup:
  1. Enter the **Connection Name**. For example, SharePoint Metadata Source. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 6(5).png)
  2. Select the Data System in **Source Type** for which you want to configure an IAM Metadata Source.
    1. If you want to create a metadata source for SharePoint (Self-Hosted), select **S****harePoint OnPrem**. Note that for SharePoint Onprem you must have a pod configured, before creating the metadata source. For more details on configuring the metadata source for SharePoint, see the [SharePoint Access Intelligence documentation](/v1/docs/microsoft-365-sharepoint-online).
    2. If you have selected Apache Ranger in Source Type, then you must provide following parameters:

| Setting | Description |
| --- | --- |
| Connection Name | Name of the connection |
| Source Type | Type of the source. By default, Apache Ranger is selected. |
| Apache Ranger Service Name | Apache Ranger Service Name. This is the Service Name of the configured Apache Ranger Service which controls the Starburst cluster. Securiti will download metadata from this service instance after connecting to the Ranger server. For instance, if the cluster is controlled by a 'STARBURST-ENTERPRISE' type service named 'starburst-enterprise-1', then enter starburst-enterprise-1. |
| URL | URL to Ranger Admin. For example, http://111.111.222.33 |
| Connection Time Out | Connection timeout in milliseconds |
| Authentication Type | Type of authentication necessary to connect to the Ranger Admin REST API endpoint. |
| Disable TLS verification | Mark this checkbox to disable TLS verification. Disabling TLS verification check enables you to reduce the strictness of the validation procedures applied when setting up an SSL/TLS connection. Note that this option should be used only in controlled environments when connecting to a trusted Ranger server. Turning off Transport Layer Security (TLS) verification doesn't impact the encryption of the session. |
| Username | Username of a Ranger account. The user must have authorization to connect to the Ranger Admin REST API endpoint. |
| Password | Password of Ranger account |
  3. If you have selected **Snowflake Cloud** as a **Source Type**, then you must provide the **Account ID** of your Snowflake account and **Warehouse** to query for metadata. For more details on configuring the metadata source for Snowflaket, see the [Snowflake Access Intelligence documentation](/v1/docs/data-access-governance-snowflake#access-intelligence).
  4. If you have selected **Starburst Activity Data - Web Integration UI** as a **Source Type**, then you must provide the Pod Name, URL, and Connection timeout etc. For more details on configuring the metadata source for Starburst Activity Data, see the [Activity Analysis documentation](/latest/docs/starburst#activity-analysis).
  5. If you have selected the **Databricks Onprem**, then you must provide the Pod Name, Driver Path, Host, Port, etc. Note that for Databricks Onprem you must have a pod configured, before creating the metadata source. For more details on configuring the metadata source for Databricks Onprem, see the [Databricks Access Intelligence documentation](/v1/docs/databricks#access-intelligence1).
  6. In the **Authentication Details** area, select the **Authentication Type**, based on the source and authentication type selected, enter details. For more information, see [data system specific access intelligence documentation](/latest/docs/configuring-access-intelligence-scans-using-access-scan-definitions-and-iam-metadata-sources#configuring-access-intelligence-scans-for-your-data-systems).
  7. Click Create **New IAM Metadata source**.
