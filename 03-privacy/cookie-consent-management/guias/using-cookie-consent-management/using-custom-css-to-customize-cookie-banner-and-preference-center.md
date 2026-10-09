---
title: "Using custom CSS to customize cookie banner and preference center"
slug: "using-custom-css-to-customize-cookie-banner-and-preference-center"
updated: 2026-09-20T13:11:50Z
published: 2026-09-20T13:11:50Z
canonical: "helpcenter.securiti.ai/using-custom-css-to-customize-cookie-banner-and-preference-center"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Using custom CSS to customize cookie banner and preference center

**Scenario**

As a Data Protection Officer, you want your cookie banner to match your brand without compromising performance or accessibility. For instance, when updating your website’s design, the cookie banner should reflect the same layout and styling while remaining compliant and accessible. Custom CSS in Securiti lets you safely style cookie banner and preference center layouts using scoped class structures. This gives you full visual control while meeting privacy and security standards.

Securiti lets you implement custom CSS directly from the management portal. This functionality lets you modify the appearance of UI elements and components of your domain’s cookie banner and preference center while ensuring design integrity and compliance with security standards.

Using Securiti's custom CSS functionality lets you follow structured class systems, avoid global styles, and ensure responsiveness to deliver a seamless and compliant customization experience. This functionality ensures compliance with security standards, simplifies customization, and reduces the risk of conflicts, providing a more reliable and controlled solution than implementing custom CSS independently.

> [!NOTE]
> **Note**
> 
> - Only the following Securiti user roles in your tenant have permission to perform WRITE actions for custom CSS, while all others have READ permissions:
>   - Super Admin
>   - Org Admin
>   - Module Owner
> - When you roll back to a previous SDK version, Securiti also restores the associated custom CSS to ensure consistent cookie banner and preference center styling across your domains.

## Guidelines for implementing custom CSS

Use the table below to understand the guidelines for appropriately implementing custom CSS:

| Guideline | Description |
| --- | --- |
| Custom CSS Implementation | Securiti strongly recommends that a technical team member, such as a **front-end software development engineer (SDE)**, **web developer**, or **solution architect**, implements custom CSS. They are better equipped to follow coding best practices and maintain styling consistency. |
| Handling incorrect CSS code | If there are syntax errors or missing closing brackets in the custom CSS properties, Securiti **highlights the issue in red**, indicating incorrect syntax. This **does not affect** your live cookie banners and preference centers, which continue to render correctly. If there is an invalid selector, Securiti ignores it, ensuring that the banner renders as expected. |
| Use predefined CSS classes | Custom CSS configuration follows a structured class system to ensure styling consistency. Always reference existing **class names** to override styles instead of creating new global styles. |
| Avoiding global CSS rules | - You must not use universal selectors such as `* {}` to prevent unintended changes. - Avoid modifying base elements such as body, html, div, and span directly. - Use scoped class selectors to limit CSS changes to intended sections. |
| Maintain responsiveness | Ensure that your custom styles maintain responsiveness across different screen sizes: - Use relative units such as `em`, `rem`, `%`, etc. instead of fixed pixel values. - Implement `@media` queries to adapt styles for various devices. |
| Security and compliance considerations | - You must not use `!important` excessively, as it can lead to conflicts with existing styles. - Ensure CSS does not introduce vulnerabilities such as displaying hidden elements unintentionally. - Validate CSS before applying changes to prevent breaking portal functionalities. |
| Testing and troubleshooting | Before deploying custom styles, you must follow these best practices: - **Preview changes:** Use web browser developer tools such as **F12** or **Inspect Element** to test styles before applying them permanently. - **Check compatibility:** Ensure that the changes do not interfere with existing functionalities. - **Revert if needed:** If issues arise, revert to the default settings and reapply styles incrementally. |

## Enabling custom CSS

To enable and apply custom CSS:

1. In Securiti, open Cookie Consent Management, and choose **Cookie Consent > Domains**.
2. On the Cookie Consent Domains page, click the domain for which you want to customize the CSS of the cookie banner and preference center.
3. Click the **Consent Code & Custom CSS** tab. Securiti lands you on the Consent Code tab by default.
4. Click the **Custom CSS** tab.
5. Near the upper right corner of the page, click **Edit**.
6. Enable the **Enable Custom CSS** toggle, as shown below.

