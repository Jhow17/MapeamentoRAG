---
title: "What's New in 1.144"
slug: "what-s-new-in-1-144"
updated: 2026-04-28T16:58:06Z
published: 2026-04-28T16:58:06Z
canonical: "helpcenter.securiti.ai/what-s-new-in-1-144"
area: geral
modulo: whats-new
tipo: guia
data_captura: 2026-10-08
---

# What's New in 1.144

### Test Pipelines with Self-Hosted Appliances

What works in a default testing environment may not always work the same way in your real-world setup with different configurations. That’s why you can now run tests on a self-hosted appliance. Pick the appliance from the test prompt settings and run your queries there. You can also see the active appliance for testing in the header. If you switch appliances, the conversation resets automatically so each test starts fresh. This ensures your testing reflects real deployment conditions and gives you more confidence in pipeline performance.

[Learn more](/latest/docs/creating-a-new-pipeline)

![User interface for managing AI pipelines with deployment and environment switching options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[Gencore]Test AI Pipelines Against Self-Hosted Appliances.png)

---

### Collect Consent for Google Ad Tech Providers with Additional Consent v2

When using Google advertising services, some partners may not appear in the IAB Global Vendor List, which needs to be accounted for in consent collection. Cookie Consent Management now supports Google's Additional Consent version 2 with IAB EU TCF v2 and later. This helps you capture consent for those additional Google partners and send it correctly to Google systems. The platform keeps IAB vendors and Google partners separate, so consent is handled accurately for each. Use this when setting up consent to make sure all relevant partners receive the right signals and avoid losing data due to incomplete signals.

