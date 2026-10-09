---
title: "Configuring cookie consent experiences using Build with AI"
slug: "configuring-cookie-consent-experiences-using-build-with-ai"
updated: 2026-09-03T06:25:13Z
published: 2026-09-03T06:25:13Z
canonical: "helpcenter.securiti.ai/configuring-cookie-consent-experiences-using-build-with-ai"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Configuring cookie consent experiences using Build with AI

**Scenario**

As a Data Privacy Officer, you need to configure cookie consent experiences that meet privacy requirements across the regions where your business operates. For instance, when launching a website globally, you may need an Opt-in cookie banner for GDPR regions and an Opt-out cookie banner for CCPA/CPRA regions. Manually configuring each regional consent experience takes time and increases the risk of configuration errors. With Securiti’s Build with AI functionality, you can specify your domain and operating regions, and Build with AI applies the appropriate consent models and generates the required cookie banners and preference center. This helps you configure and deploy compliant consent experiences across regions with less manual effort.

Securiti’s **Build with AI** is an AI assistant in the Cookie Consent Management module that helps you quickly configure and deploy a fully compliant, geolocation-based cookie banner and preference center.

You can provide the domain you want to scan, define the regions where you operate, and let the AI assistant apply the correct cookie consent model. Build with AI’s interactive chat format makes it possible for Build with AI to ask follow-up questions to fully understand your requirements and generate the necessary code and content. This minimizes the need for manual configuration and reduces the risk of non-compliance with global privacy regulations.

> [!CAUTION]
> Caution
> 
> The responses provided by this AI agent do not constitute professional or legal advice. Securiti disclaims all liability for any errors, omissions, and any consequences arising from your reliance on these responses.

Use the following table to understand the operational value of this functionality offers:

| Offering | Description |
| --- | --- |
| Domain management | When you request a domain scan, Build with AI first checks whether the domain already exists in your tenant. If it does, the AI agent scans it; if not, it creates the domain and then performs the scan to detect cookies. |
| Cookie banner and preference center generation | Based on your domain scan and configuration requirements, Build with AI helps you generate a cookie banner and preference center. You can ask Build with AI to apply a custom theme using specific colors, light or bright styling, or brand-aligned color preferences. You can also embed links to your privacy and cookie policies. |
| Compliance by region | Cookie banners are configured for the regions you specify and only appear where legally required. When you define the regions where your business operates, Build with AI maps the cookie banner to the applicable regulatory frameworks, and applies the correct cookie consent model, for instance an Opt-in under GDPR/LGPD or Opt-out under CCPA/CPRA. |
| Audit-ready compliance documentation | Build with AI automatically logs each data subject’s consent decisions, including timestamps and the selected configurations. These logs create an audit trail that helps you demonstrate compliance with global privacy regulations during reviews or regulatory inquiries. |

> [!NOTE]
> Tip
> 
> If you’re not sure where to start, you can ask Build with AI, “What can you do?” and it will immediately list down all the actions it supports.

## Key considerations

You must consider the following points when using Build with AI:

- Domain scans can take anywhere from a few minutes to a couple of hours, depending on the size of the domain.
- Securiti initiates scans one domain at a time. If you request scans for multiple domains, the system processes them sequentially by starting each scan one after the other.
- Bulk actions are not available, and each domain requires individual configuration.
- Custom CSS, custom typography, banner text changes, button label modifications, and banner logo uploads are not supported. You can apply only the supported styling options available in the interface.
- Language Intelligence does not turn on automatically and requires separate configuration in the platform if needed.
- Daily usage limits apply and reset at midnight UTC, and you can remove these limits by configuring your own LLM provider and setting it as the default.
- Cookie’s AI Agent focuses exclusively on cookie consent domain management, scanning, and cookie banner configuration, and it does not manage other privacy platform features.

## Procedure

To create and scan domains, configure cookie banners for your global locations, and deploy them to your websites:

