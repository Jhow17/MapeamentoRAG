---
title: "Configuring an IAB MSPA U.S. National cookie consent banner"
slug: "configuring-an-iab-mspa-us-national-cookie-consent-banner"
updated: 2026-04-07T10:45:55Z
published: 2026-04-07T10:45:55Z
canonical: "helpcenter.securiti.ai/configuring-an-iab-mspa-us-national-cookie-consent-banner"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Configuring an IAB MSPA U.S. National cookie consent banner

**Scenario**

As a Data Compliance Officer, you must implement consent frameworks such as IAB EU TCF, IAB MSPA U.S. National Approach or Google Consent Mode to comply with the regional laws. For instance, when expanding your website to new regions, each jurisdiction may require a different consent framework. Building custom support for each framework can take significant time and legal oversight. With Securiti’s Cookie Consent Management module, you can enable these frameworks with just a few clicks. This helps you meet global compliance requirements without writing additional code.

Securiti lets you comply with the Global Privacy Protocol (GPP) technical standard set by the Interactive Advertising Bureau (IAB). You can now comply with the IAB Multi-State Privacy Agreement (MSPA) U.S. National Approach that captures the consent preferences of the United States based website visitors in relation to advertising. It also permits the communication of received consent preferences across the digital advertising chain through the GPP as per the legal requirements and obligations imposed by the IAB Privacy Multi-State Privacy Agreement (MSPA).

The IAB MSPA provides a contractual framework which allows U.S. based **First Parties** to align their data subject consent collection practices in relation to advertising with the consent requirements of five U.S. state privacy laws (California, Colorado, Connecticut, Utah, and Virginia). The IAB MSPA U.S. National Approach assumes that the website visitor is the resident of each and every applicable jurisdiction.

The [IAB MSPA](/v1/docs/securiti-pods-and-elastic-pods) is a part of the Global Privacy Protocol (GPP) which creates a common consent framework for **advertisers**, **agencies**, **technology vendors**, and **publishers** for implementing U.S. state privacy following laws:

- California Privacy Rights Act (CPRA)
- Colorado Privacy Act (CoPA)
- Connecticut Data Privacy Act (CTDPA)
- Delaware Personal Data Privacy Act (DPDPA)
- Florida Digital Bill of Rights (FDBR)
- Indiana Consumer Data Protection Act (INCDPA)
- Iowa Consumer Data Protection Act (ICDPA)
- Kentucky's Consumer Data Privacy Act (KCDPA)
- Maryland Online Data Privacy Act (MODPA)
- Minnesota Consumer Data Privacy Act ( MCDPA)
- Montana Consumer Data Privacy Act (MCDPA)
- Nebraska Data Privacy Act (NDPA)
- New Hampshire Data Protection Act (NHDPA)
- New Jersey Data Protection Act (NJDPA)
- Oregon Consumer Privacy Act (OCPA)
- Rhode Island Data Transparency and Privacy Protection Act (RIDTPPA)
- Tennessee Information Protection Act (TIPA)
- Texas Data Privacy and Security Act (TDPSA)
- Utah Consumer Privacy Act UCPA
- Virginia Consumer Data Protection Act (VCDPA)

> [!NOTE]
> **Note**
> 
> If you want, you can display the IAB MSPA U.S. National cookie banner instead of the standard Securiti cookie consent banner. This functionality is available by request, contact your Securiti representative or [support@securiti.ai](mailto:support@securiti.ai) to activate it for your Securiti tenant.

### Key considerations

