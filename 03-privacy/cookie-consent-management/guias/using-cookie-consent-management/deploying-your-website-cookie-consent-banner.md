---
title: "Deploying your website cookie consent banner"
slug: "deploying-your-website-cookie-consent-banner"
status: "update"
updated: 2026-09-21T12:39:35Z
published: 2026-09-21T12:39:35Z
canonical: "helpcenter.securiti.ai/deploying-your-website-cookie-consent-banner"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Deploying your website cookie consent banner

**Scenario**

As a Data Compliance Officer, you need to test cookie banners in a staging environment before deploying them to production. For instance, when updating cookie banner text or consent settings, testing directly in production can lead to unintended user-facing changes. Reworking production code for test environments can also create confusion. With Securiti Cookie Consent Management, you receive separate testing code for validation and deployment code for production. This helps you launch updates confidently after reviewing changes in a safe environment.

Securiti provides testing and deployment code so you can validate cookie banner and preference center changes before applying them to production. You can deploy the code using automatic or manual SDK deployment options, configure optional consent code settings, update Content Security Policy requirements, and share or download consent codes for implementation.

## Best practices for deploying your cookie consent banner code

Securiti strongly recommends you follow the best practices outlined below to successfully deploy the cookie consent banner code on your domain(s):

- Use Securiti’s provided JavaScript deployment code as is.
- Always add this JavaScript code snippet at the beginning of the `&lt;head&gt;` tag in your domain(s).
- To ensure a seamless experience in deploying your cookie consent banner code, always use Securiti’s CSS files instead of:
  - Implementing your own CSS files, or
  - If you must use your own CSS files that you serve from your own hosting environment, integrate your CSS files with Securiti's CSS files immediately after each Securiti release.

