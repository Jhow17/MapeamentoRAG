---
title: "Universal Consent Management release notes"
slug: "universal-consent-management-release-notes"
updated: 2026-09-21T21:00:01Z
published: 2026-09-21T21:00:01Z
canonical: "helpcenter.securiti.ai/universal-consent-management-release-notes"
area: privacy
modulo: universal-consent-management
tipo: release
data_captura: 2026-10-08
---

# Universal Consent Management release notes

## 1.151

### Release updates - September 2026

#### Adding `custom_parameters` size validation for consent uploads

Securiti has introduced size validation for the `custom_parameters` field to improve the performance and stability of consent uploads through the **Consent Uploads** feature and Universal Consent APIs. This update enforces a maximum limit of **10 KB** for the `custom_parameters` field per consent record to ensure faster, more reliable processing.

For **Consent Uploads**, Securiti validates the `custom_parameters` values in uploaded consent records. If a `custom_parameters` value exceeds 10 KB in any consent record, Securiti displays an error message, as shown below.

![Consent upload dashboard showing processed and errored records with relevant job IDs.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ucm_custom_parameters(2).png)

For Universal Consent APIs, Securiti validates the `custom_parameters` value and returns an `HTTP` 400 error with an error message if the value exceeds 10 KB.

This validation applies to the following consent write endpoints:

- `/consentapi/consent_upload`
- `/consentapi/consent_upload_bulk`

For more information, see [Consent uploads via UI](/latest/docs/consent-uploads-via-ui) and [Universal Consent Management API reference](https://securiti-doc-router.securiti.ai/modules/universal-consent/apidocs/index.html).

#### Accessing Securiti’s offline plugins directly from the Chrome Web Store

Securiti now lets you download and install the **Form Extractor** web browser extension directly from the [Chrome Web Store](https://chrome.google.com/webstore/detail/djilfdbabbdlbbceebcaiipgfidkapjm) instead of downloading it in a `ZIP` file from the Universal Consent Management’s Help Center. This simplifies installation, improves extension security, and supports web browser environments that restrict manually installed extensions.

Securiti has also addressed security vulnerabilities in the **Form Extractor** extension, further improving its overall security and reliability of this extension.

For more information, see [Installing the browser plugin](/latest/docs/installing-the-browser-plugin).

---

## 1.150

### Release updates - August 2026

No updates

---

## 1.149

### Release updates - August 2026

No updates

---

## 1.148

### Release updates - July 2026

No updates

---

## 1.147

### Release updates - June 2026

No updates
