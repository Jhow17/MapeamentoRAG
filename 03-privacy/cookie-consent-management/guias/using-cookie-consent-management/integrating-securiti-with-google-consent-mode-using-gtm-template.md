---
title: "Integrating Securiti with Google Consent Mode using GTM Template"
slug: "integrating-securiti-with-google-consent-mode-using-gtm-template"
updated: 2026-08-27T08:11:47Z
published: 2026-08-27T08:11:47Z
canonical: "helpcenter.securiti.ai/integrating-securiti-with-google-consent-mode-using-gtm-template"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Integrating Securiti with Google Consent Mode using GTM Template

## Prerequisites

To successfully configure Google Consent Mode (GCM) with Securiti's GTM Template, you must have:

- A successfully scanned and GCM configured domain in the Cookie Consent Management module.
- An account on the Google Tag Manager platform.
- The GTM container for your organization must be configured within the GTM account.

Before you proceed, you must ensure that you have selected **one of the following implementation approaches**:

- Google Consent Mode (GCM) using a GTM template (covered in this help article), or
- Google Tag Manager (GTM)–based integration without GCM. See [Integrating Securiti with Google Tag Manager](/latest/docs/integrating-securiti-with-google-tag-manager).

## Procedure

If you already have a GTM-based implementation in place, do not follow the steps in this article unless you plan to migrate fully to GCM.

> [!CAUTION]
> Caution
> 
> Use either a Google Tag Manager (GTM)–based integration or a Google Consent Mode (GCM)–based integration. Do not combine both approaches. Layering GCM instructions on top of an existing GTM setup can lead to incorrect consent behavior because of conflicts and compliance issues.

To integrate Google Consent Mode with your domain if you are using GTM Template:

> [!WARNING]
> **Important**
> 
> - Google Consent Mode only governs tags that read Google's consent signals, including **GA4**, **Google Ads**, **Floodlight**, and **Google's own tag templates** in GTM. It has **no effect on non-Google tags** such as Meta, Criteo, LinkedIn, or Microsoft UET, etc. To manage consent for third-party tags, you must configure a separate event-driven method that pushes consent state to your `dataLayer` for these tags to read. For more information, see [Using the advanced event-driven methods](/latest/docs/using-the-advanced-event-driven-methods).
> - Securiti advises that if you encounter issues with missing Google Consent Mode or TCF signals on Google tags, you must start troubleshooting with Securiti support, not Google. If you encounter such an issue, contact [support@securiti.ai](mailto:support@securiti.ai) first for assistance.

1. Configure GCM from the management portal by following the procedure as explained in [Configuring Google Consent Mode](/latest/docs/configuring-google-consent-mode).
2. Access and log in to your Google Tag Manager account.
3. Configure **User-Defined Variables** as explained in [Configure User-Defined Variables](/v1/docs/integrating-securiti-with-google-consent-mode-using-gtm-template).
4. Configure Load Consent Mode Defaults tag in GTM as explained in [Configure Load Consent Mode Defaults tag](/v1/docs/integrating-securiti-with-google-consent-mode-using-gtm-template).
5. Configure Securiti's GTM template as explained in [Configure Securiti GCM Template tag](/v1/docs/integrating-securiti-with-google-consent-mode-using-gtm-template).
6. Configure Load Securiti SDK tag in GTM as explained in [Configure Load Securiti SDK tag](/v1/docs/integrating-securiti-with-google-consent-mode-using-gtm-template).
7. Submit all your changes in GTM, and place the GTM code in your website's `&lt;head&gt;` tag.

## Sequence of procedures

Follow the procedures from the following sections in a sequence:

### Configure User-Defined Variables

To create User-Defined variables of **Constant** type:

1. From the left navigation menu of GTM, click **Variables**.
2. From the upper right corner of the **User-Defined Variables** section, click **New**.

