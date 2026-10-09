---
title: "What's New in 1.148"
slug: "what-s-new-in-1-148"
updated: 2026-08-12T08:38:17Z
published: 2026-08-12T08:38:17Z
canonical: "helpcenter.securiti.ai/what-s-new-in-1-148"
area: geral
modulo: whats-new
tipo: guia
data_captura: 2026-10-08
---

# What's New in 1.148

## A Solution Brief on Minimizing ROT Data Across Your Enterprise

Redundant and obsolete data piles up across hundreds of teams in a large enterprise, and it's rarely obvious who owns it. The central data team scanning for ROT data has no way to know who to ask before deleting anything. At Securiti, we have published the ROT Data Minimization for Large Enterprises solution brief to walk you through how to close that gap using capabilities already available to you within our platform, such as: a Data Tagging policy attributes each file to its real owner, an Automation policy routes it to that owner's ServiceNow or Jira queue, and the owner reviews and quarantines only their own items in the Remediation Workbench. Deletion still runs through your own end-of-life policies, so the final call stays exactly where it belongs.

[See the blueprint for ROT data minimization](/latest/docs/rot-data-minimization-for-large-enterprises)

![Diagram illustrating data flow between ROT Data, Skype, and Jira applications.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[Brief solutions] Route Redundant and Obsolete Data to the Right Owner.jpg)

---

## Gain Visibility into Duplicate Files Across Your Data

Duplicate files accumulate across your data systems, but understanding how much storage they consume and where they exist isn't always straightforward. The new Duplicate Files reporting dashboard brings everything into a single view, highlighting key metrics such as reclaimable storage, duplicate file count, and sensitive duplicate data. It also identifies the top data systems, file owners, and folders with duplicate files. One instance surfaced 795.9k duplicate files, with a single file owner tied to over 487,000 of them, turning cleanup priorities into something you can point to instead of guess at.

[Take a look at the duplicate files report](/latest/docs/duplicate-files-dashboard)

![Overview of storage metrics including reclaimable storage and duplicate files statistics.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[SDI] Gain Visibility into Duplicate Files Across Your Data.png)

---

## Build Flexible Scope Queries & Get Notifications for Data Labeling Policies

When you're scoping a Data Labeling policy for files sitting in an S3 bucket, starting at the Data System node and working down to Files often makes more sense than starting at Files itself. Now the scope query lets you begin there, connect it to Files, and filter at each level. While you're building the policy, you can also set up an email notification so the data system owner, selected users, or both get a count of files labeled, skipped, or failed after each run.

[Read more in docs](/latest/docs/using-data-labeling-policies)

![Data system overview with email notification settings and file properties highlighted.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[SDI]Build Flexible Scope Queries and Get Notifications for Data Labeling Policies.png)

---

## Detect Sensitive Information in Swedish Files

Working with Swedish documents meant sensitive data detection wasn't built for the language yet, so results depended on English-pattern matching underneath. That's changed. The platform now supports Swedish directly, detecting names, contact details, location data, and key identifiers in Word, Excel, and PDF files written in Swedish. Discovery scans pick up these files automatically across your connected data systems, so nothing extra needs to be configured. Teams working with Swedish data get detection built for the language itself, not a workaround.

[See the list of supported languages](/latest/docs/data-classifications)

![Interface showing content classification with a save button and Swedish language option.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[CC] Detect Sensitive Information in Swedish Files.jpg)

---

## Broader OCI Asset Discovery, Now with Contextual Visualization

When you need to trace how an OCI resource connects to everything around it, the network it sits in, the risks tied to it, you want a contextual view that shows the full picture. Securiti now brings that same depth to OCI, matching the contextual data visualization already available for AWS, GCP, and Azure. It ingests OCI resources and their relationships into graph-powered dashboards, links them to existing posture scan rules, policies, and findings, and surfaces it all in Graph Explorer, Universal Data Explorer, and Inventory. Furthermore, asset discovery now covers 34 more OCI services, so you can query and filter OCI assets the same way you already do for the rest.

See how OCI [asset discovery](/latest/docs/visualizing-results-of-oci-asset-discovery) works, and check the [full list of supported services](/latest/docs/data-security-posture-management)

![Oracle Cloud Infrastructure dashboard showcasing asset discovery and service options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[IaaS Connectors] Broader Asset Discovery Support OCI Services.png)

---

## Introducing Automatic Infrastructure Deployment for EPod V2

Your team needs EPod V2 running in a fresh cloud account, but there's no Kubernetes cluster, no Redis instance, and no networking in place yet. Setting all of that up manually before even touching EPod V2 can take days. Quick Install changes that. Select your cloud provider and region in Securiti, click Prepare Template, and upload the downloaded file to your provisioning tool. It provisions the full infrastructure, networking, Kubernetes cluster, Redis, IAM roles, and deploys EPod V2 automatically. No manual setup required.

[Learn more about how Quick Install works](/latest/docs/epod-v2-installation-using-cloud-template)

![Document upload process leading to successful integration with a colorful data visualization tool.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[Platform] Introducing EPod V2 quick install.png)

---

## Authenticate the GitHub Connector with Native App Authentication

Scanning a large GitHub repository through a personal login can run into rate limits that slow things down. If that user's access changes, the scan stops until someone reconnects it. Switching to GitHub App authentication within Securiti solves both issues. It connects through the organization's GitHub account and is approved only once. Because it isn't tied to a single user's login or rate limits, even large repositories scan without the delay.

