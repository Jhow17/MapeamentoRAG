---
title: "Using the Banner Templates Gallery"
slug: "using-the-banner-templates-gallery"
status: "update"
updated: 2026-09-24T09:13:07Z
published: 2026-09-24T09:13:54Z
canonical: "helpcenter.securiti.ai/using-the-banner-templates-gallery"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Using the Banner Templates Gallery

**Scenario**

As a Data Compliance Officer, you manage multiple domains across different jurisdictions. For instance, launching a new domain in another region may require a banner aligned with that region’s privacy laws. Creating cookie banners from scratch each time can slow down deployment. Securiti’s Banner Templates Gallery provides pre-built, law-specific templates that you can reuse. This helps you reduce setup time while maintaining consistent compliance across domains.

Securiti lets you build a library of system and custom cookie banner templates for your domains. Using the Banner Templates Gallery functionality, you can import out-of-the-box system (OOTB) templates to comply with various laws, and apply these templates on the cookie banners and preference centers of your scanned and published domains, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Banner-Templates-Gallery.png)

> [!NOTE]
> **Note**
> 
> - If this functionality is not available in your Securiti tenant, contact your **Customer Success Manager** or **Account Representative** to confirm whether it is included in your plan.
> - If you are using a **freemium** or **lite** Securiti tenant, you must also have an active subscription for the **Geolocation** feature to leverage the pre-built system templates from the Banner Templates Gallery.
> - Securiti lets you import only the following banner templates if **Geolocation** feature is disabled for your Securiti tenant:
>   - Standard Opt-in
>   - Standard Opt-out
>   - Basic
> 
> ![Geolocation-disabled.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b474c227-300f-bc99-6b35-28596481989a.png)

Using the Banner Templates Gallery functionality, you can:

- Import pre-built **System Templates** from the **Master Gallery**. These system templates are based on various regulations that Securiti supports currently, such as California CPRA, EU GDPR, Canada PIPEDA, Brazil LGPD, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Import-Templates.png)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Import-System-Templates.png)
- Create custom banner templates, as shown below. Securiti lets you make your custom created banner templates fully bespoke to suit your organizational and jurisdictional requirements, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Cookie-Banner-Template.png)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Create-A-Custom-Template.png)
- Customize the pre-built system templates by cloning them first and making changes to the cloned version. This ensures that Securiti retains the original version of the system template for future updates.
- Preview your banners from the gallery.
- Delete existing templates from the gallery.
- Update your existing system banner templates from the gallery to ensure they comply with the most recent regulatory changes. When you update these templates, Securiti automatically upgrades them to the newest version available at that time.
- Apply a particular (system or custom) banner template to the desired number of scanned domains present in your Securiti tenant, and also deploy your changes.

> [!CAUTION]
> **Caution**
> 
> If Securiti auto-migrated your domain from Legacy SDK to the **Automatic SDK** deployment option and you have not yet published your domain, you must immediately add the new **Deployment Code** in it. Ensure it is placed at the beginning of the `&lt;head&gt;` tag.
> 
> This step is crucial, especially if you are using the **Banner Templates Gallery** functionality. Without updating and publishing the **Deployment Code**, your domain will not appear in the following popups:
> 
> - Step 1: Apply Template to Domain(s)
> - Step 2: Deploy Domain(s)
> 
> This prevents you from applying **system** and **custom** banner templates to multiple domains at once.

## System banner templates for countries and states

Use the following table to know which out-of-the-box (OOTB) system cookie banner templates Securiti offers:

> [!WARNING]
> Important
> 
> - The system cookie banner templates for California and Colorado remove dismiss-style actions and present clear consent preferences. Instead, the cookie banner requires data subjects to select either **Consent to all** or **Withdraw consent to all**.
> - The cookie preference center displays the “Your opt-out preference for cookies has been honored” confirmation notification when a data subject opts out through the cookie banner, preference center, a Do Not Sell or Share (DNSS) request, or an honored Global Privacy Control (GPC) signal. This confirmation notification persists across webpage loads as long as at least one non-essential cookie category remains declined.