![User-Defined_Variable_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4d3db5b8-9505-ecd5-4cbc-a3dea415331a.png)
3. Name this variable as **DomainID**, and on the **Variable Configuration** section, from the upper right corner, click **Edit** (pencil icon), as shown below. ![User-Defined_Variable_2_2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b55ea7f4-29e8-3801-5a90-c6b32a2c3d6f.png)
4. From the **Choose variable type** sidebar, select **Constant,** as shown below.

![User-Defined_Variable_2_3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b5f89eac-8b8e-837a-95f3-9c6326d5191d.png)
5. Now enter the value for the `DomainID` variable of **Constant** type, and from the upper right corner, click **Save**, as shown below.

![User-Defined_Variable_2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-48e6b2d1-120f-b23f-9f8d-7203babaf5c6.png)

You can copy the `DomainID` value from the **Deployment Code** snippet located in the **Consent Code & Custom CSS > Consent Code** tab of your scanned domain in the management portal, as shown below.

![User-Defined_Variable_4.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-aceeabd8-a289-cbe2-9fce-8fed72b2e537.png)
6. Similar to the sequence from step no. 2 through 5, configure three more variables of **Constant** type with the names provided in the table below.

| Variable | Description |
| --- | --- |
| `TenantID` | This is the **UUID** of your Securiti tenant. |
| `SecuritiCDN` | This is the **CDN value** of your Securiti cloud instance, such as `https://cdn-[your-securiti-instance].securiti.ai`. > [!WARNING] > **Important** > > You must use the appropriate CDN value for your Securiti cloud instance based on your region. Refer to the following list for the values of all Securiti cloud instances: - U.S. cloud instance: `https://cdn-prod.securiti.ai` - U.S. GCP cloud instance: `https://cdn-app1.securiti.ai` - Indonesia (Jakarta) cloud instance: `https://cdn-app2.securiti.ai` - Canada (Montreal) cloud instance: `https://cdn-app3.securiti.ai` - Australia (Sydney) cloud instance: `https://cdn-app4.securiti.ai` - UAE cloud instance: `https://cdn-app5.securiti.ai` - India (Mumbai) cloud instance: `https://cdn-app6.securiti.ai` - Kingdom of Saudi Arabia (KSA) cloud instance: `https://cdn-app7.securiti.ai` - State of Qatar cloud instance: `https://cdn-app8.securiti.ai` - EU cloud instance: `https://cdn-prod.eu.securiti.ai` |
| `SecuritiAPI` | This is the value of `data-backend-url`. |

You can find and copy the respective values for these variables from the **Deployment Code** snippet located in the **Consent Code & Custom CSS > Consent Code** tab of your scanned domain in the management portal, as shown below. ![User-Defined_Variable_5.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1d87ec9c-4635-10eb-56bc-32794cac1e77.png)
7. Once done, you will have the following User-Defined Variables:
  - `DomainID`
  - `TenantID`
  - `SecuritiCDN`
  - `SecuritiAPI`

![User-Defined_Variable_3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-08f33776-0f41-5beb-0a3a-691780af4ef3.png)

### Configure Load Consent Mode Defaults tag

To configure a Load Consent Mode Defaults tag:

1. From the left navigation menu of GTM, click **Tags**.
2. From the upper right corner of the page, click **New**, and name this tag as **Load Consent Mode Defaults**, as shown below.

![Load_Consent_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1decc9ae-4709-bf80-1eb5-57e75e7cb95b.png)
3. On the **Tag Configuration** section, from the upper right corner, click **Edit** (pencil icon), and from the **Choose tag type** sidebar select **Custom HTML**, as shown below.

![Load_Consent_2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-fdbe9968-c153-72e2-0eff-65d1d188b931.png)

![Load_Consent_3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-508549e6-207d-e2c8-3ce9-fd63aa5e3963.png)
4. Add the following script in the **HTML box**:

