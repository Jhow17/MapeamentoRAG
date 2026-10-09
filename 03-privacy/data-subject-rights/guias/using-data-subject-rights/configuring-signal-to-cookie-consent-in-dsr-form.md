---
title: "Sending Do Not Sell or Share submission signals for cookie preferences"
slug: "configuring-signal-to-cookie-consent-in-dsr-form"
updated: 2026-07-16T10:44:19Z
published: 2026-07-20T21:00:00Z
canonical: "helpcenter.securiti.ai/configuring-signal-to-cookie-consent-in-dsr-form"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Sending Do Not Sell or Share submission signals for cookie preferences

**Scenario**

As a Data Privacy Officer, you handle Do Not Sell or Share(DNSoS) requests under multiple regulations. Some regulations like CPRA mandate that upon submission of Do Not Sell or Share Personal Information (DNSoS) by a Data Subject, selling or sharing of that Data Subject’s information from Customer’s website would have to be restricted. To facilitate this, upon submission of DNS or DNSoS request, a signal can be sent to cookie consent manager to turn off non-essential cookies in the same browser and device for that website. This in turn turns off any third party solutions on the website and access to data subject’s data for those third party solutions.

### Introduction

Securiti lets you send a submission signal to the browser when selected DSR types are successfully submitted. The signal is sent at the browser level and applies only to the same browser and device used to submit the request.

The submission signal acts as a trigger. A website can listen to this signal and automatically apply browser-level actions, such as turning off non-essential cookies based on the data subject’s request. The signal is sent after the DSR is submitted.

> [!NOTE]
> Note
> 
> Securiti provides a default listener script that is designed to update cookie preferences by turning off non-essential cookies in the same browser and device where the request is submitted. This script targets the cookie preferences use case by default, and you can modify it to support other browser-level actions based on your requirements.

### Usecase

#### Update cookies preferences after a Do Not Sell request is submitted

A common use case for this framework is updating cookie preferences after a data subject submits a Do Not Sell or Do Not Share request.

Without this capability, non-essential cookies can remain enabled in the browser based on prior consent. When the website listens to the submission signal, the script updates cookie preferences by turning off all non-essential cookies in the same browser, device, and domain where the request is submitted. This applies the data subject’s preference at the time of submission.

To configure this in the DSR form:

1. In Securiti open Data Subject Rights, then choose **Settings > Form Builder.**
2. Do one of the following:
  1. To create a new form, near the upper right corner of the page, click **+Add New**.
  2. To open an existing form for editing, click its card.
  3. To create a new form based on an existing one, on the card for the existing form choose **More Actions (three dots) > Clone.**
3. In the DSR Form Builder, under **Form Settings** do the following:
  1. Expand Signal to Cookie Consent section and mark **Signal to Cookie Consent to turn off non-essential cookies** checkbox.
  2. Select **Do not Sell or Share** from the **Request Type** menu.
  3. Copy the code that needs to be added to the website.

![Form submission interface highlighting cookie consent and request type options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-01-02 at 12.07.58 PM(1).png)

The submission signal is sent only for the selected request types. Next, add the copied script to your website just before the closing <body> tag.

> [!NOTE]
> Note
> 
> You must add the copied script to your website for the website to listen to the signal.

#### Prerequisites

The cookie preference use case works only when all of the following conditions are met:

- If you are using the DSR form directly, the DSR form is embedded on the website using an iframe.
- If you are using the Privacy Center, the Privacy Center that contains the DSR form and cookie preference components is embedded on the website.
- Securiti Cookie Consent is configured on the same domain as the DSR form or Privacy Center.
- The submission signal is enabled for opt-out or Do Not Sell or Share request types in the DSR Form Builder.
- The script copied from the DSR Form Builder is added to the website.
- If signaling is enabled on a universal form that is served through an embedded privacy center for DSR intake, you must add the privacy center's embeddable domains to each signaling-enabled DSR form mapped to that universal form. Otherwise, consent signals from those forms will not reach the host page.

Cross-domain setups are not supported for this use case.
