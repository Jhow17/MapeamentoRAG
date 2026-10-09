---
title: "Configure General scans for Workday (Securiti Cloud)"
slug: "configure-general-scans-for-workday-securiti-cloud"
updated: 2026-02-06T09:54:50Z
published: 2026-02-09T22:00:15Z
canonical: "helpcenter.securiti.ai/configure-general-scans-for-workday-securiti-cloud"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configure General scans for Workday (Securiti Cloud)

In the **General** tab, configure the Security Posture scan settings.

## Security Posture Scan Settings

> [!WARNING]
> **Important**
> 
> For Workday Posture scan to run successfully, following key considerations must be taken into account.
> 
> User group must have all the necessary Permissions for the Human Resource module. See Access required for Workday modules for more information.
> 
> User group must be added to the list of Permitted Security Groups for the Web Service Task Get Integration System Users. See step 5(c) in Integration details required for Workday Authentication for more information.

- To monitor misconfigurations across your data systems, on the **General** tab, under **Security Posture Scan Settings** section, configure the following settings:

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
