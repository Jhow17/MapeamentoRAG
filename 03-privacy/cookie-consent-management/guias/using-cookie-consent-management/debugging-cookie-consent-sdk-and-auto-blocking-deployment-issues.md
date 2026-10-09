---
title: "Debugging Cookie Consent SDK and auto-blocking deployment issues"
slug: "debugging-cookie-consent-sdk-and-auto-blocking-deployment-issues"
status: "new"
updated: 2026-09-22T20:01:35Z
published: 2026-09-22T20:01:35Z
canonical: "helpcenter.securiti.ai/debugging-cookie-consent-sdk-and-auto-blocking-deployment-issues"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Debugging Cookie Consent SDK and auto-blocking deployment issues

**Scenario**

As a web, privacy, or compliance professional, you may need to investigate deployment issues with the Cookie Consent SDK and auto-blocking on websites you manage. For instance, a cookie banner may not display the expected configuration, cookies may not be blocked or released as expected, or the consent state may not match the behavior you observe on the page. With the Cookie Consent Browser Assistant, you can **self-diagnose these issues** by inspecting your SDK configuration, consent states, auto-blocking behavior, trackers, and consent lifecycle events directly in your web browser. This helps you identify and resolve common deployment issues independently **before reaching out to Securiti Support for further assistance**.

Securiti’s [Cookie Consent Browser Assistant](https://chromewebstore.google.com/detail/veeam-securitiai-cmp-assi/bahgegefjapkefhdhafefpmkffbccgih) is a web browser extension that lets you inspect and debug how the Securiti Cookie Consent SDK and auto-blocking SDK behave on any live web page without having to write any code. You can use it to review consent status, cookie banner configuration, auto-blocking activity, compliance signals, and consent lifecycle events directly from your web browser, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Cookie-Consent-Browser-Assistant.png)

This guide explains how to install and use Cookie Consent Browser Assistant. It also explains the extension screens, tables, events, and diagnostic information available in the web browser.

## Key capabilities

Use the following table to understand what you can do with the Cookie Consent Browser Assistant:

| Capability | Description |
| --- | --- |
| Health check badge | Adds a toolbar badge that gives an at-a-glance view of the cookie consent implementation status. |
| Inspection panel | Shows live consent state, blocked resources, and compliance signals such as Global Privacy Control (GPC), Google Consent Mode (GCM), IAB Transparency and Consent Framework (IAB TCF), and Global Privacy Platform (GPP). |
| Real-time event timeline | Displays consent-related events as they occur on the webpage. |
| Banner action testing | Lets you trigger cookie banner actions such as accept, reject, and open the cookie preference center directly from the webpage without writing code. |
| Issue diagnostics | Helps identify unknown trackers, configuration mismatches, auto-blocking order issues, and cookie banner behavior differences across geolocations. |
| Additional diagnostics | Supports cookie audits, configuration drift detection, and AI-assisted diagnostic prompts to help investigate consent implementation issues more efficiently. |

## Prerequisites

Use the following table to understand the requirements and compatibility details for the Cookie Consent Browser Assistant:

| Requirement | Detail |
| --- | --- |
| Web browser | Google Chrome version 119 or later, Microsoft Edge, or Mozilla Firefox version 128 or later. |
| Website | A webpage that runs the Securiti Cookie Consent SDK. The extension badge remains grey on pages where Securiti does not detect the SDK. |
| SDK build | A recent Cookie Consent SDK build provides the most complete extension details, including auto-blocking configuration, initiator lists, and event buffers. Older SDK builds, including release 1.150 and earlier, still work, but some advanced panels may show limited information. |

> [!WARNING]
> Important
> 
> Use the Cookie Consent Browser Assistant for implementation, testing, and debugging. The extension runs only in the web browser where you install it and does not affect data subjects who do not have the extension installed. Data subjects without the extension do not experience additional data collection, performance impact, or behavior changes.

## Installing the extension

You can install the Cookie Consent Browser Assistant on Google Chrome, Microsoft Edge, or Mozilla Firefox, depending on the web browser you use to test cookie consent behavior.

### Installing on Google Chrome

To install the extension on Google Chrome:

1. On the Google Chrome Web store, navigate to the [Cookie Consent Browser Assistant](https://chromewebstore.google.com/detail/veeam-securitiai-cmp-assi/bahgegefjapkefhdhafefpmkffbccgih) listing.

> [!WARNING]
> Important
> 
> This plugin is not publicly available. You can download and install it only through the link provided in step 1 of this procedure.
2. From the upper right corner, click **Add to Chrome**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/CMP-Assistant-Add-to-Chrome(1).png)
3. On the **Add “Veeam (Securiti.AI) CMP Assistant”?** popup, click **Add extension**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/CMP-Assistant-Add-extension.png)
4. From the **Extensions** menu in Google Chrome, pin **Cookie Consent Browser Assistant** so the extension icon stays visible in the toolbar.

### Installing on Microsoft Edge

1. Download the `cookie-consent-assistant-edge.zip` file.

[](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/cookie-consent-assistant-edge.zip)cookie-consent-assistant-edge108.98 KB[](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/cookie-consent-assistant-edge.zip)
2. Save the zipped file on your local machine.
3. Unzip the file. You get a folder named `cookie-consent-assistant`. Keep all the files inside it together, don't move individual files out.
4. Open Microsoft Edge, and go to `edge://extensions`.
5. Turn on **Developer mode**.
6. Near the upper left corner, click **Load unpacked**.
7. In the file picker, select the unzipped **cookie-consent-assistant** folder and confirm. The **Cookie Consent Browser Assistant** now appears in your extensions list.
8. From the Microsoft Edge toolbar, click the **Extensions** icon.
9. Click **Show in toolbar** for **Cookie Consent Browser Assistant** so the extension icon stays visible.