| Template name for country or state | Law |
| --- | --- |
| Alabama | APDPA |
| Alberta | PIPA |
| Argentina | PDPL |
| Australia | Privacy Act |
| Bahrain | PDPL |
| Bermuda | PIPA |
| Brazil | LGPD |
| British Columbia | PIPA |
| British Virgin Islands | DPA |
| Brunei Darussalam | PDPO |
| California | CPRA |
| Canada | PIPEDA |
| Cayman Islands | DPA |
| Chile | PDPL |
| China | PIPL |
| Colombia | Law 1266 |
| Colorado | CoPA |
| Connecticut | CTDPA |
| Delaware | DPDPA |
| Dubai | DIFC DPL |
| EU | GDPR |
| Florida | FDBR |
| France | DPA |
| India | DPDPA |
| Indiana | INCDPA |
| Indonesia | PDPL |
| Israel | PPL |
| Iowa | ICDPA |
| Ireland | DPA |
| Italy | PDPC |
| Japan | APPI |
| Kentucky | KCDPA |
| Latvia | PDPL |
| Louisiana | LDPA |
| Luxembourg | Law N° 686/2018 |
| Malaysia | PDPA |
| Maryland | MODPA |
| Mexico | LFPDPPP |
| Minnesota | MCDPA |
| Montana | MCDPA |
| Morocco | LPPD |
| Nebraska | NDPA |
| Netherlands | Dutch GDPR Implementation Act also known as *Uitvoeringswet Algemene verordening gegevensbescherming* (UAVG) |
| New Hampshire | NHDPA |
| New Jersey | NJDPA |
| New York | New York Attorney General's Office |
| New Zealand | Privacy Act |
| Oklahoma | OCDPA |
| Oregon | OCPA |
| Panama | PDPL |
| Peru | PDPL |
| Philippines | DPA |
| Qatar | PDPPL |
| QFC DPR |
| Quebec | Law 25 |
| Rhode Island | RIDTPPA |
| Saudi Arabia | PDPL |
| Singapore | PDPA |
| South Africa | POPIA |
| South Korea | PIPA |
| Spain | RGPD |
| Taiwan | PDPA |
| Tennessee | TIPA |
| Texas | TDPSA |
| Thailand | PDPA |
| UAE | PDPL |
| UK | DPA |
| United States | This template is based on common requirements of effective U.S. state privacy laws. You can use it by deploying one single cookie banner in the United States to comply with multiple U.S. state privacy laws. > [!CAUTION] > **Caution** > > The U.S. cookie banner template follows an **Opt-out compliance framework** and is unsuitable for processing sensitive personal data, such as precise geolocation data, which requires prior consent under certain U.S. state privacy laws. To process sensitive personal data, you must configure a separate cookie banner with Opt-in compliance type in accordance with the applicable state privacy law. |
| Utah | UCPA |
| Vermont | VDPOSA |
| Vietnam | PDPL |

## Importing a system banner template

To import a system template in the banner templates gallery:

1. In Securiti, open **Cookie Consent Management**, and choose **Cookie Consent Configurations > Banner Templates Gallery**.
2. On the Banner Templates Gallery page, from the upper right corner, click **Import Templates**, as shown below.

![Banner-templates-gallery-UI_2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b81649c2-7f0d-fb73-c200-c86300524327.png)
3. From the **Import System Templates from Master Gallery** popup, mark the checkbox next to the name of the system template, and click **Import**, as shown below.

![Screenshot_2024-02-19_at_2_49_52_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2fcc329c-9d3a-4444-af17-d0a01e6421c8.png)

You can import multiple system templates. Securiti does not let you import system template(s) that you have already imported in the template gallery, and they appear disabled with a text "Template Already Exists" next to them.

![Screenshot_2024-02-19_at_2_49_22_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-55acae5d-98dc-dbcb-0ec6-25b97c440a68.png)
4. Click the recently imported system template to open it, as shown below.

![Opening-system-template.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d443c5e9-00b0-4484-9e9a-9746499fd0f3.png)
5. On the **Template Preview** popup, from the upper right corner, click **Apply to Domains**, as shown below.

![Tempelte-preview.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3fb393fd-c74e-e59c-95ec-89678800ad38.png)
6. On the **Step 1: Apply Template to Domain(s)** popup:

> [!CAUTION]
> **Caution**
> 
> When you apply a system banner template, you may see many domains listed on the popup. Exercise caution to ensure that the system banner template aligns with the legal regulations specific to the location or region of each domain.
  1. From the domain list, mark the checkbox next to the domain(s) on which you want to apply this system template.
  2. To apply this system template to the selected domains, near the bottom of the popup, click **Apply Template**. If you also want to put the criteria of this system template into effect right away, then click **Apply & Deploy**, as shown below.

![Apply-to-domains-v3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bf4b2058-70e8-04a4-a412-dc522225dc19.png)

