---
title: "What's New in 1.137"
slug: "whats-new-in-1137"
updated: 2026-04-28T16:59:20Z
published: 2026-04-28T16:59:20Z
canonical: "helpcenter.securiti.ai/whats-new-in-1137"
area: geral
modulo: whats-new
tipo: guia
data_captura: 2026-10-08
---

# What's New in 1.137

### Introducing New RBAC with Granular Permissions

Every team structures access differently—and a one-size-fits-all role system doesn’t always cut it. With Securiti’s new RBAC, you can define roles using fine-grained permissions that go far beyond traditional owner or user labels. Build each role around specific actions that match real responsibilities, whether it's viewing metadata related to sensitive records, managing access governance operations, or modifying policies. This gives admins tighter control over who can do what, ensures users only access what they need, and supports better enforcement of least-privilege access across the platform.

[See how fine-grained permissions work in practice](/v1/docs/new-role-based-access-control-rbac-en)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-0Q82Y41L.png)

### Introducing Robotic Automation Setup Dashboard

If you are unsure where your DSR automation stands, the new dashboard answers that at a glance. It shows total purchased versus active licenses, reports on all system types, and highlights automation statuses. You might notice that one system is ready with “Active Connection,” or another is still in “Discovery Scan.” Or a system may show “Failed Connection” or “No Discovery Scan with DSR Setting.” Each status signals exactly what needs follow-up. Not sure how to complete the setup? The Setup Wizard takes you through the steps, such as connecting systems, configuring permissions, and completing scans, so the instance is ready to serve DSR requests.

[Read the Robotic Automation dashboard guide](/v1/docs/using-robotic-automation-setup-dashboard)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-IZSBH2DP.png)

### Cleaner, Region-and Language-Specific Forms

When forms try to handle too many regions and languages within the same view, they can confuse the person filling them out. Universal forms let you cut through that. You choose what countries, states, and languages should appear. With language intelligence enabled, the form also shows up in the person’s browser language. The result is one global form that automatically adapts. It is easier for you to manage, and it feels clearer for the people who use it.

[Understand how forms adapt globally](/v1/docs/creating-and-publishing-universal-forms)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-5L2SE0KM.png)

### Make Time for Complex DSRs with Deadline Adjustment

Not every DSR request fits neatly into the standard timeline. Along with auto extensions that apply only when the deadline is reached, you can now extend deadlines manually in the DSR dashboard anytime before they expire. This is useful when a request is complex, depends on subject feedback, or needs extra review of sensitive data. You can also use it when external processors are involved or workload is unusually high. Manual extension gives you flexibility to manage cases without waiting for the clock to run out.

[Review manual extension process](/v1/docs/manually-extending-for-dsr-deadlines)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-EVPJGERR.png)

### Privacy Requests Now Speak Georgian

Filling out a privacy request in a language that’s not your own can be tricky. With Georgian now supported in the Data Subject Rights module, that barrier is gone. DSR forms, universal forms, notifications, and Privacy Central are all available in Georgian. This allows data subjects to understand each step of the process in their own language. When data subjects understand the form, they are less likely to make mistakes, and you are more likely to meet response deadlines faster with complete details.

[See the list of supported languages](/v1/docs/supported-languages-in-data-subject-rights)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-SZ34PHH2.png)

### Upcoming: DSR Requests Aligned With New Vietnam Provinces

DSR requests rely on accurate region data. In the upcoming releases, Securiti will update the Vietnam region list with the government’s latest provinces and cities. The list will change from 63 provinces to 34 provinces and cities. Any DSR requests that reference the old provinces will be migrated automatically, ensuring records remain consistent with official updates.

### Integrate Your AWS Compatible Storage & RDS for MS SQL Server

Securiti expands its support for S3-compatible storages such as MinIO, StorageGrid, and IBM Cloud Object Storage, and Amazon RDS for MS SQL, helping you connect and scan more of your data systems.

With the self-hosted connector, you can integrate non-AWS S3 applications and scan for object tags, versions, and multipart uploads. Meanwhile, the new Amazon RDS for MS SQL lets you run discovery scans and automate DSR requests on your managed MS SQL databases.

[Learn how to connect S3-compatible storage and Amazon RDS MS SQL](/v1/docs/supported-data-system-connectors-in-securiti)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-PYMB1Y0R.png)

### Deeper GCP Visibility With RAG & Dataproc Discovery

It’s not always easy to keep track of where your data-heavy processes live in GCP. To help with this, asset discovery now includes GCP RAG Engine Corpus and Dataproc Clusters. These assets show up with the rest of your inventory, so you don’t need to dig around. You can quickly see where knowledge sets are stored and where large-scale jobs run. This makes it easier to map and understand your GCP environment with complete visibility into it.

[Read more in docs](/v1/docs/data-security-posture-management-solution#list-of-supported-cloud-native-services)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-5PH6E29M.png)

### Run Posture Scans on Box and Salesforce CRM (Self-Hosted)

Managing scans for self-hosted apps can get complicated when you have to set up separate connectors. Now you don’t have to. You can run posture scans on Box (Self-hosted) and Salesforce CRM (Self-hosted) with your existing on-prem connectors. This means less setup work, fewer moving parts, and the same complete security and compliance visibility into your data systems.

Read how to configure posture scans for [Box](/v1/docs/activate-the-box-self-hosted-connector-in-securiti) and [Salesforce CRM](/v1/docs/activate-the-salesforce-crm-connector-in-securiti-2)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-K0UJ05OM.png)

### New Framework Coverage: German C5

Struggling to keep pace with cloud security standards for Deutschland? The Compliance module now supports Germany’s C5 (Cloud Computing Compliance Controls Catalogue). C5 is a widely adopted baseline for auditing cloud service providers. You can operationalize C5 using pre-mapped controls and automation across areas such as access, cryptography, and incident management. For example, you can readily test if encryption keys are properly managed or if unused accounts remain active. This makes preparing for C5 audits simpler and more reliable.

[See the full list of supported frameworks](/v1/docs/using-the-framework-dashboard)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-0SXLJW5Z.png)

### Too Many Files to Label? Let Data Labeling Policy Handle It

Manually labeling files might work if you are dealing with two or five—maybe even ten. But not when there are hundreds or thousands spread across your systems. With Securiti’s Data Labeling policies, you can automatically apply sensitivity labels like Restricted, Confidential, or Public using Microsoft Purview or Google Drive Labeling. Choose whether labels should apply instantly or after review. You also control whether to keep or replace existing labels. Perfect for teams ready to stop spending time on something that should have been automatic all along.

Learn more about [Data labelling Policy for Google Drive](/v1/docs/creating-data-labeling-policy-for-google-drive-files) and [Microsoft Purview](/v1/docs/creating-data-labeling-policy-for-microsoft-purview)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-10H3R9K0.png)

### Plan, View and Launch Discovery Scans from a Single Calendar

When you are running multiple discovery scans—across multiple data systems, regions or clouds—it’s easy to lose track of what ran, what’s running, and what’s coming up. The new Scan Calendar Dashboard gives you a clear, centralized view. Each scan appears on a calendar so you can see what’s scheduled at a glance.

Switch between views, filter by systems or status, and save frequent searches to avoid starting over. You can even launch new scans directly from the calendar. If you need to share or audit the schedule, export it as a CSV

No tabs, no timelines, no digging—just everything in one place.

[Learn more about the Discovery Scan Calendar](/v1/docs/viewing-discovery-scan-calendar-dashboard-en)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-EZCYPS7P.png)
