---
title: "Audit logs for Enterprise Data Catalog"
slug: "audit-logs-for-enterprise-data-catalog"
updated: 2026-01-08T07:15:20Z
published: 2026-01-08T07:15:20Z
canonical: "helpcenter.securiti.ai/audit-logs-for-enterprise-data-catalog"
area: governance
modulo: enterprise-data-catalo
tipo: guia
data_captura: 2026-10-08
---

# Audit logs for Enterprise Data Catalog

**Scenario**

As an IT administrator, you are responsible for monitoring user activity and ensuring secure, compliant use of data systems. Without detailed logs, tracking changes or investigating issues is slow and incomplete. EDC audit logs give you a clear record of every action taken across the catalog. This lets you quickly verify activity, detect anomalies, and support audits with reliable, transparent insights.

Audit logs let you view the actions and operations performed in the Enterprise Data Catalog. This helps you gain valuable insights by viewing detailed records of actions within the Enterprise Data Catalog directly in the audit logs more effectively monitor activities.

To open audit log:

- In Securiti, click **Settings**, then click **Securiti** **>** **Audit Logs**.

The audit logs show you the following events:

| Entities (anything in the EDC, for example, tags, domains, datasets) | Actions that can be seen in the audit logs |
| --- | --- |
| Glossary terms | Creation, deletion, soft deletion, restoration |
| Domains | Creation, deletion, soft deletion, restoration |
| Tags | Creation, deletion, soft deletion, restoration |
| Global tags | Entity level change |
| Glossary terms | Entity level change |
| Owners | Entity level change |
| Domains | Entity level change |
| Metadata schema | Entity level change |
| Documentation | Entity level change |

> [!NOTE]
> **Note**
> 
> You can view the re-ingestion operation via the **EDC** **refresh** button in the audit logs. This can help you guide through every step, detailing when the process started and when it successfully concluded.

For more information about the audit logs, see [Viewing the Securiti audit log](/v1/docs/securiti-platform-viewing-the-securiti-audit-log)
