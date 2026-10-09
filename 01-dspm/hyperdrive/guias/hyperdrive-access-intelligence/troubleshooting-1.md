---
title: "Troubleshooting for Hyperdrive Activity Analysis"
slug: "troubleshooting-1"
updated: 2026-04-01T08:16:26Z
published: 2026-04-06T21:00:01Z
canonical: "helpcenter.securiti.ai/troubleshooting-1"
stale: true
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Troubleshooting for Hyperdrive Activity Analysis

Use the following guidance to resolve common issues.

### **Error Handling**

If you encounter the following error:

```plaintext
Microsoft.Exchange.Configuration.Tasks.InvalidOperationInDehydratedContextException
```

This error occurs when your Microsoft 365 tenant is in a **“dehydrated” state**.

- A dehydrated tenant has **limited Exchange Online configuration capabilities**
- Advanced features (like custom policies, roles, or configurations) are **not yet fully enabled**
- This is common in **new or lightly used tenants**

Run the following command:

```plaintext
Enable-OrganizationCustomization
```

This command converts your tenant from **dehydrated to fully provisioned state**. It also enables advanced configuration capabilities in **Exchange Online**

### **Common Issues and Resolutions**

| **Issue** | **Resolution** |
| --- | --- |
| No audit events appearing | Ensure Unified Audit Logging is enabled in Microsoft Purview. It can take up to 24 hours for data to appear |
| 401 on Graph API | Verify admin consent is granted for **AuditLogsQuery.Read.All** and ensure the client secret is valid |
| 401 on Management API | Ensure **ActivityFeed.Read** is granted under Office 365 Management APIs |
| Empty Management API content | Verify subscriptions are active. The connector starts them automatically but they may become inactive |
| Copilot events not tracked | Requires Microsoft 365 Copilot licenses. Verify **CopilotInteraction** record type is available |
