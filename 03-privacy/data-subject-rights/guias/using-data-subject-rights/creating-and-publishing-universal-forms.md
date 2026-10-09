---
title: "Creating and publishing universal forms"
slug: "creating-and-publishing-universal-forms"
updated: 2026-01-14T08:21:36Z
published: 2026-01-14T08:21:36Z
canonical: "helpcenter.securiti.ai/creating-and-publishing-universal-forms"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Creating and publishing universal forms

**Scenario**

Often, businesses may have a single website for all the geographical regions where they do business. Data subjects from all these regions would be going to that single website to submit a request. However, different data may need to be collected based on where the data subject resides and different regulations are applicable to data subject requests from different regions. With the universal intake form, users select their residency up front, and the correct form loads automatically. This ensures compliance with regional laws while making the request process smoother for both you and your users.

### Overview

Securiti lets you publish a global DSR intake form that adapts based on data subject residency. This feature lets data subjects select their residency information first before displaying the appropriate form. Data subjects can also choose the language in which they want to translate the form. The Securiti Data Subject Rights module features universal forms that automatically open the most appropriate of your DSR request forms based on location information provided by the data subject, as shown below.

![Universal_form_cookie_banner.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8870117e-97f2-ac7c-0231-fb70b5c2afb3.png)

> [!NOTE]
> **Note**
> 
> You must publish the form in the DSR Form Builder that you want to map to a respective country or state.
> 
> Securiti lets the following roles in your Securiti tenant configure DSR universal form:
> 
> - Super Admin
> - Org Admins
> - DPO
> - Module Owner

Once the data subject provides their location, the universal form redirects them to one of your DSR request forms based on a mapping that you have configured.

1. In Securiti, open **Data Subject Rights**, then choose **Settings > Universal Form Builder**.
2. Near the upper right corner of the Universal Forms panel, click **+** to create a new universal form.
3. Use the tools on the Form Settings tab to configure the following:

| Logo & Branding | Click **Upload**, then navigate to a file containing your company logo. Then click **Upload** again. |
| --- | --- |
| Embeddable Domains | Use the tools to build an allow-list of domains where you can embed the form on a web page with an HTML <frame> element. If you embed the form in a web page that is not on the list, Securiti does not serve the page. |
| **Languages Support** |
| Support All Languages | Mark this radio button to show all languages on the published universal form. |
| Only Selected Languages | Mark this radio button to show selected languages on the published universal form |
| Languages | From this menu, select languages in which you want to make the form available. For more information, see [Supported languages in Data Subject Rights](/v1/docs/supported-languages-in-data-subject-rights). |
| No language Selection | Mark this radio button to show only the default language on the published universal form. |
| Default Language | Choose the language in which form appears by default. |
| Enable Language Intelligence | Mark the checkbox to translate the universal form into one of the data subject’s browser languages that align with the language options you have set for the **Languages** menu. > [!NOTE] > **Note** > > You cannot enable this feature if No language Selection is marked. Keep these important points in mind when using the Language Intelligence option in universal form settings: - If this option is enabled and the data subject’s browser language matches one of the languages supported in the universal form, the form is automatically translated into that language. In this case, the Securiti does not consider the default language set during the form settings. > [!NOTE] > **Note** > > If the data subject’s browser has multiple supported languages, the universal form uses the first one in the browser’s preferred list. - If the browser does not support any configured language, the universal form uses the default language. |
| **Template Content** |
| Headline | Use this area to customize the text displayed at the top of the form |
| Body | Use this area to customize the body of the text displayed on the form. |
| Decline Reason | Use this area to compose the text shown to a data subject when their geography is not mapped to a form and you do not have a default form. |
| Cookie Notice | Use this area to compose the cookie notice that you want to show at the footer of the form. > [!NOTE] > **Note** > > The Cookie Notice must not be left blank. |
| Hide Securiti Branding | Mark this checkbox to hide the Securiti logo from the universal DSR form. |
4. Scroll down to the bottom of the page and click **Customize Content**.
5. Click **Add mapping** to map countries and states or regions to your existing DSR request forms.

> [!NOTE]
> **Note**
> 
> You can select the same country in multiple mappings, but you cannot select the same state more than once. Also, if the Response deadline is set to auto-detect (by IP or by country/state) in a DSR form, you cannot map that form.
  - If you want, you can map a default form that opens whenever a data subject chooses a geography to which you have not explicitly mapped a form.

> [!NOTE]
> **Note**
> 
> It is recommended to add the mapping for the default form. This ensures that if no forms match the county or state, the form automatically falls back to the default one.
  - Use **Limit Country Selection** setting to control which countries appear in the Universal Form.
    - Mark **All countries** radio button to show all countries in the Universal Form.
    - Mark **Only selected countries** radio button to restrict the list. Then, use the Countries menu to choose the countries you want to display.

![Screenshot_2025-09-28_at_7_27_25_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5c65229a-aca5-ee29-398e-d490a17ca3c1.png)
6. At the bottom of the Customize Content tab, click **Publish**, and use the tools in the Published Link and Embedded Link areas near the top of the page to preview the form and copy the links.
7. Work with your website team to either publish the link to the universal form, or to embed it in a page on your website.

> [!NOTE]
> **Note**
> 
> If the DSR form being mapped doesn’t support the language data subject chooses, the form appears in the default language you set during the form setting.

Securiti lets data subjects use the enhanced accessibility settings to make the published universal forms usable by individuals of all abilities. They can enable high color contrast to improve visibility, meet WCAG compliance, and support a wide range of users.

1. At the bottom right corner of the published form, data subjects can click **Accessibility Settings**.
2. On the Accessibility Settings popup, enable **Enable high contrast for increased visibility** toggle and click **Apply Settings**.
