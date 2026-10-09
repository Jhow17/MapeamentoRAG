---
title: "Using the advanced event-driven methods"
slug: "using-the-advanced-event-driven-methods"
updated: 2026-04-23T10:19:13Z
published: 2026-04-23T10:19:13Z
canonical: "helpcenter.securiti.ai/using-the-advanced-event-driven-methods"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Using the advanced event-driven methods

Securiti offers advanced event-driven methods that let you seamlessly enable integrations with third-party tools, frameworks, and even with your custom scripts. These methods offer you greater control over how your cookie banners interact with external platforms, and let you tailor consent management to suit your specific needs.

For instance, with the advanced event-driven methods, you can configure your cookie banners to respond dynamically to events on your domain or within integrated third-party platforms. When using Securiti's Cookie Consent SDK, these methods let you define how the SDK integrates with your domain and third-party systems. You can listen for specific events, execute custom operations based on data subject interactions, and fine-tune the consent behavior to suit your needs. This provides more flexibility in building consent solutions specifically tailored to both your compliance and business requirements.

Use the following table to learn how to handle various use cases using the advanced event-driven methods.

| Use case | Description |
| --- | --- |
| Stop data subject interaction until consent is granted | You can prevent your site visitors or data subjects from interacting with the domain until they grant consent. For instance, you can use the `beforeLoad()` event to delay page loading until the consent is provided. The `onConsentGiven()` event resumes domain functionality once consent is granted. This ensures compliance by blocking interaction until explicit consent is obtained. |
| Prevent banner visibility issues due to high `z-index` elements | You can ensure the cookie banner remains visible when elements with higher `z-index` values could obscure it. You can use the `beforeRenderBanner()` event to dynamically adjust the `z-index`. The `onCloseBanner()` event resets the `z-index` when the cookie banner is closed, preventing interference with other elements. |
| Trigger a third-party popup when a cookie category is toggled to granted | If you want, you can open a custom third-party popup when a specific cookie category is toggled to a granted state. You can do so by using the `onCategoryToggled()` event to detect cookie category changes and trigger the popup accordingly. This event lets you integrate external UI components seamlessly. |
| Synchronize the cookie banner with domain language selection | Imagine if the cookie banner’s language dynamically changes when data subjects change the domain's language via a dropdown or a menu. To tackle this scenario, you can use the `onReady()` event to ensure SDK initialization and call the `changeLanguage()` method whenever the language selection changes. This keeps the cookie banner language in sync with the domain, improving multilingual user experience. |
| Simplify CSS customization for the cookie banner | Instead of relying on CSS overrides or hacks, you can use the `beforeLoad()` event to apply styling programmatically. This ensures cleaner, more maintainable, and flexible customization without modifying CSS manually. |
| Enable compliance audits | If you use third-party audit tools to validate cookie behavior across your domains, these advanced event-driven methods let those tools simulate website visitor interactions with your cookie banner. This helps verify whether cookies are blocked or dropped in accordance with regulatory requirements. |
| Improve third-party integrations | Whether you rely on tag management systems such as Google Tag Manager (GTM), Adobe Launch, Tealium, Celebrus, third-party libraries, or custom scripts, these event-driven methods let you trigger actions based on specific events occurring on your domain or integrated platforms. |
| Enhance analytics tracking | `onLoad` in one event method that Securiti is offering, and it is triggered after the SDK is fully loaded, letting you execute logic that depends on the SDK's availability. You can use it to manage data subject consent, interact with the features of SDK, retrieve consent data, and customize the user experience. This ensures that actions, such as analytics tracking or consent-related configurations, occur reliably after the SDK becomes fully operational. |

## Advanced integration best practices guide

While the Cookie Consent SDK is highly flexible, improper use or incorrect integrations can lead to unexpected issues. Integrating the Cookie Consent SDK effectively requires understanding key design principles and best practices. This guide outlines essential considerations for maintaining compliance, ensuring stability, optimizing performance, and to avoid potential pitfalls while integrating the SDK into your workflows.

The following tables cover fundamental integration principles and a set of best practices to help you achieve a seamless and efficient implementation:

| Consideration | Description |
| --- | --- |
| Event-driven integration | You can write listeners to respond to consent-related events without overriding the SDK's core functionality. This ensures seamless integration into your workflows. |
| Immutable consent workflow | Securiti does not let you modify or interrupt cookie consent workflows. - The Implicit Consent Workflow runs continuously and cannot be stopped. - Securiti does not let you alter or replace consent data. - You can listen to consent events, but Securiti does not let you inject new consent data into the workflow. > [!NOTE] > **Note** > > The SDK maintains compliance and consistency by preventing unauthorized modifications to consent workflows. |
| Customer-driven design | Securiti's Cookie Consent SDK is built based on customer feedback and real-world usage patterns. It balances flexibility with compliance and security. |
| Integration responsibility | Our Cookie Consent SDK is powerful, but improper integration can cause issues. You must follow the advanced integration best practices guide to ensure stability and compliance. |

Use the following table to review best practices for effectively implementing the SDK, especially when initializing integrations and using third-party tools with advanced event-driven methods:

| Guideline | Description |
| --- | --- |
| Respect the design of SDK | Do not alter the SDK code, manipulate or tamper with the Data Object Model (DOM), or reverse-engineer its functionality. Unsupported modifications can cause integration failures. |
| Use the SDK as intended | The SDK is designed for managing consent workflows. Misuse may lead to compliance issues. |
| Optimize callbacks | Minimize excessive callbacks to improve page performance. Aggregate callbacks by event type for efficiency. |
| Avoid infinite recursion | Implement logic to prevent infinite recursion loops, which can degrade performance. |
| Conduct thorough testing before deploying to production | Conduct thorough QA testing before deployment to ensure smooth functionality. |
| Integration ownership | You are responsible for implementing and maintaining your integrations. Adhere to Securiti's best practices to ensure long-term reliability and stability. |
| Adhere to privacy regulations | Ensure compliance with privacy laws such as GDPR, CCPA, etc. Provide clear and data subject-friendly consent experiences. |
| Keep up with the SDK updates | Regularly update the SDK to access new features, functionalities, bug fixes, and compliance enhancements. > [!WARNING] > **Important** > > Keeping the SDK updated and adhering to best practices ensures compliance, stability, and optimal performance. |
| Handle errors gracefully | Implement error-handling mechanisms to prevent workflow disruptions. |
| Document your implementation | Maintain clear documentation to support troubleshooting, scaling, and future development. |
| Minimize third-party conflicts | Test the interactions of SDK with third-party scripts to prevent compatibility issues. |
| Monitor performance | Continuously track the performance of your domain, including load times and network requests, to identify any SDK-related latency. |

## Implementing Event Listeners in the Cookie Consent SDK

To use any event with the Cookie Consent SDK, you must integrate it within a complete script setup. Before adding event listeners such as `beforeRenderPrefCenter` or `afterRenderBanner`, you must ensure that the Cookie Consent SDK is correctly loaded.

### Key considerations

- Place event listeners after the script to ensure they are properly registered.
- Replace "// Add event listener here here" with a specific event listener.
- All event names are case-sensitive. Use them exactly as written in this help article.
- You must use the appropriate CDN value for your Securiti cloud instance based on your region such as `https://cdn-[your-securiti-instance].securiti.ai`. Use the following to see the values of all Securiti cloud instances:

| Cloud instance | Value |
| --- | --- |
| U.S. | `https://cdn-prod.securiti.ai` |
| Indonesia (Jakarta) | `https://cdn-app2.securiti.ai` |
| Canada (Montreal) | `https://cdn-app3.securiti.ai` |
| Australia (Sydney) | `https://cdn-app4.securiti.ai` |
| United Arab Emirates (UAE) | `https://cdn-app5.securiti.ai` |
| India (Mumbai) | `https://cdn-app6.securiti.ai` |
| Kingdom of Saudi Arabia (KSA) | `https://cdn-app7.securiti.ai` |
| Qatar | `https://cdn-app8.securiti.ai` |
| EU | `https://cdn-prod.eu.securiti.ai` |

> [!WARNING]
> **Important**
> 
> You must add `data-tenant-uuid` and `data-domain-uuid` for your Securiti tenant, otherwise the code snippet does not function.
> 
> You can obtain these values from the **Deployment Code** snippet located in the **Consent Code** tab of your scanned domain in the management portal.

The following example provides the correct structure, ensuring your event listeners work as expected:

```javascript
<script>
(function () {
    var s = document.createElement('script');
    s.src = 'https://cdn-prod.securiti.ai/consent/cookie-consent-sdk-loader.js';
    s.setAttribute('data-tenant-uuid', 'f262f42b-3086-44e0-b76b-589eed8b5ec8');
    s.setAttribute('data-domain-uuid', '471d094e-94dd-4a83-abba-767149ea12c1');
    s.setAttribute('data-backend-url', 'https://app.securiti.ai');
    s.setAttribute('data-skip-css', 'false');
    s.defer = true;
    // Add event listener here
    var parent_node = document.head || document.body;
    parent_node.appendChild(s);
})();
</script>
```