![Custom-CSS-Nav.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-70831037-4827-5b80-21c2-73011363d3c1.png)
7. On the confirmation popup, click **Confirm**, as shown below.

![Custom-CSS-Confirmation.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3bec853b-894f-6569-4863-8449c79b9379.png)

Once confirmed, a code editor appears below for you to use.
8. From the upper right corner of the code editor, click **Add Code Snippets**, and from the menu, select the relevant style selector to apply with custom CSS, as shown below.

![Add-Selectors-1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-eaec3174-fcc8-78b5-3137-ca546a6ede17.png)

![Add-Selectors-2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c1602311-d4d7-10ee-2d10-357ccde1c19c.png)

Securiti adds a CSS style selector in the code editor.
9. Apply custom CSS inside the style selector by copying and pasting CSS code from [Using custom CSS](/v1/docs/using-custom-css-to-customize-cookie-banner-and-preference-center) section, based on the UI element or component you want to override for your domain's cookie banner and preference center.

> [!NOTE]
> **Tip**
> 
> If you've added custom CSS and deployed your cookie configuration, but the styles are not appearing on the live cookie banner and preference center, try adding the `important` rule to those CSS snippets in the code editor.

## Understanding domain-specific CSS class naming

Securiti scopes all predefined CSS classes using a unique domain-based hash. For instance, `.abc123-header`. This naming convention prevents conflicts with global or external styles and ensures that your custom styles only affect Securiti components.

It works by:

- All predefined classes use a domain-specific prefix such as `.abc123-`. For instance:
  - **Header:** `.abc123-header`
  - **Button:** `.abc123-button`
  - **Footer:** `.abc123-footer`
- These hash-prefixed class names are consistent across cookie banners and other UI components.
- Securiti applies the `!important` tag to critical styles to prevent overrides.

```javascript
function generateCSSWithImportant(classes) {
                return `
                ${classes.header} {
                color: #333 !important;
                font-size: 16px !important;
                }
                ${classes.button} {
                background-color: #007BFF !important;
                border-radius: 4px !important;
                }
                ${classes.footer} {
                padding: 20px !important;
                text-align: center !important;
                }
                `;
                }
                const customCSS = generateCSSWithImportant(cssClasses);
```

> [!NOTE]
> **Note**
> 
> This approach lets you safely style your cookie banners and preference centers while reducing the risk of breaking layouts or conflicting with other website elements.

## Using custom CSS

> [!WARNING]
> **Important**
> 
> Securiti strongly recommends that a technical team member, such as a **front-end software development engineer (SDE)**, **web developer**, or **solution architect**, implements custom CSS. They are better equipped to follow coding best practices and maintain styling consistency.

Use the following table to understand what exactly you can customize with custom CSS, including the targeted UI elements and their purpose:

> [!CAUTION]
> **Warning**
> 
> If there are syntax errors or missing closing brackets in the custom CSS properties, Securiti **highlights the issue in red,** indicating incorrect syntax. This **does not affect** your live cookie banners and preference centers, which continue to render correctly.
> 
> If there is an invalid CSS selector, Securiti ignores it, ensuring that the banner renders as expected.