> [!NOTE]
> **Note**
> 
> To do so, integrate Securiti’s most recent CSS files into your hosted version of CSS files after every Securiti release. This ensures you're always up to date with our latest improvements and bug fixes.
- Make all your cookie configuration changes before you add the deployment code to the `&lt;head&gt;` tag. Configure settings such as **strict CSP**, **auto-blocking**, **ADA compliance**, and **top-level domain tracking** on the **Consent Code** tab first, and then add the deployment code to your domain.
- If your domain enforces a Content Security Policy, update it before you deploy. See [Configuring your Content Security Policy](/latest/docs/deploying-your-website-cookie-consent-banner#configuring-your-content-security-policy).
- For tag management systems like Google Tag Manager (GTM), Securiti’s recommended best practice is to add the provided JavaScript deployment code at the beginning of the `&lt;head&gt;` tag. This is because scripts from the `&lt;head&gt;` tag always load before those from the `&lt;body&gt;` tag. Securiti aims to load its SDK first to avoid potential delays in rendering your cookie consent banners on your live domains due to script loading from the `&lt;body&gt;` tag.

## Deploying cookie banner using Automatic or Manual SDK deployment options

> [!WARNING]
> **Important**
> 
> Use the following table to understand the difference between the automatic and manual SDK deployment options:
> 
> | SDK Deployment Option | Description |
> | --- | --- |
> | Automatic SDK deployment | You can choose this option for all your existing and new domains. It lets you automatically receive Securiti’s latest SDK updates with each Securiti release. |
> | Manual SDK deployment | You can choose this SDK deployment option for all your existing and new domains. It lets you **pin your domain** to Securiti’s latest SDK version or the SDK version available at the time when you choose this option. For instance, if you choose manual SDK deployment option after the Securiti 1.101 release, your domain will be pinned to the SDK version released with this Securiti release. |
> 
> Securiti displays your previously configured **Dismiss link** as a **Dismiss button** by default on your opt-out compliance type cookie consent banner, after the auto-migration of your domains from **Legacy SDK** to **Automatic SDK deployment** option. If you want to revert this change to display the **Dismiss button** as a **Dismiss link**, you can do that by editing your cookie configuration from the **Customize Banner and Preference Center** tab of your domain.

To deploy a cookie banner on your domain using either **Automatic** or **Manual SDK deployment** option:

1. On the Cookie Consent Domains page, click the domain for which you want to deploy the cookie consent banner.

![Screenshot_2024-07-24_Cookies_domain1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-50c72043-04b0-720f-e9df-7b3ca0ca91c9.png)
2. Click the **Consent Code & Custom CSS** tab. Securiti lands you on the Consent Code tab by default, as shown below.

![Consent-Code-and-Custom-CSS-tab.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-fa658bef-29f7-3780-89c6-c2fc9fdfe401.png)
3. From the upper right corner of the page, click **Edit** to enable edit mode for the Consent Code & Custom CSS tab.
4. To deploy the cookie banner and preference center for your website, you can choose either **automatic** or **manual SDK deployment** option, as shown below. This version control functionality lets you control the deployment version of Securiti SDK and CSS updates for your cookie banners and preference centers. Choose one of the following options that better aligns with the requirements of your organization:
  1. From the Production Deployment Option section, mark the **Automatically deploy** Securiti **SDK and CSS updates** radio button to receive the latest Securiti SDK updates for your cookie banner and preference center with each Securiti release.

![Automatic-SDK-Deployment.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e537888e-26b1-265d-12f1-b052b918744b.png)
  2. From the Production Deployment Option section, mark the **Manually deploy** Securiti **SDK and CSS updates by clicking Deploy** radio button to choose manual deployment of Securiti SDK for your cookie banner and preference center.

![Manual-SDK-Deployment.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-238a0916-55b0-839c-0190-90bb81a53540.png)

> [!WARNING]
> **Important**
> 
> - If you mark the **manual SDK deployment** radio button, your published configuration remains unchanged when Securiti releases new SDK updates. Manual deployments update only when you publish new changes.
> - To update a manual deployment, save your latest cookie configuration changes, click **Deploy**, and then follow the publish code procedure. This includes adding the updated deployment code at the beginning of the `&lt;head&gt;` tag of your domain.
> - You need to deploy the updated consent code only once. If you switch from manual SDK deployment to automatic SDK deployment, and then switch back to manual SDK deployment, you do not need to redeploy the deployment code.
> - Securiti recommends manual deployment if you do not want to automatically apply new SDK changes to your cookie banners and preference centers, or if you use custom CSS. If you use highly customized CSS or manual CSS overrides, use the **Testing Code** and test your changes in your staging, QA, or native environments, as shown below. ![Manual-Deployment-Recommendation.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-831c2817-05ca-6a06-4e0f-276f39dc37b1.png)
> - If you update your cookie configuration or want to use a new release feature, you must update the domain to the latest available SDK version.
5. To publish your latest cookie configuration, save all your changes. Your changes for any tab of the Cookie Configuration page are saved locally in the draft. You must then deploy these changes to publish them on your domain(s).

From the upper right corner of the Cookie Configuration page, click **Deploy**, as shown below.

![Deploy-Changes.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f9a886c9-8b79-ac8e-1855-17e016c54f6e.png)

> [!WARNING]
> **Important**
> 
> You must save your changes made to any subtab on the **Cookie Configuration** page before switching to another tab. If you have unsaved changes in any of the tabs, Securiti shows you a confirmation popup. On the **Unsaved Changes** popup, either save your changes or discard them, as shown below.
> 
> ![Unsaved-Changes.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-fe00873b-e6b9-c63c-912b-175ca9919bfd.png)
6. On the **Publish Code** popup, adhere to the following granular publish code procedure:
  1. Click **Copy Test Code** to copy the testing code for your QA or staging domain(s). The checkmark on the left side of the text turns green if the code is copied successfully.

Add this Testing Code at the beginning of the `&lt;head&gt;` tag in your QA or staging domain(s) to validate your cookie configuration changes.
  2. Once you're satisfied with the performance of testing code, click **Copy Production Code** to copy the deployment code for your live or production domain(s). The checkmark on the left side of the text turns green if the code is copied successfully.

Add this Deployment Code at the beginning of the `&lt;head&gt;` tag in your live or production domain to publish your latest cookie configuration changes.
  3. In the **Change Note** field, add the appropriate summary or reason(s) for your latest cookie configuration changes to maintain the record. This reason shows up in the published version history of your code deployments.

![Screenshot_2024-07-24_Publish_code_step5c.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-41918b1e-7815-5495-f6d7-40f8bbc1894f.png)
  4. Mark the **Show Banner Again** checkbox to revoke the previous given consent and preferences of your data subjects, and to show them the cookie banner and preference center with the latest configuration.

![Screenshot_2024-07-24_Show_Banner_Again_step5d.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8fbfc630-83a5-755d-ba30-8dd873ef1800.png)
  5. Near the bottom of the **Publish Code** popup, click **Publish** to publish your changes, as shown below.

![Screenshot_2024-07-24_Publish_step5e.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e2e7bb77-e0a4-e928-70ff-9f7dcd2d61f3.png)
7. If your website enforces strict content security policies (CSPs), enable the **strict CSP** toggle, as shown below.

![Strict-CSP.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6b6b02ba-a9d9-868d-548d-f07460c5f672.png)

> [!NOTE]
> **Note**
> 
> The **strict CSP** toggle and your own Content Security Policy do two different jobs. Configure both.
> 
> - The **strict CSP** toggle changes how Securiti delivers the SDK. Securiti applies hashes to the inline code it adds to your webpage so that a strict policy allows that code to run without a broad exception for inline scripts.
> - Your Content Security Policy controls what the web browser loads. You must still allow the Securiti source in it, whether or not you enable this toggle.
8. (Optional) Enable the **Enable ADA compliance** toggle, as shown below.

![ADA-Compliance.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7a3cf823-cd48-cd7e-0ee8-9be1c1c6042e.png)

> [!NOTE]
> **Note**
> 
> ADA-accessible cookie banners let your website visitors use features such as:
> 
> | Feature | Description |
> | --- | --- |
> | Screen reader report | Banners can be accessed through screen readers. |
> | Keyboard navigation | Every element of the banners can be accessed through a keyboard, without the need for a mouse or trackpad. |
9. (Optional) Enable the **Use top-level domain to track consent status** toggle to automatically record the consent of your data subjects for all your existing subdomains via the cookie banner and preference center of your base (top-level) domain.

When you enable this toggle, it shows your cookie banner and preference center to your data subjects when they visit your base domain. And once your data subjects give their consent through your deployed cookie banner and preference center, their consent is also recorded automatically for all existing **subdomains** of your organization or business.

![Top-level-Domain-Tracking.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3065dfcb-5891-3f80-2cef-e1c5956ba8a0.png)

> [!WARNING]
> **Important**
> 
> - You must deploy the deployment code in your base domain and the subdomains belonging to your base domain before using the top-level domain tracking functionality.
> - For instance, subdomains belonging to your base domain `www.securiti.ai` could be `app.securiti.ai`, `app.eu.securiti.ai`, `app2.securiti.ai`, etc.
> - Do not deploy the deployment code on unrelated domains. For instance, refrain from deploying the code on domains that are not subdomains of your base domain.
10. (Optional) Securiti lets you display a **Manage Consent Preferences** button on your domain. From the right side of the code box, click **Copy Code** to copy the code snippet to the clipboard. Carefully paste this code snippet into your website's code where you want the button to appear.

You can also customize the text of the button label from the code snippet to suit. Your data subjects can click this button to open the cookie preference center and manage their consent preferences.

![Auto-Manual-manage-preferences.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2e8fb12e-f3e1-7e34-7bf7-426a10c87dd4.png)
11. Copy the **Testing** and **Deployment** code snippets from the code boxes, as shown below, and paste them into a text file for later use.

![Screenshot_2023-09-26_at_12_58_19_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c3b6c01f-7a91-9b41-523d-d7df1f31994d.png)
12. Switch on the **Enable Auto Blocking** toggle, and copy the **Autoblocking Testing Code**, as shown below. Add this code snippet at the beginning of the `&lt;head&gt;` tag of your QA or staging domain(s) for testing purposes.

![Screenshot_2023-09-25_at_3_43_49_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a0a328be-be58-4514-d7fa-1e8ec3a9cee8.png)

![Screenshot_2023-09-25_at_3_43_49_PM_2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-dd829a33-924f-07f4-c6ea-b58fa7eebd36.png)

Once you're satisfied with the test changes on your QA or staging domain(s), copy the **Autoblocking Deployment Code** snippet, as shown below, and add it at the beginning of the `&lt;head&gt;` tag of your live or production domain(s). For more information on auto-blocking, see [Automatically blocking scripts from dropping cookies](/latest/docs/automatically-blocking-scripts-from-dropping-cookies).
13. You can add an initiator path to a cookie category through the **Categorize Initiators** section, as shown below. It lets you assign the root URL of a scanned cookie to a single cookie category.

![Screenshot_2023-09-11_at_1_58_03_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-eb22d8b2-6d0b-9a3c-037d-19baa2556356.png)

![Screenshot_2024-07-24_Step12bSS.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c62d627e-4e74-ced2-584f-a8aad2d4e455.png)

![Screenshot_2024-07-24_Step12cSS.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1e13a341-2f9a-f2f4-4388-f9d4a6fb0a37.png)

> [!NOTE]
> **Note**
> 
> Adding initiator paths to cookie categories lets Securiti apply category-based auto-blocking to those initiators.
> 
> - Click **+ Add Initiator Path**, and select the cookie category for the initiator path.
> - Add the URL in the **Initiator URL** field, and from the upper right corner of the page, click **Save**, as shown below.
> 
> ![Save.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c14d40e1-d6cb-e3a7-be27-0bb4cc1a583a.png)
14. Save and deploy the new code to your web server.

> [!NOTE]
> **Note**
> 
> When you preview your cookie consent banner in Securiti, it may appear different from when it is displayed on your website. This is because when the cookie banner is displayed on your domain it inherits the font styles from the domain.

## Configuring your Content Security Policy

If your domain enforces a Content Security Policy, add Securiti as an allowed source. If you do not, the web browser can block the Consent SDK, and your cookie banner might not render.

### Allow the Securiti source

Add the following source to your Content Security Policy:

`https://*.securiti.ai`

The asterisk is a wildcard that matches any Securiti host. Use the wildcard instead of naming a single host.

Securiti serves the Consent SDK from several CDN hosts, and the host that serves your domain can change between releases. If your Content Security Policy names only one host, such as `https://cdn-app.securiti.ai`, the policy can stop matching when the host changes, and your cookie banner might stop rendering.

### Add the source to the required CSP directives

At minimum, the following directives must include the Securiti source:

| **Directive** | **Why Securiti needs it** |
| --- | --- |
| `script-src` | Loads `cookie-consent-sdk-loader.js` and the Consent SDK. |
| `style-src` | Loads the Securiti CSS files that style your cookie banner and preference center. You do not need this directive if you set the `data-skip-css` attribute to `TRUE` and serve your own CSS. |

## Key points for implementations with high customizations

- If your domain enforces a Content Security Policy, allow the Securiti source in your policy. Use the wildcard source instead of a single CDN host because the host that serves your domain can change between releases.
- If you use a highly customized CSS or perform manual CSS overrides, Securiti strongly recommends that you use the **Testing Code** and test your changes in your native environments.

![Screenshot_2024-07-24_Key_points_for_implementations_with_high_customizations_SS.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2ce7c0c2-d05e-c3bc-05ba-6f33104f8c3e.png)
- You must update your custom CSS to align it with Securiti’s new SDK and CSS changes.

> [!WARNING]
> **Important**
> 
> - Securiti strongly recommends that you use Securiti’s CSS file instead of hosting and serving your own CSS file. If you choose to use your own custom CSS file, you must maintain alignment with Securiti’s CSS. Integrate Securiti’s most recent CSS file into your hosted version after every Securiti release. This helps keep your CSS aligned with Securiti’s latest improvements and bug fixes.
> - You must also do this if you use CSS forking, such as using Securiti’s CSS files and serving them from your own hosting environment.
- If you do not redeploy the Securiti SDK code, your forked CSS stops matching the current Securiti CSS, and any Content Security Policy entry that names a specific Securiti host can stop matching the host that now serves your domain.
  - Allow `https://*.securiti.ai` in your Content Security Policy so that a host change does not break your cookie banner.
- Choosing the manual deployment option lets you pin your domain to the Securiti release version of your choice. Securiti supports your current published version indefinitely.
- The SDK loader `&lt;script&gt;` tag contains the `data-skip-css` attribute for the **Testing** and **Deployment Code** snippets, as shown below. The SDK loader looks for the value of the `data-skip-css` attribute in the `&lt;script&gt;` tag and performs the following actions:

> [!NOTE]
> **Note**
> 
> By default, the value of the `data-skip-css` attribute is **false**.

> [!CAUTION]
> **Caution**
> 
> - Securiti strongly recommends you use its CSS files instead of your own. However, you can set the value of `data-skip-css` attribute as **TRUE** only if you use forked CSS in your domain(s). For instance, if you use Securiti’s CSS files and serve them from your own hosting.
> - Note that once you perform this action, your cookie banner(s) and preference center(s) **do not receive** Securiti’s styling, and they appear with plain text with no styling at all.
> - If you set the value of this attribute as **TRUE**, the banner position, button shape, color palette(s), preference center styles, and the styles in all of the consent frameworks offered by Securiti stop loading in your domain(s).
  - If you set the value as **FALSE**, the SDK loader loads the Securiti’s CSS files in your domain(s).
  - If you set the value as **TRUE**, the SDK loader **does not load** the Securiti’s CSS files in your domain(s).

![Screenshot_2023-09-26_at_10_21_18_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-32f53e65-3ea0-afdd-f682-794b355f3cb8.png)

## Sharing and downloading consent codes

You can share the consent deployment codes with the internal and external members of your organization via email directly from the UI.

To share the consent codes via email:

1. On the **Cookie Consent Domains** page, click the domain for which you want to download the consent deployment codes, as shown below.

![Screenshot_2023-08-21_at_9_57_40_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a79d12ba-c09f-93e9-4f4e-7a712350ac7b.png)
2. On the **Consent Code & Custom CSS > Consent Code** tab, from the right side of the **Share Codes Snippets** section, click **Share Codes via Email**, as shown below.

![Share-Codes.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b6dfe38b-3abe-fc46-26e5-fe891d9f7eac.png)
3. On the **Share Consent Codes** popup, from the **Email** menu, select the email address of the recipient you want to share these codes with.
4. From the **Message** text field compose your message that you want to send via email.
5. Enable the **Include Testing Code** toggle only if you want to also attach the testing code in the email, as shown below.

![Screenshot_2023-08-15_at_12_30_00_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-03e7f261-cf36-773a-40d4-9050fdb81a33.png)

> [!WARNING]
> **Important**
> 
> - You can also share the consent codes via email with the stakeholders that are external to your organization.
> - Save all changes before sharing consent codes via email to ensure that the code snippets include the latest configurations.
> - Only the following Securiti user roles in your tenant can share the consent codes via email:
>   - Super Admin
>   - Org Admin
>   - Module Owner
>   - Operator
> - The following Securiti user roles in your tenant have READ-only permissions for this functionality:
>   - DPO
>   - User

If you do not want to copy the code snippets block by block, you can directly download the consent deployment codes from the UI in a single text file.

To download the consent codes from the UI:

1. On the **Consent Code & Custom CSS > Consent Code** tab, from the right side of the **Share Codes Snippets** section, click **Download All Codes**, as shown below.

![Download-Codes.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-73dcb7e8-ce2d-f750-9b15-b91e91a1fc54.png)

This downloads a text file containing all consent deployment codes on your local machine.
2. To access the file, open the **Downloads** directory on your local machine.

> [!WARNING]
> **Important**
> 
> - To download the consent codes with latest configurations, save all your changes and then download the codes.
> - Only the following Securiti user roles in your tenant can download the consent codes:
>   - Super Admin
>   - Org Admin
>   - Module Owner
>   - Operator
> - The following Securiti user roles in your tenant have READ-only permissions for this functionality and cannot download the consent codes from the UI:
>   - DPO
>   - User

## FAQs

****Can I add the deployment code (Consent SDK) in the body tag instead of the head tag?****

Securiti’s recommended best practice is to place the deployment code at the beginning of the `&lt;head&gt;` tag. This ensures that our SDK loads first, minimizing any potential delays in rendering cookie consent banners on domains.

****Why is it preferable to place the deployment code in the <head> tag?****

Scripts from the `&lt;head&gt;` tag always load before those from the `&lt;body&gt;` tag, and Securiti aims to load its SDK first to avoid any possible delays or unknown side effects, such as delayed rendering of cookie consent banners on your domains.

****Can I still use GTM to deploy the SDK code in the <body> tag?****

While deploying the deployment code (Consent SDK) in the `&lt;body&gt;` tag using GTM may work in specific cases, success isn't guaranteed due to variations in GTM configurations. You can use this approach if it works for you, but Securiti strongly recommends that you thoroughly test your cookie banner and preference center configurations in your QA or staging environments to ensure they render as expected.

****What does the asterisk mean in the Content Security Policy guidance?****

The asterisk is a wildcard that matches any Securiti host. Allowing `https://*.securiti.ai` permits every host Securiti serves the consent SDK from, including hosts that change between releases. Allow the wildcard rather than a single host. If you allow only `https://cdn-app.securiti.ai` and Securiti later serves your domain from a different host, your web browser blocks the SDK and your cookie banner stops rendering.