## Event-driven methods

The event-driven methods are grouped into eight categories, documented in the following sections. Choose the appropriate group to suit your requirements.

> [!WARNING]
> Important
> 
> All event names are case-sensitive.

### Domain Page Events

- `beforeLoad`

Triggers before the Cookie Consent SDK is initialized and loaded. It lets you make custom configurations before the SDK becomes active on your domain page.

You can use this event for the following use cases:

To use this event, you can push it to the `SecuritiDataLayer` array before the SDK is initialized.

```javascript
<!-- After adding this script, call setConsentBannerParams({uuid: <unique id> }) to set a unique ID for a customer. -->
<script>
(function () {
    var s = document.createElement('script');
    s.src = 'https://cdn-prod.securiti.ai/consent/cookie-consent-sdk-loader.js';
    s.setAttribute('data-tenant-uuid', 'f75254cd-f75257cd-2139-4c4d-9k68-79659dc2f02a');
    s.setAttribute('data-domain-uuid', '85d0768e-d727-4dc5-84f6-feb6af78402s');
    s.setAttribute('data-backend-url', 'https://app.securiti.ai');
    s.setAttribute('data-skip-css', 'false');
    s.defer = true;
    window.SecuritiDataLayer = window.SecuritiDataLayer || [];
    SecuritiDataLayer.push([
        'beforeLoad',
        (bareSdk) => {
            console.log('Before Load Event Triggered');
            if (!bareSdk.isConsentGiven()) {
                console.log('Consent was not given previously');
            }
            // Below settings are Optional
            bareSdk.setUuid('123e4567-e89b-12d3-a456-426614174000');
            bareSdk.setLanguage('fr');
            bareSdk.setLocation('US');
        }
    ]);
    var parent_node = document.head || document.body;
    parent_node.appendChild(s);
})();
</script>
```

| Key Method | Description |
| --- | --- |
| `isConsentGiven()` | Returns a Boolean indicating whether the data subject has already given consent. |
| `setUuid(uuid)` | Lets you assign a universally unique identifier (UUID) for the data subject. |
| `setLanguage(isoCode)` | Lets you set the language for the cookie banner using the ISO language codes such as `en`, `fr`, `ja`, etc. |
| `setLocation(isoCode)` | Lets you set the location for consent purposes using the ISO country codes such as `AU`, `US`, `IN`, etc. |
  - When you want to adjust settings dynamically based on session data or data subject context.
  - When you want to apply custom configurations, such as setting `UUID`, language, or location.
  - When you want to run pre-initialization logic tailored to your needs.
- `onConfigLoad`

This event fires after the domain and cookie configurations are successfully loaded. It lets you execute custom logic once the cookie configuration of your domain becomes available.

You can use this event for the following use cases:

```javascript
<script>
window.SecuritiDataLayer = window.SecuritiDataLayer || [];
SecuritiDataLayer.push([
    'onConfigLoad',
    (configSdk) => {
        console.log('Config Loaded Event Triggered');
        if (configSdk.isConsentGiven()) {
            console.log('User has already given consent');
        }
        const consentDetails = configSdk.getConsent();
        console.log('Consent Details:', consentDetails);
        const categories = configSdk.getCategories();
        console.log(' Categories:', categories);
        const bannerVersion = configSdk.getBannerVersion();
        console.log('Banner Version:', bannerVersion);
        const sdkVersion = configSdk.getSdkVersion();
        console.log('SDK Version:', sdkVersion);
    }
]);
</script>
```

| Key Method | Description |
| --- | --- |
| `isConsentGiven()` | Returns a Boolean indicating whether the data subject has already given consent. |
| `getConsent()` | Lets you retrieve the consent details, including category-specific consents. |
| `getCategories()` | Lets you retrieve the list of all available cookie categories. |
| `getBannerVersion()` | Lets you retrieve the cookie banner version. |
| `getSdkVersion()` | Lets you retrieve the SDK version. |
  - When you want to access data subject consent preferences or cookie categories.
  - When you want to perform actions based on loaded configuration data.
- `onLoad`

Triggers after the SDK has fully loaded. You can use this event to manage data subject consent or interact with the features of the SDK once it is ready. This event is primarily used to interact with the SDK once it is fully operational, letting you display cookie banners, manage consent preferences, or retrieve SDK-related details.