Securiti shows you a success message near the upper right corner once the system template is successfully applied and deployed to the selected domains.

> [!NOTE]
> **Note**
> 
> - Securiti processes the application and deployment of templates across domains in batches, each consisting of 50 domains. If you select more than 50 domains, Securiti displays a progress bar that shows the completion percentage of the banner template's application and deployment to the domains. This makes it easy for you to visualize the percentage of the batch operations being performed.
> - You can use the **Abort** popup to instantly cancel the ongoing batch operations. Securiti retains any completed actions, but halts all pending actions. ![Abort-popup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0a59cf4c-9517-a5c2-38e8-b4b91a154c0c.png)

- On the **Step 2: Deploy Domains** popup:

> [!CAUTION]
> **Caution**
> 
> When you deploy a system banner template, you may see many domains listed on the popup. Exercise caution to ensure that the system banner template aligns with the legal regulations specific to the location or region of each domain.
  1. From the right side of the domain(s), click **Preview** to preview the applied system banner template, as shown below.

![Deploy-preview.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b61e56bc-eb90-96e4-3aa9-05a49e646ee4.png)

Securiti redirects you to the Cookie Banner Preview page. From this page, you can completely preview the look and feel of your applied system template, as shown below.

![Screenshot_2024-01-16_at_4_55_21_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-16fdf1bf-8c4d-e9b5-0d2a-f6504cb7d6bb.png)
  2. After previewing the system template changes, on the **Step 2: Deploy Domains** popup, mark the checkboxes next to the domains to which you want to deploy this system template. Add your reason or summary of changes in the **Change Note** section, acknowledge your understanding of the terms by marking the checkbox next to each, and then click **Deploy**, as shown below.

![Deploy-popup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f680fe12-fa23-4a29-bcd9-97ec98af9ee6.png)

Securiti shows you a confirmation message near the upper right corner of the page once the system template successfully deploys to the selected domains.

### Key considerations when applying and deploying banner templates

- The deploy action only publishes the cookie banner and preference center configurations such as **auto-blocking** and **GPC** changes.
- The deploy action **does not** publish the **cookie categorization** and **consent frameworks** changes. They remain in the draft mode.
- Once you deploy a banner template to multiple domains, Securiti automatically updates the domains pinned to the **manual SDK deployment** option to the latest Securiti release version available at the time of publishing.
- After applying a banner template on domain(s), deleting it from the templates gallery does not erase the applied changes from the domain(s). Securiti only deletes the banner template from the gallery; your updates remain as they are on the domains.

## Creating a custom banner template

You can also create custom banner templates if you do not wish to choose system templates. Securiti lets you make your custom banner templates fully bespoke to suit your organizational and jurisdictional requirements.

To create a custom banner template:

1. In Securiti, open **Cookie Consent Management**, and choose **Cookie Consent Configurations > Banner Templates Gallery**.
2. On the Banner Templates Gallery page, from the upper right corner, click **+ Cookie Banner Template**, as shown below.

![Create-custom-template.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f6e429ef-6d6d-1559-06e5-a79277579b90.png)
3. From the **Create a Custom Template** popup:
  1. To create a new custom banner template from scratch, click **Start a Blank Template**, as shown below.

![Create-custom-template-popup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-52f54c12-5fbd-5ded-9205-0558d76865b8.png)
  2. (Optional) To create a custom banner template on top of your imported system templates, click **Use Existing System Template**, as shown below.

![Existing-template.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5dac82ac-ba33-29ef-108a-75d293e3c850.png)
  3. On the **Start a New Template Using System Template** popup, select one system template from the menu and click **Select**, as shown below.

![Existing-template-choose.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-44cf30a2-4c9f-1b09-7e05-c80bebcc0cd2.png)

![Existing-select.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ba14a3b5-72dd-27c4-8304-693f5d52bf9a.png)

> [!NOTE]
> **Note**
> 
> The **Select System Template** menu displays the system banner templates that you have already imported in your banner templates gallery.
4. On the **Create New Template** page, from the **Template Name** text field, type a unique name for your custom banner template, and customize it to suit your organizational requirements as explained in [Customizing your website cookie consent banner](/v1/docs/customizing-your-cookie-banner-and-preference-center).

When you are satisfied with the custom banner template changes, from the upper right corner of, click **Create New Template**, as shown below.

![creatingtemplete-step4.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9b1e6467-d892-7770-00e7-84783adfecda.png)