```javascript
<script async src='{{SecuritiCDN}}/consent/cookie_banner/{{TenantID}}/{{DomainID}}/google_consent_defaults.js'></script>
```
5. Near the bottom, expand the **Advanced Settings** option, and from **Tag firing options** menu, choose **Once per page**, as shown below.

![Load_Consent_4.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6bea2a4c-1de2-53e4-619f-8d3e45e28f50.png)

![Load_Consent_5.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a52ad388-bf0a-64cb-859c-15e35a1f39c8.png)
6. Once done, from the upper right corner, click **Save** to save these changes.

### Configure Securiti GCM Template tag

To configure Securiti's GCM Template:

1. From the left navigation menu of GTM, click **Templates**.
2. On the **Tag Templates** section, and from the upper right corner, click **Search Gallery**, as shown below

![Template_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-fffbe0b3-1885-2b1a-86a0-6927c8d705d6.png)
3. On the **Import Tag Template** sidebar, from the upper right corner, click **Search** (magnifying glass icon) to search for Securiti's template from **Google's Community Template Gallery**. In the search bar, type "Securiti, Inc. CMP", and press **Enter**, as shown below.

![Template_2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8f780a63-c87e-ff85-cc15-5b2166deb493.png)

![Template_3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-002d4f89-7721-2775-2882-652006f4005a.png)
4. Click the "Securiti, Inc. CMP" template, and from the upper right corner, click **Add to workspace**, as shown below.

![Template_4.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9e20f13a-9bba-34b2-9440-52494ac7a6de.png)
5. On the confirmation popup, near the bottom right corner, click **Add**, as shown below.

![Template_5.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ae1eca46-883d-ae3e-7c66-4a170c4e71eb.png)
6. Once done, from the left navigation menu of GTM, click **Tags**.
7. From the upper right corner of the page, click **New**, and name this tag as **Securiti GCM Template Tag**.
8. On the **Tag Configuration** section, from the upper right corner, click **Edit** (pencil icon), as shown below.

![Temp_Tag_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8bf24584-3f24-b771-1efd-568b961e8a51.png)
9. From the **Choose a tag type** sidebar, select **Securiti, Inc. CMP**, as shown below.

![Temp_Tag_2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3a5fe63c-863a-0b49-a8ac-cbdaf7e7233b.png)
10. Mark the radio button below the **Enable Consent Mode?** to **Yes**, as shown below.

![Temp_Tag_3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1ca5f675-2baf-74b4-8cfe-4a81586cff2d.png)
11. Near the bottom, expand the **Advanced Settings** option:

> [!NOTE]
> **Note**
> 
> Based on the aforementioned configuration, the default setup loads first, followed by our template, and then Securiti's SDK loads.
  1. From the **Tag firing options** menu, choose **Once per page**.
  2. Expand the **Tag Sequencing** option, and mark the checkbox for **Fire a tag before Securiti GCM Template Tag fires**.
  3. Click **Setup Tag**, and on the **Choose a tag** page, select the **Load Consent Mode Defaults** tag, as shown below.

![Temp_Tag_4.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-47a22c6c-1829-1daa-91ff-6f1c68b2ac50.png)

![Temp_Tag_5.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-67d14d0a-ad84-1f6e-0aaf-68e782c0fc42.png)
12. On the **Triggering** section, from the upper right corner, click **Edit** (pencil icon), as shown below.

![Temp_Tag_6.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6030f836-f90b-3124-58b2-d285a457e918.png)
13. On the **Choose a trigger** page, select **Consent Initialization - All Pages**, as shown below.

![Temp_Tag_7.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5263e877-a5a4-bf47-5cf4-c8f40afc93dc.png)
14. From the upper right corner, click **Save**, as shown below. ![Temp_Tag_8.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-106cf2e3-442b-6d5b-5869-e81ba9e92944.png)

### Configure Load Securiti SDK tag

To configure the Load Securiti SDK tag, first you must configure a trigger. To do so:

> [!NOTE]
> **Note**
> 
> Use this procedure only if you are deploying your domain with GTM for the first time. If you have already configured Securiti’s SDK in your Google Tag Manager setup, you can disregard the following procedure.

1. From the left navigation menu of GTM, click **Triggers**.
2. From the upper right corner of the **Triggers** section, click **New**, and name this trigger as **Watcher - Dom Ready**, as shown below.

![Trigger_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-621b05f6-b967-23e6-853c-371729a5a4fd.png)
3. On the **Trigger Configuration** section, from the upper right corner, click **Edit** (pencil icon), as shown below.

![Trigger_2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d881b45c-d400-d970-1dfd-354c8aabf652.png)
4. From the **Choose a trigger type** sidebar, select **Dom Ready**, as shown below.

![Trigger_3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8ab4fc11-a14f-8fa1-4ce7-830a0eaa4a25.png)
5. From the **This trigger fires on** section, mark the radio button for **All Dom Ready Events**, as shown below.

![Trigger_4.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a1ef490c-6d24-124e-7fff-b21c11ca2ea4.png)
6. From the upper right corner of the page, click **Save**, as shown below.

![Trigger_5.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-fd15be4a-d475-ee56-8843-5f4b301310df.png)
7. Once done, now configure the Load Securiti SDK tag. From the left navigation menu of GTM, click **Tags**.
8. From the upper right corner of the page, click **New**, and name this tag as **Load Securiti SDK**.

![Load_SDK_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-97216c91-cb0e-edf9-7eba-995c54c8844a.png)
9. On the **Tag Configuration** section, from the upper right corner, click **Edit** (pencil icon), as shown below.

![Load_SDK_2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-27346c5e-a75f-dc07-0a9f-ef5cdb6186b9.png)
10. From the **Choose a tag type** sidebar, select **Custom HTML**, as shown below.

![Load_SDK_3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-97b798c3-d64e-49ae-f3a6-525228231485.png)
11. Add the following code snippet in the **HTML** field, as shown below.

```javascript
<script>
                            (function() {
                            var s = document.createElement('script');
                            s.src = '{{SecuritiCDN}}/consent/cookie-consent-sdk-loader.js';
                            s.setAttribute('data-tenant-uuid', '{{TenantID}}');
                            s.setAttribute('data-domain-uuid', '{{DomainID}}');
                            s.setAttribute('data-backend-url', '{{SecuritiAPI}}');
                            s.setAttribute('data-skip-css', 'false');
                            s.defer = true;
                            var parent_node = document.head || document.body;
                            parent_node.appendChild(s);
                            })()
                            </script>
```

![Load_SDK_4.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a215f318-46ea-ec0c-1bdd-07f3f1859791.png)

You must add appropriate values for the following variables. You can find and copy the respective values for these variables from the **Deployment Code** snippet located in the **Consent Code & Custom CSS > Consent Code** tab of your scanned domain in the management portal, as shown below.

| Variable | Description |
| --- | --- |
| `TenantID` | This is the **UUID** of your Securiti tenant. |
| `DomainID` | This is the **UUID** of your scanned domain. |
| `SecuritiCDN` | This is the **CDN value** of your Securiti cloud instance such as `https://cdn-[your-securiti-instance].securiti.ai`. > [!WARNING] > **Important** > > You must use the appropriate CDN value for your Securiti cloud instance based on your region. Refer to the following list for the values of all Securiti instances: - U.S. cloud instance: `https://cdn-prod.securiti.ai` - U.S. GCP cloud instance: `https://cdn-app1.securiti.ai` - Indonesia (Jakarta) cloud instance: `https://cdn-app2.securiti.ai` - Canada (Montreal) cloud instance: `https://cdn-app3.securiti.ai` - Australia (Sydney) cloud instance: `https://cdn-app4.securiti.ai` - UAE cloud instance: `https://cdn-app5.securiti.ai` - India (Mumbai) cloud instance: `https://cdn-app6.securiti.ai` - Kingdom of Saudi Arabia (KSA) cloud instance: `https://cdn-app7.securiti.ai` - State of Qatar cloud instance: `https://cdn-app8.securiti.ai` - EU cloud instance: `https://cdn-prod.eu.securiti.ai` |
| `SecuritiAPI` | This is the value of `data-backend-url`. |