You can use this event for the following use cases:

```javascript
<script>
window.SecuritiDataLayer = window.SecuritiDataLayer || [];
SecuritiDataLayer.push([
    'onLoad',
    (sdk) => {
        console.log('SDK Loaded Event Triggered');
    }
]);
</script>
```
  - When you want to perform actions that require the SDK to be fully loaded.
  - When you want to access and manage data subject consent data.
- `onConsentGiven`

Triggers when a data subject explicitly provides consent and also when implicit consent is set up. It lets developers execute custom logic, such as logging consent, updating UIs, or triggering third-party integrations, immediately after consent is granted.

This event provides a reliable way to:

You can listen to the `onConsentGiven` event by pushing it to the `SecuritiDataLayer` array, which serves as the event queue for the Cookie Consent SDK.

```javascript
window.SecuritiDataLayer = window.SecuritiDataLayer || [];
SecuritiDataLayer.push([
    'onConsentGiven',
    (sdk, consent) => {
        // Use the consent object as shown below
        /*
          {
            "category": {
                "Advertising": "denied",
                "Analytics & Customization": "denied",
                "Essential": "granted",
                "Performance & Functionality": "denied",
                "Social Networking": "denied"
            }
          }
        */
        // Add your custom logic here
    }
]);
```
  - React to data subject's consent in real-time.
  - Update application state or UI components based on the new consent preferences.
  - Trigger third-party analytics, tracking, or marketing tools only when data subject consent is provided.

### Cookie Banner Events

This section outlines key events triggered by the cookie consent banner, letting you implement custom logic based on data subject interactions. These events let you manage consent preferences and customize the experience according to your specific requirements.

| Event | Description |
| --- | --- |
| `beforeRenderBanner` | Triggers just before the cookie banner is rendered. This event lets developers modify configurations or perform custom logic before the cookie banner is displayed. ```javascript window.SecuritiDataLayer = window.SecuritiDataLayer \|\| []; SecuritiDataLayer.push([ 'beforeRenderBanner', (sdk) => { // Add your custom logic here before rendering the cookie banner console.log('beforeRenderBanner Event Triggered'); } ]); ``` |
| `afterRenderBanner` | Triggers immediately after the cookie banner is rendered. This event lets developers execute custom logic or track post-render actions after the cookie banner is displayed. ```javascript window.SecuritiDataLayer = window.SecuritiDataLayer \|\| []; SecuritiDataLayer.push([ 'afterRenderBanner', (sdk) => { // Add your custom logic here } ]); ``` |
| `onClickPreferencesLink` | Triggers when the data subject clicks the **Cookie Preferences** link on the cookie banner. This event lets you perform custom actions before the cookie preference center is displayed. ```javascript window.SecuritiDataLayer = window.SecuritiDataLayer \|\| []; SecuritiDataLayer.push([ 'onClickPreferencesLink', (sdk) => { // Add your custom logic here } ]); ``` |
| `onImplicitConsent` | Triggers when implicit consent is assumed based on the configuration. Using this event, you can handle scenarios where consent is inferred according to the compliance policy. ```javascript window.SecuritiDataLayer = window.SecuritiDataLayer \|\| []; SecuritiDataLayer.push([ 'onImplicitConsent', (sdk) => { // Add your custom logic here } ]); ``` |
| `onClickAccept` | Triggers when the data subject clicks the **Accept** or **Allow** button on the cookie banner. ```javascript window.SecuritiDataLayer = window.SecuritiDataLayer \|\| []; SecuritiDataLayer.push([ 'onClickAccept', (sdk) => { // Add your custom logic here } ]); ``` |
| `onClickDismiss` | Triggers when the data subject clicks the **Dismiss** or **Decline** button on the cookie banner. ```javascript window.SecuritiDataLayer = window.SecuritiDataLayer \|\| []; SecuritiDataLayer.push([ 'onClickDismiss', (sdk) => { // Add your custom logic here } ]); ``` |
| `onCloseBanner` | Triggers when the cookie banner is closed, either by the data subject dismissing it or through automatic closure. You can use this event for actions you want to perform after the cookie banner is closed. ```javascript window.SecuritiDataLayer = window.SecuritiDataLayer \|\| []; SecuritiDataLayer.push([ 'onCloseBanner', (sdk) => { // Add your custom logic here } ]); ``` |

### Cookie Preference Center Events

This section describes events triggered when data subjects interact with the cookie preference center. These events let you apply custom logic based on data subject choices, helping you maintain compliance and provide greater control over privacy preferences.