Securiti shows you a confirmation message near the upper right corner of the page once a custom banner template is created successfully.
5. Click the recently created custom template to open it, as shown below.

![Opening-custom-template.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ab585223-22e7-9785-124b-d88cc1c361bf.png)
6. On the **Template Preview** page, from the upper right corner of the page, click **Apply to Domains**, as shown below.

![creatingtemplete-step6.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e2b4e9b3-4fe9-1622-cc73-04fd5be72c57.png)
7. On the **Step 1: Apply Template to Domain(s)** popup:

> [!CAUTION]
> **Caution**
> 
> When you apply a custom banner template, you may see many domains listed on the popup. Exercise caution to ensure that the custom banner template aligns with the legal regulations specific to the location or region of each domain.
  1. From the domain list, mark the checkbox next to the domain(s) on which you want to apply this custom banner template, as shown below.
  2. To simply apply this custom banner template to the selected domains, near the bottom of the popup, click **Apply Template**. If you also want to put the criteria of this custom banner template into effect right away, then click **Apply & Deploy**, as shown below.

![Apply-to-domains-v3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bf4b2058-70e8-04a4-a412-dc522225dc19.png)

Securiti shows you a success message near the upper right corner once the custom banner template is successfully applied and deployed to the selected domains.

> [!NOTE]
> **Note**
> 
> - Securiti processes the application and deployment of templates across domains in batches, each consisting of 50 domains. If you select more than 50 domains, Securiti displays a progress bar that shows the completion percentage of the banner template's application and deployment to the domains. This makes it easy for you to visualize the percentage of the batch operations being performed.
> - You can use the **Abort** popup to instantly cancel the ongoing batch operations. Securiti retains any completed actions, but halts all pending actions. ![Abort-popup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0a59cf4c-9517-a5c2-38e8-b4b91a154c0c.png)
8. On the **Step 2: Deploy Domains** popup:

> [!CAUTION]
> **Caution**
> 
> When you apply a custom banner template, you may see many domains listed on the popup. Ensure that the custom banner template aligns with the legal regulations specific to the location or region of each domain.
  1. From the right side of the domain(s), click **Preview** to preview the applied custom banner template, as shown below.

![Deploy-preview.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b61e56bc-eb90-96e4-3aa9-05a49e646ee4.png)

Securiti redirects you to the Cookie Banner Preview page. From this page, you can completely preview the look and feel of your applied custom banner template, as shown below.

![Screenshot_2024-01-16_at_4_55_21_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-16fdf1bf-8c4d-e9b5-0d2a-f6504cb7d6bb.png)
  2. After previewing the custom banner template changes, on the **Step 2: Deploy Domains** popup, mark the checkboxes next to the domains to which you want to deploy this custom banner template. Add your reason or summary of changes in the **Change Note** section, acknowledge the terms and conditions by marking the checkbox next to each, and then click **Deploy**, as shown below.

![Deploy-popup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f680fe12-fa23-4a29-bcd9-97ec98af9ee6.png)

Securiti shows you a confirmation message near the upper right corner of the page once the custom banner template successfully deploys to the selected domains.

The California Privacy Rights Act (CPRA) amended the CCPA by adding additional consumer privacy rights and obligations for businesses. It also created the California Privacy Protection Agency (CPPA), tasked with enforcing the law and educating the public on their rights and obligations under the law.

The General Data Protection Regulation (GDPR) is an European Union (EU) regulation on information privacy. It aims to ensure the protection of personal information through a human rights-centric approach, and imposes obligations onto organizations anywhere, so long as they target or collect data related to people in the EU.

The Personal Information Protection and Electronic Documents Act (PIPEDA) is the Canadian federal privacy law for private organizations. It sets out the ground rules for how businesses must handle personal information in the course of their commercial activity and provides the individuals with the right to access and rectify their personal data. Securiti’s Privacy Notice Management module lets you create a PIPEDA compliant privacy notice(s) for your organization.

Lei Geral de Proteção de Dados (LGPD) or simply called General Data Protection Law is Brazil’s first comprehensive legislation aimed at protecting the fundamental right of privacy. It applies to every natural person or legal entity, either public or private, that handles personal data of Brazilian citizens. The LGPD can also apply extraterritorially similar to the GDPR. You can choose between Global or LGPD template in Privacy Notice Management module.

A consumer right under the California Consumer Privacy Act (CCPA) that lets data subjects direct businesses to stop selling or sharing their personal information with third parties, including for targeted advertising or cross-context behavioral advertising.

