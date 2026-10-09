---
title: "Configuring geo-specific consent states for cookie categories"
slug: "configuring-geo-specific-consent-states-for-cookie-categories"
updated: 2026-08-28T05:27:03Z
published: 2026-08-28T05:27:03Z
canonical: "helpcenter.securiti.ai/configuring-geo-specific-consent-states-for-cookie-categories"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Configuring geo-specific consent states for cookie categories

**Scenario**

As a Data Privacy Officer, you must serve different cookie rules based on a visitor’s location. For instance, users in one region may require Opt-in consent, while others may allow Opt-out by default. Hardcoding these rules increases complexity and the risk of errors. With Securiti’s Category Mappings and Location Override features let you apply Opt-in or Opt-out states by region. This helps you adapt quickly to global laws and deliver a region-aware consent experience.

> [!WARNING]
> **Important**
> 
> The Opt-out Rules subtab is **deprecated** and **no longer in use**. You can now configure **Location Overrides** for each cookie banner individually. To maintain equivalent functionality, use the **Hybrid** compliance type in the **Customize Banner and Preference Center** tab. After deprecation, Securiti **will not support** any existing configurations made in the Opt-out Rules subtab.
> 
> For more information, see [Customizing your cookie banner and preference center](/v1/docs/customizing-your-cookie-banner-and-preference-center).

Securiti's **Category Mappings** feature empowers you to fine-tune your cookie configuration with greater precision and flexibility. It lets you **disable Opt-out rights** for specific cookie categories, ensuring that **Essential** cookies remain unaffected. You can configure Opt-in and Opt-out states for cookies at an individual cookie category level. You can also apply these configurations to specific geolocations using the **Location Override** feature. This comprehensive customization enhances compliance with regional regulations and improves user experience.

This functionality ensures that you can customize the cookie configuration of your domain to meet the diverse needs of your business and comply with regional regulations by letting you:

- Choose from **three default consent states** based on your organization's unique business needs and regulatory requirements:

> [!NOTE]
> **Note**
> 
> If you map a cookie category to **Always Active** consent state, it behaves like the Essential category. This disables Opt-out for that cookie category and prevents data subjects from modifying their consent preferences.
  - Always Active
  - Granted
  - Declined
- Disable Opt-out rights of data subjects and website visitors for specific cookie categories with the exception of **Essential** cookie categories.
- Configure **Opt-in** and **Opt-out** states for cookies at the **individual cookie category level** after scanning a domain or importing offline scanner data.

> [!NOTE]
> **Note**
> 
> From the menu next to the cookie category name, select the default state for the cookie category. For instance, to make the cookie category act as an **Essential** category, select the **Always Active** option from the menu.
- Apply these configurations to **specific geolocations**, such as countries and regions.
- Serve different Opt-in or Opt-out cookie states based on the data subject's location, as determined by their IP address.

### Key considerations

You must consider the following points when configuring geo-specific states for the cookie categories of your domain:

- Securiti does not let you change the default Opt-out state of the **Essential** cookie category.
- You can only edit the cookie category mappings when you have an **unpublished draft** of the cookie configuration. This means that Securiti lets you apply geo-specific consent states to cookie categories individually only if your domain has changes in draft mode that are yet to be deployed.
- If you access the Category Mappings section **with no changes** in the draft mode, Securiti shows you only the published cookies categories to your domains, with some cookies in them, as shown below.
- If you access the Category Mappings section **with changes** in the draft mode, Securiti shows you all cookie categories with or without cookies in them.

### Mapping consent states to cookie categories for the selected compliance type

**Scenario**

As a Data Protection Officer, you must apply the right consent logic across banners and geolocations. Doing this manually for each category is confusing. Securiti lets you map consent states such as Opt-in or Opt-out to cookie categories per compliance type. You ensure consistent consent handling across banners and meet law-specific requirements effortlessly.

Securiti lets you map consent states to cookie categories at the **cookie banner level**. This means the selected consent states apply to the cookie categories in your domain's cookie banner and preference center for data subjects and website visitors in the geolocation configured for that cookie banner.

> [!NOTE]
> **Important**
> 
> Most privacy laws require domains to allow data subjects and visitors the right to Opt-out of **Non-Essential** cookies. You must ensure compliance with applicable privacy laws before mapping consent states to the cookie categories on your domain.

To map the consent states to the cookie categories for the cookie banner:

1. Once the website scan you started in [Scanning your website for cookies](/v1/docs/scanning-your-website-for-cookies) completes, choose **Cookie Consent > Domains**.
2. On the Cookie Consent Domains page, click the domain whose cookie categories you want to map with consent states.
3. Click the **Customize Banner and Preference Center** tab. Securiti lands you on the **Configuration & Mapping** subtab by default.
4. Scroll down to the **Banner Compliance Type** section, select the appropriate compliance type for your cookie banner and preference center, and expand the **Category Mappings** section, as shown below.

![Category-Mappings-Expanded.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7b78a4ae-e776-70b4-24f2-8c2c48da93c3.png)
5. Near the upper right corner of the page, click **Edit**.

> [!NOTE]
> **Note**
> 
> You can only edit the Category Mappings when you have an **unpublished draft** of the cookie configuration. This means that Securiti lets you apply geo-specific consent states to cookie categories individually only if your domain has changes in draft mode that are yet to be deployed.
6. Use the menus next to the cookie category names to set the default consent state for desired cookie categories.
7. When you are done mapping the consent states to the cookie categories, near the upper right corner of the page, click **Save**.
8. From the upper right corner of the page, click **Deploy**.
9. On the **Publish Code** popup, from the **Change Note** section, enter the summary of the changes you performed, and then from the bottom of the popup, click **Publish**.