| Event | Description |
| --- | --- |
| `beforeRenderPrefCenter` | Triggers just before the consent preference center is rendered and displayed to the data subject. It lets developers execute custom logic, modify configurations, or adjust settings before the preference center appears. ```javascript window.SecuritiDataLayer = window.SecuritiDataLayer \|\| []; SecuritiDataLayer.push([ 'beforeRenderPrefCenter', (sdk) => { // Add your custom logic here } ]); ``` |
| `afterRenderPrefCenter` | Triggers immediately after the consent preference center is rendered and displayed to the data subject. It lets developers perform actions or customizations once the preference center is fully loaded and visible, such as adjusting the layout, populating dynamic content, or initializing tracking scripts. ```javascript window.SecuritiDataLayer = window.SecuritiDataLayer \|\| []; SecuritiDataLayer.push([ 'afterRenderPrefCenter', (sdk) => { // Add your custom logic here } ]); ``` |
| `onClickSavePreferences` | Triggers when the data subject clicks the **Save Preferences** button in the cookie preference center. It lets developers execute custom logic or track the data subject's actions immediately after they save their consent preferences. ```javascript window.SecuritiDataLayer = window.SecuritiDataLayer \|\| []; SecuritiDataLayer.push([ 'onClickSavePreferences', (sdk) => { // Add your custom logic here } ]); ``` |
| `onCategoryToggled` | Triggers when a data subject toggles their consent for a specific cookie category or data processing activities, such as switching from consented to decline or vice versa. It lets developers react in real-time to the data subject's interaction with consent preferences, enabling dynamic adjustments to functionality or UI. ```javascript window.SecuritiDataLayer = window.SecuritiDataLayer \|\| []; SecuritiDataLayer.push([ 'onCategoryToggled', (sdk, categoryName, toggleState) => { // Add your custom logic here // toggleState can be either true or false } ]); ``` |
| `onCategoryChange` | Triggers whenever there is a change in the data subject's consent status for any cookie category or data processing activities. It lets developers monitor and react to updates in consent preferences, whether the data subject grants or revokes consent for specific cookie categories. ```javascript window.SecuritiDataLayer = window.SecuritiDataLayer \|\| []; SecuritiDataLayer.push([ 'onCategoryChange', (sdk, categoryName, oldState, newState) => { // Add your custom logic here // oldState, newState can be either granted or denied } ]); ``` |
| `onCategoryConsented` | Triggers when a data subject explicitly provides consent for a specific cookie category or data processing activities. It lets developers perform actions based on the data subject's decision to allow certain cookie categories, such as enabling specific services or triggering related features. ```javascript window.SecuritiDataLayer = window.SecuritiDataLayer \|\| []; SecuritiDataLayer.push([ 'onCategoryConsented', (sdk, categoryName) => { // Add your custom logic here } ]); ``` |
| `onCategoryDeclined` | Triggers when a data subject explicitly declines consent for a specific cookie category or data processing activities. It lets developers handle scenarios where a data subject opts out of particular cookie categories such as **Analytics**, **Advertising**, **Social Networking**, etc., and customize the behavior accordingly. ```javascript window.SecuritiDataLayer = window.SecuritiDataLayer \|\| []; SecuritiDataLayer.push([ 'onCategoryDeclined', (sdk, categoryName) => { // Add your custom logic here } ]); ``` |
| `onClosePrefCenter` | Triggers when the data subject closes the cookie preference center, either by clicking the close button or through other mechanisms such as a timeout or automatic closure. It lets developers execute custom actions or handle specific logic after the preference center is closed. ```javascript window.SecuritiDataLayer = window.SecuritiDataLayer \|\| []; SecuritiDataLayer.push([ 'onClosePrefCenter', (sdk) => { // Add your custom logic here } ]); ``` |

### Global Privacy Control (GPC) Events

| Method | Description |
| --- | --- |
| `onGpcDetected` | Triggers when the Global Privacy Control (GPC) signal is detected in the web browser of the data subject or site visitor. It lets you respond immediately to the visitor's privacy preferences. ```javascript window.SecuritiDataLayer = window.SecuritiDataLayer \|\| []; SecuritiDataLayer.push([ 'onGpcDetected', (sdk) => { // Add your custom logic here } ]); ``` |
| `onGpcCategoryConflict` | Triggers when there is a conflict between the GPC signal and the consent preferences for a specific cookie or data category. It lets you handle discrepancies between the GPC signal and data subject consent. ```javascript window.SecuritiDataLayer = window.SecuritiDataLayerr \|\| []; SecuritiDataLayer.push([ 'onGpcCategoryConflict', (sdk, categoryName, toggleState) => { // Add your custom logic here // toggleState is Boolean. Use values such as true or false } ]); ``` |

