---
title: "Understanding how Securiti categorizes cookies and trackers"
slug: "understanding-how-securiti-categorizes-cookies-and-trackers"
updated: 2026-09-22T12:31:11Z
published: 2026-09-22T12:31:11Z
canonical: "helpcenter.securiti.ai/understanding-how-securiti-categorizes-cookies-and-trackers"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Understanding how Securiti categorizes cookies and trackers

Securiti’s Cookie Consent Management module categorizes cookies and trackers detected during a domain scan into out-of-the-box (OOTB) cookie categories. Securiti uses cookie metadata, such as name, domain, source script, expiration, data type, and third-party associations, to identify each cookie’s purpose and assign it to a cookie category.

Use the following table to understand Securiti’s **eight** OOTB cookie categories and their purposes:

| Cookie Category | Purpose |
| --- | --- |
| Essential | These cookies are necessary for the website to function properly. They support critical features such as authentication, maintaining session state, managing shopping carts, and enabling payment transactions. Data subjects cannot disable this cookie category from the preference center. |
| Advertising | These cookies enable websites to deliver relevant advertisements or support integration with third-party ad services. They track browsing behavior across sites to build data subject or user profiles and deliver targeted content, improving ad relevance and effectiveness. |
| Analytics & Customization | These cookies provide site owners with statistical insights, such as page visits, dwell time, bounce rates, technologies used to access the site, and load performance. They help analyze usage trends and optimize the user experience. |
| Performance & Functionality | These cookies help improve site performance and usability. They remember data subject preferences such as selected language, region, or login details, and collect information about how data subjects interact with the website, such as pages visited and links clicked. |
| Social Networking | These cookies are set by social media platforms to enable content sharing and engagement features such as Like or Share buttons. They may track data subject activity across websites to build behavioral profiles and deliver social or interest-based advertising. > [!NOTE] > Note > > At the moment, Securiti does not push any cookies or trackers into this cookie category. However, you can manually move or assign relevant cookies or trackers here to suit. |
| Unclassified | These cookies and trackers are known to Securiti but they do not match any record in the Securiti cookie knowledge base, so Securiti cannot determine their purpose yet. Review them and assign each one to a specific cookie category. |
| Biometrics | These cookies use biometric identifiers, such as fingerprints or browser-specific data, to distinguish data subjects and sessions, enhancing security and preventing fraudulent activity. |
| Precise Geolocation | These cookies collect accurate geographic data such as latitude, longitude, or radius to deliver content or services tailored to a data subject’s physical location. |

Securiti categorizes **cookies**, **image beacons**, **pixels**, **trackers**, **local storage items**, **session storage items**, and **other tracking technologies** based on their purpose and behavior. If Securiti detects a cookie or tracker but cannot assign it to a specific cookie category, it places it in the **Unclassified** cookie category. Review these cookies and assign each one to a specific cookie category. Until you do, data subjects see them in the preference center as Unclassified. Under the Opt-out compliance type, Securiti enables the Unclassified cookie category by default, so its initiators run until a data subject declines it. Assigning a cookie also improves future scans. Securiti keeps your assignment for later scans of the same domain and does not return the cookie to the Unclassified cookie category.

> [!WARNING]
> Important
> 
> Once customized, Securiti retains these manual categorizations for future scans of the same domain and does not rely on the knowledge base to categorize those specific cookies again.

Additionally, Securiti’s categorization framework includes modern consent-related categories such as **Biometrics** and **Precise Geolocation** to align with evolving privacy laws and consent requirements. These categories ensure that data subject choices are handled transparently and in compliance with frameworks like GDPR, CPRA, and LGPD.

## Key factors Securiti uses to categorize cookies and trackers

Use the following table to understand the key factors Securiti uses to categorize cookies and trackers:

| Factor | Description |
| --- | --- |
| Purpose detection | Identifies whether a cookie is necessary for basic site functionality or used for purposes such as analytics or marketing. |
| Source and domain analysis | Determines whether a cookie originates from a first-party or third-party source. |
| Vendor mapping | Matches cookies to known services, vendors, or platforms based on metadata and domain information. |
| Behavioral pattern recognition | Detects how cookies collect, store, or share data to understand their operational intent. |

Together, these factors help Securiti categorize cookies consistently, reduce manual categorization effort, and present cookie purposes clearly in cookie banners and preference centers.