[See how Google's Additional Consent v2 works with IAB EU TCF](/latest/docs/configuring-an-iab-eu-tcf-v23-cookie-consent-banner)

![Cookie consent management interface with options to save preferences for user consent.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Collect Consent for Google Ad Tech Providers with Additional Consent v2.jpg)

---

### Manage Risks With The Risk Register And Remediation Workflows

Risk V2 introduces a register-first model that connects risk visibility, ownership, and remediation in one place. The Risk Register now supports direct risk creation and import, filter-based navigation, and a list view with inherent and residual scores, linked objects, and assigned owners and reviewers.

A new Risk Detail page lets users assign ownership, link related objects, manage remediation actions, submit exception requests, and attach evidence. All actions are recorded as activities to maintain a traceable history across risks and related workflows.

[Learn more about upgrading from Risk V1 to Risk V2](/latest/docs/using-the-risk-register-list-view)

![A risk register displaying various risk statuses and their corresponding scores and owners.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[Assessment Automation] Manage risks with an improved risk register and remediation workflow - Risk V2.png)

---

### Fine-Tune Subtask Instructions at Task and Request Level

Handling DSRs often means dealing with subtasks across many systems. For example, you may want strict requirements for high-risk systems but simpler steps for others. Instead, subtasks often follow predefined instructions that don’t always match the request, leading to extra edits and inconsistent results. You can now customize subtask instructions to match each request type and task.

You decide when attachments or processing details are required and which steps appear in reports. This helps reduce manual fixes and keeps outputs clear and relevant.

[Learn how to customize subtask instructions](/latest/docs/customizing-subtask-instructions)

![Flowchart illustrating subtasks, request types, and DSR workbench connections.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[DSR] Customizing Subtasks Instructions-2.jpg)

---

### Backup Pod in Private Cloud Storage

When your platform data already lives in Private Cloud Storage (PCS), it makes sense to keep backups there too. You can now back up all pods directly to PCS, so your data and backups stay in the same place. This works alongside FTP-based backups, giving you flexibility in how you manage storage for AWS and GCP. With everything in PCS, it becomes easier to locate backups and restore data, without switching between systems.

[Understand how to use PCS alongside FTP backups](/latest/docs/backing-up-and-restoring-pod)

![Illustration showing cloud services integration between Google Cloud and AWS platforms.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Pod’s backup in Private Cloud Storage.jpg)

---

### Reuse Existing Pods Across AWS Accounts

When running discovery across AWS accounts, you may want to build on the pods you already have. Now, instead of starting fresh, you can choose to reuse your existing Securiti pods, and connect additional accounts as needed. Moreover, the IaaS onboarding flow has also been enhanced to present the available options more clearly, with in-line descriptions to guide your configuration.

[Learn how to reuse pods for AWS discovery](/latest/docs/creating-an-aws-iaas-instance-version-1111-and-later)

![AWS configuration options for deployment methods, highlighting 'Use Existing Pod' selection.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[IaaS Cloud]Refined AWS Onboarding Experience (2).jpg)

---

### Discover More AI Assets: AI Search, AI Knowledge Base, VertexAI VectorSearch

The more AI resources you can see and track, the more control you have. Asset Discovery now includes Azure AI Search, Azure AI Knowledgebase, and GCP Vertex AI Vector Search in your scans. These services are commonly used for search, knowledge retrieval, and vector-based operations. Once a scan runs, they show up alongside your existing assets. You can use this to quickly see where AI services are in use and keep your inventory accurate, without having to manually trace these resources across different platforms.

[View supported AI services in Asset Discovery](/latest/docs/data-security-posture-management)

![Comparison of Azure and Google Cloud services with icons and features highlighted.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[IaaS] Discover More AI Assets_ AI Search, AI Knowledge Base, Data Sources, Vertex AI Vector Search (1).png)

---

### New UX for All Your Integrations

Integrations are now available in a new standalone section with a refreshed experience. Securiti has introduced a dedicated section, where you can access all integration categories - Monitored data systems, Unmonitored data systems, User-defined systems, CMDB systems, IaaS Connectors, Keyrings, Credential Vaults, Trust Store, Drivers, Webhooks, and Private Cloud Storage - from a single place.

Each page includes search and filtering options, so you can quickly locate specific connectors or configurations without scrolling through long lists. With a cleaner layout and better organization, you can manage integrations in a more user-friendly manner. If you rely on integrations, this new experience is worth checking out.

[Learn more in docs](/latest/docs/using-integrations-in-securiti)

![User interface showing the 'Add Integration' section with highlighted 'Integrations' option.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[Data Systems and Connectors] Revamped User Experience for Integrations.jpg)

---

### Connect Your Oracle Eloqua with Securiti

Handling privacy requests across marketing systems like Oracle Eloqua is no longer a challenge when a native Securiti integration is available. The Oracle Eloqua Marketing Automation connector now lets you bring that data into Securiti and include it in your data privacy operations. Once connected, you can run discovery scans to identify and classify personal data, and handle DSRs using the same process as other systems. This helps you find relevant records faster and avoid switching between various tools otherwise.

[Learn how to connect Oracle Eloqua](/latest/docs/oracle-eloqua)

![Eloqua logo connected to a database icon, illustrating integration concepts.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[Data System Connectors]Oracle Eloqua data system connector.jpg)

---

### The All-New EDC Health Dashboard

Sometimes you just need to know which EDC-specific service is causing an issue before digging deeper. The EDC Health dashboard now shows the status of key EDC-specific services used by your tenant in one place. You can view services like ingestion, dataset, glossary, search, and policy, and filter them as Healthy, Failed, or Degraded. This helps you quickly spot failing services, understand platform availability, and focus your troubleshooting without checking multiple systems.

[Learn more](/latest/docs/edc-health-dashboard)

![EDC Health Dashboard displaying status options for monitoring health conditions.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[EDC] Introducing the EDC Health Dashboard.png)

---

### Validation Workbench for Structured Data Is Now Available for SDI Customers

Validation Workbench for structured data is now available for all Sensitive Data Intelligence customers. Discovery scans can produce a large number of classification results, and checking them manually can be time-consuming. Validation Workbench helps you review sampled detections through validation sessions. You can examine scan results, correct misclassified data elements, and organize reviews by scan job or data element type. As you validate, the workbench calculates classification accuracy and helps identify detectors that may need tuning.

[Learn more in docs](/latest/docs/validation-workbench-for-structured-data)

![Dashboard displaying reviewed columns, precision percentage, and user information for data analysis.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[SDI] Review Structured Data Classification Through the Validation Workbench (5).jpg)

---

### Azure Blob Storage Support in Data Labeling

Managing sensitive documents in Azure Blob Storage often means handling labeling separately. Now, Data Labeling policies let you apply MIP sensitivity labels directly to files in Blob Storage. For example, you can classify and protect financial reports where they are stored. You can use this to make sure your data follows labeling rules without extra steps or moving files between systems.

[Learn more in docs](/latest/docs/configuring-data-labeling-policies)

![Illustration showing data management and security concepts with icons and connections.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[SDI] Azure Blob Storage Support in Data Labeling.jpg)

---

### Amazon S3 Support for Central Quarantine

If sensitive files get flagged, it is not always clear where to isolate them for review. File Quarantine policies now support Amazon S3 for central quarantine, so you can move those files to a designated S3 location. For example, files with personal information can be moved to a secure quarantine bucket. You can use this to keep flagged data separate and review it safely before taking action.

[Read more in docs](/latest/docs/using-quarantine-destinations)

![Icons representing cloud services and data security on a green background.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[SDI] Amazon S3 Support in File Quarantine.jpg)

---

### New Role-Based Permissions for Policies

If your compliance team asks, “Can we restrict policy access to just what someone needs?”, you can now say yes. Instead of one permission set across every policy type, you can grant view or manage access per policy type, and scope it to all policies within that type or only the ones they own. This helps ensure the right people handle the right policies without overexposing sensitive information.

[Go to docs for details](/latest/docs/sensitive-data-intelligence-roles-and-permissions)

![Role-based permissions interface showing policy types and access options for users.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[SDI] New Role-Based Permissions for Policies.png)

---

### Bulk Assign Roles using User Groups

Need to assign the same roles to multiple users? User Groups let you do it in one step. Define a user group, attach roles, and users inherit access as soon as they are added. You can structure groups by team, title, or function, and update permissions by adding or removing users. This gives you a central way to manage access at scale.

[See how roles are assigned to groups](/latest/docs/user-groups)

![Diagram illustrating user management tasks: creating groups, allocating users, and defining roles.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Allocate roles to users with User Groups.jpg)