[Get the details in the GitHub App setup guide](/latest/docs/connecting-github-with-securiti)

![Illustration showing connection between two platforms with a central figure representing integration.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[Connector]GitHub App Configuration &amp; Handshake.png)

---

## Operationalize Compliance for Chile, Canada, NIST, and Quebec

Compliance teams covering multiple jurisdictions spend more time mapping controls to regulations than actually testing them. The Compliance module now includes four new frameworks: Chile's Law No. 21.719, OSFI Canada Guideline B-13, NIST Privacy Framework, and Quebec Law 25. The Chile framework lets you check cross-border transfer assessments and sensitive data handling. OSFI covers technology governance and cyber security posture against Canada's financial institution requirements. NIST helps verify data processing policies and access controls across the full data lifecycle. Quebec Law 25 lets you confirm consent is purpose-specific and destruction policies are enforced. From Chile to Canada, all four frameworks are ready the moment your team needs them.

[See supported list of frameworks](/latest/docs/using-the-framework-dashboard)

![Overview of privacy frameworks including NIST, Quebec Law 25, and Chile PPDL.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/New Frameworks Coverage in Compliance.png)

---

## Custom Risk Levels and Scoring in Risk V2

When risk scoring needs to reflect your organization's definitions of likelihood, severity, and acceptable exposure, Risk V2 now provides the controls to configure it. From Risk Settings under Risk Management, Risk Admins can switch between Linear and Risk Matrix scoring frameworks, define custom risk levels, configure the risk matrix grid up to 10×10, and choose an aggregation methodology across Mean, Median, or Maximum. These settings apply to privacy assessments and data mapping objects. Changes to risk level labels, scores, and matrix cell scores apply to existing inherent and residual risk values automatically.

[Learn more about configuring risk settings](/latest/docs/configuring-settings-in-risk-v2)

![Graph comparing Linear Model and Risk Matrix models with risk levels indicated.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[Risk Management] Risk settings enhancements in Risk V2.jpg)

---

## Meet Consent Agent: AI-Powered Cookie Consent Compliance Detection & Remediation

Your legal team flags a cookie compliance violation, but no one knows how widespread it is or where to start. That uncertainty is what makes cookie consent compliance hard to manage at scale. Consent Agent scans your domains against privacy and cookie compliance requirements, identifies issues, and flags them as risks. Your team can remediate manually with guided workflows, or let automated workflows handle it entirely. A single dashboard shows compliance health across all scanned domains, so you can assess posture, monitor risks, and track remediation progress in one place.

[See how to set up and use Consent Agent](/latest/docs/using-the-compliance-dashboard-to-remediate-cookie-compliance-risks)

![Overview of Consent Agent with compliance scores and remediation options displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Meet Consent Agent - AI-Powered Cookie Consent Compliance Detection &amp; Remediation.png)

---

## Unified Consent Across All Your Domains

If you run multiple websites, data subjects may have to give cookie consent preferences separately on each one, even when it's the same person moving from site to site. Now you can group those domains into a Cross-Domain Consent Group, map each domain's cookie categories to a shared set of OOTB standard categories, and let one consent choice apply across all of them. Once this setup goes live, a data subject who accepts or declines cookies on one site sees that same consent preferences reflected across other sites in the group, cutting down repeat prompts and keeping consent consistent across your web presence.

[Learn how to configure Cross-Domain Consent Groups](/latest/docs/using-cross-domain-consent-groups-to-sync-consent-across-domains)

![Illustration of cross-domain consent group connecting multiple websites for data sharing.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Unified Consent Across All Your Domains.jpg)

---

## Improved Error Visibility while Testing your GenAI Pipelines

Troubleshooting a GenAI pipeline means tracking down exactly what went wrong, whether that's a connection issue, a misconfigured endpoint, a bad query, or something else. Gencore AI now provides clearer error reporting across the board when you test your pipeline, so failures of any kind are easier to identify, not just the common connectivity and authentication cases. The Test interface reflects this broader visibility, giving you a more complete picture of pipeline health whenever a test doesn't go as expected.

[Read the docs on pipeline troubleshooting updates](/latest/docs/creating-a-new-pipeline)

![Error message displayed in a test pipeline interface with retry option.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[Gencore] Improved error visibility while testing GenAI pipelines.jpg)

---

## Filter the EDC Dashboard by Domain and Owner

A data catalog that spans dozens of domains and hundreds of owners is hard to read as a single view. The EDC Dashboard now lets you filter by Domain or Owner, with search built into both. Applying a filter updates every section at once, including tile counts, onion graphs, bar charts, and top-list recommendations, so the entire dashboard reflects your selected scope.

[Read more on filtering your dashboard by domain or owner](/latest/docs/edc-dashboard)

![Dashboard interface showing options to narrow down data by owner or domain.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/EDC Dashboard_ Smarter Filtering and PDF Export.png)

---

## Lock Glossary Terms, Nodes, and Data Products Against Edits

Catalog entries that feed compliance reports or downstream governance workflows are easy to break if anyone can edit them. There has been no way to lock a Glossary Term, Node, or Data Product in place once it's been finalized. Now you can mark any of these entities as read-only directly on their details page. Every attribute becomes non-editable until you explicitly reverse it. The feature uses the same permission as the existing dataset read-only capability.

Find the full guide on locking catalog [glossaries](/latest/docs/glossary-terms) and [data products](/latest/docs/data-products)

![Overview of data integrity and governance with glossary terms and data products.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Read-Only Support for Glossary Terms, Nodes, and Data Products.png)
