---
title: "Using a Securiti cookie consent banner on a WordPress website"
slug: "using-a-securiti-cookie-consent-banner-on-a-wordpress-website"
updated: 2025-10-30T19:48:17Z
published: 2025-11-03T06:12:47Z
canonical: "helpcenter.securiti.ai/using-a-securiti-cookie-consent-banner-on-a-wordpress-website"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Using a Securiti cookie consent banner on a WordPress website

To use the Securiti cookie consent banner on a website you maintain with WordPress, you add both the CSS and JavaScript snippets to the theme footer php file.

> [!NOTE]
> **Note**
> 
> You must have a Premium WordPress subscription. Otherwise the Theme Editor you need for this procedure is not available.

Follow this procedure:

1. If you haven't already done so, in Securiti create a cookie consent banner for the domain as described in [Building a website cookie consent banner](/v1/docs/customizing-your-cookie-banner-and-preference-center).
2. In Securiti, open the Consent Code tab for the domain.
3. In a separate browser tab, log in to WordPress and open your site’s dashboard.
4. On the left side navigation bar, choose **Appearance > Theme Editor**.
5. In the Theme Files tree near the right edge of the page, open **Theme Footer (footer.php)**.
6. Near the end of the theme footer, paste the Securiti CSS code snippet, followed by the JavaScript snippet, as shown in the screenshot and example code below.

![WordPress_example1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ac5dafef-6e1a-3e09-0212-ec576b9815f2.png)

```javascript
<!--start of cookie consent code-->

	<link rel='stylesheet' type='text/css' href='https://cdn-app.securiti.ai/consent/cookie-consent.css' />

	<script type="text/javascript" src="https://cdn-app.securiti.ai/consent/sdk-stub.js" defer></script>
	<!-- After adding this script, call setConsentBannerParams({uuid: <unique id> }) to set unique ID for a customer. -->
	<script>
		(function () {
		var s = document.createElement('script');
		s.src = 'https://cdn-app.securiti.ai/consent/cookie-consent-sdk.js';
		s.setAttribute('data-tenant-uuid', 'f262f42b-3086-44e0-b76b-589eed8b5ec8');
		s.setAttribute('data-domain-uuid', '471d094e-94dd-4a83-abba-767149ea12c1');
		s.setAttribute('data-backend-url', 'https://app.securiti.ai');
		s.defer = true;
		var parent_node = document.head || document.body;
		parent_node.appendChild(s);
		s.addEventListener('load', function() { window.initCmp(); });
	})()
	</script>

<!--end of cookie consent code-->
```
7. Click **Update File**.
8. Publish the updated website.

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>

## Related

- [Deploying your website cookie consent banner](/deploying-your-website-cookie-consent-banner.md)