The Global Privacy Control (GPC) is a browser-based global opt-out tool that lets the Internet users signal their opt-out consent settings to websites, advertisers, and publishers on the world wide web. Some global privacy laws, such as the CPRA, require covered entities to mandatorily detect and honor users’ GPC signal. The Cookie Consent Management module lets you configure cookie banners and preference centers with GPC to ensure detection of the GPC signals on the web browsers of your data subjects to honor their opt-out cookie preferences

The Alabama Personal Data Protection Act (APDPA) applies to persons that conduct business operating in or targeting Alabama that meet one of two thresholds:

(i) processing personal data of more than 25,000 consumers, excluding the processing of payment data; or

(ii) deriving 25%+ of gross revenue from data sales.

From Securiti’s **Banner Templates Gallery**, you can import a ready-to-use system banner template designed specifically for Alabama and apply it to your domains.

Alberta's Personal Information Protection Act (PIPA) is a private sector privacy law that applies to private sector organizations, including corporations, unincorporated associations, trade unions, partnerships, and individuals and non-profit organizations (in connection with their commercial activities).

From Securiti’s **Banner Templates Gallery**, you can import a ready-to-use system banner template designed specifically for Alberta and apply it to your domains.

The Personal Data Protection Law (PDPL) governs both automated and non-automated processing of personal data. It applies to residents, persons having businesses in Bahrain, and non-residents processing personal data using means located within Bahrain, excluding means used solely for personal data transit across Bahrain. From Securiti’s Banner Templates Gallery, you can import a ready-to-use system banner template designed specifically for Bahrain and apply it to your domains.

The Personal Information Protection Act 2016 (PIPA) applies to all organizations that use personal information in Bermuda, unless it is otherwise specified. The Act covers the personal information that is used partially or completely through automated means, or part of or is intended to be part of a structured filing system.

From Securiti’s **Banner Templates Gallery**, you can import a ready-to-use system banner template designed specifically for Bermuda and apply it to your domains.

Personal Information Protection Act (PIPA) applies to private sector entities in British Columbia, including persons, unincorporated associations, trade unions, and trust or non-profit organizations that collect, use, or disclose personal information. The p urpose of PIPA is to govern the collection, use, or disclosure of personal information by organizations for ‘reasonable’ purposes in a manner that protects the rights of data subjects.

From Securiti’s **Banner Templates Gallery**, you can import a ready-to-use system banner template designed specifically for British Columbia and apply it to your domains.

The British Virgin Islands' Data Protection Act, 2021 (BVI DPA) provides a framework for the protection of personal data. It applies to individuals and entities established in the British Virgin Islands (BVI) that process personal data, as well as those outside the BVI who use local equipment for processing data. The BVI DPA aims to safeguard personal data, promote transparency, and ensure accountability in data processing practices.

From Securiti’s **Banner Templates Gallery**, you can import a ready-to-use system banner template designed specifically for British Virgin Islands and apply it to your domains.

The Personal Data Protection Order (PDPO) governs the collection, use, and disclosure of personal data by individuals and organisations, whether or not they are based in or recognised under the laws of Brunei Darussalam. However, it has certain exemptions, such as for individuals acting in a personal capacity, employee actions, and public agencies.

From Securiti's Banner Templates Gallery, you can import a ready-to-use system banner template designed specifically for Brunei Darussalam and apply it to your domains.

The Data Protection Act applies to a data controller if: (a) the data controller is established in the Cayman Islands and the personal data are processed in the context of that establishment; or (b) the data controller is not established in the Cayman Islands, but the personal data are processed in the Cayman Islands other than for the purposes of transit of the data through the Cayman Islands.

From Securiti’s **Banner Templates Gallery**, you can import a ready-to-use system banner template designed specifically for Cayman Islands and apply it to your domains.

The Personal Information Protection Law (PIPL) is China’s primary data protection statute. It applies mainly to any organization or individual that processes the personal information of people within China. Additionally, this law covers entities outside China if they provide products or services to people in China, analyze or assess the behavior of individuals within China, or as otherwise required by Chinese law and regulations.

From Securiti’s **Banner Templates Gallery**, you can import a ready-to-use system banner template designed specifically for China and apply it to your domains.

Colorado Privacy Act (CoPA) is a privacy law applicable to a person doing business in Colorado, or producing/delivering products or services intentionally targeted to Colorado residents, if the person processes personal data (PD) of 100,000 consumers in a year or derives profit from sale of PD while processing PD of at least 25,000 consumers.

