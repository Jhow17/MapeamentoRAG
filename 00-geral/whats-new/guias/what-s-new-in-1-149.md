---
title: "What's New in 1.149"
slug: "what-s-new-in-1-149"
updated: 2026-08-12T08:57:00Z
published: 2026-08-12T08:57:00Z
canonical: "helpcenter.securiti.ai/what-s-new-in-1-149"
area: geral
modulo: whats-new
tipo: guia
data_captura: 2026-10-08
---

# What's New in 1.149

## Analyze Cookie Consent Risks via the Compliance Metrics Dashboard

You manage cookie consent compliance across 220 domains, and Monday morning starts with the same question: which sites need attention right now? The new Compliance Metrics dashboard in Cookie Consent Management answers that in one screen. A gauge shows your overall compliance score, a trend line shows how it's moved over time, and widgets break down critical risk domains, failed tests by type and severity, aging risks, and remediation progress by assignee. Click any chart segment or row and you land on the exact filtered list behind it, from domains at risk to who's still working through pending fixes.

[Explore the Compliance Metrics dashboard in detail](/latest/docs/using-compliance-metrics-to-monitor-cookie-compliance-risks-and-remediations)

![Overview of cookie compliance metrics including scores and risk distributions for domains.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Cookie Consent Compliance Metrics.png)

---

## Organize your Privacy Notices and Templates with Custom Metadata

One privacy notice or template can apply to multiple business units, regions, or use cases, with no field to record which one applies and no way to search for it later. Custom Metadata closes that gap by letting you tag privacy notices and templates with your own structured, business-specific fields, keeping them organized, searchable, and governable. For example, you can tag privacy notices by jurisdiction, audience, or language, while tagging templates by business function, document purpose, or content owner. This lets you quickly identify the exact notices and templates you need.

[Learn how to use Custom Metadata with your privacy notices and templates](/latest/docs/understanding-custom-metadata)

![Interface for adding custom metadata with fields for region, internal notes, and business.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Custom Metadata for Privacy Notices and Templates(1).png)

---

## Show Request Types Based on the Data Subject's Detected Residency

Previously, a DSR form set to auto-detect residency still showed every configured request type, so a data subject in a region with no right to erasure could still select Erasure and submit it. Now, the new Enable Dynamic Rendering of Request Types option changes that. Once marked, Securiti determines the applicable regulation from the detected IP address or the Country and State entered, then renders only the request types tied to that regulation. For example, a data subject in California sees CPRA request types, while one in the EU sees GDPR request types instead. If no regulation applies, the form shows the request types you've configured.

[Learn more about dynamic rendering of request types](/latest/docs/creating-and-publishing-dsr-request-forms)

![Visual representation of IP address location in the United States and California.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/state and IP address-v2.png)

---

## Sequential Execution of DSR Task Templates Based on Level Outcomes

Task rules used to execute every associated template at once, so retrieval, review, and verification all ran in parallel with no way to hold one back until another was resolved. Now you can organize a rule's templates into up to 4 levels, so a level's templates execute only once the templates in the level before it reach the status you define, such as approved, declined, error, or no data found. For example, set legal review to execute only after retrieval templates come back approved, instead of both running at the same time. Each level supports up to 10 execution blocks, and you can chain multiple conditions together for more control.

[See how to configure sequential task processing](/latest/docs/configuring-sequential-task-processing-in-dsr-forms)

![Progression from Level 1 tasks to Level 2 tasks in a project management interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[DSR] Support for sequential tasks.jpg)

---

## Download All Attachments in a Task or DSR With One Click

Downloading attachments from a DSR with dozens of files used to mean opening each one individually, whether reviewing a single subtask or preparing a full case file. Now a single click downloads a zip file of every attachment at the subtask, task, or DSR level. For example, click Download All Attachments on a DSR to get every file across every task and subtask in one zip, instead of working through them one by one. You only need view access to the DSR to download its attachments, not ownership. Securiti emails a download link once the file is ready, active for 24 hours, and logs every request in the DSR audit log.

[See how to download all attachments in a subtask, task, or DSR request](/latest/docs/previewing-and-downloading-dsr-and-dsr-subtask-reports)

![Overview of DSR Workbench with tasks and subtasks for project management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[DSR] Download all attachments across tasks, subtasks and DSRs (1).png)

---

## Introducing the Risk Metrics Dashboard

A nine-widget Risk Metrics Dashboard is now available under Risk Management. Widgets include:

- Risk by Status
- Residual Risk by Level
- Overdue Risks
- Risk Created by Quarter
- Risk by Scope
- Risks Closed by Quarter
- Risk Levels per Organization
- Risk by Tag Type
- Risk Breakdown by Tag Types

Clicking a slice or segment on any widget opens a pre-filtered risk view for that selection. A global filter bar narrows data across all widgets, and each widget can be expanded to full screen. Learn more about the Risk Metrics Dashboard.

[Learn more about the Risk Metrics Dashboard](/latest/docs/navigating-the-risk-metrics-dashboard)

![Dashboard displaying risk metrics, including total risks and overdue items by status.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[Risk Management] Introducing the Risk Metrics Dashboard (1).jpg)

---

## Integrate Your Self-hosted Adobe Marketo Engage with Securiti

If you are managing sensitive data in Self-hosted Adobe Marketo Engage, Securiti now provides deeper visibility and governance across the data system. Adobe Marketo Engage connector discovers and classifies structured records and unstructured files like email attachments. You can also run DSR requests for access, deletion, and correction against that data directly on-premises.

[Learn how to integrate Adobe Marketo Engage](/latest/docs/adobe-marketo-engage-connectors)

![Integration of two platforms showcasing various file types and formats for processing.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[Data System Connectors] Introducing Jira Cloud and Adobe Marketo Engage for Unstructured and hybrid Data Scanning-3 (1).png)

---

## Passport ID Detection Now Covers 12 More EU Countries

When you need reliable passport detection across EU data, coverage matters as much as accuracy. Securiti’s Passport ID detection already handled many formats well. Now it extends to 12 more EU countries: Austria, Belgium, Bulgaria, Croatia, Cyprus, Czechia, Denmark, Estonia, Finland, Greece, Hungary, and Latvia. This includes detection across both OCR and non-OCR content, so a passport number is flagged whether it appears as text in a document or as an image in a scanned file.

[Explore the OCR-supported document types in detail](/latest/docs/ocs-supported-document-types)

![A world map with an emphasis on OCR Scan technology for document processing.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[CC] Expanded Passport Detection(1).jpg)
