---
title: "What's New in 1.151"
slug: "what-s-new-in-1-151"
status: "new"
updated: 2026-09-22T07:55:30Z
published: 2026-09-22T07:55:30Z
canonical: "helpcenter.securiti.ai/what-s-new-in-1-151"
area: geral
modulo: whats-new
tipo: guia
data_captura: 2026-10-08
---

# What's New in 1.151

## Introducing AI Tuning for document types

A data governance lead finds a sensitive file misclassified in a public storage bucket. Without a way to fix the classification at scale, the same error likely exists across hundreds of similar files. Document Type AI Tuning lets you correct a misclassified file and automatically apply that correction across all semantically similar files at once. What used to require touching each file individually now takes a single feedback session, giving your team confidence that document classifications across your unstructured data actually reflect reality.

[Find out how to correct classifications at scale in the docs](/latest/docs/classifying-document-types-using-ai-tuning)

![Document Type interface showcasing AI Tuning feature for enhanced functionality.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[SDI] Document Type AI Tuning.png)

---

## Detect Sensitive Information in Czech Files

Working with Czech documents meant sensitive data detection wasn't built for the language yet, so results depended on English-pattern matching underneath. That's changed. The platform now supports Czech directly, detecting names, contact details, location data, and key identifiers in Word, Excel, and PDF files written in Czech. Discovery scans pick up these files automatically across your connected data systems, so nothing extra needs to be configured. Teams working with Czech data get detection built for the language itself, not a workaround.

[See the list of supported languages](/latest/docs/data-classifications)

![Diagram illustrating a connection between two elements, highlighting the 'Cz' component.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[SDI] Detect Sensitive Information in Czech Files.png)

---

## Monitor Policy Activity from a Centralized View

When a policy fails, you need to check which files are affected and why. To do this, you typically had to check Action History for run details and then switch to Policy Logs to investigate file-level errors. With the new View Activity option for Data Labeling and File Quarantine policies, you can now view both the Action History and Policy Logs on a single Policy Activity page. For example, when a Data Labeling run fails, you can open View Activity to review the run details and identify the affected files and errors in the logs, without switching pages.

[Learn more in docs](/latest/docs/viewing-policy-activity-action-history-and-logs)

![Overview of policy activity showing total runs, completed, and failed statuses.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[SDI] Monitor Policy Execution from a Centralized View.png)

---

## Discovery Scan support for Sybase Connector

When you need to find where PII sits in a Sybase database, predefined classification results may not provide the scan scope flexibility you need. Discovery scan lets you configure the required scan scope instead. It classifies Sybase databases and tables, including CLOB columns, and sampling is adjustable for field classification and CLOB columns, so you scan enough to be confident without reading every value. Limits on data elements per column and per data element type keep the results specific rather than exhaustive.

[Learn how to configure](/latest/docs/configure-discovery-scans-in-sybase-ase)

![Icons representing security and data management connected by a central interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image (32)(1).png)

---

## Operationalize Compliance for Indonesia PDPL and Singapore PDPA

Keeping up with new privacy laws across Asia Pacific? The Compliance module now supports Indonesia's PDPL and Singapore's PDPA. The PDPL sets rules for consent, children's data, cameras in public spaces, DPIAs, and cross-border transfers, while the PDPA governs purpose limitation, access and correction, breach notification, and Do Not Call obligations. Use the PDPL framework to confirm consent is collected before processing, verifiable parental consent is in place for children's data, and notice is posted wherever public-space cameras operate. Or use the PDPA framework to test if marketing lists went out without Do Not Call screening, terminated numbers were never reported, or access requests missed their deadline. Pre-mapped requirements make it easier to start projects and close compliance gaps fast.

[See the list of supported frameworks](/latest/docs/using-the-framework-dashboard)

![Comparison of Indonesia's PDPL and Singapore's PDPA regulations with respective flags.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[Compliance] Indonesia PDPL &amp; Singapore PDPA Frameworks.png)

---

## Revamped EDC Ingestion Experience

Adding a metadata ingestion source used to mean working inside a popup with room for the required fields and not much else. Setup now happens on a full page, with optional settings surfaced as form fields and a description under each one. After a run, per-source history and tabs for assets, statistics, logs, and the recipe show what came in, with rollback if it did not. Authentication also moves out of the YAML recipe and into form fields, so a typo no longer surfaces as a failed connection with little to go on, and a connection test reports each check.

[See more in docs](/latest/docs/using-edc-sources)

![Overview of data catalog ingestion process with connection status and statistics.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[EDC] Ingestion Creation Gets a Bigger Canvas.png)

---

## Debug Cookie Consent Issues Without Leaving Your Web Browser

Debugging cookie consent on a live page used to mean digging through console output or immediately reaching out to Securiti Support to check the configuration. The CMP Assistant plugin, now available for Google Chrome, Microsoft Edge, and Mozilla Firefox, lets you self-diagnose these issues right from the page you're on. A DevTools panel shows the live consent state, every blocked or unblocked tracker with its reason, decoded IAB EU TCF, GPP, and Google Consent Mode signals, and a running event timeline. The toolbar badge turns red or yellow the moment something's wrong, so you know before a customer does, and buttons let you accept, reject, or reload without leaving the webpage.

