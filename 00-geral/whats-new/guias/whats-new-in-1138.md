---
title: "What's New in 1.138"
slug: "whats-new-in-1138"
updated: 2026-04-28T16:59:07Z
published: 2026-04-28T16:59:07Z
canonical: "helpcenter.securiti.ai/whats-new-in-1138"
area: geral
modulo: whats-new
tipo: guia
data_captura: 2026-10-08
---

# What's New in 1.138

### Deploy Securiti in Your Existing Kubernetes Cluster

Managing multiple Kubernetes clusters can be complex. With Elastic Pods V2, you can now deploy Securiti in your existing Kubernetes cluster, or set up a separate one. This means you no longer need to look into a standalone setup for Securiti platform, making it low maintenance, faster deployment setup, with centralized monitoring, all from your existing infrastructure. It’s a cleaner way to run Securiti alongside your existing workloads, using the tools and services you already have in place.

[Read more in the docs](/v1/docs/elastic-pods-v2)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-5BJ1HB0G.png)

---

### Discover Your Cloud AI Assets: Amazon Q, Azure ML Studio, and Vertex AI

Using AI tools across clouds like AWS, Azure, and GCP? It’s easy to lose track if the AI services are left unattended. Securiti’s Asset Discovery now shows Amazon Q, Azure ML Studio, and GCP VertexAI assets along with your other discovered assets. You can see all your AI resources in one view instead of jumping between cloud consoles. It helps you stay organized and makes sure no assets are left out.

[Learn more in the Asset Discovery documentation](/v1/docs/data-security-posture-management-solution#list-of-supported-cloud-native-services)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-02W34NTV.png)

### Run Postures Scans on Self-Hosted Connectors

Run posture scans on DocuSign, G Suite Gmail (Attachments & Message Body), Slack, and Zendesk Support using the connectors you’ve already deployed. No extra configuration needed. It’s a faster way to get deep visibility without setting up each system from scratch. This helps you extend visibility and coverage with the same level of security controls and compliance visibility throughout the multi cloud environment.

Learn how to scan [DocuSign](/v1/docs/activate-the-docusign-connector-in-securiti), [G Suite Gmail](/v1/docs/g-suite-gmail-message-body-attachments-connectors), [Slack](/v1/docs/activate-the-slack-connector-in-securiti), and [Zendesk Support](/v1/docs/activate-the-zendesk-support-connector-in-securiti)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-EJWS96TP.png)

### Fix Once, Automate the Rest: AI Tuning for Structured Data

Reviewing structured data scans can feel endless when working with huge volumes of structured data, where every column needs attention. AI Tuning cuts down that effort. Correct a single column, and the system applies your feedback to other similar columns. Next time you scan, it already knows how to classify them. You are no longer stuck repeating the same fix across datasets. You stay in control by adjusting similarity settings and reviewing linked data elements. And because it relies on metadata, your sensitive data never leaves your environment.

[Learn more about AI Tuning](/v1/docs/classifying-columns-using-ai-tuning)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-7586DPH6.png)

### Turn Dashboard Insights into Jira & ServiceNow Tickets—Automatically

Certain numbers on your dashboard shouldn’t spike, like the count of violations or failed records. Rather than watching them all the time or logging tickets yourself, you can now define automation policies for any dashboard widget. Securiti will automatically raise Jira or ServiceNow tickets based on the set scope and rule. You get the action you need, directly from the insight, no switching tools.

[See how to set up automation for dashboard widgets](/v1/docs/configuring-automation-policies-en)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-GE0EKE55.png)

### Scan MIP Encrypted Files in SharePoint Online and OneDrive

Encrypted files are no longer left out of your scans. Securiti now includes them when they are protected with Microsoft Purview labels in SharePoint Online and OneDrive. The files are securely opened through Purview and scanned for classification, while their names and locations stay the same. Just confirm that your Purview connector is active and encryption labels are set up. Now your scans catch all files, not just the unencrypted ones.

Learn how to discover encrypted files in [Microsoft 365 SharePoint Online](/v1/docs/configure-discovery-scans-in-microsoft-365-sharepoint-online) and [OneDrive scans](/v1/docs/configure-discovery-scans-in-microsoft-365-onedrive)

### ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-4N3W8TEM.png)Assessment Comments for Streamlined Reviews

Still switching to chat tools for review discussions? Securiti now brings comments directly into assessments.

Reviewers and admins can:

- Add, edit, or delete comments anytime, even after completion.
- See “edited” labels with timestamps for full audit history.
- @Tag respondents or reviewers to loop them in. “Reviewer only” comments restrict tags to reviewers.

All comments, with user and datetime details, appear in the final PDF export keeping every note tied to the assessment.

[Read how to do it](/v1/docs/understanding-workflow-stages-and-assessment-use-cases)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-TPHK6LOV.png)

### Keep a Tab on DSR Subtasks Across Their Lifecycle

Need a clear way to spot which DSR subtasks need attention today? Add deadlines in your subtask templates and see them at multiple fronts across the DSR module. Check deadlines on the Subtask Management page, in metadata cards, and in both workbenches. Filter or export by date to track progress. Subtasks transition to overdue status when time is up, and reminder emails go out three and one day before. This keeps every task accountable and reduces missed deadlines.

[See detailed documentation here](/v1/docs/understanding-task-templates-and-rule-based-task-creation)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-GQEQ33N6.png)

### Track DSR Automations and Collaborate Instantly

Tracking DSR automation setups is now easier and more actionable. You can see exactly where each data system instance is in its automation journey—for example, whether it is stuck at the discovery scan stage, the table training is incomplete, or a connector failed during setup. If something needs clarification, send a message directly to the data system owner from the same view. They receive an email notification, ensuring faster collaboration and resolution.

[Read the Robotic Automation dashboard guide](/v1/docs/using-robotic-automation-setup-dashboard)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-2UD36MOI.png)
