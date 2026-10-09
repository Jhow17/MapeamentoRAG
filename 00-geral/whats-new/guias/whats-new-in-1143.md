---
title: "What's New in 1.143"
slug: "whats-new-in-1143"
updated: 2026-04-28T16:58:26Z
published: 2026-04-28T16:58:26Z
canonical: "helpcenter.securiti.ai/whats-new-in-1143"
area: geral
modulo: whats-new
tipo: guia
data_captura: 2026-10-08
---

# What's New in 1.143

### Try the New Interactive DSPM Demos for AWS

Want to see how a feature works before setting it up yourself? You can now walk through it step by step. Just open a demo and press the right arrow on your keyboard, as we show each action on the screen, with clear explanations along the way. Today, these demos cover our DSPM functionality for AWS and let you learn at your own pace. You can also open the related Help Center articles from the relevant demo section if you want to dive into the details. More interactive demos for other clouds and features will be added soon. Stay tuned!

[Explore the DSPM demos for AWS](/latest/docs/interactive-demos)

![AWS interactive demo interface with a prominent 'Start Demo' button highlighted.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Published Interactive demos-1 (1).png)

---

### Next Generation DSPM Solution Using Outpost

Imagine kicking off a discovery scan on a massive enterprise dataset, only to realize it may need more compute power than the regular ones. Hyperdrive mode makes that possible, by adding that extra capacity when you need it. Supported for selected Microsoft 365 apps, Amazon S3, NFS, and SMB, Hyperdrive scans run through AWS Outpost instead of regular pods. This lets Securiti dynamically increase compute capacity for demanding scans and scale back once the workload is complete. So you can discover faster, and protect more, regardless of the data size.

[Explore the documentation to use Hyperdrive](/latest/docs/hyperdrive-overview)

![Diagram illustrating cloud storage options with M365, S3, SMB, and NFS services.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[Connectors] Connect Data Systems using Hyperdrive (3).jpg)

---

### All New Gencore AI Analytics Dashboard

You may need quick answers to basic questions like who is using a pipeline and how fast it responds. The Gencore Analytics dashboard now answers those questions directly based on data such as aggregated usage, average response times for GenAI pipelines and firewalls, and unique user counts for your GenAI pipelines. This helps you understand real usage patterns without manually looking for them. You can take actions based on these insights by reviewing the dashboard regularly to catch slowdowns or unexpected spikes. Go to the Gencore Analytics dashboard, choose your pipeline, and use the metrics to track and guide your next set of changes.

[View detailed guidance](/latest/docs/using-gencore-ai-analytics)

![Gencore AI Analytics Dashboard displaying user statistics and API call data.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[Gencore AI] Analytics Dashboard.jpg)

---

### Manage Azure Credential Rotation with Terraform

When it’s time to rotate Azure credentials, you want a clear and reliable way to handle this change. You can now renew credentials for an existing Azure instance using a Terraform template. This means your team can apply the same infrastructure-as-code practices you already use for provisioning and updates. It brings consistency to how credentials are managed and refreshed. You can use it during scheduled rotations or security updates to keep access active and scanning uninterrupted, while cutting down on back-and-forth steps.

[Refer to the documentation for Azure credential rotation steps](/latest/docs/performing-actions-post-azure-instance-creation)

![Interface for renewing credentials with fields for username and password.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[IaaS Cloud] Azure Credential Renewal via Terraform-2(1).png)

---

### Introducing Hierarchical File View in Data Remediation Dashboards

Tracking down the source of policy violations can take time when files are shown in a flat list. With the new Folder Browser toggle in the Data Remediation dashboards, you can now switch to a hierarchical view that groups files by folder and scopes them to the selected policy. This makes it easier to see which locations are driving the most violations. You can focus on the top 10 high-impact folders first and plan remediation in a more structured and efficient way.

[Check the documentation for the hierarchical file view](/latest/docs/using-data-remediation-dashboard)

![A central folder icon connected to three subordinate folder icons, illustrating organization.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[SDI] Hierarchical File View in Data Remediation Dashboards.png)

---

### Fine-Tune Remediation Policies with File-Level Control

When policies are set with a broad scope, not every flagged file always needs action. You might want certain files to remain untouched, even if they technically match policy criteria. Now, from the Data Remediation dashboard, you can mark specific files as Excluded so selected policies ignore them, or use Exclude Global to prevent enforcement across all policies. If files were already removed from your source system, you can mark them as Deleted to avoid repeated quarantine or labeling attempts. This gives you clearer oversight and better control over remediation decisions.

[Learn more in docs](/latest/docs/using-data-remediation-dashboard)

![A dashboard displaying metrics, graphs, and options for data management and analysis.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[SDI]File Remediation and Reversal Actions.jpg)

---

### Custom Relationships for Glossary Terms and Term Groups

Glossary terms don’t always fit neatly into a single group. EDC now lets you define custom relationships between Glossary Terms and Term Groups so your glossary structure reflects how your data is actually organized.

For example, a term like Customer Data can include Email Address, be governed by a GDPR policy, and be owned by Sales, all without being limited to one group. Data stewards can link terms to the right groups and organize glossary structures more clearly.

[See the documentation for glossary term relationships](/latest/docs/glossary-terms)

![Icons representing coding and document processing connected by a line.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[EDC] Custom Relationships for Glossary Terms and Term Groups.jpg)

---

### OOTB Cookie Banner Template for Israel, DIFC, QFC, Peru, Panama & New York

When expanding into new markets, configuring cookie banners for each region can slow you down especially when regional requirements differ for legal compliance. Cookie Consent Management now provides six additional region-specific cookie banner templates in the Banner Templates Gallery for Dubai, Israel, New York, Panama, Peru, and Qatar. Simply pick the template that matches your target region, review the cookie banner settings, and publish. This gives you a structured starting point and minimizes manual setup work.

[Explore the new cookie banner templates](/latest/docs/using-the-banner-templates-gallery)

![Flags and city names representing various countries and cities around the world.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/OOTB Cookie Banner Template for Israel, DIFC, QFC, Peru, Panama &amp; New York.jpg)

---

### Get Insights Into Every Consent With the Universal Consent Dashboard & Metrics

When consent data is collected across multiple channels, it can be difficult to get a complete view of data subject choices and activity. The new Universal Consent Dashboard & Metrics centralizes this information, allowing you to see what data subjects agreed to and how consent was submitted. For instance, if consent is collected from a Preference Center, web consent form, or API, this unified experience helps you track trends, analyze engagement patterns, and gain a comprehensive understanding of data subject consent behavior.

[Read the documentation on the Universal Consent Dashboard](/latest/docs/using-the-universal-consent-dashboard-and-metrics)

![Dashboard displaying universal consent metrics, including unique users and consent status.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Universal Consents Dashboard &amp; Metrics.jpg)
