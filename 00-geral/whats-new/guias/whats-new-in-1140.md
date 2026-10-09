---
title: "What's New in 1.140"
slug: "whats-new-in-1140"
updated: 2026-04-28T16:58:51Z
published: 2026-04-28T16:58:51Z
canonical: "helpcenter.securiti.ai/whats-new-in-1140"
area: geral
modulo: whats-new
tipo: guia
data_captura: 2026-10-08
---

# What's New in 1.140

### Introducing the New Help Sidebar + New Help Center Experience

We have officially launched a brand-new help center experience, and at the heart of it is the new AI-based Help Sidebar. Click the Help button within the Securiti platform to open a smart, contextual sidebar that shows the exact article related to what you are working on. Need more answers? You can chat with the built-in AI assistant right there. You can also explore the new experience of the documentation in a new tab, with a refreshed layout and information more accessible.

> [!NOTE]
> Note
> 
> While the new experience is fully live, you may notice some small updates and refinements in the coming days as we polish things further.

![Securiti Help Center interface featuring AI assistance and user feedback options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/move to doc360 (2).jpg)

---

### Discover More Cloud Assets: OpenAI Agent, OpenAI Knowledge Base, and Key Vault

When you’re trying to understand your risk in Azure cloud, missing AI or secret-related services creates blind spots. With this update, Asset Discovery can now find Azure OpenAI Agent, Azure OpenAI Knowledge Base, and Azure Key Vault. It identifies agents, the knowledge sources they rely on, and the vaults that store keys and secrets. Run an Asset Discovery scan, and these services appear alongside your other assets. That helps you review exposure, plan controls, and keep your inventory up to date.

[Learn more in docs](/v1/docs/data-security-posture-management-solution#list-of-supported-cloud-native-services)

![Visual representation of features including a star, book, and key icons connected to a central logo.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[IaaS Cloud] Discover More Cloud Assets_ OpenAI Agent, OpenAI Knowledge Base, and Key Vault.jpg)

---

### Support for CockroachDB and Microsoft Dynamics 365 Finance & Operations

Sensitive data lives in more places than ever, and now you can connect two more of them. With Securiti, bring Microsoft Dynamics 365 Finance and Operations and CockroachDB into your data and asset discovery strategy using self-hosted connectors. Set up is simple: use OAuth for Dynamics 365 and Basic Authentication or Vault secrets for CockroachDB. Then kick off scans to see what’s where across schemas, tables, and views, all while staying in control from a central dashboard.

Learn how to integrate [CockroachDB](/v1/docs/cockroach-connectors-en) and [Microsoft Dynamics 365 Finance & Operations](/v1/docs/microsoft-dynamics-365-finance-and-operations-connectors)

![Two logos displayed on a light blue background, representing different brands or services.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[Data System Connectors] Support for CockroachDB and Microsoft Dynamics 365 Finance &amp; Operations.jpg)

---

### New Masking Condition for Data Sanitization

Some fields aren’t just numbers or text, they are a mix of both, like license numbers, access tokens, or insurance IDs. These need a smarter approach to masking. That’s why Gencore AI’s Data Sanitizer node now includes a masking condition tailored for alphanumeric strings. It replaces these values with randomized but realistic patterns, and you can turn it on only where needed. It lives right alongside your current masking options, so setup stays simple.

[Learn more in docs](/v1/docs/data-sanitizer)

![New Data Sanitizer Node featuring Alphanumeric Masking and example data XYS123!](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[Gencore]New Masking Conditions for Data Sanitization.jpg)

---

### Automate Next Steps in Assessments

Sometimes you need an assessment to move forward only when the right answer appears. Associate Rules help you set that up. You can trigger another assessment when a form is completed or when a key question is answered. You can also bring in people at the right moment. For example, add a legal reviewer when the stage moves to In Review, or add a respondent when a question confirms data sharing. This gives you steady control over who joins, what they can see, and when they are added.

[Learn more about Associate Rules](/v1/docs/configuring-template-rules)

![Flowchart illustrating a process with decision points and outcomes for functions.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[Assessment Automation]Automate actions in assessment templates.jpg)

---

### Go Beyond the Defaults with Regulation Adjustments

You may run into DSR requests that do not fully match the built in rules. Your interpretation may be stricter, or you may need coverage for a region still missing. The Regulations Support page helps you fill those gaps. It shows every standard regulation and lets you adjust details or create one of your own. You can search, filter, and check request types and timelines before making changes. This gives you a clear path to keep compliance aligned with your internal policy.

[Show me how to do it](/v1/docs/using-the-regulations-support-dashboard)

![Overview of DSR regulations support with key statistics and relevant categories displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[DSR]Enhancements to Robotic Automation Dashboard (1).jpg)

---

### See Post-Consent Behavior Through Automated Simulation

Seeing what happens after a data subject grants cookie consent is now part of the scanning experience. The cookie scanner now works with major CMPs such as **CookieYes**, **OneTrust**, **TrustArc**, and **Usercentrics** to surface cookie behavior across consent setups. It automatically simulates consent during a scan and uncovers the cookies that appear only after approval. It also checks how your domain behaves with GPC turned on or off to give you a complete picture of your consent experience. If a cookie banner loads late, the scanner still captures the right signals, ensuring nothing is missed. The final report clearly shows which CMP was detected and how consent was recorded, giving you confidence that cookie blocking and unblocking work exactly as intended.

[Learn more about automated consent simulation](/v1/docs/scanning-your-website-for-cookies)

![A cookie consent notification with user profile and action buttons displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/See Post-Consent Behavior Through Automated Simulation.jpg)

---

### Stay Aligned With IAB TCF Rules With the New v2.3 TC String Format

Managing consent under IAB EU TCF now requires sending the updated v2.3 TC String structure to vendors. Securiti generates this format automatically, so you do not need to adjust anything manually. The updated TC String includes essential consent details, a complete list of vendors shown to the data subject, and an optional publisher section for your own restrictions. This helps keep your transparency signals accurate and ensures vendors can read your consent data without issues.

[See how the updated TC String format works](/v1/docs/configuring-an-iab-eu-tcf-v22-cookie-consent-banner)

![IAB Europe logo surrounded by icons representing data and privacy concepts.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Stay Aligned With IAB TCF Rules With the New v2.3 TC String Format.jpg)