To update the extension, extract the new zipped version over the old folder and replace the existing files. Then, return to `edge://extensions` and click the refresh icon on the extension card.

### Installing on Mozilla Firefox

1. Download the `cookie-consent-assistant-firefox.zip` file.

[](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/cookie-consent-assistant-firefox(1).zip)cookie-consent-assistant-firefox109.03 KB[](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/cookie-consent-assistant-firefox(1).zip)
2. Save the zipped file on your local machine.
3. Unzip the file. You get a folder named `cookie-consent-assistant-firefox`. Keep all the files inside it together, don't move individual files out.
4. In the Firefox address bar, type `about:debugging#/runtime/this-firefox` and press **Enter**.
5. Click **Load Temporary Add-on**.
6. In the file picker, select the `cookie-consent-assistant-firefox.zip` file you downloaded.
7. The add-on appears in the list and is now active.
8. Open a webpage that uses the Securiti cookie banner.
9. Look for the Cookie Consent Browser Assistant icon in the Firefox toolbar.

> [!NOTE]
> Note
> 
> A green badge means that the Cookie Consent Browser Assistant running.
10. For the full details view, open Firefox Developer Tools, or press **F12,** and click the **Veeam CMP Assistant** tab.

> [!WARNING]
> Important
> 
> This is a temporary add-on, and Firefox removes it every time you close and reopen Firefox. This is expected. To use the tool again after restarting Firefox, repeat the steps 4 to 10 above. Your computer and settings are not affected.

## Getting started

1. Open a webpage that uses Securiti’s cookie banner. The extension shows a colored badge on the toolbar icon after it detects the Cookie Consent SDK.
2. For a quick health check, click the toolbar icon to open the popup. The popup shows a status indicator, such as **OK**, **Warnings**, **Problem**, or **Not detected**. It also directs you to the **DevTools** panel for detailed diagnostics.

> [!NOTE]
> Note
> 
> The popup provides status information only. It does not include controls.
3. To inspect detailed diagnostics, open Chrome DevTools. You can press **F12**, or right-click the page, and select **Inspect**.
4. In **DevTools** panel, select the **Veeam CMP Assistant** tab.
5. Use the control buttons, such as **Accept all**, **Reject all**, and **Preference center**, to test the cookie banner behavior.
6. As you interact with the cookie banner, review the tables and event timeline to see how the consent state, auto-blocking behavior, and compliance signals update in real time.

## Understanding the toolbar badge

The badge on the extension toolbar icon shows the consent health of the current webpage.

Use the following table to understand each badge status:

| Badge | What it means |
| --- | --- |
| Grey or no badge | Securiti does not detect the Cookie Consent SDK on the webpage. There is no consent setup to inspect. |
| Green | Securiti detects the Cookie Consent SDK, the configuration loads successfully, and the webpage does not show warnings or problems. |
| Yellow | Securiti detects the Cookie Consent SDK, but the webpage has warnings. For instance, the configuration may still be loading, auto-blocking may be missing, the webpage may use a test build, or Securiti may detect unpublished trackers. |
| Red | Securiti detects a problem. For instance, the configuration might fail to load, the Cookie Consent SDK or auto-blocking script may have a placement or build issue, or a compliance check may fail. You can open the DevTools panel to review the issue. |

## Using the control buttons

The control buttons appear at the top of the **DevTools** panel. You can use them to test the cookie banner behavior and web browser actions while troubleshooting consent behavior on the webpage.

Cookie banner control buttons, such as **Accept all**, **Reject all**, **Show banner**, **Close banner**, and **Preference center**, use the Cookie Consent SDK’s public methods to simulate data subject interactions. Cookie Consent Browser Assistant does not fabricate or alter consent preferences. **Clear cookie** and **Reload** are web browser actions.

Use the following table to understand the available control buttons:

| Button | What it does |
| --- | --- |
| Accept all | Grants consent to every cookie category. |
| Reject all | Denies every optional cookie category. |
| Show banner | Shows the cookie banner again. |
| Close banner | Dismisses the cookie banner from view. |
| Preference center | Opens the cookie preference center where individual cookie categories can be turned on or off. |
| Clear cookie | Deletes the Cookie Consent SDK consent cookies from the web browser so you can test the first-visit experience again. This is a web browser action, not an SDK call. |
| Reload | Reloads the page. This is useful after you clear cookies. |

## Using the DevTools panel

The panel is organized into eleven tabs, described below.

### Overview tab

This tab shows the overall consent health of the current webpage.

#### Status

This section shows a color-coded list of checks:

- Green indicates a healthy check.
- Yellow indicates a warning.
- Red indicates a problem.
- Grey indicates that Securiti does not detect the SDK.