1. In Securiti, open **Cookie Consent Management**, and choose **Cookie Consent > Domains**.
2. Near the upper right corner, click **Build with AI**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Build-with-AI-button.png)
3. (If not already selected) In the **New Consent Configuration** sidebar on the left, select the Cookie Consent AI Agent from the **Select an agent** menu, as shown below.
4. In the **New Consent Configuration** sidebar on the left, enter a prompt such as “Create and scan” followed by the domain you want to scan in the text area at the bottom, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Build-with-AI-1.png)

> [!CAUTION]
> Warning
> 
> Be specific in your prompts so Build with AI can act accurately and without repeated clarification. Even though the chat retains context, vague instructions may not produce the desired outcome. For instance, instead of writing “create GDPR banners”, use a precise prompt such as “create and apply GDPR cookie banners to my domain”.
5. From the bottom right, press enter or click the black arrow icon to submit your input.
6. Select one of the following options to allow or restrict the AI agent’s actions, as shown below: ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Build-with-AI-2.png)

| Option | Description |
| --- | --- |
| Deny | Immediately stops the AI agent from performing the requested action. Domain creation or scanning gets cancelled. |
| Allow for this session | Let the AI agent perform actions for the current session only. The agent requests consent again in a new session. |
| Allow once | Let the AI agent perform a specific action one time. The agent requests consent again for subsequent actions. |

For instance, when you enter the prompt “Create and scan www.securiti.ai”, Build with AI creates the domain and also assigns the Created by AI Agent label to the domain. It then generates a default consent banner configuration, and initiates the domain scan. It then confirms each completed action and presents next steps, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Build-with-AI-3.png)

> [!NOTE]
> Note
> 
> - If the domain already exists, Build with AI detects the existing domain, displays its details, and prompts you to proceed directly with scanning the domain, as shown below.![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Build-with-AI-4.png)
> - Build with AI automatically extracts the privacy policy links from your domain and adds them to the cookie banner and preference center.
7. To style the cookie banner and preference center with your domain’s theme and color scheme, enter a prompt such as “Apply a light theme with blue buttons and a white background.”

Once Build with AI generates the theme, review the styling and request changes as needed. For instance, use prompts such as “Increase color contrast” or “Change the cookie banner background to yellow.”
8. To create cookie banners for major global jurisdictions, enter a prompt such as “Apply cookie banners for major global locations”.
9. Once you have tested the cookie banners, prompt Build with AI to “Deploy all the cookie banners”.

> [!WARNING]
> Important
> 
> When you deploy, all changes go live. Build with AI displays a warning and asks you to confirm that you have thoroughly tested your cookie banner configurations before proceeding.
10. To deploy the cookie banners, type “I confirm” and submit the prompt.

The General Data Protection Regulation (GDPR) is an European Union (EU) regulation on information privacy. It aims to ensure the protection of personal information through a human rights-centric approach, and imposes obligations onto organizations anywhere, so long as they target or collect data related to people in the EU.

Lei Geral de Proteção de Dados (LGPD) or simply called General Data Protection Law is Brazil’s first comprehensive legislation aimed at protecting the fundamental right of privacy. It applies to every natural person or legal entity, either public or private, that handles personal data of Brazilian citizens. The LGPD can also apply extraterritorially similar to the GDPR. You can choose between Global or LGPD template in Privacy Notice Management module.

The California Consumer Privacy Act (CCPA) was the first state-level comprehensive privacy law in the United States. It applies broadly to for-profit businesses that collect personal information from California consumers, creating certain rights for consumers and obligations for businesses in relation to personal data processing. It was amended by the California Privacy Rights Act (CPRA) in 2020.

The California Privacy Rights Act (CPRA) amended the CCPA by adding additional consumer privacy rights and obligations for businesses. It also created the California Privacy Protection Agency (CPPA), tasked with enforcing the law and educating the public on their rights and obligations under the law.
