---
title: "Using a Securiti cookie consent banner on a Wix website"
slug: "using-a-securiti-cookie-consent-banner-on-a-wix-website"
updated: 2025-10-30T19:48:12Z
published: 2025-11-03T06:12:47Z
canonical: "helpcenter.securiti.ai/using-a-securiti-cookie-consent-banner-on-a-wix-website"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Using a Securiti cookie consent banner on a Wix website

To use the Securiti cookie consent banner on a website you maintain with Wix, you create two tracking tools; one for the CSS that goes in the head, and another for the Javascript code snippet that goes in the body. Follow this procedure:

1. If you haven't already done so, in Securiti create a cookie consent banner for the domain as described in [Building a website cookie consent banner](/v1/docs/customizing-your-cookie-banner-and-preference-center).
2. In Securiti, open the Consent Code tab for the domain.
3. In a separate browser tab, log in to Wix and open your site’s dashboard.
4. Go to Settings, then choose Choose **Advanced Settings > Tracking Tools**.
5. Click **+ New Tool** and from the menu choose **Custom**.
6. In the Edit Tool box, apply the following settings:

| Paste the code snippet here | Paste the Securiti CSS code from the upper box on the Consent Code tab. |
| --- | --- |
| Name | Enter a convenient name, for example “Securiti cookie consent CSS.” |
| Add Code to Pages | Configure to suit. |
| Place Code in | Choose **Head**. |
7. Click **Apply**.
8. Repeat steps 4-7, except use the following settings in the Edit Tool box:

| Paste the code snippet here | Paste the Securiti CSS code from the *middle* box on the Consent Code tab. |
| --- | --- |
| Name | Enter a convenient name, for example “Securiti cookie consent CSS.” |
| Add Code to Pages | Configure to suit. |
| Place Code in | Choose **Body - start**. |
9. Publish the updated website.

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>

## Related

- [Deploying your website cookie consent banner](/deploying-your-website-cookie-consent-banner.md)
