---
title: "Advanced cookie banner scripting"
slug: "advanced-cookie-banner-scripting"
updated: 2026-03-09T21:04:05Z
published: 2026-03-09T21:04:05Z
canonical: "helpcenter.securiti.ai/advanced-cookie-banner-scripting"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Advanced cookie banner scripting

You can modify the cookie consent banner JavaScript snippet to:

- Set the unique ID for a page visitor.
- Set language overrides for specific URLs.
- Open the cookie preference center.

To show the cookie preferences center:

- Add the following code just after the banner JavaScript snippet to use the `showConsentPreferencesPopup` function:

```javascript
<!-- You may style the button by overriding class "cmp-revoke-consent" -->
<button class="cmp-revoke-consent" 
onclick="showConsentPreferencesPopup()">Revoke Consent</button>
```

### For domains using Manual and Automatic SDK deployment options

Use the following procedure to set a **unique ID** or to set **language overrides** if you are using either **Manual** or **Automatic SDK deployment** option for you domain(s):

1. Replace the standard JavaScript snippet with this one depending upon your region:

> [!WARNING]
> **Important**
> 
> You must add `data-tenant-uuid` and `data-domain-uuid` for your Securiti tenant, otherwise the code snippet does not fetch cookies and cookie categories.
  1. Use the following snippet for the **U.S.** region.

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
    s.addEventListener('load', function() {
        // window.setConsentBannerParams({ . . . });
    });
    var parent_node = document.head || document.body;
    parent_node.appendChild(s);
})()
</script>
```
  2. Use the following snippet for **Jakarta**.

```javascript
<script>
(function () {
    var s = document.createElement('script');
    s.src = 'https://cdn-app2.securiti.ai/consent/cookie-consent-sdk-loader.js';
    s.setAttribute('data-tenant-uuid', 'f262f42b-3086-44e0-b76b-589eed8b5ec8');
    s.setAttribute('data-domain-uuid', '471d094e-94dd-4a83-abba-767149ea12c1');
    s.setAttribute('data-backend-url', 'https://app2.securiti.ai');
    s.setAttribute('data-skip-css', 'false');
    s.defer = true;
    s.addEventListener('load', function() {
        // window.setConsentBannerParams({ . . . });
    });
    var parent_node = document.head || document.body;
    parent_node.appendChild(s);
})()
</script>
```
  3. Use the following snippet for **Montreal**.

```javascript
<script>
(function () {
    var s = document.createElement('script');
    s.src = 'https://cdn-app3.securiti.ai/consent/cookie-consent-sdk-loader.js';
    s.setAttribute('data-tenant-uuid', 'f262f42b-3086-44e0-b76b-589eed8b5ec8');
    s.setAttribute('data-domain-uuid', '471d094e-94dd-4a83-abba-767149ea12c1');
    s.setAttribute('data-backend-url', 'https://app3.securiti.ai');
    s.setAttribute('data-skip-css', 'false');
    s.defer = true;
    s.addEventListener('load', function() {
        // window.setConsentBannerParams({ . . . });
    });
    var parent_node = document.head || document.body;
    parent_node.appendChild(s);
})()
</script>
```
  4. Use the following snippet for **Sydney**.

```javascript
<script>
(function () {
    var s = document.createElement('script');
    s.src = 'https://cdn-app4.securiti.ai/consent/cookie-consent-sdk-loader.js';
    s.setAttribute('data-tenant-uuid', 'f262f42b-3086-44e0-b76b-589eed8b5ec8');
    s.setAttribute('data-domain-uuid', '471d094e-94dd-4a83-abba-767149ea12c1');
    s.setAttribute('data-backend-url', 'https://app4.securiti.ai');
    s.setAttribute('data-skip-css', 'false');
    s.defer = true;
    s.addEventListener('load', function() {
        // window.setConsentBannerParams({ . . . });
    });
    var parent_node = document.head || document.body;
    parent_node.appendChild(s);
})()
</script>
```
  5. Use the following snippet for the **United Arab Emirates (UAE)**.

```javascript
<script>
(function () {
    var s = document.createElement('script');
    s.src = 'https://cdn-app5.securiti.ai/consent/cookie-consent-sdk-loader.js';
    s.setAttribute('data-tenant-uuid', 'f262f42b-3086-44e0-b76b-589eed8b5ec8');
    s.setAttribute('data-domain-uuid', '471d094e-94dd-4a83-abba-767149ea12c1');
    s.setAttribute('data-backend-url', 'https://app5.securiti.ai');
    s.setAttribute('data-skip-css', 'false');
    s.defer = true;
    s.addEventListener('load', function() {
        // window.setConsentBannerParams({ . . . });
    });
    var parent_node = document.head || document.body;
    parent_node.appendChild(s);
})()
</script>
```
  6. Use the following snippet for **Mumbai**.

```javascript
<script>
(function () {
    var s = document.createElement('script');
    s.src = 'https://cdn-app6.securiti.ai/consent/cookie-consent-sdk-loader.js';
    s.setAttribute('data-tenant-uuid', 'f262f42b-3086-44e0-b76b-589eed8b5ec8');
    s.setAttribute('data-domain-uuid', '471d094e-94dd-4a83-abba-767149ea12c1');
    s.setAttribute('data-backend-url', 'https://app6.securiti.ai');
    s.setAttribute('data-skip-css', 'false');
    s.defer = true;
    s.addEventListener('load', function() {
        // window.setConsentBannerParams({ . . . });
    });
    var parent_node = document.head || document.body;
    parent_node.appendChild(s);
})()
</script>
```
  7. Use the following snippet for **Kingdom of Saudi Arabia (KSA)**.

```javascript
<script>
(function () {
    var s = document.createElement('script');
    s.src = 'https://cdn-app7.securiti.ai/consent/cookie-consent-sdk-loader.js';
    s.setAttribute('data-tenant-uuid', 'f262f42b-3086-44e0-b76b-589eed8b5ec8');
    s.setAttribute('data-domain-uuid', '471d094e-94dd-4a83-abba-767149ea12c1');
    s.setAttribute('data-backend-url', 'https://app6.securiti.ai');
    s.setAttribute('data-skip-css', 'false');
    s.defer = true;
    s.addEventListener('load', function() {
        // window.setConsentBannerParams({ . . . });
    });
    var parent_node = document.head || document.body;
    parent_node.appendChild(s);
})()
</script>
```
  8. Use the following snippet for **Qatar**.

```javascript
<script>
(function () {
    var s = document.createElement('script');
    s.src = 'https://cdn-app8.securiti.ai/consent/cookie-consent-sdk-loader.js';
    s.setAttribute('data-tenant-uuid', 'f262f42b-3086-44e0-b76b-589eed8b5ec8');
    s.setAttribute('data-domain-uuid', '471d094e-94dd-4a83-abba-767149ea12c1');
    s.setAttribute('data-backend-url', 'https://app6.securiti.ai');
    s.setAttribute('data-skip-css', 'false');
    s.defer = true;
    s.addEventListener('load', function() {
        // window.setConsentBannerParams({ . . . });
    });
    var parent_node = document.head || document.body;
    parent_node.appendChild(s);
})()
</script>
```
  9. Use the following snippet for the **E.U.** region.

```javascript
<script>
(function () {
    var s = document.createElement('script');
    s.src = 'https://cdn-prod.eu.securiti.ai/consent/cookie-consent-sdk-loader.js';
    s.setAttribute('data-tenant-uuid', 'f262f42b-3086-44e0-b76b-589eed8b5ec8');
    s.setAttribute('data-domain-uuid', '471d094e-94dd-4a83-abba-767149ea12c1');
    s.setAttribute('data-backend-url', 'https://app.eu.securiti.ai');
    s.setAttribute('data-skip-css', 'false');
    s.defer = true;
    s.addEventListener('load', function() {
        // window.setConsentBannerParams({ . . . });
    });
    var parent_node = document.head || document.body;
    parent_node.appendChild(s);
})()
</script>
```
2. Use the `window.setConsentBannerParams` method to configure and pass banner parameters. It takes an object as input:

You can combine the elements as shown in this example:

```javascript
 window.setConsentBannerParams(
  {    uuid: <unique_id>,
       overrideBannerLanguage: {
          'https://securititest.local/solutions': 'de',
          'https://securititest.local/privaci': 'fr',
  }
```

> [!NOTE]
> **Note**
> 
> When specifying a URL in the `overrideBannerLanguage` parameter, all its subpaths inherit the assigned language. For instance, if `https://securititest.local/privaci` is set to **French (fr)**, any subpath such as `https://securititest.local/privaci/test1` also uses French. You only need to specify the main path, as subpaths automatically adopt the same language.
  - To pass a unique identifier of the user:

```javascript
window.setConsentBannerParams({uuid: <unique id> })
```
  - To override banner language for specific set of URLs:

```javascript
window.setConsentBannerParams(
{overrideBannerLanguage: {
        'https://securititest.local/solutions': 'de',
        'https://securititest.local/privaci': 'fr',
 }
})
```

> [!NOTE]
> Note
> 
> To display the cookie banner in the data subject's preferred browser language, enable the
> 
> **Language** toggle located in the **Banner Intelligence** section on the left panel of the
> 
> **Customize Banner and Preference Center** tab. This setting overrides the default cookie banner language for the selected URLs, as shown below.
> 
> ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Banner-Intelligence-Language.png)
  - To override the banner location:

```javascript
window.setConsentBannerParams({ 
    overrideBannerLocation:{CustomBannerLocation:'CA#US'}
})
```

### Using the `window.registerSrtiCookieSDKEvents` custom callback method

Securiti lets you use the `window.registerSrtiCookieSDKEvents` custom callback method, which triggers when the cookie preference center is closed. You can use this custom callback method to perform actions after the cookie preference center is closed.

For instance, you can use this custom callback method if you're using a floating icon to display the cookie preference center on your domain, and your website visitors click the floating icon to manage their cookie preferences. It restores focus to the floating icon once the cookie preference center is closed. Additionally, if the visitors use accessibility tools to access the floating icon, the keyboard tabulation automatically returns to it after the cookie preference center is closed.

#### For domains that don't use strict CSP

If your domain does not use strict CSP, to use the custom callback method:

- Add the following script to your domain. The new code containing the custom callback method is **highlighted in bold** for emphasis.

```javascript
<!-- After adding this script, call setConsentBannerParams({uuid: <unique id> }) to set unique ID for a customer.  -->
<script>
(function () {
	var s = document.createElement('script');
	s.src = 'https://cdn-prod.securiti.ai/consent/cookie-consent-sdk-loader.js';
	s.setAttribute('data-tenant-uuid', 'f75254cd-f75257cd-2139-4d4c-9a68-79659dc2f02a');
	s.setAttribute('data-domain-uuid', '85d0768e-d727-4dc5-84f6-feb6af64202s');
	s.setAttribute('data-backend-url', 'https://app.securiti.ai');
	s.setAttribute('data-skip-css', 'false');
	s.defer = true;
        s.addEventListener('load', function() {
           window.registerSrtiSDKEvents('onPrefCenterClose', function() {
              // Add your custom code here.
           })
        });
	var parent_node = document.head || document.body;
	parent_node.appendChild(s);
})()
</script>
```

> [!WARNING]
> **Important**
> 
> You must add `data-tenant-uuid` and `data-domain-uuid` for your Securiti tenant, otherwise the code snippet does not work.

#### For domains that use strict CSP

If your domain enforces strict content security policies, and you have enabled the **strict CSP** on it, to use the custom callback method:

1. Add the following script to your domain:

```javascript
<script
	defer
	data-strict-csp
	data-securiti-staging-mode="true"
	data-skip-css="false"
	src="https://cdn-prod.securiti.ai/consent/cookie-consent-sdk-loader-strict-csp.js"
	data-tenant-uuid="f75254cd-2139-4d4c-9a68-79659dc2f02a"
	data-domain-uuid="85d0768e-d727-4dc5-84f6-feb6af64202s"
	data-backend-url="https://app.securiti.ai">
</script>
```

> [!WARNING]
> **Important**
> 
> You must add `data-tenant-uuid` and `data-domain-uuid` for your Securiti tenant, otherwise the code snippet does not work.
2. Add the following code snippet at the top of your JavaScript or `.js` file:

> [!NOTE]
> **Note**
> 
> Due to strict CSP guidelines, inline scripts are not allowed. You must copy this script into a `.js` file and reference it from there.

```javascript
//callback.js
var securitiSdkRef = document.querySelector("script[data-domain-uuid]")
securitiSdkRef.addEventListener('load', function() {
  window.registerSrtiSDKEvents('onPrefCenterClose', function() {
    console.log('Preference center is closed.');
  })
})
```
3. Load the JavaScript or `.js` file immediately after the Securiti SDK code by adding the following script:

```plaintext
<script src="callback.js"></script>
```

#### 

A small text file that is stored on a data subject's or website visitor's device (computer, smartphone, or tablet) by a domain (website). Cookies are used to collect information about the user's interactions with the website, such as preferences, login status, and browsing history. This information helps domains enhance user experience, perform analytics, and deliver personalized content and advertisements. Cookies can be categorized into various types, including Essential, Performance, Functionality, and targeting cookies, each serving different purposes in managing user consent and data privacy.
