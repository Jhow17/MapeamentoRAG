---
title: "What's New in 1.150"
slug: "what-s-new-in-1-150"
updated: 2026-09-22T08:25:10Z
published: 2026-09-22T08:25:10Z
canonical: "helpcenter.securiti.ai/what-s-new-in-1-150"
area: geral
modulo: whats-new
tipo: guia
data_captura: 2026-10-08
---

# What's New in 1.150

## Protect Files with MIP Sensitivity Labels

A sensitivity label without protection behind it is mostly cosmetic. It flags a file as sensitive, but anyone who already has access can still open it, copy it, or send it on. Now, Data Labeling policies can apply MIP sensitivity labels that carry protection settings, so the file is automatically encrypted and locked to the users or groups that policy allows. Someone outside that group can still get the file in their inbox, they just can't decrypt it.

The new Protected by Labels filter in the Data Labeling remediation dashboard confirms which files ended up under that protection, closing the gap between tagging a file and actually securing it.

[Get the configuration steps in the docs](/latest/docs/protected-sensitivity-labels)

![Illustration of MIP sensitivity labels showing document protection and data classification process.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[SDI] Protect and Encrypt Files with MIP Sensitivity Labels.jpg)

---

## Apply Remediation Actions at the Folder Level

When multiple files containing sensitive data are located within the same folder, remediating each file individually can require additional time and effort. You can now apply remediation actions to an entire folder at once. For example, if you identify multiple files containing sensitive data that you want to remediate, go to the Folder Browser view in the Data Remediation dashboard, select the folder containing those files, and apply the Remediate action to all files within the selected folder. This helps you remediate large volumes of sensitive data while reducing the time and effort required to manage individual files.

[Find out more about folder browser in the docs](/latest/docs/using-data-remediation-dashboards)

![Diagram illustrating HR records management with data sources, owners, and tags connected.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[SDI] Simplify Data Remediation with Multi-Entity Filtering and Folder-Level Actions.png)

---

## Route Remediation Tasks to the Right Stakeholders Using Securiti Tag Category

Imagine thousands of files across your organization are tagged with the email addresses of their respective data system owners. Manually identifying each owner and routing remediation tasks to them can be time-consuming and difficult to scale. With tag-based grouping in Automation Policies, you can now group File Insights, File Quarantine, and File ROT entities by Securiti Tag Category and dynamically route remediation tasks and email notifications to the stakeholders associated with each tag value. This helps you direct remediation work to the right stakeholders at scale, reduce manual triage, and accelerate remediation workflows.

[Follow the full setup guide in the doc](/latest/docs/using-automation-policies)

![Overview of file categories including insights, quarantine, and ROT management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[SDI] Delegate Remediation Tasks Using Tags in Automation Policies (3).jpg)

---

## Picking Up a Closed DSR Instead of Starting Over

A closed DSR request comes back to life, maybe new information about the data subject surfaces, or you catch that it was closed in error, or a regulator follows up months later. Until now, the only path forward was opening a brand new request and losing the original thread. Reopening DSRs changes that. Once enabled, eligible roles can reopen a closed request directly from the DSR workbench and continue working on it in place. No duplicate request, no lost history, just the original case picked back up.

[Read how to open closed DSRs](/latest/docs/filtering-data-elements-in-dsr-attachments)

![Form to re-open a Data Subject Request with options and action buttons.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[DSR] Reopening closed DSRs (2).png)

---

## Choosing What Data Elements Reach the Data Subject

When you need to send a data subject only the information relevant to their request, not every single element a system happens to store, the old attachment behavior got in the way. Robotic Automation included everything it found for unstructured data systems, with no way to hold specific elements back. Now you can exclude individual data elements, like a rewards number or frequent flyer number, from the file. Every other element for that data subject still appears, just not the ones you chose to leave out.

[See how to exclude data elements from DSR report](/latest/docs/filtering-data-elements-in-dsr-attachments)

![Interface for filtering data elements in a report, including options to include or exclude.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[DSR]Include exclude data elements from Robotic Automation searches (2).jpg)

---

## Bring Consent Collection to Smart TVs and Streaming Devices

Streaming audiences expect the same privacy controls on their TV that they get everywhere else, and now you can deliver that. MACM now supports consent management natively on Android TV, Google TV, Amazon Fire TV, and Apple TV (tvOS), built on the same Android and iOS SDKs already powering your mobile app. Consent screens respond to D-pad and Siri Remote input, with focus states clear enough to read from across the room. Consent collection stops being something you have to work around for TV.

[Read more about consent support for connected TV apps](/latest/docs/deploying-a-consent-banner-and-preference-center-to-the-mobile-application)

![Illustration showing device security connections to various streaming platforms like Android and Apple TV.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Bring Consent Collection to Smart TVs and Streaming Devices.png)

---

## Self-Service Mobile App Consent Data Exports

An auditor asks for six months of mobile app consent records, and pulling that data used to mean a support ticket and a wait for DevOps to run it manually. Mobile App Consent Management now includes a built-in export capability. Pick a date range, kick off the export, and get an email with a download link once it's ready. The data comes bundled as a zip of CSVs, so large exports stay manageable. One export runs at a time, with automatic retries if something fails along the way.

[Learn how to manage consent data exports](/latest/docs/exporting-mobile-app-consent-data)

![User interface for exporting consent records with date range selection and export button.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Self-Service Mobile App Consent Data Exports.png)

---

## Introducing Fine-Grained RBAC v2 for Assessments and Risk

Picture a team split across three areas: one person launches assessments and manages templates, another reviews flagged questions and creates risks, a third just updates a risk's deadline and owner without touching anything else. Under the old model, all three needed the same all-or-nothing Module Owner or User role. RBAC v2 changes that. Build custom roles scoped to exact actions across Assessment Automation, Vendor Assessment, and Risk Management, from launching assessments and inviting vendors in bulk to updating just a risk's status and deadline. Each role only opens what the job actually requires.

Learn more about custom roles in [Assessments](/latest/docs/assessment-automation-rbac-permissions), [Vendor Assessment](/latest/docs/vendor-assessments-rbac-permissions), and [Risk](/latest/docs/risk-management-rbac-permissions)

![User interface for managing privacy assessment permissions with checkboxes and action buttons.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[Assessment Automation _ Risk Management] Introducing Fine-Grained RBAC v2 for Assessments and Risk.jpg)