Connecticut Data Privacy Act (CTDPA) is a privacy law applicable to a person doing business in Connecticut or producing products or services targeted to Connecticut residents, if the person processes personal data (PD) of 100,000 consumers or derives 25% of gross revenue from sale of PD while processing PD of at least 25,000 consumers in a calendar year.

The Delaware Personal Data Privacy Act applies to persons doing business in Delaware or targeting its residents, and which controls or processes data for either 35,000 consumers,excluding payment data, or controls and processes data for 10,000 consumers while earning over 20% of revenue from selling personal data. From Securiti’s Banner Templates Gallery, you can import a ready-to-use system banner template designed specifically for Delaware and apply it to your domains.

The DIFC Data Protection Law applies to personal data processing within the DIFC by local or foreign controllers and processors. It covers automated and filing systems, excludes personal or household activities, and recognizes agreements with third c ountries or international bodies that ensure adequate data protection.

From Securiti’s **Banner Templates Gallery**, you can import a ready-to-use system banner template designed specifically for DIFC and apply it to your domains.

Florida Digital Bill of Rights (FDBR) is a privacy law applicable to persons who collect and process personal data about consumers while conducting business in Florida. However, the law only covers entities making in excess of $1 billion in global gross annual revenues and fulfilling certain other conditions. From Securiti’s Banner Templates Gallery, you can import a ready-to-use system banner template designed specifically for Florida and apply it to your domains.

The Digital Personal Data Protection Act (DPDPA) is a privacy law applicable to all persons processing digital personal data within India or offering goods or services to individuals within India.

From Securiti’s Banner Templates Gallery, you can import a ready-to-use system banner template designed specifically for India and apply it to your domains.

The Indiana Consumer Data Protection Act (INCDPA) applies to a person that conducts business in Indiana or services that are targeted to residents of Indiana and that during a calendar year: (1) controls or processes personal data of at least 100,000 consumers; or (2) controls or processes personal data of at least 25,000 consumers and derives more than 50% of gross revenue from the sale of personal data.

From Securiti’s **Banner Templates Gallery**, you can import a ready-to-use system banner template designed specifically for Indiana and apply it to your domains.

Israel’s Protection of Privacy Law (PPL) applies to any organization, in Israel or abroad, that collects, stores, or processes personal data of Israeli residents. It regulates all personal data, imposes stricter rules for sensitive data, governs data transfers, and protects individuals’ privacy rights.

From Securiti’s **Banner Templates Gallery**, you can import a ready-to-use system banner template designed specifically for Israel and apply it to your domains.

Kentucky's Consumer Data Privacy Act (KCDPA) applies to persons that conduct business in Kentucky or produce products or services that are targeted to residents of Kentucky and that during a calendar year control or process personal data of at least: (1) One hundred thousand (100,000) consumers; or (2) Twenty-five thousand (25,000) consumers, and derive over fifty percent (50%) of gross revenue from the sale of personal data.

From Securiti’s **Banner Templates Gallery**, you can import a ready-to-use system banner template designed specifically for Kentucky and apply it to your domains.

Louisiana Data Privacy Act (LDPA) applies to any entity or a person doing business in the state that meets one of three operational thresholds:

(i) exceeding $25 million in gross annual revenue, commercially handling the personal data of at least 75,000 consumers, households or devices annually; or

(ii) generating 50% or more of its yearly revenue directly from the sale of personal data.

From Securiti’s **Banner Templates Gallery**, you can import a ready-to-use system banner template designed specifically for Louisiana and apply it to your domains.

The Maryland Online Data Privacy Act (MODPA) is a privacy law applicable to a person who conducts business in Maryland or provide products or services to Maryland residents, and which during the preceding calendar year: (1) controlled or processed the personal data of at least 35,000 consumers, excluding payment data; or (2) controlled or processed personal data of at least 10,000 consumers and derived 20% of revenue from sale of personal data.

From Securiti's **Banner Templates Gallery**, you can import a ready-to-use system banner template designed specifically for Maryland and apply it to your domains.

The Federal Law on the Protection of Personal Data Held by Private Parties (LFPDPPP) is a privacy law applicable throughout the national territory of Mexico and aims to protect personal data held by private parties. The law seeks to regulate legitimate, controlled, and informed processing of personal data to guarantee individuals’ privacy. From Securiti's Banner Templates Gallery, you can import a ready-to-use system banner template designed specifically for Mexico and apply it to your domains.