For details about each status message, see the [Status messages](/latest/docs/debugging-cookie-consent-sdk-and-auto-blocking-deployment-issues#status-messages) section.

#### Detection and versions

This section shows which parts of the consent stack are present on the webpage.

Use the following table to understand the fields in the Detection and versions section:

| Field | Meaning |
| --- | --- |
| Consent SDK | Shows whether the Securiti Cookie Consent SDK is loaded. |
| Config loaded | Shows whether Securiti downloaded and applied the cookie banner configuration for the domain. |
| Config not found | Shows whether the Cookie Consent SDK loaded but could not find a configuration. A Yes value usually indicates an incorrect domain ID or tenant ID. |
| Auto-Blocking | Shows whether the auto-blocking SDK is present. Auto-blocking holds back trackers until the data subject provides the required consent. |
| IAB TCF | Shows whether the IAB Transparency and Consent Framework API is present. This API supports programmatic advertising consent in the EU. |
| GPP | Shows whether the IAB Global Privacy Platform API is present. This API supports US state privacy signals. |
| GCM | Shows whether Google Consent Mode is present. Google Consent Mode passes consent to Google tags. |
| Domain UUID | Shows the unique ID that identifies this website in the Securiti configuration. |
| Tenant UUID | Shows the unique ID that identifies your tenant. |
| SDK version | Shows the version of the Cookie Consent SDK running on the webpage. |

#### Banner config

This section shows the cookie banner settings that the Cookie Consent SDK resolves for the current visit.

| Field | Meaning |
| --- | --- |
| Resolved location | Shows the geographic region that the Cookie Consent SDK applies for the current visit. This determines which cookie banner and rules appear. |
| Resolved language | Shows the language that the Cookie Consent SDK selects for the cookie banner text during the current visit. |
| Compliance type | Shows the consent model in effect, such as Opt-in, Opt-out, or Hybrid. |
| Default language | Shows the fallback language that the Cookie Consent SDK uses if the data subject's language is not available. |
| Location intelligence | Shows whether the SDK automatically detects the data subject's region. |
| Language intelligence | Shows whether the SDK automatically detects the data subject's language. |
| Default banner | Shows the cookie banner that appears when no more specific cookie banner matches the visit. |
| Available cookie banners | Shows the number and names of configured cookie banner variants. |

### Consent tab

This tab shows the data subject's recorded consent preferences, along with the identity and version details associated with the consent record.

#### Consent state

The top rows show whether Securiti has recorded consent, along with the Cookie Consent SDK and cookie banner versions.

Use the following table to understand the cookie category columns in the Consent state section:

| Column | Meaning |
| --- | --- |
| ID | Shows the internal identifier for the cookie category. |
| Category | Shows the cookie category name, such as Necessary, Analytics, or Marketing. |
| Always Active? | Shows whether the cookie category is essential and cannot be turned off. A Yes value means the cookie category is always active. |
| User's state | Shows the data subject's current recorded consent preference, such as Granted, Denied, or Not available. |
| Default state | Shows the state that the cookie banner applies before the data subject makes a choice, based on the compliance type. |

#### Identity and version

Use the following table to understand the fields in the Identity and version section:

| Field | Meaning |
| --- | --- |
| Subject ID | Shows the anonymous identifier tied to the data subject's consent record from the consent cookie. |
| Published version | Shows the version of the consent configuration that Securiti last showed to the data subject. |
| Last sync | Shows when the data subject's web browser last synced with the published configuration. If the web browser has not synced, this field shows never. |

#### Cookie (`__privaci_cookie_consents`)

This section shows the raw consent cookie stored in the web browser in a readable format. It includes the cookie category consent map, location, and consent decision timestamp.

### Cross-Domain tab

Cross-Domain Consent (CDC) shares a data subject's consent preferences across a group of related domains, so a consent preference saved on one domain can apply to other domains in the same group. This tab shows how Cross-Domain Consent is configured for the domain group and what happened during cross-domain sync for the current visit.

> [!NOTE]
> Note
> 
> If the domain does not use Cross-Domain Consent, the Cookie Consent Browser Assistant shows that Cross-Domain Consent is not configured.

#### Cross-Domain Consent

Use the following table to understand the Cross-Domain Consent fields:

| Field | Meaning |
| --- | --- |
| Enabled | Shows whether Cross-Domain Consent is enabled for the domain. |
| Group name/Group ID | Shows the Cross-Domain Consent Group that the domain belongs to. |
| Consent strategy | Shows how Securiti reconciles consent across the group. Use Latest Consent applies the most recent consent preference from any domain in the group. Use Consent After Login applies consent based on the known logged-in user and can replace previously recorded anonymous consent after the user logs in and provides consent. |
| CDN state | Shows whether Securiti has published the group configuration to the CDN. |
| Additional banner text/Banner text | Shows whether Securiti adds text to the cookie banner to explain cross-domain consent sharing, and shows the configured text. |
| Show domains in preference center | Shows whether Securiti lists the domains in the group in the cookie preference center. |

#### Category mappings

Cross-Domain Consent uses cookie category mappings to share consent across domains. Each cookie category on the current domain must map to a Standard Category ID (`sdc_id`). The Standard Category ID acts as the shared key that lets Securiti apply consent for the same standard cookie category across domains in the group.

> [!NOTE]
> Note
> 
> If a cookie category mapping is missing, Securiti cannot apply shared consent for that cookie category on the domain. Securiti’s Cookie Consent Browser Assistant flags missing cookie category mappings as issues in the **Overview** tab.

Use the following table to understand the category mapping columns:

| Column | Meaning |
| --- | --- |
| Category | Shows the cookie category on the current domain. |
| Domain category ID | Shows the cookie category ID in the domain configuration. |
| Standard Category ID (`sdc_id`) | Shows the shared standard cookie category key that the domain cookie category maps to. Securiti uses this key to share consent for the standard cookie category across the group. |

### Auto-blocking tab

This tab shows the current auto-blocking behavior on the webpage. Auto-blocking prevents trackers, such as scripts, iframes, images, and embeds, from running until the data subject provides consent for their cookie category.

#### Auto-blocking summary

Use the following table to understand the fields in the Auto-blocking summary section:

| Field | Meaning |
| --- | --- |
| Compliance type | Shows the consent model that auto-blocking is enforcing. |
| Block unpublished | Shows whether auto-blocking also blocks trackers that are not in the known tracker list, such as unpublished or unknown trackers. |
| Location | Shows the region for which auto-blocking is applying rules. |
| Non-opt-out categories | Shows the categories that are always allowed, such as essential categories. |
| Scanner found initiators | Shows the number of trackers that the domain scan discovered. |
| Custom initiators | Shows the number of trackers that you manually added to the configuration. |

> [!NOTE]
> Note
> 
> On Cookie Consent SDK builds from release 1.150 or earlier, auto-blocking still works, but the auto-blocking summary might show that the configuration is not available to the extension. The live Blocked resources table remains accurate.

#### Scanner-found initiators and Custom initiators

These sections show trackers that the Cookie Consent SDK knows about. The Scanner-found initiators table shows trackers found automatically by the domain scan. The Custom initiators table shows trackers added manually. Both tables use the same columns.

Use the following table to understand the columns in the Scanner-found initiators and Custom initiators sections:

| Column | Meaning |
| --- | --- |
| Initiator | Shows the tracker URL or identifier. |
| Type | Shows the tracker type, such as script or cookie. |
| Categories | Shows the consent categories that the tracker belongs to. |
| Status | Shows the tracker's current state on the webpage, such as blocked, allowed, or not on the webpage. The Cookie Consent Browser Assistant reads this state live from the webpage and does not infer it from consent. |

#### Blocked resources

This section shows a live table of each monitored resource on the webpage, such as a script, iframe, image, or embed. The table includes the resource URL, category, and current state, such as blocked or allowed.

> [!NOTE]
> Note
> 
> Inline items that do not have a URL show a location path and a short content preview so you can find the exact element on the webpage.

Each blocked row includes an Unblock button. Click Unblock to force-run that blocked resource as a one-time override. This helps you test what the resource does after Securiti releases it. This action does not change consent, and reloading the webpage restores normal blocking behavior. The Cookie Consent Browser Assistant logs each use as a manualUnblock entry in the event tables.

#### Unknown or unpublished trackers

This section shows resources that auto-blocking flagged as unpublished. These are trackers that auto-blocking found on the webpage but that are not in the approved configuration. Review and categorize these trackers.

#### Blocked and unblocked events

This section shows a log of each time auto-blocking blocked or released a resource, with the newest event listed first. Block entries appear in red, and unblock entries appear in green. For details about each event, see the [Auto-blocking events](/latest/docs/debugging-cookie-consent-sdk-and-auto-blocking-deployment-issues#auto-blocking-events) section.

### Cookie Audit tab

This tab compares the cookies and storage items present on the webpage with the names declared in the loaded consent configuration. If the Cookie Consent Browser Assistant observes a cookie or storage item that is not declared in the configuration, it shows the item as unknown. This can indicate configuration drift and also appears in the Overview status list.

> [!NOTE]
> Note
> 
> The **Cookie Audit** tab provides review guidance and does not confirm a violation. A webpage might include functional or infrastructure cookies that have not been classified.

Securiti’s Cookie Consent Browser Assistant can audit first-party and parent-domain cookies. It cannot detect third-party cookies set under other domains. It reads localStorage and sessionStorage from the webpage when access is available. If the webpage blocks access, the relevant rows show Not readable.

#### Config vs page

This section shows a summary of the audit for the current webpage.

Use the following table to understand the rows in the **Config vs page** section:

| Row | Meaning |
| --- | --- |
| Declared in config | Shows the number of cookie or storage names declared in the loaded configuration. |
| Unknown cookies | Shows the number of observed cookies that do not match any declared name. |
| Unknown localStorage | Shows the number of observed `localStorage` items that are not declared in the loaded configuration. If the webpage blocks access, this row shows Not readable. |
| Unknown sessionStorage | Shows the number of observed `sessionStorage` items that are not declared in the loaded configuration. If the webpage blocks access, this row shows Not readable. |
| Status | Shows `N` unknown when the Cookie Consent Browser Assistant finds configuration drift. If Cookie Consent Browser Assistant does not find configuration drift, this row confirms that all observed items are known to the configuration. |

#### Unknown cookies

This section shows cookies on the webpage that are not declared in the loaded configuration.

| Column | Meaning |
| --- | --- |
| Name | Shows the cookie name. |
| Domain | Shows the domain where the cookie is set, such as a first-party domain or parent domain. |

#### Unknown localStorage and Unknown sessionStorage

Two lists of undeclared storage keys found on the page. Each shows a single Name (key) column. If the page prevents storage access, the section notes that localStorage or sessionStorage isn't readable on this page.

> [!NOTE]
> Note
> 
> If the webpage prevents access to localStorage or sessionStorage, the Unknown localStorage and Unknown sessionStorage sections show that the storage type is Not readable on the webpage.

### GPC tab

Global Privacy Control (GPC) is a web browser-level signal that communicates a data subject's Opt-out preference, such as do not sell or share my data. This tab shows whether GPC is active and whether the Cookie Consent SDK honors the signal.

Use the following table to understand the fields in the GPC tab:

| Field | Meaning |
| --- | --- |
| GPC enabled (config) | Shows whether GPC handling is enabled in the configuration. |
| GPC detected (`onGpcDetected`) | Shows whether the Cookie Consent SDK detected and acted on a GPC signal during the current visit. |
| Browser signal (navigator.globalPrivacyControl) | Shows the raw GPC signal that the web browser sends, independent of the Cookie Consent SDK. |
| All locations | Shows whether GPC applies in every location instead of specific regions only. |
| GPC locations | Shows the specific regions where GPC applies. |

The GPC category conflicts section lists cases where a data subject's category choice contradicts the GPC signal. The section includes the Time, Category, and Toggle state columns.

### GCM tab

Google Consent Mode (GCM) passes a data subject's consent preferences to Google tags, such as Google Analytics and Google Ads tags, so they can adjust their behavior.

#### Google Consent Mode

Use the following table to understand the fields in the Google Consent Mode section:

| Field | Meaning |
| --- | --- |
| GCM enabled (config) | Shows whether Google Consent Mode is enabled in the configuration. |
| TCF support | Shows whether Google Consent Mode also passes IAB TCF signals. |
| Consent given (onGCMConsentGiven) | Shows whether the GCM consent signals have been sent to Google tags. |

#### GCM signals

This section lists each signal that the Cookie Consent SDK reports, with a value of Granted or Denied.

Use the following table to understand GCM signals:

| Signal | Meaning |
| --- | --- |
| ad_storage | Indicates consent for advertising cookies and storage. |
| analytics_storage | Indicates consent for analytics cookies and storage. |
| ad_user_data | Indicates consent to send the data subject's data for advertising. |
| ad_personalization | Indicates consent for personalized advertising. |

### IAB/GPP tab

This tab shows advertising industry consent signals in a readable format instead of displaying only raw technical strings. The Cookie Consent Browser Assistant decodes these strings in your web browser using the webpage's consent API. It does not download external data for decoding.

Use the following table to understand the consent standards shown in the IAB and GPP tab:

| Consent standard | Description |
| --- | --- |
| TCF | The IAB Transparency and Consent Framework (IAB TCF) for the EU. This section shows CMP metadata, the TC string, decoded purposes the data subject consented to, legitimate interests, special features the data subject opted into, and vendor IDs the data subject consented to. |
| GPP | The Global Privacy Platform. This section shows the header and each applicable decoded section, such as EU TCF, US national sections, and US state sections. |

> [!NOTE]
> Note
> 
> Vendor and purpose names come from the IAB Global Vendor List. Securiti’s Cookie Consent Browser Assistant does not download the Global Vendor List, so the **IAB** tab and **GPP** tab shows IDs and standard policy names instead of every vendor brand name.

Next to each raw TC or GPP string, the Cookie Consent Browser Assistant shows an optional Decode link. If you click Decode, the extension opens the public iabgpp.com decoder in a new tab.

### Tests tab

This tab includes on-demand checks that help you validate cookie banner behavior and consent enforcement. The tab currently includes two cards: Simulate location and Consent honoring.

#### Simulate location

The Simulate location card lets you test the cookie banner as a data subject from another region would see it. When you select a location, the Cookie Consent Browser Assistant reloads the webpage and re-resolves the cookie banner and auto-blocking behavior for that geography. The other tabs then reflect the simulated location.

The override applies only to a first-time data subject with no consent cookie on a domain that has Location Intelligence enabled. If a consent choice already exists, the Cookie Consent SDK uses the recorded location instead. In that case, the Clear consent & simulate button lets you test again as a first-time data subject.

A status badge under the dropdown shows whether the simulation took effect, was not applied, or Location Intelligence is off.

> [!NOTE]
> Note
> 
> The location list includes a representative set of locations. It does not include every supported location.

Use the following table to understand the available location groups:

| Group | Locations |
| --- | --- |
| US states (Opt-out) | California, Colorado, Connecticut, Virginia, and Texas. |
| Europe (Opt-in) | France, Germany, Ireland, and United Kingdom. |
| Other strict (Opt-in) | Australia, Brazil, Canada, India, and South Africa. |

#### Consent honoring

The Consent honoring card verifies whether denied-category trackers remain blocked. Auto-blocking enforces consent at webpage load and does not delete cookies. To run the test, click **Reject all**, then click **Reload**.

If a denied-category tracker still loads after the webpage reloads, the Cookie Consent Browser Assistant shows it in the Status list on the Overview tab. This check uses the live DOM state and covers the resource types that auto-blocking monitors, including scripts, iframes, images, and embeds.

If auto-blocking is not active on the webpage, the card shows that consent enforcement cannot be tested.

### Events tab

This tab shows a live, timestamped log of consent lifecycle events, with the newest event listed first. The **Detail** column shows additional context, such as the configuration file URL that loaded or whether GPC drove implicit consent.

For details about each event, see the [Consent lifecycle events](/latest/docs/debugging-cookie-consent-sdk-and-auto-blocking-deployment-issues#consent-lifecycle-events) section.

### AI tab

This tab packages the current webpage's consent diagnostics into a prompt that you can copy into your preferred AI tool.

To use the **AI** tab:

1. Select a preset question or enter your own question.

> [!NOTE]
> Note
> 
> Preset questions include:
> 
> - Diagnose compliance issues.
> - Explain the consent state.
> - Why is a resource blocked?
> - Explain the IAB TCF and GPP.
> - Explain GCM and GPC.
2. Review the live preview to confirm what the Cookie Consent Browser Assistant will copy.
3. Click Copy prompt for AI, then paste the prompt into your preferred AI tool.

> [!NOTE]
> Note
> 
> Securiti’s Cookie Consent Browser Assistant does not send AI prompt content anywhere. It only copies text to your clipboard.

The packaged prompt includes the webpage URL and configuration IDs, such as the domain UUID and tenant UUID, to provide context. It excludes the consent cookie value, raw IAB TC or GPP strings, and other identifier-like fields.

## Consent lifecycle events

The Events timeline records each step of the consent lifecycle.

Use the following table to understand consent lifecycle events:

| Event | When it fires | What it means |
| --- | --- | --- |
| `consentExists` | The moment the extension attaches to the webpage. | Records whether a consent cookie already existed when inspection began. The event shows Consent Exists if the cookie existed, or No Consent if it did not. |
| `beforeLoad` | Before the Cookie Consent SDK initializes. | Indicates that the Cookie Consent SDK is about to start. |
| `onConfigLoad` | After the cookie banner configuration downloads. | Indicates that the Cookie Consent SDK fetched this domain's cookie banner and rules configuration. The Detail column links to the exact configuration file that is loaded. |
| `onLoad` | When Cookie Consent SDK code finishes loading. | Indicates that the Cookie Consent SDK code is now present on the webpage. |
| `onReady` | When the Cookie Consent SDK is fully initialized. | Indicates that setup is complete and the cookie banner, if needed, is on screen. Controls become available from this point. |
| `onConsentGiven` | Whenever Securiti records a consent decision. | Records the authoritative consent-saved moment. This event fires when the data subject accepts, rejects, or saves consent preferences, or when Securiti applies a previously stored decision. |
| `onClickAccept` | When the data subject clicks Accept All. | Records the accept-all button click. |
| `onClickDismiss` | When the data subject closes or dismisses the cookie banner. | Records that the cookie banner was dismissed. |
| `onClickPreferencesLink` | When the data subject opens the cookie preference center. | Records that the detailed consent preferences were opened. |
| `onClickSavePreferences` | When the data subject clicks Save in the cookie preference center. | Records that custom preferences were saved. |
| `onCategoryToggled` | When the data subject turns a cookie category on or off in the cookie preference center. | Records each individual cookie category toggle before saving. |
| `onImplicitConsent` | When consent is assumed without an explicit click. | Occurs in Opt-out regions or when continued web browsing counts as consent. The Detail column notes if the event was driven by GPC Regulation. |
| `onGpcDetected` | When the web browser sends a Global Privacy Control signal. | Indicates that the Cookie Consent SDK detected the Do Not Sell or Share signal and is honoring it. |
| `onGpcCategoryConflict` | When a cookie category choice contradicts the GPC signal. | Indicates that the data subject enabled a category that GPC says should be off, or vice versa. This flags a conflict to review. |
| `onGCMConsentGiven` | When Google Consent Mode signals are sent. | Indicates that consent values, such as ad_storage and analytics_storage, were passed to Google tags. |
| `manualUnblock` | When you click an Unblock button. | Records that you manually force-ran a single blocked resource as a one-off override. |

## Auto-blocking events

Auto-blocking emits its own events. The Cookie Consent Browser Assistant shows these events in the Blocked or Unblocked events log on the **Auto-blocking** tab.

Use the following table to understand auto-blocking events:

| Event | When it fires | What it means |
| --- | --- | --- |
| `onAutoBlockingReady` | When auto-blocking finishes initializing. | Indicates that auto-blocking is active and monitoring the webpage. The event includes the configuration, such as categories and whether Securiti blocks unpublished trackers. |
| `onResourceBlocked` | Each time a resource is held back. | Indicates that Securiti prevented a script, iframe, image, or embed from running because the data subject has not granted consent for its cookie category. The event includes the resource, resource type, categories, and blocking reason. |
| `onResourceUnblocked` | Each time a blocked resource is released. | Indicates that Securiti allowed a previously blocked resource to run because the data subject granted consent for its cookie category or because a data subject manually unblocked it. |
| `onUnpublishedResourceDetected` | When an unknown tracker is found. | Indicates that auto-blocking detected a resource that is not in the approved configuration. Securiti lists the resource in the Unknown / unpublished trackers table for review. |

Blocked resources carry a reason explaining why they were blocked.

Use the following table to understand blocked resource reasons:

| Reason | Meaning |
| --- | --- |
| `consent-declined` | The data subject actively declined the cookie category that the resource belongs to. |
| `compliance-default` | Securiti blocked the resource by default before the data subject selected a consent preference. This typically applies in Opt-in regions, where resources do not run until the data subject provides consent. |
| `unpublished` | The resource is not in the approved configuration, and block unpublished is enabled. Securiti blocks the resource as an unknown tracker. |

## Cross-Domain Consent events

When Cross-Domain Consent is active, the Cookie Consent SDK emits events during each step of the cross-domain sync process. The Cookie Consent Browser Assistant shows these events in the Runtime log on the Cross-Domain Consent tab and in the main Events timeline.

Use the following table to understand Cross-Domain Consent events:

| Event | When it fires | What it means |
| --- | --- | --- |
| `onCdcSyncStart` | A cross-domain sync begins. | The Cookie Consent SDK starts reconciling the data subject's consent with the Cross-Domain Consent Group. The event details show the sync path, such as seed, same-user, cross-user, or background, and what triggered the sync. |
| `onCdcSyncSkipped` | The sync is skipped early. | The Cookie Consent SDK does not run the sync because there is no consent to sync yet or because the last sync happened recently. |
| `onCdcServerStatus` | The Cookie Consent SDK fetches the group's stored consent. | The server returns the latest known consent for the data subject across the Cross-Domain Consent Group, including the number of categories and whether consent exists. |
| `onCdcConsentApplied` | Shared consent is applied. | The Cookie Consent SDK writes consent from the Cross-Domain Consent Group to the web browser so the data subject does not need to provide consent again. |
| `onCdcConsentSkipped` | Shared consent is not applied. | The Cookie Consent SDK does not apply server consent because it was already applied, the local consent preference is newer, no items matched, or some categories are not mapped. |
| `onCdcConsentedItemIgnored` | A consented server cookie category is ignored. | The Cookie Consent SDK cannot use a consented cookie category from the server because it has no Standard Category ID or no matching local category. This event does not mean that Securiti dropped a cookie. |
| `onCdcStitch` | The Cookie Consent SDK posts a cross-user link. | The Cookie Consent SDK links anonymous consent to the known user after login so the consent can follow the user across the group. |
| `onCdcStitchSkipped` | The Cookie Consent SDK skips the cross-user link. | The Cookie Consent SDK does not need to link consent because the logged-in user already has stored consent or because a different user just logged in. |
| `onCdcCookiesReset` | Consent cookies are cleared. | A different known user logged in, so the Cookie Consent SDK clears the previous user's consent cookies and shows the cookie banner again. |
| `onCdcSyncComplete` | The sync finishes. | The Cookie Consent SDK completes the cross-domain sync for the current visit. |

## Status messages

Use the following table to understand each **Status** message on the **Overview** tab, its related toolbar badge color, and the recommended action.

| Level | Message | What to do |
| --- | --- | --- |
| Green | Consent SDK ready. | No action required. The Cookie Consent SDK is loaded and working. |
| Green | Auto-Blocking active. | No action required. Auto-blocking is blocking trackers until the data subject provides the required consent. |
| Green | Google Consent Mode enabled/IAB TCF present. | No action required. Securiti detects the configured consent signal. |
| Green | Cross-Domain Consent enabled, all categories mapped (N domain(s) in the group) | No action required. Cross-domain consent sharing is configured correctly. |
| Grey | Securiti Cookie Consent SDK not detected on this webpage. | This is expected on webpages that do not use the Cookie Consent SDK. If you expect the Cookie Consent SDK to load on this webpage, confirm that the SDK loader script is present. |
| Yellow | Consent SDK loaded and configured, but not ready yet, banner controls unavailable for a moment. | This message usually appears during startup and should clear on its own. |
| Yellow | Consent SDK detected but not ready, config still loading. | This message is usually temporary. If it remains visible, the configuration might be failing to load. |
| Yellow | Consent SDK is in Test Mode, loaded against staging or preview, not production. | No action is required during testing. Before go-live, turn off the staging flag and use the production build. |
| Yellow | SDK CSS is skipped, the site is using its own banner styles. | No action is required if you intentionally use custom cookie banner styles. |
| Yellow | Auto-Blocking SDK not detected. | If you use auto-blocking, confirm that the auto-blocking script is installed on the webpage. |
| Yellow | Auto-Blocking is using the Test build, not the production build. | Switch auto-blocking to the production build before go-live. |
| Yellow | N unpublished or unknown tracker(s) detected. | Review these trackers on the **Auto-blocking** tab and categorize them. |
| Yellow | N cookie(s), localStorage, or sessionStorage item(s) observed on the page aren't declared in the loaded consent configuration. | Review the items on the Cookie Audit tab. Then, run a domain scan in the Admin Portal to classify them and republish the configuration. |
| Yellow | Consent changed this session, but the page hasn't reloaded yet, so Auto-Blocking still reflects the state from the previous load. | Reload the webpage to apply the updated consent preference. Existing cookies are not deleted. |
| Yellow | Google Consent Mode is enabled, but no Google tag (GTM or gtag.js) was detected on the page. | Confirm that the Google tag is deployed on the webpage. If the tag loads later through a tag manager, confirm that the container is live. |
| Red | Consent SDK config not found (`COOKIE_SDK_CONFIG_NOT_FOUND`), check the domain / tenant UUID. | Check the domain UUID and tenant UUID in the SDK loader script. The IDs might be incorrect, or the domain might not be configured. |
| Red | Auto-Blocking is not the first script, N script(s) load before it. | Move the auto-blocking script so it is the first script on the webpage. Scripts that load before auto-blocking cannot be blocked. |
| Red | Auto-Blocking script must be placed inside <head>. | Move the auto-blocking script into the webpage `&lt;head&gt;` and place it before other scripts. |
| Red | Build mismatch: Consent SDK and Auto-Blocking builds don't match. | Make sure the Cookie Consent SDK and auto-blocking use the same build type. For instance, both must use Test builds or both must use Production builds. |
| Red | A GCM or TCF configuration validation message (for example, the google_consent_defaults script isn't loaded, or a TCF stub is loaded while IAB EU is disabled). | Review the Google Consent Mode or IAB TCF configuration. For instance, confirm that the `google_consent_defaults` script loads when required and that IAB EU settings match the TCF stub configuration. |
| Red | Consent SDK loader is embedded N times on this page. It must be included only once. Duplicate loads re-initialize the SDK and can double-fire events and re-render the banner. | Remove the duplicate Cookie Consent SDK loader script. Duplicate SDK loaders can reinitialize the SDK, trigger duplicate events, or render the cookie banner more than once. |
| Red | Auto-Blocking script is embedded N times on this page. It must be included only once. Duplicate Auto-Blocking scripts re-run interception and can conflict. | Remove the duplicate auto-blocking script. Duplicate auto-blocking scripts can rerun interception logic and cause conflicts. |
| Red | N non-essential tracker(s) are firing before consent in an opt-in region. | Review auto-blocking placement and initiator categorization so non-essential trackers remain blocked until the data subject provides consent. |
| Red | N tracker(s) are loading despite the visitor denying their cookie categories. | Investigate why the denied-category resource still loads. Verify auto-blocking placement and initiator categories. |
| Red | The banner is configured with a less strict compliance type than the detected location requires. | Update the compliance type for that location to meet or exceed the required consent model. |
| Red | The detected location requires honoring a universal opt-out (GPC) signal, but GPC isn't enabled or configured for that location. | Enable GPC handling and include the detected location in the GPC configuration. |
| Red | N non-essential category/ies) are granted by default in an opt-in banner. | Set the default state of non-essential categories to denied in the cookie banner configuration. |
| Red | Cross-Domain Consent is enabled but has no category mappings. | Add category-to-Standard-Category ID (`sdc_id`) mappings for this domain on the Cross-Domain Consent tab. |
| Red | Cross-Domain Consent: N cookie categor(y/ies) have no Standard Category (`sdc_id`) mapping. | Map the remaining cookie categories to a Standard Category ID so Securiti can apply shared consent on this domain. |

## Privacy and data handling

The Cookie Consent Browser Assistant does not make network requests on its own. It reads only the information that the webpage and the Cookie Consent SDK make available in your web browser.

The cookie banner control buttons use the Cookie Consent SDK's public methods to perform visitor-equivalent actions. Clear cookie and Reload are standard web browser actions. The extension does not fabricate or alter stored consent preferences of the data subject. The AI tab only copies text to your clipboard. For details about what the copied prompt includes and excludes, see the [AI tab](/latest/docs/debugging-cookie-consent-sdk-and-auto-blocking-deployment-issues#ai-tab) section.

The only outbound action available in the extension is the optional Decode link on the **IAB** tab and **GPP** tab. If you click this link, Securiti opens a public decoder in a new tab.

## Troubleshooting

Use the following table to troubleshoot common issues in the Cookie Consent Browser Assistant:

| Issue | Resolution |
| --- | --- |
| The badge stays grey. | Securiti does not detect the Cookie Consent SDK on the webpage, or the SDK has not loaded yet. Confirm that the loader script is present, then reload the page. |
| The Securiti CMP Assistant tab does not appear in DevTools. | Close and reopen DevTools after installing or reloading the extension. Make sure DevTools is open for the web browser tab that you want to inspect. |
| The auto-blocking summary says the configuration is not exposed, but resources are blocked. | The website may use an older Cookie Consent SDK build, such as release 1.150 or earlier. Auto-blocking still works, but the extension may not show the full configuration summary. The live Blocked resources table remains accurate. |
| Tables are empty right after the page loads. | Some data appears only after the Cookie Consent SDK is ready or after the data subject interacts with the cookie banner. Use the control buttons or reload the webpage, then review the tables again. |
| The extension does not show the latest version after you unzip a new version. | Extract the new version over the existing folder and replace the files. Then, go to `chrome://extensions`, click the reload icon on the extension card, and reload the webpage. |

The Global Privacy Control (GPC) is a browser-based global opt-out tool that lets the Internet users signal their opt-out consent settings to websites, advertisers, and publishers on the world wide web. Some global privacy laws, such as the CPRA, require covered entities to mandatorily detect and honor users’ GPC signal. The Cookie Consent Management module lets you configure cookie banners and preference centers with GPC to ensure detection of the GPC signals on the web browsers of your data subjects to honor their opt-out cookie preferences

Google Consent Mode (GCM) is a functionality that allows website owners to adjust how their Google services behave based on the consent preferences of their data subjects. When a data subject opts in or out of cookies for advertising or analytics, Consent Mode dynamically adapts, ensuring that Google's tools comply with the data subject's choices. Essentially, it enables websites to respect user consent for cookies while still providing valuable data insights and advertising capabilities in a privacy-focused manner

The Interactive Advertising Bureau (IAB) is a trade association representing advertising businesses. It develops industry standards, conducts research, and provides legal support for the online advertising industry. Cookie Consent Management module lets you configure your cookie banners and preference centers with two IAB privacy consent frameworks: the **EU TCF v2.2** and the **MSPA U.S. National**.

The Transparency and Consent Framework (TCF) is a voluntary consent standardization protocol tool developed by the IAB Europe. It facilitates publishers, vendors, and consent management platforms (CMPs) to comply with certain provisions of the ePrivacy Directive and the GDPR.

The Global Privacy Platform (GPP) is a protocol designed by the Interactive Advertising Bureau (IAB) Tech Lab to streamline and standardize the transmission of consumer consent choice signals from websites and applications to IAB enrolled providers. The framework enables user consent signals to be communicated throughout the digital ad supply chain

Under an Opt-in consent banner compliance type, the app's non-essential SDKs remain inactive until a mobile app user explicitly grants consent. Only strictly necessary SDKs (which are essential for basic functioning of the app) are active by default. This approach aligns with privacy regulations such as GDPR, which require explicit consent before accessing data or storing information on a mobile app user’s device.

Under an Opt-out consent banner compliance type, the mobile app's SDKs are active by default. However, mobile app users can visit the consent preference center to withdraw their consent and Opt-out of optional SDK usage. This approach is less strict than Opt-in compliance type and is common in jurisdictions with less stringent privacy laws.

Under a hybrid compliance type, data subjects can manage both opt-in and opt-out consent within the same jurisdiction, depending on the type of cookie and applicable laws. You can configure default consent states for different cookie categories, such as setting sensitive data cookies to **Declined** and others to **Granted**. This ensures compliance with varying consent requirements under different privacy laws.

## Related

- [Resolving cookie categorization conflicts in auto-blocking](/resolving-cookie-categorization-conflicts-in-auto-blocking.md)
- [Cookie Consent Management terminologies](/cookie-consent-management-terminologies.md)
- [Automatically blocking scripts from dropping cookies](/automatically-blocking-scripts-from-dropping-cookies.md)
- [Using Cross-Domain Consent Groups to sync consent across domains](/using-cross-domain-consent-groups-to-sync-consent-across-domains.md)
- [Configuring Google Consent Mode](/configuring-google-consent-mode.md)
- [Configuring the GPC consent framework and flyout](/configuring-the-gpc-consent-framework-and-flyout.md)
- [Configuring an IAB EU TCF v2.3 cookie consent banner](/configuring-an-iab-eu-tcf-v23-cookie-consent-banner.md)