Your changes are now published and deployed to your domain. Securiti shows you a confirmation message.
10. Proceed to [Deploying your website cookie consent banner](/v1/docs/deploying-your-website-cookie-consent-banner).

### Mapping consent states to cookie categories by region or location

Securiti lets you map consent states to cookie categories at a **location-specific level**. This means the selected consent states apply to the cookie categories in the cookie banner and preference center configured for a specific country, state, province, or region.

> [!NOTE]
> **Important**
> 
> Most privacy laws require domains to allow data subjects and visitors the right to Opt-out of **Non-Essential** cookies. You must ensure compliance with applicable privacy laws before mapping consent states to the cookie categories on your domain.

To map the consent states to the cookie categories on the location-specific level:

1. Once the website scan you started in [Scanning your website for cookies](/v1/docs/scanning-your-website-for-cookies) completes, choose **Cookie Consent > Domains**.
2. On the Cookie Consent Domains page, click the domain whose cookie categories you want to map with consent states.
3. Click the **Customize Banner and Preference Center** tab. Securiti lands you on the **Configuration & Mapping** subtab by default.
4. Scroll down to the **Banner Compliance Type** section, select the appropriate compliance type for your cookie banner and preference center, and expand the **Category Mappings** section.
5. Near the upper right corner of the page, click **Edit**.

> [!NOTE]
> **Note**
> 
> You can only edit the Category Mappings when you have an **unpublished draft** of the cookie configuration. This means that Securiti lets you apply geo-specific consent states to cookie categories individually only if your domain has changes in draft mode that are yet to be deployed.
6. Expand the **Location Override** section, and enable the **Enable Location Override** toggle.
7. Once done, click **Add countries or regions for override**, as shown below.

![Add-mapping.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1f13b02f-536c-15b4-5684-77fa39255af8.png)
8. Either scroll the list of regions to select the specific country or type its name in the search bar. Once you find it, from the right side, click **Next** (right arrow icon), as shown below.

![Select-region.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-631d0c0a-35d0-74a0-80ba-8aaf14846e9f.png)

> [!NOTE]
> **Important**
> 
> Securiti does not let you create a separate cookie banner for a state or province if a cookie banner for the broader country already includes Location Overrides. For instance, if the province of Mendoza is already mapped in the Location Overrides of an Argentina-specific cookie banner, Securiti automatically prevents you from creating a separate cookie banner for Mendoza.
9. Either select the states or provinces to suit your preferences or click **Select All**. You can also mark the checkbox located at the left side of the country to select all of its states or provinces, as shown below.

![Select-all-states.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8747738a-d308-5604-62f3-352e3b85a738.png)
10. Once done, near the bottom of the **Overrides** section, click **Add Mapping**, as shown below.

![Add-region-mapping.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2dc0b72c-0081-8560-a95f-ca1f191fc128.png)
11. From the menu, select the cookie category you want to map the **opt-in** or **opt-out** state to. For instance, in the following screenshot for the United States of America, we are selecting the **Performance and Functionality** and **Social Networking** cookie categories.

![Custom-mapping.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5d6697c4-781d-264a-a03d-05503c86e507.png)

> [!NOTE]
> **Note**
> 
> When your data subjects or website visitors from the United States of America interact with your domain's cookie banner and preference center, Securiti treats the **Social Networking** cookie category as **Essential**, and the **Performance and Functionality** cookie category as **Non-Essential**.
12. If you want to map these same consent states to cookie categories for another country, click **Edit** (pencil icon) near the upper right corner of the **Overrides** section. Then, from the menu on the right side, select one or more countries, as shown below.

![Edit-override.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e3536424-5411-f642-bbb6-c59e176b1680.png)
13. If you wish to delete the Opt-out mapping for a particular cookie category, from the right side of the mapped cookie category, click **Delete** (trash icon), as shown below.

![Delete-cookie-category.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c220ab26-6db1-2f20-439a-6fb137d159df.png)
14. Securiti also lets you delete the whole overrides section. To delete the whole overrides section, near the upper right corner of the section, click **Delete** (trash icon). On the **Delete location overrides** popup, in the text field, type "delete", and near the bottom of the popup, click **Delete**, as shown below.

![Delete-overrides-section.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7eb05f0f-9525-58e3-fdcc-11618ac59362.png)

![Delete-Location-Override.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f8fa3459-987b-733b-dd49-20f11e4dce2e.png)
15. When you are done mapping the location-specific consent states to the cookie categories, near the upper right corner of the page, click **Save**.
16. From the upper right corner of the page, click **Deploy**.
17. On the **Publish Code** popup, from the **Change Note** section, enter the summary of the cookie configuration changes you performed, and then from the bottom of the popup, click **Publish**.

Your changes are now published and deployed to your domain. Securiti shows you a confirmation message.
18. Proceed to [Deploying your website cookie consent banner](/v1/docs/deploying-your-website-cookie-consent-banner).

The Opt-out cookie banner compliance type assumes consent for cookies from the outset. Here, cookies might be set on the data subject's device when they first visit your domain, but the data subject has the option to withdraw their consent and opt out of cookie usage. This model is less strict than Opt-in and is often seen in jurisdictions with less stringent privacy laws. Data subjects, website visitors, and data subjects must be given a clear and straightforward way to decline cookies, usually through the cookie preference center or settings panel.

## Related

- [Categorizing your website cookies](/categorizing-your-website-cookies.md)
- [Deploying your website cookie consent banner](/deploying-your-website-cookie-consent-banner.md)