### Google Consent Mode (GCM) Event

`onGCMConsentGiven`

Triggers when Google Consent Mode (GCM) is enabled and the data subject provides consent. This lets developers execute custom logic based on granted consent, such as enabling analytics or advertising tools in compliance with GCM.

```javascript
window.SecuritiDataLayer = window.SecuritiDataLayer || [];
SecuritiDataLayer.push([
    'onGCMConsentGiven',
    (sdk, gcmConsent) => {
        // Add your custom logic here
        // gcmConsent structure example:
        /*
        {
          "ad_storage": "denied",
          "ad_user_data": "denied",
          "ad_personalization": "denied",
          "analytics_storage": "denied",
          "functionality_storage": "denied",
          "personalization_storage": "denied",
          "security_storage": "granted"
        }
        */
    }
]);
```

### API Interface Methods

- `onReady(callback)`

Lets you execute the callback once the Cookie Consent SDK is fully loaded and becomes available. You can use this to ensure that the SDK is ready before interacting with it.

```javascript
SecuritiSDK.onReady(sdk => {
    // Perform actions with the SDK
    // Refer to the "SDK Object" section below for a full list of interface methods
});
```
- `registerEvent(eventName, callback)`

Lets you register a callback to listen for Cookie Consent SDK events after the SDK has been executed.

> [!WARNING]
> **Important**
> 
> You must use this method after the SDK has loaded, not before.

**Webpage Script Order:**

> [!WARNING]
> **Important**
> 
> - Events such as `beforeLoad`, `onConfigLoad`, and `onLoad` do not work with `registerEvent()` because they execute during script load as mentioned in step [2](/v1/docs/using-the-advanced-event-driven-methods) of the **Webpage Script Order**.
> - For the complete list of `eventName` values, refer to the [Domain Page Events section](/v1/docs/using-the-advanced-event-driven-methods).
> - `callback` is the method to execute when the event is triggered.

```javascript
SecuritiSDK.registerEvent(
  'onCategoryChange',
  (sdk, categoryName, oldState, newState) => {
      if (newState === 'denied') {
        console.log(`${categoryName} is denied`);
      } else {
        console.log(`${categoryName} is granted`);
      }
  }
);
```
  1. Use `SecuritiDataLayer` before the consent script execution, because `registerEvent()` is unavailable at this point.
  2. Load the Cookie Consent SDK, which adds the `registerEvent()` method to the page.
  3. Use `registerEvent()` after loading the Cookie Consent SDK. `SecuritiDataLayer` event may not work as expected after this point.

### Single Page Application (SPA) Methods

You can handle the behavior of the cookie banner configured with Implicit Consent on single-page applications (SPAs) with the SPA methods. In SPAs, when website visitors or data subjects click a tab or select an element, the webpage does not refresh, and the URL stays the same, even though the content updates. As a result, the cookie banner, which is set to close when the webpage changes or reloads, does not disappear because there is no page reload.

To handle this behavior in SPAs, Securiti lets you use the following approaches:

| Approach | Description |
| --- | --- |
| Developer notification | Securiti lets the developers invoke a callback within navigation change handlers to notify the SDK of routing events. |
| Routing detection | Developers can enable the **SPA mode** flag in the SDK to detect navigation events triggered by `History.pushState`, `History.replaceState`, `popstate`, or URL hash changes. |

Use the following table to understand the methods available for the aforementioned approaches:

| Method | Description |
| --- | --- |
| Integration with Navigation Change Handlers | Lets you customize options more extensively. ```javascript const YourNavigtationHandler = (page) => { // Add this code on your Navigation Handler window.SecuritiSDK && window.SecuritiSDK.onReady(sdk => { if (sdk.isConsentGiven()) { sdk.closeBanner(); } }); // Add your custom logic here. For example // setActivePage(page); }; ``` |
| Integration with `History.pushState` router or URL hash router | Lets you seamlessly handle the cookie banner transitions once you enable the SDK mode flag. > [!WARNING] > **Important** > > You must add the following code snippet before the Cookie Consent SDK (JavaScript snippet). ```javascript // Add this code snippet just before Consent SDK window.SecuritiDataLayer = window.SecuritiDataLayer \|\| []; SecuritiDataLayer.push([ 'beforeLoad', bareSdk => bareSdk.enableSPA() ]); ``` |

