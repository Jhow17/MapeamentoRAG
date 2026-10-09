---
title: "Visualizing the data subject journey on your domain"
slug: "visualizing-the-data-subject-journey-on-your-domain"
updated: 2025-12-09T12:08:38Z
published: 2025-12-09T12:08:38Z
canonical: "helpcenter.securiti.ai/visualizing-the-data-subject-journey-on-your-domain"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Visualizing the data subject journey on your domain

The user journey diagram below shows what happens when a data subject visits your domain and interacts with the cookie banner deployed using Securiti’s Cookie Consent Management module. It walks through the basic flow, covering cookie banner display, consent detection, preference selection, and enforcement of consent choices through script behavior.

> [!NOTE]
> **Important**
> 
> This diagram shows a simplified journey and does not represent every possible path. It **does not cover** scenarios such as:
> 
> - Cookie banner dismissal by the data subject
> - GPC signal detection
> - Implicit consent flows
> - Interactions with IAB EU TCF v2.3 or IAB MSPA U.S. National cookie banners
> 
> Use this diagram to understand the core experience, but refer to your specific compliance setup for complete coverage.

Use this visual to better understand how Securiti fits into your domain's consent flow. It can support privacy reviews, documentation, and internal audits by clarifying how consent is captured and applied.

![Flowchart illustrating cookie consent process for website visitors and data subjects.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/CCM-End-User-Journey-Design.drawio.png)

The Global Privacy Control (GPC) is a browser-based global opt-out tool that lets the Internet users signal their opt-out consent settings to websites, advertisers, and publishers on the world wide web. Some global privacy laws, such as the CPRA, require covered entities to mandatorily detect and honor users’ GPC signal. The Cookie Consent Management module lets you configure cookie banners and preference centers with GPC to ensure detection of the GPC signals on the web browsers of your data subjects to honor their opt-out cookie preferences

The Interactive Advertising Bureau (IAB) is a trade association representing advertising businesses. It develops industry standards, conducts research, and provides legal support for the online advertising industry. Cookie Consent Management module lets you configure your cookie banners and preference centers with two IAB privacy consent frameworks: the **EU TCF v2.2** and the **MSPA U.S. National**.

The Transparency and Consent Framework (TCF) is a voluntary consent standardization protocol tool developed by the IAB Europe. It facilitates publishers, vendors, and consent management platforms (CMPs) to comply with certain provisions of the ePrivacy Directive and the GDPR.

The Multi-State Privacy Agreement (MSPA) serves as a contractual framework designed to aid IAB publishers, advertisers, agencies, and ad tech intermediaries. Its purpose is to facilitate compliance with distinct U.S. state privacy laws. This is achieved by sending, receiving, and honoring standardized opt-out consent signals through the GPP.