![User-Defined_Variable_5.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1d87ec9c-4635-10eb-56bc-32794cac1e77.png)
12. Near the bottom, expand the **Advanced Settings** option, and from the **Tag firing options** menu, choose **Once per page**, as shown below.

![Load_SDK_5.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ae1ce5ab-a409-abd5-b7ec-c53ec0184fef.png)
13. On the **Triggering** section, from the upper right corner, click **Edit** (pencil icon), as shown below.

![Load_SDK_6.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9b1ccc1a-23b1-cdfd-b74a-79481d614d82.png)
14. On the **Choose a trigger** page, select **Watcher → DOM Ready**, as shown below. ![Load_SDK_7.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b3e175d3-c34b-6602-ba41-af9280175b43.png)
15. From the upper right corner, click **Save** to save all your changes, as shown below. ![Load_SDK_8.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b4e77dbe-f430-78b8-d2d1-4ff4ce6416e9.png)

## Managing consent events in GCM for timing-sensitive GTM deployments

When using Google Consent Mode (GCM), if you are experiencing **timing issues** when deploying the consent banner and SDK through Google Tag Manager (GTM), you can improve performance by embedding the scripts **directly into your domain's HTML**, instead of relying on GTM for injection.

This alternative method ensures that consent-related scripts load **before GTM**, preventing race conditions that may delay tag execution or affect the accuracy of consent signal processing.

> [!NOTE]
> Note
> 
> Auto-blocking prevents a script from loading at all until consent is given, for any vendor, Google or non-Google. This is a separate mechanism from Google Consent Mode. Auto-blocking does not send live consent state to tags that are already loaded and running through GTM.

### Recommended script order

To avoid conflicts and ensure proper initialization, you must follow this order in your domain's `&lt;head&gt;` tag:

1. (Optional) Securiti's auto-blocking script

If you are using Securiti's auto-blocking solution, this script must be the very first script in the `&lt;head&gt;` tag. It ensures third-party tags are blocked based on consent status before they load.
2. Load Google Consent Mode (GCM) defaults

Inject the following script to load default settings for Google Consent Mode (GCM).

```javascript
<script src="https://<securiti_cdn_host_url>/consent/cookie_banner/<tenant_id>/<domain_uuid>/google_consent_defaults.js">
</script>
```

For instance, insert the script with approrpriate variable values like this:

```javascript
<script src="https://cdn-prod.securiti.ai/consent/cookie_banner/b9153366-8d40-43b0-8009-e7c5f7321d6c/cf577c68-346b-40ab-9e5e-b32d78wff61v/google_consent_defaults.js">
</script>
```

You must add appropriate values for the following variables. You can find and copy the respective values for these variables from the **Deployment Code** snippet located in the **Consent Code &amp; Custom CSS > Consent Code** tab of your scanned domain in the management portal, as shown below.

| Variable | Description |
| --- | --- |
| `tenant_id` | This is the **UUID** of your Securiti tenant. |
| `domain_uuid` | This is the **UUID** of your scanned domain. |
| `securiti_cdn_host_urlritiCDN` | This is the **CDN value** of your Securiti cloud instance such as `https://cdn-[your-securiti-instance].securiti.ai`. > [!WARNING] > **Important** > > You must use the appropriate CDN value for your Securiti cloud instance based on your region. Refer to the following list for the values of all Securiti instances: - U.S. cloud instance: `https://cdn-prod.securiti.ai` - U.S. GCP cloud instance: `https://cdn-app1.securiti.ai` - Indonesia (Jakarta) cloud instance: `https://cdn-app2.securiti.ai` - Canada (Montreal) cloud instance: `https://cdn-app3.securiti.ai` - Australia (Sydney) cloud instance: `https://cdn-app4.securiti.ai` - UAE cloud instance: `https://cdn-app5.securiti.ai` - India (Mumbai) cloud instance: `https://cdn-app6.securiti.ai` - Kingdom of Saudi Arabia (KSA) cloud instance: `https://cdn-app7.securiti.ai` - State of Qatar cloud instance: `https://cdn-app8.securiti.ai` - EU cloud instance: `https://cdn-prod.eu.securiti.ai` |

