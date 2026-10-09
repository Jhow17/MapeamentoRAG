---
title: "Initiate Microsoft Dynamics 365 CRM Suite (Securiti Cloud) data scanning"
slug: "initiate-microsoft-dynamics-365-crm-suite-securiti-cloud-data-scanning"
updated: 2026-07-28T13:05:55Z
published: 2026-07-28T21:00:00Z
canonical: "helpcenter.securiti.ai/initiate-microsoft-dynamics-365-crm-suite-securiti-cloud-data-scanning"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Initiate Microsoft Dynamics 365 CRM Suite (Securiti Cloud) data scanning

> [!NOTE]
> Note
> 
> For Securiti Cloud connectors, the first scheduled scan after activation must be initiated manually by clicking the Initiate Data Scan. This requirement does not apply to connector reconfigurations. After the initial scan, all subsequent scheduled scans run automatically according to the configured schedule.
> 
> 
> 
> Securiti scans the calculated columns in Microsoft Dynamics 365 CRM tables. If calculated columns are equal or less than 50, then scanned through a normal scanning approach. If calculated columns in the Table are more than 50, then columns are scanned through chunking due to [Microsoft limitation.](https://learn.microsoft.com/en-us/power-apps/maker/data-platform/define-rollup-fields)

After you configure the Microsoft Dynamics 365 CRM Suite Connector, configure its scan policy, then initiate learning:

## Data Scan Policies

If you constantly add, edit, and delete files from their respective drives, the Securiti Connector must regularly rescan your data systems to discover new and updated files.

1. To discover new and updated files, on the **General** tab, under the **Data Scan Policies** section, configure the following settings :

> [!NOTE]
> Note
> 
> You can change scan policy settings (if any) during a scan instead of waiting for the scan to complete. New changes take effect when the current scan finishes.
2. Apply the following settings under Data Scan Policies section:

| Setting | Description |
| --- | --- |
| **Auto Scan** | Mark the **Auto Scan** checkbox to enable automatic re-scans of your data systems Instance. |
| **Scan Interval** | Use the **Scan Interval** tools to configure how often Securiti does the re-scan. It gives the following options: - Day - Week - Month |
3. Once you have updated the configurations, click **Initiate Data Scan** or **Save**. Wait while the connector transitions through the data scanning states.

- Securiti scans your Dynamics CRM Data system to learn its tables and schemas. Securiti uses this data to respond quickly to DSR requests submitted by data subjects.
- Wait while the Connector transitions through the following states:
  - Scheduled for Learning
  - Learning Schemas
- After the connector finishes learning the tables and schemas, it redirects you to the **Table Training** tab.
- Perform Table training on the Microsoft Dynamics 365 CRM Suite data system instance. For more information, see [Table training for structured and hybrid data systems](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems).