| What you can override | Purpose and usage |
| --- | --- |
| Cookie banner | Lets you customize the cookie banner’s text and background to match your brand identity. ```css .cc-window{ color: red !important; background-color: blue !important; } ``` |
| Cookie banner links | Lets you change the appearance of links in the cookie banner for better visibility and a consistent user experience. ```css .cc-link { color: yellow !important; } .cc-link:hover { text-decoration: none !important; color: orange !important; } .cc-message-container a { color: yellow !important; } .cc-window.cc-banner p a { color: yellow !important; } ``` |
| Cookie banner button | Lets you customize the appearance of buttons in the cookie banner, allowing for branding and user interface consistency. ```css .cc-btn { color: red !important; border-color: white !important; background-color: yellow !important; } .cc-btn:hover { color: white !important; border-color: red !important; background-color: blue !important; } ``` |
| Cookie banner close button | Lets you control the style of the close button in the cookie banner, which helps with visual consistency. ```css .cc-window .cc-close.cc-close-banner-btn { fill: red !important; } ``` |
| Cookie preference center modal | Lets you customize the modal's background color for better user experience in the cookie preference center. ```css .cmp-modal { background-color: blue !important; } .cmp-body{ color:darkgoldenrod !important; } ``` |
| Cookie preference center header | Lets you customize the header's text color in the cookie preference center, improving its visibility. ```css .cmp-modal__title { color: darkgoldenrod !important; } ``` |
| Cookie preference center IAB tabs | Lets you customize the appearance of IAB (Interactive Advertising Bureau) tabs in the cookie preference center to match your branding and ensure clarity for data subjects. ```css .cmp-horizontal-tabs__nav ul li a { background-color: white !important; } .cmp-horizontal-tabs__nav ul li a span { color: #000 !important; } .cmp-horizontal-tabs__nav ul li.is-active a { background-color: blue !important; } .cmp-horizontal-tabs__nav ul li.is-active span { color: #fff !important; } ``` |
| Cookie preference center close button | Lets you style the close button in the cookie preference center, ensuring it fits seamlessly with your app’s design and providing users with a consistent experience. ```css .cmp-modal__close { background-color: transparent !important; border: dotted !important; padding: 7px !important; } .cmp-modal__close svg{ fill: #fff !important; } @media (min-width: 768px) { .cmp-modal__close { top: 0; right: 32px; } } ``` |
| Cookie preference center description link | Lets you customize the styling of description links to align with your domain's design and ensure a smooth experience for data subjects. ```css .cmp-modal__sub-title a { text-decoration: none !important; color: red !important; } ``` |
| Cookie preference center IAB tab cookie info text | Lets you adjust the styling of cookie information text under IAB tabs, helping improve transparency and readability for data subjects. ```css .cmp-iab-purpose-tab { color: red !important; } .cmp-iab-purpose-tab p { color: red !important; } .cmp-iab-purpose-tab table { color: red !important; } .cmp-iab-purpose-tab table tr th, .cmp-iab-purpose-tab table tr td { font-size: 16px !important; line-height: 24px !important; color:#4c4e54 !important; } ``` |
| Cookie preference center cookie category tabs | Lets you modify the styling of cookie category tabs, giving you control over the visual organization in the cookie preference center for a better data subject experience. ```css .cmp-tabs__nav ul li { line-height: 18px !important; color: currentColor !important; padding: 4px 8px 4px 24px !important; font-size: 14px !important; } .cmp-tabs__nav ul li.is-active { color: #fff !important; background-color: #3974e6 !important; } ``` |
| Consented cookie category checkmark | Lets you style the checkmark next to consented cookie categories, enhancing the clarity and user experience for data subjects. ```css li.is-active .cmp-check-icon { fill: #fff !important; } ``` |
| Cookie category heading | Lets you customize the appearance of cookie category headings, making it easier for data subjects to understand and navigate their choices. ```css .cmp-tabs__title { color: #fff !important; } .cmp-tabs__title.cmp-fixed-wd-title { width: 65% !important; } ``` |
| First-party and third-party cookie description labels | Lets you adjust the labels for first-party and third-party cookie descriptions, helping to clearly communicate privacy practices to data subjects. ```css .cmp-tabs__sub-title { color: #fff !important; text-transform: uppercase !important; } ``` |
| Cookies accordion style | Lets you customize the accordion-style layout of cookie categories, improving the readability and usability of the cookie preference center for data subjects. ```css .cmp-accordion__title { color:#dedde2 !important; padding-top: 1px !important; line-height: 24px !important; padding-right: 24px !important; } .cmp-accordion__item { border-bottom: 1px solid#2e2d33 !important; } .cmp-accordion__content>.cmp-accordion .cmp-accordion__header { min-height: auto !important; } .cmp-accordion__header { background-color: transparent !important; padding: 16px 0 !important; cursor: pointer !important; } .cmp-accordion__sub-title { color:#9c98a8 !important; word-break: break-word !important; margin-top: 8px !important; padding: 3px !important; } .cmp-body:not(.cmp-multi-level) .cmp-modal .cmp-modal__body .cmp-accordion table, .cmp-body:not(.cmp-multi-level) .cmp-modal .cmp-modal__body .cmp-accordion table tbody, .cmp-body:not(.cmp-multi-level) .cmp-modal .cmp-modal__body .cmp-accordion table tr.cmp-cookie-info, .cmp-body:not(.cmp-multi-level) .cmp-modal .cmp-modal__body .cmp-accordion table th.cmp-cookie-head, .cmp-body:not(.cmp-multi-level) .cmp-modal .cmp-modal__body .cmp-accordion table td.cmp-cookie-text { background-color: transparent !important; } ``` |
| Cookie category toggle switch | Lets you style the toggle switches for each cookie category, making consent choices clearer for data subjects. ```css .cmp-switch { width: 56px !important; height: 24px !important; } .cmp-switch__label.cmp-always-active { width: auto !important; } @media (min-width: 768px) { .cmp-switch__label { top: 3px; right: 60px; } } .cmp-switch__label { font-size: 12px !important; color: #9c98a8 !important; opacity: 1 !important; line-height: 18px !important; } .cmp-switch input { width: 0 !important; height: 0 !important; } .cmp-switch.readonly input+.cmp-switch__slider { background-color: #5d5a66 !important; opacity: .5 !important; } .cmp-switch input:checked+.cmp-switch__slider { background-color: #3974e6 !important; } .cmp-switch__slider { border-radius: 30px !important; background-color: #5d5a66 !important; } .cmp-switch input:checked+.cmp-switch__slider svg { fill:#5d5a66 !important; } .cmp-switch__slider svg { fill:#fff !important; } .cmp-switch input:checked+.cmp-switch__slider svg { fill:#5d5a66 !important; } .cmp-check-icon, .cmp-expand-icon, .cmp-indeterminate-icon { width: 18px !important; fill: #fff !important; height: 18px !important; min-width: 18px !important; } ``` |
| Purpose and Vendor filter selection | Lets you customize how Purpose and Vendor filters appear, improving usability in complex consent workflows. ```css .cmp-filter { margin-left: 16px; } .cmp-dropdown-label { font-size: 14px !important; line-height: 24px !important; } .cmp-dropdown-button { width: 150px !important; font-size: 12px !important; padding: 4px 8px !important; height: 24px !important; background-color: #5d5a66 !important; } .cmp-dropdown-list { background-color:#5d5a66 !important; } .cmp-dropdown-list li { margin: 2px auto !important; font-size: 12px !important; line-height: 18px !important; border-top: 1px solid #674534 !important; } ``` |
| Box-shadow for cookie banner and outline | Lets you enhance the cookie banner’s visibility with shadow and outline styling, drawing data subjects' attention. ```css .cmp-body :focus,.cmp-body :focus-visible,.cc-window :focus,.cc-window :focus-visible,.cc-window.cc-banner :focus,.cc-window.cc-banner :focus-visible { outline-offset: 2px; box-shadow: none !important; outline: 1px solid var(--prefFocusRingColor,var(--prefButtonColor,#3974e6)) !important } ``` |
| Margin-top for accordion | Lets you fine-tune spacing above the accordion sections for better layout and readability in the cookie preference center. ```css #cmp-accordion { margin-top: 15px !important } ``` |
| Box-shadow and outline for toggles (CMP switch) | Lets you visually emphasize toggle switches with shadows or outlines, improving accessibility and interaction clarity. ```css .cmp-switch input:focus+.cmp-switch__slider { margin: 1px 0; outline-offset: 2px; box-shadow: none !important; outline: 1px solid var(--prefFocusRingColor,var(--prefButtonColor,#3974e6)) !important } ``` |
| Revoke button display | Lets you control the appearance of the Revoke Consent button, which reopens the cookie preference center. You can place it anywhere on your website, making it prominent and easy for your data subjects to find. ```css .cmp-revoke-consent { color: #00A000 !important; background-color: #FFA500 !important; padding-top: 1rem !important; padding-bottom: 1rem !important; padding-left: 2rem !important; padding-right: 2rem !important; box-shadow: 0 3px 6px 0 rgba(0, 0, 0, 0.16) !important; border-radius: .5rem !important; font-weight: 700 !important; position: fixed !important; left: 0px !important; bottom: 60px !important; max-height: 80% !important; overflow-y: auto !important; } ``` |
| Color for links in CMP modal subtitle | Lets you customize link colors in modal subtitles for consistent branding and better content visibility. ```css .cmp-modal__sub-title a { text-decoration: underline; color: var(--prefLinkColor,#1ca8dd) !important } ``` |
| Font size and line-height of CMP tabs nav elements | Lets you adjust the text size and spacing of tab labels for better readability and alignment with your brand. ```css .cmp-tabs__nav ul li { margin: 0; position: relative; border-radius: 7px; line-height: 18px; color: currentColor; text-transform: none; padding: 4px 8px 4px 24px; font-size: 14px !important; line-height: 24px !important } ``` |
| Box-shadow and outline for accordions | Lets you add visual depth or emphasis to accordion containers, improving clarity and structure in the layout. ```css .cmp-accordion .cmp-accordion__item>button:focus,.cmp-accordion .cmp-accordion__item>button:focus-visible { outline: none !important; box-shadow: none !important } .cmp-accordion__item>button:focus+.cmp-accordion__header, .cmp-accordion__item>button:focus-visible+.cmp-accordion__header { outline-offset: 2px; box-shadow: none !important; outline: 1px solid var(--prefFocusRingColor,var(--prefButtonColor,#3974e6)) !important } .cmp-accordion__header a:focus,.cmp-accordion__header a:focus-visible { box-shadow: none !important; outline: 1px solid var(--prefFocusRingColor,var(--prefButtonColor,#3974e6)) !important } ``` |
| Overflow visibility for accordion title | Lets you control how long or overflowing titles behave, helping avoid cut-off text or layout issues. ```css .cmp-accordion__title { display: flex; font-size: 14px; color: #dedde2; font-weight: 600; padding-top: 1px; line-height: 24px; padding-right: 24px; overflow: visible !important; justify-content: space-between; color: var(--prefTextColor,#dedde2) } ``` |
| Font-weight for Purpose Details tab heading | Lets you adjust the heading weight for emphasis, improving content hierarchy and visual clarity. ```css .cmp-accordion__content.purpose-details h4 { font-size: 12px; line-height: 18px; margin-top: 16px; font-weight: 500 !important } ``` |
| To hide Securiti logo | Lets you hide the default logo for a fully white-labeled experience aligned with your brand identity. ```css .cmp-undisclosed-item { display: none !important } ``` |
| Box-shadow and outline for cookie banner body (multi-level) | Lets you enhance the visual hierarchy of multi-level cookie banners, making the sections distinct and easier to navigate. ```css .cmp-body.cmp-multi-level * :focus { outline-offset: 2px; box-shadow: none !important; outline: 1px solid var(--prefFocusRingColor,var(--prefButtonColor,#3974e6)) !important } ``` |
| Color for links on cookie banner for IAB U.S national cookie banner | Lets you customize link colors, ensuring that they match your brand’s color scheme while maintaining accessibility. ```css .cmp-body .cmp-modal .cmp-us-nation-list a { text-decoration: underline; color: var(--prefLinkColor,#1ca8dd) !important } ``` |
| Box-shadow for subtabs of horizontal tab for multi-level cookie banner | Lets you add emphasis to subtabs in multi-level cookie banners, helping users quickly distinguish different sections. ```css .cmp-body.cmp-multi-level .cmp-horizontal-tabs__nav.subtabs button:focus-visible { box-shadow: none !important } ``` |
| Box-shadow and outline for CMP switch (toggle) for multi-level | Lets you style toggle switches for better visibility and user interaction in multi-level cookie banners. ```css .cmp-body.cmp-multi-level .cmp-switch input:focus+.cmp-switch__slider { outline-offset: 2px; box-shadow: none !important; outline: 1px solid var(--prefFocusRingColor,var(--prefButtonColor,#3974e6)) !important } .cmp-modal__close:focus,.cc-link.cmp-pref-link:focus, .cc-link.cmp-open-pref:focus, .cmp-body.cmp-multi-level .cmp-details-view .cmp-details-header h1:focus { outline-offset: 2px; box-shadow: none !important; outline: 1px solid var(--prefFocusRingColor,var(--prefButtonColor,#3974e6)) !important } ``` |
| Font weight for headers such as H1, H2, H3, H4 | Lets you adjust header weights to define a clear content structure and improve readability on your cookie banners and preference centers. ```css .cmp-body.cmp-multi-level .cmp-pref-included-card h2 { padding: 0; margin-top: 0; font-size: 20px; line-height: 24px; margin-bottom: 16px; font-weight: 500 !important; color: var(--prefTextColor,#4c4e54) } .cmp-body.cmp-multi-level .cmp-pref-included-card h3 { padding: 0; margin-top: 0; font-size: 16px; line-height: 24px; margin-bottom: 8px; font-weight: 600 !important; color: var(--prefTextColor,#4c4e54) } ``` |
| Margin for buttons | Lets you adjust the spacing around buttons for better alignment and a more visually appealing layout. ```css .cc-floating.cc-theme-wire .cc-compliance .cc-btn.cc-dismiss, .cc-floating.cc-theme-block .cc-compliance .cc-btn.cc-dismiss, .cc-floating.cc-theme-classic .cc-compliance .cc-btn.cc-dismiss, .cc-floating.cc-theme-wire .cc-compliance .cc-btn.cc-allow, .cc-floating.cc-theme-block .cc-compliance .cc-btn.cc-allow, .cc-floating.cc-theme-classic .cc-compliance .cc-btn.cc-allow { margin: 0 8px 8px 0 !important } .cc-floating.cc-theme-wire .cc-compliance .cc-deny, .cc-floating.cc-theme-block .cc-compliance .cc-deny, .cc-floating.cc-theme-classic .cc-compliance .cc-deny { margin: 0 8px 8px 0 !important } ``` |
| Box-shadow and outline for multi-level cookie banner items | Lets you apply distinct styles to items within multi-level cookie banners, enhancing visibility and user experience. ```css .cmp-dropdown-list li:focus,.cmp-dropdown-list li:focus-visible, .cmp-body.cmp-multi-level .cmp-dropdown-list li:focus, .cmp-body.cmp-multi-level .cmp-dropdown-list li:focus-visible { outline-offset: 1px; box-shadow: none !important; outline: 1px solid var(--prefFocusRingColor,var(--prefButtonColor,#3974e6)) !important } ``` |
| Box-shadow and outline for input checkboxes (toggles) | Lets you customize checkboxes and toggles for clearer interaction and to maintain visual consistency. ```css .cmp-dropdown-list input[type="checkbox"]:focus+label::before { outline-offset: 2px; box-shadow: none !important; outline: 1px solid var(--prefFocusRingColor,var(--prefButtonColor,#3974e6)) !important } ``` |
| Display visibility for Vendors list associated with Purposes | Lets you control the visibility of the vendors list linked to specific purposes, improving the clarity of consent options. ```css .hide-obj-legitimate-text,.hide-obj-applied,.hide-vendor,.hide-purposes-content,.hide-no-purpose-content { display: none !important } ``` |
| Font-weight for accordion header | Lets you adjust the font weight of accordion headers for better emphasis and a more organized user interface. ```css .cmp-body .cmp-modal .cmp-accordion .cmp-accordion__item table tbody tr.cmp-cookie-info th.cmp-cookie-head, .cmp-body .cmp-modal .cmp-accordion .cmp-accordion__item table tbody tr.cmp-cookie-info td.cmp-cookie-text { font-weight: 500 !important } ``` |
| Background color for below | Lets you customize the background color of elements for enhanced visual hierarchy and readability. ```css .cmp-body:not(.cmp-multi-level) .cmp-modal .cmp-modal__body .cmp-accordion table, .cmp-body:not(.cmp-multi-level) .cmp-modal .cmp-modal__body .cmp-accordion table tbody, .cmp-body:not(.cmp-multi-level) .cmp-modal .cmp-modal__body .cmp-accordion table tr.cmp-cookie-info, .cmp-body:not(.cmp-multi-level) .cmp-modal .cmp-modal__body .cmp-accordion table th.cmp-cookie-head, .cmp-body:not(.cmp-multi-level) .cmp-modal .cmp-modal__body .cmp-accordion table td.cmp-cookie-text { background-color: transparent !important } .cmp-body.cmp-multi-level .cmp-modal .cmp-modal__body .cmp-accordion table, .cmp-body.cmp-multi-level .cmp-modal .cmp-modal__body .cmp-accordion table tbody, .cmp-body.cmp-multi-level .cmp-modal .cmp-modal__body .cmp-accordion table tbody th, .cmp-body.cmp-multi-level .cmp-modal .cmp-modal__body .cmp-accordion table tbody td { background-color: transparent !important } ``` |
| Padding left for cookie text in accordion (Cookie Domain) | Lets you adjust the indentation of cookie domain text in the accordion for better alignment and aesthetics. ```css .cmp-body .cmp-modal .cmp-accordion .cmp-accordion__item table tbody tr.cmp-cookie-info td.cmp-cookie-text { padding-left: 12px !important } ``` |
| Color for tooltip paragraph in Vendors list tab, p tags in tooltip, anchor tags in cookie banner message | Lets you style the tooltips and anchor tags for a more cohesive design and clearer user interactions. ```css .cmp-body.cmp-multi-level .cmp-vendor-list .cmp-vendor-list-tile .cmp-tooltip-content p { margin: 0; font-size: 12px; line-height: 16px; color: var(--prefBodyColor,#fff) !important } .cmp-accordion__item .cmp-tooltip-content p { margin: 0; font-size: 12px; font-weight: 400; line-height: 16px; color: var(--prefBodyColor,#fff) !important } .cc-message-container a,.cc-window.cc-banner p a { color: var(--prefLinkColor,#4c4e54) !important } ``` |
| Margin left for buttons at responsive design `@media(min-width: 768px) and (max-width: 991px)` | Lets you adjust the button margins for better spacing and alignment in tablet-sized responsive views. ```css .cc-theme-edgeless.cc-window.cc-banner .cc-compliance .cc-btn+.cc-btn { margin-left: 1px !important } ``` |
| Font and color related to ATBs | Lets you modify the font and color settings for ATBs (Actionable Text Blocks), enhancing visual appeal and accessibility. ```css .atabs__list__tab span { margin-left: 4px; letter-spacing: -0.02em !important } .atabs__list__tab .cmp-category { padding: 8px 8px 8px 24px; font-size: 14px !important; line-height: 18px !important; color: currentColor !important } @media screen and (max-width: 768px) .atabs__list__tab svg { left: 20px !important } ``` |
| GPC flyout banner | Lets you customize the appearance of the GPC flyout banner, including background, header, text, links, and action button styling to match your website’s branding. ```css .f-gpc-banner { background-color: #000 !important; color: #fff !important; } ``` |
| GPC floating icon | Lets you customize the appearance of the GPC floating icon, including its visibility, size, position, and color to align with your website’s design. ```css .f-gpc-flyout { bottom: 20px !important; width: 40px !important; } ``` |
| GPC close button | Lets you customize the appearance of the close button in the GPC flyout banner, including its color and icon styling. ```css .f-gpc-banner .f-banner-close-btn { color: #fff !important; } ``` |

The Interactive Advertising Bureau (IAB) is a trade association representing advertising businesses. It develops industry standards, conducts research, and provides legal support for the online advertising industry. Cookie Consent Management module lets you configure your cookie banners and preference centers with two IAB privacy consent frameworks: the **EU TCF v2.2** and the **MSPA U.S. National**.

## Related

- [Customizing your cookie banner and preference center](/customizing-your-cookie-banner-and-preference-center.md)
- [Best practices for cookie banners and preference centers](/best-practices-for-cookie-banners-and-preference-centers.md)
- [Deploying your website cookie consent banner](/deploying-your-website-cookie-consent-banner.md)