### SDK Object Methods

### 

#### 

- 

#### 

#### 

#### 

#### 

#### 

- 

#### 

|  |  |
| --- | --- |
|  |  |
|  |  |

#### 

Use the following table to identify the most appropriate SDK Object method for your use case from the event-driven methods above.

| Method | Description |
| --- | --- |
| `isConsentGiven()` | Returns a Boolean indicating whether the data subject has already given consent. ```javascript SecuritiSDK.onReady(sdk => { let given = sdk.isConsentGiven(); }); ``` |
| `getConsent()` | Lets you retrieve the details of the current consent record, including cookie category-specific consents. ```javascript SecuritiSDK.onReady(sdk => { let consent = sdk.getConsent(); console.log(consent); }); ``` |
| `getCategoryConsent(categoryName)` | Returns the consent state value for a specific cookie category name. For instance, values such as `granted`, `denied`, `not_available`. ```javascript SecuritiSDK.onReady(sdk => { let state = sdk.getCategoryConsent('Analytics'); console.log(state); }); ``` |
| `getCategories()` | Returns the cookie categories object of the cookie banner. ```javascript SecuritiSDK.onReady(sdk => { let categories = sdk.getCategories(); categories.forEach(category => { console.log(`${category.name}, ${category.disable_opt_out}, ${category.base_category}`); }); }); ``` |
| ​`getCookiesByCategory()` | Returns all cookies associated with a specific cookie category. ```javascript SecuritiSDK.onReady(function(sdk) { const cookies = sdk.getCookiesByCategory("advertisement"); console.log(cookies); }); ``` |
| `showBanner()` | Lets you display the cookie banner. ```javascript SecuritiSDK.onReady(sdk => { if (!sdk.isConsentGiven()) { sdk.showBanner(); } }); ``` |
| `closeBanner()` | Lets you close and hide the cookie banner. ```javascript SecuritiSDK.onReady(sdk => { sdk.closeBanner(); }); ``` |
| `showPreferenceCenter()` | Lets you display the cookie preference center. ```javascript SecuritiSDK.onReady(sdk => { sdk.showPreferenceCenter(); }); ``` |
| `closePreferenceCenter()` | Lets you close and hide the cookie preference center. ```javascript SecuritiSDK.onReady(sdk => { sdk.closePreferenceCenter(); }); ``` |
| `changeLanguage(isoCode)` | Lets you change the language of the cookie banner and preference center. For the list of all supported languages, see [Cookie consent banner translations](/v1/docs/cookie-consent-banner-translations). ```javascript SecuritiSDK.onReady(sdk => { // Change display language to French. sdk.changeLanguage('fr'); }); ``` |
| `acceptAll()` | Lets you submit consent by accepting all cookie categories. ```javascript SecuritiSDK.onReady(sdk => { sdk.acceptAll(); }); ``` |
| `rejectAll()` | Lets you submit consent by rejecting all cookie categories except the Essential cookie category, which is required for the basic functioning of the domain. ```javascript SecuritiSDK.onReady(sdk => { sdk.rejectAll(); }); ``` |
| `getBannerVersion()` | Lets you retrieve the cookie banner version. ```javascript SecuritiSDK.onReady(sdk => { let bannerVersion = sdk.getBannerVersion(); }); ``` |
| `getSdkVersion()` | Lets you retrieve the SDK version. ```javascript SecuritiSDK.onReady(sdk => { let sdkVersion = sdk.getSdkVersion(); }); ``` |
| `getDefaultConsentState()` | Lets you derive the cookie category states based on the compliance type of the cookie banner. For instance: - The state for **Essential** cookie categories is always **granted**. - For **Non-essential** cookie categories: - In **Opt-in** cookie banners, the state is **denied**. - In **Opt-out** cookie banners, the state is **granted**. > [!NOTE] > **Note** > > This method also respects Global Privacy Control (GPC) cookie category exclusions. For instance, in an Opt-out compliance type cookie banner, the excluded cookie categories are denied, while the remaining cookie categories are granted. ```javascript SecuritiSDK.onReady(sdk => { let defaultState = sdk.getDefaultConsentState(); console.log(defaultState); }); ``` **Outputs** ```javascript //For an Opt-in compliance type cookie banner { "category": { "Essential": "granted", "Advertising": "denied", "Analytics & Customizations": "denied", "Performance & Functionality": "denied", "Social Networking": "denied" } } //For an Opt-out compliance type cookie banner { "category": { "Essential": "granted", "Advertising": "granted", "Analytics & Customizations": "granted", "Performance & Functionality": "granted", "Social Networking": "granted" } } ``` For an example of using the `getDefaultConsentState()` method in a GTM integration, see [this section](/v1/docs/using-the-advanced-event-driven-methods). |

