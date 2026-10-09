---
title: "What's New in 1.146"
slug: "what-s-new-in-1-146"
updated: 2026-08-12T08:35:16Z
published: 2026-08-12T08:35:16Z
canonical: "helpcenter.securiti.ai/what-s-new-in-1-146"
area: geral
modulo: whats-new
tipo: guia
data_captura: 2026-10-08
---

# What's New in 1.146

## Try the New DSPM Demos for GCP

Four simple controls are all it takes to start your DSPM journey with security on GCP. This includes: knowing how data gets scanned, how sensitive information is flagged, which policies apply and what do the results or findings look like. Our newly launched interactive demos for GCP covers all of them. See these controls in action in our setup before you even get started. It's a low-friction way to get familiar with our Data Command Center’s capabilities before you configure anything. When you need more context, the related Help Center article is linked and can be accessed directly from the demo section.

[Explore the DSPM demos for GCP](/latest/docs/interactive-demos)

![New interactive demos feature with navigation buttons and progress indicators displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[IaaS Cloud] Try the New DSPM Demos for GCP.png)

## Cookie Scans That Follow Real User Journeys

Say you run a cookie scan against a marketing site and it comes back clean. Then a data subject fills out the demo form, clicks through to the pricing page, and three new trackers fire that the scan never saw. Cookie scanner now accepts user journey recordings from Google Chrome DevTools. Record interactions like form entries, button clicks, and page navigation, upload the file, and the scanner replays those actions during a scan. Cookies and trackers that only appear after site visitor interaction show up in the results, and you get a clearer picture of what actually fires across a real session.

[See how to use user journey recordings in cookie scans](/latest/docs/recording-user-journeys-for-cookie-domain-scans)

![Dashboard displaying JSON data, security status, and various metrics for monitoring.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Cookie Scans That Follow Real User Journeys.jpg)

## Validate Consent Authenticity with Double Opt-In Email Confirmation

A data subject submits their preferences through your universal preference center, but the email address has a typo, or worse, belongs to someone else entirely. Although the consent record gets created, it doesn't actually represent the person it claims to. Double opt-in email confirmation closes that loop. Universal preference centers can now send a verification email, and preferences stay inactive until the data subject confirms ownership from their inbox. Invalid sign-ups drop off before they enter your consent records, and the preferences you do activate are tied to a real, reachable person.

[Read more about double opt-In email verification](/latest/docs/configuring-a-double-opt-in-preference-center)

![User preferences submission leads to email verification and confirmation process.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Support double opt in consent via email.jpg)

## Bring Consent Into Your Unity Apps

A player taps into a Unity-built mobile game, and the consent banner kicks them out to a browser tab to pick preferences. The flow breaks, the moment is gone. Not anymore. Unity Gaming Framework support handles consent and keeps it all in-app. Now you can display consent banners and preference centers directly inside Unity-based Android and iOS apps, capture player choices, and let players manage SDK Purposes and Permissions without leaving the app. Consent handling stays consistent across native Android, iOS, Flutter, React Native, and Unity. Players get a smoother way to manage preferences, and your consent setup covers every framework you ship in.

[Learn how to integrate SDK in your Unity apps](/latest/docs/unity-sdk-integration-and-implementation-guide)

![Unity framework support for Android and iOS applications highlighted in the image.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Bring Consent Into Your Unity Apps.jpg)

## Build Templates for Your Privacy Notices

Copying structure, wording, and translations into every new privacy notice is slow and inconsistent. Small differences may creep in, and fixing them takes more time than the original work. Notice templates in Privacy Notice Management give you a reusable baseline. Now you can build a template once in the editor, with the sections, details, translations, preview included. Every notice you create from it starts from the same foundation. Less repetition, more consistency.

[Learn how to use privacy notice templates](/latest/docs/creating-and-managing-privacy-notice-templates)

![Interface showing Privacy Notice Management with options to customize content and templates.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[PNM] Templates for Privacy Notices.jpg)

## Start Privacy Notices the Way That Fits Your Needs

Your legal team already has a privacy notice in a Word file. Porting it to the platform interface from scratch means duplicating work you've already done. Now you can import it directly, whether it's a PDF, Word, or plain text — and take it from there. Or use the wizard for step-by-step guidance, pick a template, or start blank. That is, four ways to create a privacy notice, each matching a different starting point. The setup process fits how you already work, not the other way around.

[Explore more about new ways to create notices](/latest/docs/creating-a-new-privacy-notice)

![Options to create a new privacy notice using various methods are displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[PNM]All-New Privacy Notice Creation Experience.png)

## DSR Regulations Coverage Expands to PIPEDA and LFPDPPP

When a DSR falls under Canada's federal PIPEDA or Mexico's LFPDPPP, you need to know the regulation, the research behind your response, and the templates for any required notifications all available in the same place. Both regulations are now supported in the Data Subject Rights module for commercial entities. PIPEDA closes the federal gap in Canadian coverage, sitting alongside the provincial regulations already in the module. LFPDPPP adds Mexico. Both come with regulatory research summaries and notification extension templates, so federal Canadian and Mexican DSRs can be processed without working around the gap.

[See the list of supported regulations](/latest/docs/supported-jurisdictions-and-regulations-in-dsr-form)

![Map showing Canada, Mexico, and a central icon representing collaboration between them.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[DSR] Support for Mexico and canada regulation in DSR.jpg)

## Multiple Policy Owners for Shared Remediation Work

When only one person can own a policy, everyone else has to route requests through them or use shared accounts to get anything done. That bottleneck slows down remediation and creates coordination overhead that shouldn't exist. Multiple policy owners let you assign co-owners to a policy so more than one person can manage it, track results, and handle remediation tasks directly. In RBAC, the View Owned Policies permission covers co-owned policies automatically, so teams get access without needing additional permission changes every time responsibilities shift.

[Read more in docs](/latest/docs/policies)

![Data labeling interface showing file details, owner, and co-owners for HR files.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[SDI] Multiple Policy Owners for Shared Remediation Work-1.jpg)

## Expanded EDM Coverage: Amazon RDS for MySQL

Before, EDM indexing and profiling didn't cover Amazon RDS for MySQL, which meant that source either got skipped or required extra handling to fit into your sensitive data workflows. Now it's fully supported. You can create precise data indexes and profiles for Amazon RDS for MySQL the same way you would for other structured sources. Sensitive data is detected and matched more consistently, and the results hold up better across your broader data environment.

[See list of data systems supporting EDM Coverage](/latest/docs/supported-data-systems-for-exact-data-indexes)

![Illustration showing data flow between database services and email communication.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[SDI] Expanded EDM Coverage_ Amazon RDS for MySQL.jpg)

## Introducing RBAC v2 for Enterprise Data Catalog

When one person manages tags, another creates data quality checkpoints, and a third handles governance actions, built-in roles may not always cover those distinctions. RBAC V2 in Enterprise Data Catalog lets you create custom roles scoped to exactly what each job needs. Catalog assets, metadata operations, and specific actions are all configurable. Teams work within the right boundaries without waiting on permission changes every time responsibilities shift.

[Learn how default and custom roles are defined](/latest/docs/edc-rbac-permissions-and-roles)

![Enterprise Data Catalog permissions for data quality findings and expectations management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[EDC] RBAC for Enterprise Data Catalog.jpg)
