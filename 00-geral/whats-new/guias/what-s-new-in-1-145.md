---
title: "What's New in 1.145"
slug: "what-s-new-in-1-145"
updated: 2026-08-12T08:37:04Z
published: 2026-08-12T08:37:04Z
canonical: "helpcenter.securiti.ai/what-s-new-in-1-145"
area: geral
modulo: whats-new
tipo: guia
data_captura: 2026-10-08
---

# What's New in 1.145

## Try the New DSPM Demos for SharePoint

If you like learning by seeing things in action, this is for you. Open the SharePoint Online demo and move through it step by step with clicks or keystrokes. You will see how SharePoint data is scanned, how sensitive information is identified, what the results look like, and which policies can be applied. It’s all laid out for you, at your pace. If your team uses Microsoft 365, this is a simple way to understand how to apply DSPM controls in your environment.

[Explore the DSPM demos for SharePoint Online](/latest/docs/dspm-for-sharepoint)

![Interactive demo interface showcasing navigation buttons and progress indicators for user engagement.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[Interactive Demos] Interactive demos for sharepoint.png)

---

## Monitor, Analyze, and Respond to AI-driven Actions

AI agents can perform actions quickly, making it important to track and verify their impact. The Agent Activity Overview and Agent Commander for M365 dashboards help you monitor how agents, users, and applications interact with your data across connected systems.

- You can analyze activity, such as share, access, and delete actions through interactive timelines and detailed audit logs.
- You can apply filters to focus on specific events, and correlate actions across agents and data systems.
- Most importantly, the dashboard also supports Undo for AI-driven changes using restore points, helping you recover from unintended actions and maintain control over your data.

[Learn more about using dashboards for agent activity](/latest/docs/undo-ai-dashboard)

![A dashboard displaying various data visualizations and metrics for analysis.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[Agent Activity] Monitor, analyze, and respond to AI-driven actions.jpg)

---

## Smart Tracking With Data Tagging

Many teams struggle to organize governance data in a way that reflects how their business actually operates. With the new Data Tagging Policy, you can apply your own business tags to assessments, vendors, and data assets across the platform. For example, by tagging vendors as High Risk, you can quickly filter and view all high-risk vendors, generate reports focused on those vendors, and trigger follow-up actions such as additional risk assessments, without manually sorting through records.

[Read more in docs](/latest/docs/configuring-data-tagging-policy)

![Interface for adding and removing tags with categories and data types options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[SDI] Smart Tracking With Data Tagging2.jpg)

---

## Data Labeling Now Supports Scheduling

Sometimes you don’t want labeling jobs to run during peak hours, so as to play safe and not let anything impact system performance. You can now set a specific time for Data Labeling policies using the UTC selector. If no data changes are detected, the job skips automatically to make sure only meaningful updates are processed and system resources are used only when needed. You can then track and review results in the Reporting dashboard to understand how data is labeled and identify patterns that may need adjustments.

[Learn how to schedule Data Labeling policies](/latest/docs/configuring-data-labeling-policies)

![Icons representing scheduling, smart labeling, and insights for efficient task management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[SDI] Smart Scheduling and Labeling for Data Labeling.jpg)

---

## Detect Sensitive Information in Japanese Files

Working with Japanese documents as part of your data landscape? You can now scan them for sensitive information. Securiti now supports the detection of names, contact details, location data, and key identifiers in Japanese content across Word, Excel, and PDF files. If these files already exist in your connected data systems, discovery scans pick them up automatically. This ensures you do not miss sensitive information in your documents.

[View all supported languages for data detection](/latest/docs/data-classifications)

![Content classification interface with a save button and highlighted character input.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[SDI]Support for Japanese Language.jpg)

---

## Experience Full SaaS Outpost Deployment

