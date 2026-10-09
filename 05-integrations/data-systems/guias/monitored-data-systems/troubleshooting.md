---
title: "Troubleshooting for Microsoft 365 Calendar"
slug: "troubleshooting"
updated: 2025-10-31T07:27:57Z
published: 2025-11-03T06:25:23Z
canonical: "helpcenter.securiti.ai/troubleshooting"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Troubleshooting for Microsoft 365 Calendar

**Issue:** I clicked Authenticate & Activate Connector in Securiti but got a Microsoft error “No reply address is registered for the application.”

**Resolution:** In Azure, click **Azure Active Directory > App Registrations**, then click the app registration in question. Click the link next to Redirect URIs and make sure that the redirect URI is of type Web and that the URI is one of the following:

- US Cloud: `https://app.securiti.ai/static/activateConnector.html`
- US1 Cloud: `https://app1.securiti.ai/static/activateConnector.html`
- Canada Cloud: **`https://app3.securiti.ai/static/activateConnector.html`**
- EU Cloud: `https://app.eu.securiti.ai/static/activateConnector.html`
- Indonesia Cloud: `https://app2.securiti.ai/static/activateConnector.html`
- Australia Cloud: **`https://app4.securiti.ai/static/activateConnector.html`**
- UAE Cloud: **`https://app5.securiti.ai/static/activateConnector.html`**
- Mumbai Cloud: **`https://app6.securiti.ai/static/activateConnector.html`**
- KSA Cloud: **`https://app7.securiti.ai/static/activateConnector.html`**
- Qatar Cloud: **`https://app8.securiti.ai/static/activateConnector.html`**
- Sovereign deployment: **`https://&lt;sovereign_deployment_portal_host&gt;/static/activateConnector.html`**

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>