[Learn how to install and debug with the Cookie Consent Browser Assistant](/latest/docs/debugging-cookie-consent-sdk-and-auto-blocking-deployment-issues)

![A browser window displaying cookie settings with options for managing cookies.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Debug Cookie Consent Issues Without Leaving Your Web Browser.jpg)

---

## A Dedicated Audit Log for Every Cookie Consent Change

Tracing a specific consent change, especially one tied to a domain that no longer exists, calls for a level of precision that goes beyond a general activity view. The new module-level audit log in Cookie Consent Management delivers comprehensive and richer domain-specific visibility built for exactly that. Search for specific events, narrow results with filters, and find what happened even after a domain is gone. It also brings Cookie & Tracker Library audit records into the same view, so nothing lives in a separate place, and everything is exportable in a CSV format on demand.

[Dive deep in the Cookie Consent Management audit log](/latest/docs/using-the-cookie-consent-management-audit-log)

![Audit log displaying user activities with filters for domain, user, and time.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/A Dedicated Audit Log for Every Cookie Consent Change.png)

---

## Cookie Banner Templates for Four More U.S. States

Expanding your cookie consent setup across U.S. states can take extra time when each region needs its own banner configuration. Cookie Consent Management now includes four new OOTB cookie banner templates in the Banner Templates Gallery for Alabama, Louisiana, Oklahoma, and Vermont. You can select the template for the state you need, review the preset cookie banner settings, and publish it after making any required adjustments. This gives you a faster starting point and helps reduce repetitive setup work for state-specific consent experiences.

[Explore the new cookie banner templates](/latest/docs/using-the-banner-templates-gallery)

![States listed with Alabama marked as excluded from the selection process.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Cookie Banner Templates for Four More U.S. States.jpg)

---

## Bring Consent Into Your Unreal Engine Apps

Gaming teams need consent experiences that work inside the game, not outside the player flow. With support for the Unreal Engine gaming framework, you can now bring in-app consent banners and preference centers to Unreal Engine-based Android and iOS games. Players can review their choices and manage SDK Purposes and Permissions without leaving the game experience. Together with existing Unity support, this helps you keep consent handling consistent across your gaming frameworks while giving players a smoother way to manage their preferences.

[Learn how to enable consent management for Unreal Engine apps](/latest/docs/unreal-engine-sdk-integration-and-implementation-guide)

![Connection between two logos representing different platforms or technologies.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Bring Consent Into Your Unreal Engine Apps.png)

---

## Control Who Gets Access to What with the New RBAC in Privacy Notice Management

Handing someone the ability to approve a privacy notice used to mean handing them the ability to edit and publish it too, since permissions weren't split that granularly. The new RBAC for Privacy Notice Management changes that. Build custom roles around exactly what a person does, like a privacy notice reviewer who can view and approve but not edit or publish. Assign multiple roles per user, set read-only access where nothing should change, and restrict notices or templates by owner or approver status. Dependent permissions are granted automatically, so setup stays simple.

[Find the details in Privacy Notice Management RBAC permissions](/latest/docs/privacy-notice-management-rbac-permissions-and-roles)

![User permissions for Privacy Notice Reviewer include view and approve options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[Privacy Notices] RBAC implementation for Privacy Notice.jpg)

---

## Archive Privacy Notices Without Letting Them Go

Business changes can make some privacy notices no longer relevant for active use without making permanent deletion the right choice. The new Archive feature lets you retire these notices while preserving them for future use. For instance, if your organization offers a seasonal product only during summer or temporarily stops offering a product due to supply issues, you can archive its privacy notice instead of deleting it. When the product becomes available again, you can restore the notice at the same URL.

[Learn how to archive and restore a privacy notice in Archiving your privacy notice](/latest/docs/archiving-your-privacy-notice)

![Privacy notice indicating archived document with download icon and highlighted status.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[Privacy Notices] Archive privacy notices.jpg)

---

## Account Creation Rules, Now Set Per Request Type

A data subject submits a Do Not Sell request and gets back a simple confirmation, not a personal data report like Access or Port would return. Being asked to create an account just to see that confirmation is an extra step they should not need. That control used to live at the tenant level, one setting applying to every request type across all your DSR forms. Now it moves down to the form level, so account creation can be skipped for specific request types within a single form, and a data subject gets their confirmation right away.

[Show me how to configure it](/latest/docs/creating-and-publishing-dsr-request-forms)

![DSR Form Builder interface showing options for request type and user preferences.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[DSR]Ability to not have DS Portal login for just DNS requests (1).png)

---

## Tracking Controls Alongside Risks

Risk Management has never had a way to track the controls put in place to manage a risk, so remediation work and governance evidence lived in spreadsheets or separate tools, disconnected from the risk itself. The new Controls Register fixes that. Create a control from a risk's details page or from the register, track its status through implementation, and record its effectiveness using the risk level or severity and likelihood scales as your risk settings. Reviewed and approved controls then factor directly into the risk's residual score, so the score reflects what's actually been done, not just what was proposed.

[Learn more about Controls linking](/latest/docs/using-controls-register)

![Controls Register displaying statuses: Not Implemented, In Progress, and In Review.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[Risk Management] Tracking Controls Alongside Risks.jpg)