When working with smaller data systems, you want to start scanning quickly without setting up infrastructure first. With Securiti Hosted Outpost, the infrastructure is managed for you within the Securiti cloud. You do not need to set up or maintain resources in your own environment. You can connect your data system and start scanning directly. This keeps the scanning experience the same while reducing the overhead of deployment and ongoing infrastructure management.

[Learn more about it](/latest/docs/full-saas-outpost-deployment)

![Illustration showing connection between two abstract shapes representing data integration.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[Pods]Securiti Hosted Outpost (1).png)

---

## Control Vault Authentication Using Selected Pods

In multi-environment setups, you may want more control over where vault authentication runs. With this update, you can now limit vault authentication to specific pods. This reduces unwanted authentication attempts and ensures connectors use vault credentials only from selected pods. You can adjust the selection anytime, with safeguards to prevent breaking active scans.

[Read more about vault authentication setup](/latest/docs/managing-credentials-configuring-credential-vaults#adding-a-credential-vault-instance)

![Pod configuration interface displaying selected pods and credentials vault icon.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[Integrations] Control vault authentication by pods.jpg)

---

## Track Scan Queries with Labels in Teradata and BigQuery

When reviewing query logs, it’s not always clear which queries are triggered by Securiti scans. Logs often show queries from different sources, such as users, tools, and automated jobs, and it is not easy to tell them apart. You can now add a Query Label for BigQuery or a Query Band for Teradata in connector settings to tag all scan queries. This helps you filter and track scan activity in logs. For example, you can separate scan queries from other queries to see their usage and cost in BigQuery or monitor their execution in Teradata.

Learn more in [Google BigQuery](/latest/docs/activate-the-google-bigquery-connector-in-securiti) and [Teradata](/latest/docs/activate-the-teradata-connector-in-securiti) docs

![Illustration showing connections between two applications with icons and labels.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[Connectors] Track scan queries with labels in Teradata and BigQuery.png)

---

## Use IRSA with Dedicated IAM Roles for Amazon S3

Giving pods access to Amazon S3 involves managing and rotating credentials, which can become an ongoing task. This update lets you use IRSA so your Kubernetes pods can access S3 without relying on static credentials. Each pod can assume an IAM role through its service account, which keeps access limited and easier to manage. It helps reduce manual credential handling and follows least-privilege access practices. You can apply this by setting up IRSA and linking your service accounts with the right IAM roles.

[Learn more about it](/latest/docs/irsa-authentication-steps-for-iam-role-in-securitii)

![Icons representing different technologies connected in a network diagram format.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[Connectors] IAM Roles for Service Account for Amazon S3.png)

---

## Scan Read-Only Replica Server in SMB

If your production SMB servers are under heavy load, you may want to run discovery scans without affecting production workloads. Shift those scans to your Replica environment instead of production. This reduces pressure on active systems while keeping full visibility into your sensitive data. It’s a great fit for large, high-volume environments. Simply configure your Replica server and start running discovery scans without impacting your production systems.

[Learn how to authenticate and scan](/latest/docs/smb-connectors)

![Illustration showing document search process between SMB and verification steps.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[Connectors]Support for Disaster Recovery Scanning (DR) for Netapp SMB Servers.png)

---

## Introducing SCIM for User Management in Securiti

When user changes happen in your identity provider, updating them again in Securiti can be repetitive. System for Cross-domain Identity Management (SCIM) support helps you avoid that. It syncs users and groups from your identity provider to Securiti automatically. Whether a user is added, updated, or deactivated, the same change is applied in real time. This removes the need for manual user management and keeps access aligned across both systems.

[Learn to synchronize your users](/latest/docs/scim)

![SCIM integration diagram showcasing connections with Google and other services.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[System Settings] SCIM for user management.jpg)

---

## All Notice Communication in One Place with Messages

Reviewing a privacy notice often means conversations are split across emails and chats, making it hard to keep track of messages and responses. The new Messages feature now keeps all communication in one place within Privacy Notice Management. You can tag an approver, share context, and track their response directly in the same thread. You can also view system notifications and manage conversations without leaving the task. This keeps all messaging in one place and reduces back and forth.

View Messages feature documentation

![User profiles with options for notifications, adding contacts, and deleting messages.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Improved Collaboration in Privacy Notice Management using Messages.jpg)

---

## Update DSR Emails at the Time of Approval or Rejection

When you send a DSR approval or rejection, you may need to adjust the message for that specific case. Earlier, you had to update the template in Notification Templates, and the same version was used everywhere. Now you can preview the email at the time of sending and make changes right there. The preview shows the correct template based on request type and language. You can edit the subject, message, or specific details before sending. This helps you handle case-by-case communication without changing the base template.

Explore more in the documentation

![Illustration showing the process of sending an email from a contact list.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[DSR] Preview Email Before Completing or Rejecting DSR.jpg)

---

## Enhancements to Assessment Tags Across Dashboards, Exports, and Automation

Assessment tags now carry through dashboards and exports. CSV detail, CSV summary, and PDF exports include tag data so reports match what is tracked in assessments.

The rules engine now supports tag actions. Template admins can automatically apply one or more tags based on existing events and conditions. Tags are selected from the central tag library, with the option to create new ones where permitted.

Both the assessments list and dashboard now supports filtering by tag type. Users can apply the property to search from the available tags to narrow results.

[Learn more about Assessment Tags](/latest/docs/configuring-template-rules)

![Icons representing actions: click, export, and filter in a circular layout.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[Assessment Automation].jpg)

---

## Get Consent Records When You Need Them

Getting consent records used to mean raising a support request and waiting for a response. Consent Export Data removes that dependency by letting you export data directly from Cookie and Universal Consent Management. For instance, if you need consent data for a specific period, you can run an export and get notified by email when it completes. You can select a date range and download large datasets on your own. This gives you control to get consent data whenever you need it.

Learn how to export [Cookie](/latest/docs/exporting-cookie-consent-data) and [Universal Consent](/latest/docs/exporting-universal-consent-data) data

![Illustration showing data export process from CCM and UCM to CSV format.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Export Consent Data in Cookie and Universal Consent Management.jpg)

---

## Take a Look at the EDC Dashboard Enhancements

Understanding data quality, ownership, and usage patterns is now faster and more intuitive. The enhanced dashboard experience provides richer context through checkpoint scores, domain-level governance status, and clear visibility into asset ownership distribution. It also highlights popular and frequently updated assets, helping you focus on what matters most. With all key insights available in one place, you can quickly identify gaps, prioritize actions, and make informed decisions, without navigating across multiple pages.

[Explore more in docs](/latest/docs/edc-dashboard)

![Overview of the EDC Dashboard highlighting asset usage, ownership, and visibility features.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[EDC] EDC Dashboard revamp.png)

---

## External OAuth Support for Conversations API

Sometimes your application calls the Conversations API on behalf of a user, but the system may not be able to tell who that user is. This happens because API keys identify the pipeline, not the user. You can now add an external OAuth provider to the pipeline configuration. The API uses the OAuth token to identify the user and apply access rules. Once configured, send the user’s OAuth token with your request so results match the user’s permissions.

[Learn more in docs](/latest/docs/using-oauth-providers)

![Illustration of external OAuth providers with user and API icons for integration.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[Gencore] External OAuth Support for Conversations API.png)

---

## Revamped User Portal Experience

If you’ve been juggling multiple configurations in one portal, this update gives you a cleaner way to manage them. You can now create separate portals for different deployments, each with its own settings. This helps keep things organized and reduces confusion. Messaging integrations are now part of the portal itself, so everything is managed in one place. The settings page is also restructured into tabs, so it’s easier to find what you’re looking for and make changes faster.

[Read more about the new user portal experience](/latest/docs/configuring-user-portal)

![User portal interface displaying options for single sign-on and messaging apps.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[Gencore] User Portal revamp.png)