The Minnesota Consumer Data Privacy Act (MCDPA) is a privacy law applicable to legal entities which conduct business in Minnesota or provide products or services to Minnesota residents, and which satisfy one or more of following thresholds: (1) control or process personal data of at least 100,000 consumers, excluding payment data, during a calendar year; or (2) process or control personal data of 25,000 consumers and derive 25% of revenue from sale of personal data.

From Securiti's **Banner Templates Gallery**, you can import a ready-to-use system banner template designed specifically for Minnesota and apply it to your domains.

Montana Consumer Data Privacy Act (MCDPA) is a privacy law applicable to a person doing business in Montana or producing products or services targeted to Montana residents, if the person:

- Controls or processes personal data (PD) of 50,000 consumers in a year.
- Derives 25% of gross revenue from sale of PD while processing PD of at least 25,000 consumers.

From Securiti’s **Banner Templates Gallery**, you can import a ready-to-use system banner template designed specifically for Montana and apply it to your domains.

The Nebraska Data Privacy Act (NDPA) is a privacy law applicable to a person, excluding a small business as defined by the Small Business Act, who: (a) conducts business in Nebraska or produces products or services consumed by Nebraska residents; and (b) processes or engages in the sale of personal data. From Securiti’s Banner Templates Gallery, you can import a ready-to-use system banner template designed specifically for Nebraska and apply it to your domains.

The New Hampshire Data Protection Act (NHDPA) is applicable to persons doing business in New Hampshire or targeting its residents, and which controls or processes the personal data of either 35,000 consumers, excluding payment data; or of 10,000 consumers and deriving 25 percent of revenue from selling personal data.

From Securiti’s **Banner Templates Gallery**, you can import a ready-to-use system banner template designed specifically for New Hampshire and apply it to your domains.

The New Jersey Data Protection Act (NJDPA) is applicable to persons doing business in New Jersey or targeting its residents, and which controls or processes data for either 100,000 consumers, excluding payment data, or for 25,000 consumers while earning revenue or discounts from selling personal data.

From Securiti’s **Banner Templates Gallery**, you can import a ready-to-use system banner template designed specifically for New Jersey and apply it to your domains.

New York does not currently have a comprehensive data privacy law. However, the banner template is based on guidance published by the New York Attorney General’s Office regarding website privacy controls to regulate online tracking.

From Securiti’s **Banner Templates Gallery**, you can import a ready-to-use system banner template designed specifically for New York and apply it to your domains.

The Oklahoma Consumer Data Privacy Act (OCDPA) applies to controllers or processors that conduct business in Oklahoma, or produce products/services targeted to its residents, and meet either of the following thresholds:

(i) Control or process the personal data of at least 100,000 consumers, or

(ii) Control or process the personal data of at least 25,000 consumers AND derive over 50% of gross revenue from the sale of personal data.

From Securiti’s **Banner Templates Gallery**, you can import a ready-to-use system banner template designed specifically for Oklahoma and apply it to your domains.

Oregon Consumer Privacy Act (OCPA) is a privacy law applicable to a person doing business in Oregon or producing products or services to Montana residents, if the person during a calendar year:

- Controls or processes personal data (PD) of 100,000 consumers.
- Derives 25% of gross revenue from sale of PD while processing PD of at least 25,000 consumers.

From Securiti’s **Banner Templates Gallery**, you can import a ready-to-use system banner template designed specifically for Oregon and apply it to your domains.

The law applies to the processing of personal data if the databases are located in Panama, the controller is domiciled in Panama, the data originates from or is stored in Panama; or the processing is carried out for online commercial activities aimed at the Panamanian market.

From Securiti’s **Banner Templates Gallery**, you can import a ready-to-use system banner template designed specifically for Rhode Island and apply it to your domains.

Peru’s Personal Data Protection Law (PDPL) covers all personal data contained in personal data databases publicly and privately administered, and processed in Peruvian territory by an organisation. Processing of sensitive data requires special protections under the law.

From Securiti’s **Banner Templates Gallery**, you can import a ready-to-use system banner template designed specifically for Rhode Island and apply it to your domains.

The Personal Data Privacy Protection Law (PDPPL) applies to the electronic processing of personal data. This also includes instances when traditional and electronic processing are combined. The PDPPL does not explicitly define the territorial scope of the law. However, it is reasonable to assume that the PDPPL at least applies to the processing of personal data within the territory of Qatar.

