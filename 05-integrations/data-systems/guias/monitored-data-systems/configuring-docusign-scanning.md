---
title: "Configuring general scan settings for DocuSign (Securiti Cloud)"
slug: "configuring-docusign-scanning"
updated: 2026-07-03T06:55:18Z
published: 2026-07-03T06:55:18Z
canonical: "helpcenter.securiti.ai/configuring-docusign-scanning"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configuring general scan settings for DocuSign (Securiti Cloud)

> [!NOTE]
> Note
> 
> For Securiti-Cloud connectors, the first scheduled scan after activation must be initiated manually by clicking the Initiate Data Scan. This requirement does not apply to connector reconfigurations. After the initial scan, all subsequent scheduled scans run automatically according to the configured schedule.

This article covers the post-authentication scan settings for the DocuSign Securiti Cloud connector.

## Security Posture scan settings

To monitor misconfigurations across your data systems, on the **General** tab, under **Security Posture Scan Settings** section, configure the following settings:

> [!NOTE]
> Note
> 
> You cannot cancel a running Security Posture scan, it must complete its current scanning because the platform does not support in-flight termination. However, you can disable posture scanning by clearing Enable Security Posture Scan checkbox to prevent any future or scheduled runs from starting.

| Setting | Description |
| --- | --- |
| Security Posture Scan Settings | Marking the **Enabling Security Posture Management** checkbox runs one-time or periodic posture scans as per your schedule settings. After marking the checkbox, set the Period and Exclusion Time in the fields below. Running posture scans on the Data system checks for any policy violations and performs automated Remediation of misconfigurations. > [!NOTE] > **Note** > > By default, the **Auto Scan** option is selected. |
| The **Select mode** lets you monitor the misconfigurations associated with your SaaS Cloud account. For SaaS applications, **Monitor Only** is available for now. > [!NOTE] > **Note** > > This option is enabled by default if the Enable Security Posture Management checkbox is marked. |
| Marking the **Auto Scan** checkbox lets you schedule automatic posture scans to discover your data systems and their security posture. |
| If **Schedule automatic scans to Discover Data Systems and their Security Posture** is selected, you can set the Period for your scan frequency. The scan period can be hourly, weekly, or monthly. |
| After scheduling automatic scans, you can set the time range in **Exclusion Time**, which you need to avoid running posture scans, such as maintenance. |

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

The connector discovers user Envelopes and Attachments (including their constituent elements such as Documents). During this process, the state shows as “learning.” The connector re-learns this information after every scan interval before a re-scan.

If the DocuSign connector discovers a change in either Envelopes or Attachments, it updates its database:

- For changes in envelopes, the timestamp for each envelope gets updated whenever a change is made in it. This can be the addition of a new document or updating the contents of an existing one.
- For changes in Attachments, any modifications made to either Signer-originated (external) attachments and those attached with regular envelopes (including Documents) is reflected in a timestamp update for each incremental change to these items.

Once the connector comes out of the initial learning state, the status shows “learning complete” and the connector waits for your input to either:

- Scan all discovered users and their contents using the default scan policy:

By default, auto-scan is enabled and DocuSign scans once at an hourly interval when prompted.
- Let you to change the scan policy and initiate a full scan followed by rescans at regular intervals.

## Breach Analysis

In the **Configuration** tab, under the **Breach** section, mark the **Breach Analysis** checkbox to initiate enhanced analysis for any reported incident for your data system and get an automated report for remediation.
