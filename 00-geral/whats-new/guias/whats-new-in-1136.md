---
title: "What's New in 1.136"
slug: "whats-new-in-1136"
updated: 2026-04-28T16:59:39Z
published: 2026-04-28T16:59:39Z
canonical: "helpcenter.securiti.ai/whats-new-in-1136"
area: geral
modulo: whats-new
tipo: guia
data_captura: 2026-10-08
---

# What's New in 1.136

### Deploy Firewalls for Safe Use of AI—Right in Your Environment Public Preview

Want to deploy your gencore services on your own infrastructure? Securiti has you covered!

Gencore AI now supports self-hosted deployments; a powerful enhancement that lets you deploy your gencore services in your own Kubernetes infrastructure. Additionally, you can configure the Gencore firewalls with your deployment on your GCP infrastructure. This feature equips you with greater control, flexibility, and compliance alignment by supporting Gencore services deployment within your own cloud or on-prem infrastructure. It also enables you to align more closely with the internal security requirements without being tied to a specific cloud setup.

[Show me how to do it](/v1/docs/configuring-user-portal)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-8IIKT0JM.png)

### Configure Multiple OpenAI-Compatible Models in Gencore AI

Tired of redoing your model setup every time you want to try something new? Now you don’t have to. Gencore AI supports multiple OpenAI-compatible model configurations. You can label them, keep them side by side, and switch between them as needed. Whether you're working on speed, accuracy, or just trying out a new approach, it’s all there, ready to go.

[Read more in docs](/v1/docs/configuring-llm-providers)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-DELCS8DP.png)

### See What’s Running in GenAI Pipeline - All in One Place

Quickly understand the status of your GenAI pipelines with the new stats bar now available at the pipeline level. Check out the newly added stats to view scan health, see how many files were processed or how much data was analyzed, and review the number of findings or policy violations detected, all in one place, without navigating across multiple views. These findings are generated against the rules defined in the LLM Firewall policy, so you can determine what action needs to be taken next.

[Learn more about it](/v1/docs/creating-a-new-pipeline)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-AF63DMTG.png)

### New Framework Coverage: India DPDPA and NIST 800-53

Trying to keep up with new laws and security frameworks? The Compliance module now supports India’s DPDPA and NIST 800-53. India’s DPDPA sets strict rules for consent, notices, children’s data, and cross-border transfers, while NIST 800-53 provides guidance on access, incident handling, and resilience. Use the DPDPA framework to confirm if consent is collected before data is processed, transfers are compliant, and DPIAs are completed where needed. Or use NIST to test if unused accounts are still active, audit logs are missing, or response playbooks haven’t been updated. Pre-mapped requirements make it easier to start projects and close compliance gaps fast.

[Find the full list of supported frameworks](/v1/docs/using-the-framework-dashboard)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-IPDTB3RG.png)

Bring Azure Logs and GCP Secrets Into View

Cloud services that handle logs and secrets are critical, but they’re not always easy to keep track of. Discovery now includes Azure Activity Logs and GCP Secret Manager assets, covering both Secrets and Regional Secrets. This means activity data in Azure and sensitive values in GCP are visible alongside your other assets. Having them in one place reduces blind spots and makes it simpler to understand where critical information lives across clouds.

[Learn more about asset discovery](/v1/docs/data-security-posture-management-solution#list-of-supported-cloud-native-services)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-N2AB1KNI.png)

### Use Enterprise Data Catalog in Your Preferred Language

Working in a catalog that is not in your language can slow you down. Now you can set the Enterprise Data Catalog to the language you are most comfortable with. Go to your profile settings and pick from the supported options, like English, Japanese, or Italian. Once you select it, the entire interface updates right away. This way, you do not need to rely on translations or workarounds. Your catalog is ready in the language you use every day.

[See how to set your preferred language in the Enterprise Data Catalog](/v1/docs/managing-your-securiti-user-profile)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-IFF3TUY0.png)

### Expand Your Regional Coverage with 8 New Cookie Banner Templates

Creating region-specific banners takes time, especially when the legal language is involved and you are starting from scratch. To make that easier, we have added 8 new ready-to-use cookie banner templates for Alberta, Bermuda, British Columbia, British Virgin Islands, Cayman Islands, Indiana, Kentucky, and Rhode Island. These templates come preconfigured with legally reviewed language, consent behaviors, along with button labels and layouts. No need to worry about manual setup, everything's already in place. If you're managing consent for these regions, you can now use these templates instead of starting from zero.

[Explore the new banner templates](/v1/docs/using-the-banner-templates-gallery)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-RQSVM2GG.png)

### Robust Data Handling with Object Multi-Select Questions

With our new Object Multi-select feature, you can now choose multiple options for a single object question. For example, if a question asks “Which data systems store customer email addresses?” you can select Salesforce, Workday, and a custom database. Each selection is displayed as a label for easy viewing and automatically generates its own field question. This lets you manage risks, responses, notes, and history for each object separately.

[Discover how to manage multiple objects in a single question](/v1/docs/answering-assessment-questions-in-securiti#answer-object-and-field-assessment-questions)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-5L0N9MG6.png)

### Export Different Versions with an Updated Template Builder UI

Working through templates is smoother now. The Assessment Template Builder has a new design that makes the layout clearer and the process quicker. You can create and prepare templates in less time with fewer clicks. The update also adds a PDF export option, available in both the template detail and templates list view. That means you can download both the past and latest versions on demand and keep them for record-keeping. Both changes aim to save time and make the builder easier to use.

[Learn more about managing templates for compliance](/v1/docs/creating-custom-assessment-templates-in-securiti)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-9B6MFG54.png)

### Edit Text, Colors, and Translations on the DSR Summary Page

After the data subject's identity is successfully verified, the summary page is often the first thing they read. With this update, you can shape that page to fit your needs. Write your own header and body text. Change the top band color. Choose which fields to show and which to skip. You can also prepare different content for third party verification, password-less login, and exceptions. That way, the page does more than confirm identity. It helps align the data subject on what they need to know next.

[Learn more on customizing request summary](/v1/docs/customize-dsr-request-summary-page)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-SROQAOXJ.png)