This functionality lets you comply with the [IAB U.S. National Privacy Technical Specification](https://www.iabprivacy.com/IAB%20MSPA%20Technical%20Signaling%20Implementation%20Guidelines%20v1.4%2010.15.24%20%5BFINAL%5D%5B68%5D.pdf) and provides the following compliance opportunities:

- Complying with requirements of **First Parties**
- Adhering to **Opt-out mode**
- Ensuring compliance with the **U.S. National Approach**
- Allowing data subjects to opt out of **sale of data**, **sharing of data**, and **targeted advertising**
- Complying with the requirements of **Covered Transactions**

As per the IAB, the following table explains the provisions that MSPA covers:

| Provision | Description |
| --- | --- |
| Gap transactions | This means making sure there are clear rules for sharing personal information in digital ads, even when there's no formal contract. |
| Measurement and frequency capping | This involves tracking how often ads are shown to the data subjects or consumers and setting limits, especially when using outside companies for these tasks. |
| Contextual advertising and advertising on a publisher’s first-party segments | This refers to showing ads based on the content of a webpage or using data collected directly from the website visitors. |
| A 'national' approach option to state privacy compliance | This means following the strictest privacy rules from different states to ensure everyone's privacy is protected. |
| Use of the IAB Tech Lab’s technical specification for U.S. State Signals in the GPP | This involves using specific guidelines from a tech organization to handle signals about user privacy from different U.S. states within a global privacy platform. |

### Procedure

To configure an IAB MSPA U.S. National cookie banner:

1. If you have not already done so, configure a standard cookie consent banner for your domain as described in [Customizing your cookie banner and preference center](/v1/docs/customizing-your-cookie-banner-and-preference-center).

> [!NOTE]
> **Note**
> 
> You can select the **multi level** preference center style for the IAB MPSA U.S. National cookie consent banner. It also shows **Ad Preferences** tab for this consent framework that lets you give access to manage different types of consents to the external vendors, and can also provide consents to the purposes.

The IAB MPSA U.S. National cookie banner uses the same website code as our standard cookie consent banner. Also, you might want to display the standard cookie consent banner outside of the United States.
2. In Securiti, open **Cookie Consent Management**, and choose **Cookie Consent > Domains**.
3. On the Cookie Consent Domains page, click the card for the domain you want the IAB MPSA U.S. National banner for.
4. Click the **Consent Frameworks** tab.
5. Click the **Interactive Advertising Bureau (IAB)** tab.
6. Near the upper right corner of the page, click **Edit**.
7. Mark the **MSPA U.S. National** checkbox, as shown below.

![Enable_IAB_US_National.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-90475ab0-b3f5-1b1b-2b06-7b3ffa1938e4.png)
8. Click the links to find out how Securiti lets you comply with the IAB MSPA U.S. National Approach with its existing functionalities and the limitations of our existing functionality. Upon clicking on these links, Securiti opens a side panel from the right side with the detailed information containing references/links to relevant official sources from the IAB, as shown below.

![MSPA_2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6d65b4e8-f52f-8229-342d-c2e83b626a68.png)

![MSPA_3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-007e2692-373f-76d5-c27b-e3843c567f1b.png)
9. Enable **Translation Mapping** to add custom translations for texts that appear on the cookie banner, as shown below.

![MSPA_Enable_Translation_Mapping.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-faec18ef-419b-736c-2c5e-46a3a3771e26.png)

> [!NOTE]
> **Tip**
> 
> Perform this step after configuring the whole IAB MSPA U.S. National cookie banner.
  - From the **Select Language** menu, choose the language for which you want to provide the custom translation, as shown below.

![MSPA_Translation.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-88a7fc4e-097f-5b3f-c4b1-a5009051437a.png)

You can add your custom translations for your cookie banner text fields, as shown below. Securiti automatically translates the cookie banner text based upon your custom provided translation for the selected language when it detects that same language in the web browser of your data subjects.

![MPSA_Translated.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3e92aeba-bf83-34dd-1eed-5a5420d0b8ae.png)
10. Configure the IAB MSPA (U.S. National Approach) Data Processing Purposes as explained in the following table:

You can choose the relevant processing purpose(s) (sale of data, sharing of data or targeted advertising or all) depending on your processing of data. Securiti provides the relevant default text to appear on your MSPA U.S. National cookie banner for the processing purpose(s).

> [!NOTE]
> **Tip**
> 
> Above each textbox, Securiti provides some regulatory context on when data processing constitutes sale of data, sharing of data, and targeted advertising. This regulatory information is there to guide you how to draft the text of the banner depending on your use and processing of data, and whether it constitutes sale, sharing of data or targeted advertising.

| Data Processing Purpose | Description |
| --- | --- |
| First Paragraph | Add the first sentence that appears at the very start of your cookie banner text before the descriptions of all processing purposes. Either use Securiti's default description or add your custom first sentence. |
| Sale of Data | You can either use the default descriptions for these processing purposes that Securiti is providing or you can add your custom descriptions for these processing purposes to suit. You can also preview how these texts collectively look on your cookie banner. From the upper right corner of the IAB MSPA (U.S. National Approach) Data Processing Purposes section, switch the toggle from **Edit** to **Preview** mode to preview your cookie banner text, as shown below. ![MSPA_Banner_Text_Temp_Preview.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-659656f0-9731-59cc-4cb6-65ca72afe7cb.png) |
| Sharing of Data |
| Targeted advertising |
| Last paragraph | Add the last sentence that appears at the very end of your cookie banner text after the descriptions of all processing purposes. Either use Securiti's default description or add your custom last sentence. |
11. In the **Opt-out Button Text** field, enter the name for the global Opt-Out button. By default, Securiti provides the **Opt-out All** text as the button name.

> [!NOTE]
> **Important**
> 
> When your data subjects click global **Opt-out All** button from the cookie banner, they are automatically opted out from all non-essential cookie categories as well as from the IAB processing purposes such as **sale of data**, **sharing of data**, or **targeted advertising**. This choice is then passed down to other IAB affiliated ad-tech vendors through the IAB String. Per our legal understanding, the global Opt-Out button is necessary on the first layer (cookie banner) even if there are granular opt outs available on the second layer (cookie preference center).
12. From the **Ad Preferences Descriptions** section, you can provide descriptions for the following data processing purposes that appear on the **Ad Preferences** tab of the cookie preference center with which your data subjects or website visitors interact:

Securiti lets you edit and customize the default descriptions of the data processing purposes to suit your organizational and business needs.

![IAB-MSPA-Ad-Preferences.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-79cc45df-fe5f-59dd-def8-f5dc8c8e33f7.png)
  - Sale of data
  - Sharing of data
  - Targeted advertising
13. Use the **Location Intelligence** section to select a specific region in which you want to display your configured IAB MSPA U.S. National cookie banner, as shown below.
  1. Mark the **All** radio button to display this banner in all regions of the globe.
  2. Mark **Show only in** radio button and select one or more particular regions to display this cookie banner in, as shown below.

![MSPA_4.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8a87732e-5c8d-6dfa-4140-4e12f4eb3611.png)
14. Mark the **Hide Cookie Categories Tab** checkbox if you want to hide the cookie categories from your IAB MSPA U.S. National cookie banner, as shown below.

> [!NOTE]
> **Important**
> 
> - You must disable auto-blocking functionality for your cookie banner to enable the **Hide Cookie Categories Tab** toggle.
> - Securiti does not record consent against normal cookie categories when you hide the Cookie Categories tab from the cookie preference center.

![MSPA_5.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c88d7509-67bf-eced-6ea9-707e0983c001.png)
15. Mark the **Include U.S. Privacy String in GPP** checkbox to concatenate the IAB GPP privacy string along with the MSPA U.S. National privacy string, as shown below.

![MSPA_6.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0144536a-e1b7-120c-1eaa-7b9e6405229b.png)
16. Mark the **Show Close Button on Banner** checkbox to display an **X** icon (close button) on the upper right corner of your cookie banner, as shown below.

![MSPA_7.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ba7b034d-962a-74c1-aba5-8ae09c8f5a5f.png)
17. Near the upper right corner of the page, click **Save** to save your configured changes, as shown below.

![MSPA_8.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-fdea1121-d739-e60f-f2a1-e89466d13bf3.png)
18. After saving, near the upper right corner of the page, click **Deploy** to deploy your cookie banner, as shown below.

![MSPA_9.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-33d4f7cb-6068-06fd-f86f-6c00e4452909.png)
19. Follow the deployment procedure on the **Publish Code** popup. For instance, in the **Change Note** text section, add the summary of your latest changes that you have made for your cookie banner and preference center.

![MSPA_11.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-03ec2ad7-64c5-7b82-e104-ef79c1a88496.png)
20. On the **Publish Code** popup, mark the **Show Banner Again** checkbox if you want to show your cookie banner and preference center on your domain(s) again to your data subjects, as shown below. After you publish your latest changes, this feature ensures to show your cookie banner and preference center again to your data subjects when they visit your domain.

![MSPA_12.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-03c452be-ba0c-23a6-c801-953e510a8b63.png)
21. Near the bottom of the Publish Code popup, click **Publish** to publish your IAB MSPA U.S. National cookie banner and preference center, as shown below.

![MSPA_10.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0ea3abd7-cdaf-b803-4cdb-e70b78ce5c37.png)

Securiti displays a success message when your cookie configuration changes are successfully deployed to your domain, as shown below.

The Global Privacy Platform (GPP) is a protocol designed by the Interactive Advertising Bureau (IAB) Tech Lab to streamline and standardize the transmission of consumer consent choice signals from websites and applications to IAB enrolled providers. The framework enables user consent signals to be communicated throughout the digital ad supply chain

The Interactive Advertising Bureau (IAB) is a trade association representing advertising businesses. It develops industry standards, conducts research, and provides legal support for the online advertising industry. Cookie Consent Management module lets you configure your cookie banners and preference centers with two IAB privacy consent frameworks: the **EU TCF v2.2** and the **MSPA U.S. National**.

The Multi-State Privacy Agreement (MSPA) serves as a contractual framework designed to aid IAB publishers, advertisers, agencies, and ad tech intermediaries. Its purpose is to facilitate compliance with distinct U.S. state privacy laws. This is achieved by sending, receiving, and honoring standardized opt-out consent signals through the GPP.

The California Privacy Rights Act (CPRA) amended the CCPA by adding additional consumer privacy rights and obligations for businesses. It also created the California Privacy Protection Agency (CPPA), tasked with enforcing the law and educating the public on their rights and obligations under the law.

Colorado Privacy Act (CoPA) is a privacy law applicable to a person doing business in Colorado, or producing/delivering products or services intentionally targeted to Colorado residents, if the person processes personal data (PD) of 100,000 consumers in a year or derives profit from sale of PD while processing PD of at least 25,000 consumers.

Connecticut Data Privacy Act (CTDPA) is a privacy law applicable to a person doing business in Connecticut or producing products or services targeted to Connecticut residents, if the person processes personal data (PD) of 100,000 consumers or derives 25% of gross revenue from sale of PD while processing PD of at least 25,000 consumers in a calendar year.

The Delaware Personal Data Privacy Act applies to persons doing business in Delaware or targeting its residents, and which controls or processes data for either 35,000 consumers,excluding payment data, or controls and processes data for 10,000 consumers while earning over 20% of revenue from selling personal data. From Securiti’s Banner Templates Gallery, you can import a ready-to-use system banner template designed specifically for Delaware and apply it to your domains.

Florida Digital Bill of Rights (FDBR) is a privacy law applicable to persons who collect and process personal data about consumers while conducting business in Florida. However, the law only covers entities making in excess of $1 billion in global gross annual revenues and fulfilling certain other conditions. From Securiti’s Banner Templates Gallery, you can import a ready-to-use system banner template designed specifically for Florida and apply it to your domains.

The Indiana Consumer Data Protection Act (INCDPA) applies to a person that conducts business in Indiana or services that are targeted to residents of Indiana and that during a calendar year: (1) controls or processes personal data of at least 100,000 consumers; or (2) controls or processes personal data of at least 25,000 consumers and derives more than 50% of gross revenue from the sale of personal data.

From Securiti’s **Banner Templates Gallery**, you can import a ready-to-use system banner template designed specifically for Indiana and apply it to your domains.

The Iowa Consumer Data Protection Act (ICDPA) applies to persons doing business in Iowa or targeting its residents, if they either control or process data for at least 100,000 people, or for 25,000 people while earning 50% of their revenue from selling personal data. From Securiti’s Banner Templates Gallery, you can import a ready-to-use system banner template designed specifically for Iowa and apply it to your domains.

Kentucky's Consumer Data Privacy Act (KCDPA) applies to persons that conduct business in Kentucky or produce products or services that are targeted to residents of Kentucky and that during a calendar year control or process personal data of at least: (1) One hundred thousand (100,000) consumers; or (2) Twenty-five thousand (25,000) consumers, and derive over fifty percent (50%) of gross revenue from the sale of personal data.

From Securiti’s **Banner Templates Gallery**, you can import a ready-to-use system banner template designed specifically for Kentucky and apply it to your domains.

The Maryland Online Data Privacy Act (MODPA) is a privacy law applicable to a person who conducts business in Maryland or provide products or services to Maryland residents, and which during the preceding calendar year: (1) controlled or processed the personal data of at least 35,000 consumers, excluding payment data; or (2) controlled or processed personal data of at least 10,000 consumers and derived 20% of revenue from sale of personal data.

From Securiti's **Banner Templates Gallery**, you can import a ready-to-use system banner template designed specifically for Maryland and apply it to your domains.

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

Oregon Consumer Privacy Act (OCPA) is a privacy law applicable to a person doing business in Oregon or producing products or services to Montana residents, if the person during a calendar year:

- Controls or processes personal data (PD) of 100,000 consumers.
- Derives 25% of gross revenue from sale of PD while processing PD of at least 25,000 consumers.

From Securiti’s **Banner Templates Gallery**, you can import a ready-to-use system banner template designed specifically for Oregon and apply it to your domains.

Rhode Island Data Transparency and Privacy Protection Act (RIDTPPA) applies to for-profit entities conducting business in Rhode Island or targeting its residents. It specifically applies to those that control or process the personal data of at least 35,000 customers, or those that control or process personal data of at least 10,000 customers and derive over 20% of gross revenue from selling personal data.

From Securiti’s **Banner Templates Gallery**, you can import a ready-to-use system banner template designed specifically for Rhode Island and apply it to your domains.

The Tennessee Information Protection Act (TIPA) is a privacy law applicable to a person who: (1) conducts business in Tennessee and exceeds twenty-five million dollars in revenue; and (2) controls or processes personal information of at least 25, 000 consumers and derive more than 50% of revenue from sale of personal information or controls or processes personal information of 175,000 consumers during a calendar year.

From Securiti's **Banner Templates Gallery**, you can import a ready-to-use system banner template designed specifically for Tennessee and apply it to your domains.

Texas Data Privacy and Security Act (TDPSA) is a privacy law applicable to a person, excluding a small business as defined by the United States Small Business Administration, who:

- Conducts business in Texas or produces products or services consumed by residents of Texas.
- Processes or engagees in the sale of personal data.

From Securiti’s **Banner Templates Gallery**, you can import a ready-to-use system banner template designed specifically for Texas and apply it to your domains.

Utah Consumer Privacy Act (UCPA) is a privacy law applicable to a person doing business in Utah or producing products or services targeted to Utah residents, if the person has more than $25,000,000 annual revenue, and processes personal data (PD) of 100,000 consumers in a year or derives 50% of gross revenue from sale of PD while processing PD of at least 25,000 consumers.

From Securiti’s **Banner Templates Gallery**, you can import a ready-to-use system banner template designed specifically for Utah and apply it to your domains.

Virginia Consumer Data Protection Act (VCDPA) is a privacy law applicable to persons doing business in Virginia or producing products or services targeted to Virginia residents, if the persons either process personal data (PD) of 100,000 consumers in a year or derive 50% of gross revenue from sale of PD while processing PD of at least 25,000 consumers.

The Opt-out cookie banner compliance type assumes consent for cookies from the outset. Here, cookies might be set on the data subject's device when they first visit your domain, but the data subject has the option to withdraw their consent and opt out of cookie usage. This model is less strict than Opt-in and is often seen in jurisdictions with less stringent privacy laws. Data subjects, website visitors, and data subjects must be given a clear and straightforward way to decline cookies, usually through the cookie preference center or settings panel.

Signal means any signal defined by the IAB EU TCF v2.2 **Policies** or **Specifications** sent by a CMP to **Vendors**, usually on behalf of a **Publisher**. This includes information about the transparency, consent, and/or objection status of a Vendor and/or Purpose, the opt-in status of a Special Feature, and Publisher restrictions.

A small text file that is stored on a data subject's or website visitor's device (computer, smartphone, or tablet) by a domain (website). Cookies are used to collect information about the user's interactions with the website, such as preferences, login status, and browsing history. This information helps domains enhance user experience, perform analytics, and deliver personalized content and advertisements. Cookies can be categorized into various types, including Essential, Performance, Functionality, and targeting cookies, each serving different purposes in managing user consent and data privacy.

Purpose refers to one of the designated reasons for handling data, including the personal data of individuals, by those involved in the IAB EU TCF v2.2 consent framework. These reasons are outlined in the Policies or Specifications, and Vendors declare a Legal Basis for them in the Global Vendor List (GVL). The data subjects are given a choice, such as granting consent or expressing objection based on the Legal Basis for processing, facilitated by the CMP.

## Related

- [Understanding IAB Global Privacy Protocol (GPP)](/understanding-iab-global-privacy-platform-gpp.md)
- [Configuring the GPC consent framework and flyout](/configuring-the-gpc-consent-framework-and-flyout.md)
- [Configuring Google Consent Mode](/configuring-google-consent-mode.md)