From Securiti's **Banner Templates Gallery**, you can import a ready-to-use system banner template designed specifically for Qatar and apply it to your domains.

The QFC Data Protection Regulations govern the processing of personal data of individuals by controllers and processors. They cover automated and relevant non-automated processing within filing systems and apply to entities incorporated or registered inside and outside the QFC.

From Securiti’s **Banner Templates Gallery**, you can import a ready-to-use system banner template designed specifically for QFC Data Protection Regulations and apply it to your domains.

Rhode Island Data Transparency and Privacy Protection Act (RIDTPPA) applies to for-profit entities conducting business in Rhode Island or targeting its residents. It specifically applies to those that control or process the personal data of at least 35,000 customers, or those that control or process personal data of at least 10,000 customers and derive over 20% of gross revenue from selling personal data.

From Securiti’s **Banner Templates Gallery**, you can import a ready-to-use system banner template designed specifically for Rhode Island and apply it to your domains.

The Personal Data Protection Law is applicable to the processing of personal data of individuals within Saudi Arabia, including data of residents processed by entities outside Saudi Arabia. It also covers the personal data of deceased individuals if it can identify them or their family members. From Securiti’s Banner Templates Gallery, you can import a ready-to-use system banner template designed specifically for Saudi Arabia and apply it to your domains.

The Personal Data Protection Act (PDPA) is applicable to the collection, use, and disclosure of personal data by organizations within Singapore. They also apply to organizations outside of Singapore that process data of individuals in Singapore or track their online activities within Singapore. From Securiti's Banner Templates Gallery, you can import a ready-to-use system banner template designed specifically for Singapore and apply it to your domains.

The Tennessee Information Protection Act (TIPA) is a privacy law applicable to a person who: (1) conducts business in Tennessee and exceeds twenty-five million dollars in revenue; and (2) controls or processes personal information of at least 25, 000 consumers and derive more than 50% of revenue from sale of personal information or controls or processes personal information of 175,000 consumers during a calendar year.

From Securiti's **Banner Templates Gallery**, you can import a ready-to-use system banner template designed specifically for Tennessee and apply it to your domains.

Texas Data Privacy and Security Act (TDPSA) is a privacy law applicable to a person, excluding a small business as defined by the United States Small Business Administration, who:

- Conducts business in Texas or produces products or services consumed by residents of Texas.
- Processes or engagees in the sale of personal data.

From Securiti’s **Banner Templates Gallery**, you can import a ready-to-use system banner template designed specifically for Texas and apply it to your domains.

The Personal Data Protection Law (PDPL) applies to the processing of personal data using electronic or other systems. It covers:

- Individuals who live or have a business in the UAE

Individuals or companies in the UAE that process personal data

Individuals or organizations outside the UAE that process the personal data of individuals within the UAE

From Securiti's **Banner Templates Gallery**, you can import a ready-to-use system banner template designed specifically for UAE and apply it to your domains.

The Data Protection Act 2018 (DPA) along with the UK GDPR constitutes the legislative framework applicable to processing of personal data in the UK. The DPA controls how personal data of individuals is used by organizations, businesses or the government.

Utah Consumer Privacy Act (UCPA) is a privacy law applicable to a person doing business in Utah or producing products or services targeted to Utah residents, if the person has more than $25,000,000 annual revenue, and processes personal data (PD) of 100,000 consumers in a year or derives 50% of gross revenue from sale of PD while processing PD of at least 25,000 consumers.

From Securiti’s **Banner Templates Gallery**, you can import a ready-to-use system banner template designed specifically for Utah and apply it to your domains.

The Vermont Data Privacy and Online Surveillance Act (VDPOSA) applies to persons or entities that conduct business in Vermont, or produce products or services targeted to Vermont residents, and met the following thresholds during the preceding calendar year:

(i) processed the personal data of at least 35,000 consumers and sensitive data of at least 3,000 consumers, excluding the processing of payment data; or

(ii) offered for sale the personal data of at least 3,000 consumers.

From Securiti’s **Banner Templates Gallery**, you can import a ready-to-use system banner template designed specifically for Vermont and apply it to your domains.

The Personal Data Protection Law (PDPL) applies to Vietnamese and foreign agencies, organizations, and individuals (‘entities’) within Vietnam, Vietnamese entities abroad, and any foreign entities directly involved in or related to personal data processing activities in Vietnam.

From Securiti’s **Banner Templates Gallery**, you can import a ready-to-use system banner template designed specifically for Vietnam and apply it to your domains.