### Sending consent states to Google Tag Manager (GTM)

You can use the `getDefaultConsentState()` method to send the default cookie category states to the GTM data layer. This example demonstrates how to implement a basic GTM integration with Securiti's Cookie Consent SDK.

> [!WARNING]
> **Important**
> 
> This is a sample implementation to illustrate how consent data can be passed to GTM. You can modify this based on your specific GTM setup or integration needs.

To send consent states to GTM:

1. Create the following two **data layer variables** in GTM:

![DataLayerVariables.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-fc6a8ed1-81ce-f0c2-3282-1e5a259871e5.png)
  - `cookieCategory`
  - `cookieCategoryState`
2. Create a trigger in GTM of type **Custom Event** with the event name set to `consentGiven`, as shown below.

This trigger is fired when the consent data is pushed to the GTM data layer.

![ConsentGivenEvent.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-30b16b9a-ac9c-4c2c-50cb-d701ae178815.png)
3. (Optional) Create a tag for analytics.
  - You can configure this tag to fire when consent is given for a specific cookie category. For instance, fire **Google Analytics** only when `cookieCategory` equals **analytics** and `cookieCategoryState` equals **granted**.

![Analytics-Tag.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-83ce3c85-3b7c-1c8c-2650-68a4f15d2296.png)
4. Create a tag of type **Custom HTML** to load the Securiti SDK and push consent data. For instance, use the following custom HTML code:

> [!CAUTION]
> **Warning**
> 
> You must not use the following code as-is; it is provided solely for illustrative purposes to demonstrate what can be done.
> 
> ```javascript
> <script>
> function sendConsentGivenToDataLayer(consent) {
>     if (consent && consent['category']) {
>         var keys = Object.keys(consent['category']);
>         for (var i = 0; i < keys.length; i++) {
>             var category = keys[i];
>             var state = consent['category'][category];
>             dataLayer.push({
>                 'event': 'consentGiven',
>                 'cookieCategory': category,
>                 'cookieCategoryState': state
>             });
>         }
>     } else {
>         console.log('Consent is not available, sendConsentGivenToDataLayer failed', consent);
>     }
> }
> window.SecuritiDataLayer = window.SecuritiDataLayer || [];
> var alreadySentOnInit = false;
> // Triggered when the user gives consent
> window.SecuritiDataLayer.push([
>     'onConsentGiven',
>     function(sdk, consent) {
>         alreadySentOnInit = true;
>         sendConsentGivenToDataLayer(consent);
>     }
> ]);
> // Triggered on every page load
> window.SecuritiDataLayer.push([
>     'onLoad',
>     function(sdk) {
>         if (alreadySentOnInit) {
>             return; // Already handled
>         }
>         alreadySentOnInit = true;
>         const consent = sdk.isConsentGiven()
>             ? sdk.getConsent()
>             : sdk.getDefaultConsentState(); // Send default state if no consent yet
>         sendConsentGivenToDataLayer(consent);
>     }
> ]);
> // Load the Consent SDK
> (function () {
>     var s = document.createElement('script');
>     s.src = 'https://cdn-prod.securiti.ai/consent/cookie-consent-sdk-loader.js';
>     s.setAttribute('data-tenant-uuid', 'b9157866-8d40-43b0-8009-e7c5f7342b6c');
>     s.setAttribute('data-domain-uuid', '55dcae51-3b31-4a61-af55-a2bwr0b0f808');
>     s.setAttribute('data-backend-url', 'https://app.securiti.ai');
>     s.setAttribute('data-skip-css', 'false');
>     s.defer = true;
>     (document.head || document.body).appendChild(s);
> })();
> </script>
> ```

![Consent-SDK-Tag.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-22d0a288-ac0f-4100-c508-7a2d64bab3a1.png)

#### 

#### 

The Global Privacy Control (GPC) is a browser-based global opt-out tool that lets the Internet users signal their opt-out consent settings to websites, advertisers, and publishers on the world wide web. Some global privacy laws, such as the CPRA, require covered entities to mandatorily detect and honor users’ GPC signal. The Cookie Consent Management module lets you configure cookie banners and preference centers with GPC to ensure detection of the GPC signals on the web browsers of your data subjects to honor their opt-out cookie preferences