![User-Defined_Variable_5.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1d87ec9c-4635-10eb-56bc-32794cac1e77.png)
3. Cookie banner and SDK script

Copy this script from the **Consent Code & Custom CSS > Consent Code** tab and place it **just before** the GTM container snippet (`gtm.js`). This script loads all required consent assets, including the Securiti's Cookie Consent SDK.
4. Google Tag Manager container script (`gtm.js`)

This is the standard script provided by Google for deploying tags.

> [!NOTE]
> **Note**
> 
> To ensure default consents are applied before any dependent scripts execute, **do not add** **the** `async` **attribute** to the `&lt;script&gt;` tag for the Google Consent Mode (GCM) defaults. Loading the script synchronously ensures that default values are accessible to other scripts when they run.

### Impact of script order and direct deployment

This deployment method ensures that:

- Consent is evaluated before GTM tags execute.
- Auto-blocking, if used, is initialized before any third-party scripts.
- Timing issues related to GCM's default settings are avoided.
- You no longer need to rely on GTM to load `loadConsentModeDefaults`, `loadConsentModifiers`, or the `loadSecuritiSDK` tag because these are now handled directly by the embedded script.

### Additional configuration considerations

- You can still use the Securiti **GCM template** in GTM to configure Google Consent Mode behaviors, but the cookie banner and SDK scripts must be deployed directly into your domain's HTML.
- This solution simplifies setup for customers who experience timing inconsistencies when loading consent-related scripts through GTM.

## FAQs

****Can I still use GTM for deploying the cookie banner and SDK if I am not experiencing timing issues?****

Yes. Securiti recommends the alternative method only if you are witnessing delays in consent evaluation or GTM tag execution. If everything is working as expected, you can continue using the standard GTM-based deployment.

****What is the purpose of removing the async attribute from the script tag?****

The `async` attribute causes the script to load independently, which may result in **default consent values not being available** when dependent scripts execute. Removing it ensures **synchronous loading**, so other scripts can reliably access consent status.

****Where exactly should I place the auto-blocking script if I am using it?****

The auto-blocking script should be the **first script inside the** `&lt;head&gt;` **tag**, before the cookie banner script and before `gtm.js`. This ensures third-party tags are blocked right from the start, based on consent.

****Do I still need to configure the** **Securiti** **GCM template in GTM?****

Yes, if you are using GCM. However, when using this alternative method, you can skip the GTM steps related to loading consent mode defaults, consent modifiers, and the SDK, as those are now handled directly through the embedded script.

****Will this solution work across all environments such as staging and production?****

Yes, as long as you ensure the scripts are placed in the correct order and not modified by other deployment tools, this solution will work consistently across environments.

Google Consent Mode (GCM) is a functionality that allows website owners to adjust how their Google services behave based on the consent preferences of their data subjects. When a data subject opts in or out of cookies for advertising or analytics, Consent Mode dynamically adapts, ensuring that Google's tools comply with the data subject's choices. Essentially, it enables websites to respect user consent for cookies while still providing valuable data insights and advertising capabilities in a privacy-focused manner

## Related

- [Configuring Google Consent Mode](/configuring-google-consent-mode.md)
- [Using the advanced event-driven methods](/using-the-advanced-event-driven-methods.md)