In general, the categorization process involves mapping cookies to known vendors or technologies, examining their usage patterns (for instance, analytics vs. ad tracking), and aligning them with standardized consent purposes. This ensures consistency, compliance, and transparency in how cookies are presented to data subjects and site visitors in cookie banners and preference centers.

## How Securiti improves cookie and tracker categorization

The Knowledge Base (KB) team categorizes cookies based on information available across reliable web sources using three main methods:

### 1. Machine learning (ML) categorization

The ML-based algorithm uses a model trained on manually researched cookies as training data to predict cookie categories accurately. It processes only uncategorized entries from the input data and stores the classified results in the output directory.

During execution, Securiti provides detailed categorization statistics such as the number of predictions per model and the proportion of unclassified cookies. Securiti evaluates model performance using precision, recall, and confusion matrix metrics to ensure accuracy and consistency across cookie categorizations.

You can configure additional options such as evaluation files or custom output paths through command-line parameters.

### 2. Automation tool

The cookie categorization engine automatically categorizes cookies to support privacy compliance and analysis. It combines web search data with artificial intelligence to categorize cookies accurately. The automated workflow includes:

- Initialization
- Web search and data gathering
- Content processing
- AI-based categorization
- Response processing
- Quality control
- Output and storage

Securiti uses the **Google Custom Search API** and classifies cookies into OOTB cookie categories using the following capabilities:

- Handling web content and large language model (LLM) fallback paths
- Validating data
- Managing errors and cache
- Supporting batch processing for scalability and resume functionality

Securiti operates in two modes:

#### Web content mode

- Uses extracted web content to categorize cookies
- Follows context-based information strictly
- Avoids probabilistic language

#### Fallback mode

- Uses the LLM’s internal knowledge when web data is unavailable
- Makes informed assumptions based on cookie naming patterns
- Applies reasonable defaults for unknown cookies

This approach provides reliable and scalable cookie categorization by combining web data with AI inference. It ensures data integrity through multiple validation and fallback steps.

### 3. Manual research

The KB team researches cookies across different search engines and websites. They categorize each cookie according to the standard cookie category description format and the details available on the source site.

They also analyze cookies based on ownership. If a cookie is initialized by or associated with a specific vendor, the cookie’s service name is attributed to that vendor. For instance, a cookie created by Google Analytics is categorized under Google’s services.

## How Securiti matches cookie metadata

Securiti matches cookie metadata, such as cookie category, description, and display name, against records in the consent database.

Use the following table to understand how Securiti matches cookie metadata:

| Lookup type | Description |
| --- | --- |
| Exact match lookup | When both the cookie name and cookie host are an exact match, Securiti retrieves the full metadata record from the consent database. This applies to both regex-based and standard cookies. |
| Partial lookup | When only a cookie name matches, the lookup returns essential metadata such as cookie category and description. This maintains performance while still identifying relevant cookies. |
| Wildcard or broad lookup | When a host matches multiple cookies or patterns, Securiti uses predefined lookup rules to ensure dynamic or pattern-based cookies are resolved accurately without duplicating or overwriting shared data. |

These lookup methods help Securiti retrieve relevant cookie metadata while maintaining consistency across domains.

The General Data Protection Regulation (GDPR) is an European Union (EU) regulation on information privacy. It aims to ensure the protection of personal information through a human rights-centric approach, and imposes obligations onto organizations anywhere, so long as they target or collect data related to people in the EU.

The California Privacy Rights Act (CPRA) amended the CCPA by adding additional consumer privacy rights and obligations for businesses. It also created the California Privacy Protection Agency (CPPA), tasked with enforcing the law and educating the public on their rights and obligations under the law.

Lei Geral de Proteção de Dados (LGPD) or simply called General Data Protection Law is Brazil’s first comprehensive legislation aimed at protecting the fundamental right of privacy. It applies to every natural person or legal entity, either public or private, that handles personal data of Brazilian citizens. The LGPD can also apply extraterritorially similar to the GDPR. You can choose between Global or LGPD template in Privacy Notice Management module.

## Related

- [Cookie Consent Management terminologies](/cookie-consent-management-terminologies.md)
- [Resolving cookie categorization conflicts in auto-blocking](/resolving-cookie-categorization-conflicts-in-auto-blocking.md)
