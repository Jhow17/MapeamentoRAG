---
title: "Understanding the Privacy Platform Integrations"
slug: "understanding-the-privacy-platform-integrations"
status: "update"
updated: 2026-03-31T10:26:31Z
published: 2026-03-31T10:26:53Z
canonical: "helpcenter.securiti.ai/understanding-the-privacy-platform-integrations"
area: privacy
modulo: universal-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Understanding the Privacy Platform Integrations

**Scenario**

As a Data Privacy Officer, you must ensure consent preferences are accurately reflected across systems used for marketing and customer engagement. Keeping consent records aligned across multiple platforms can be challenging and may lead to outdated or inconsistent consent data. With Securiti’s Privacy Platform Integrations, you connect Universal Consent Management with third-party CRM systems such as Salesforce and Pardot to automate consent data flows. For instance, when a data subject withdraws marketing consent in Salesforce, the record is automatically ingested into Securiti and processed through the Rules Matrix to determine the correct consent state. This keeps consent records synchronized across systems, reduces manual effort, and helps you enforce consent preferences consistently.

Securiti's Privacy Platform Integrations (PPI) functionality lets you enable seamless connectivity between Universal Consent Management module and third-party systems such as marketing platforms, Customer Relationship Management (CRM), and data tools. By integrating with external platforms, you can automate consent-driven workflows, ensure consistent consent propagation, and maintain alignment between your privacy infrastructure and the broader tech stack.

Privacy Platform Integrations support both **inbound** and **outbound** consent data flows. For instance, you can ingest consent records from platforms like **Salesforce** or **Pardot** (inbound) and process them through Securiti's **Rules Matrix** to determine jurisdiction-based consent states. These records are then populated into the Universal Consent Management module. Conversely, you can push consent records maintained in Securiti (outbound) to Salesforce or Pardot, ensuring that consent status is accurately reflected and enforced in downstream systems used for marketing or customer engagement.

> [!NOTE]
> **Note**
> 
> Securiti currently supports privacy integrations for Salesforce and Pardot.

For more information on setting up integrations, see:

- [Configuring Salesforce Integration in Securiti](/v1/docs/configuring-salesforce-integration-in-securiti)
- [Configuring Pardot Integration in Securiti](/v1/docs/configuring-pardot-integration-in-securiti)

A system or platform used to manage an organization's interactions with its current and potential customers. CRM systems help organizations store contact data, track communication history, manage sales pipelines, and support customer engagement across various channels such as email, phone, and marketing platforms.

## Related

- [Configuring Salesforce Integration in Securiti](/configuring-salesforce-integration-in-securiti.md)
- [Configuring Pardot Integration in Securiti](/configuring-pardot-integration-in-securiti.md)
- [Using the Privacy Platform Integrations Runtime Logs](/using-the-privacy-platform-integrations-runtime-logs.md)
- [Using the Privacy Platform Integrations Audit Log](/using-the-privacy-platform-integrations-audit-log.md)
