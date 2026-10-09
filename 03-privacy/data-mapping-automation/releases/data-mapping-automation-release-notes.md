---
title: "Data Mapping Automation release notes"
slug: "data-mapping-automation-release-notes"
updated: 2026-09-21T21:00:01Z
published: 2026-09-21T21:00:01Z
canonical: "helpcenter.securiti.ai/data-mapping-automation-release-notes"
area: privacy
modulo: data-mapping-automation
tipo: release
data_captura: 2026-10-08
---

# Data Mapping Automation release notes

## 1.151

### Release updates - September 2026

#### Resolved issue

- Fixed an issue where the Okta connector in Data Mapping Automation and Security Posture Management recognized only Okta’s US cell and did not let users specify a different cell. Customers can now provide either the Instance ID or the Instance ID along with the Okta domain. Securiti supports the following input formats:

| Input | Example |
| --- | --- |
| Instance ID only | `integrator-6647233` |
| Instance ID + Production domain | `integrator-6647233.okta.com` |
| Instance ID + EMEA domain | `integrator-6647233.okta-emea.com` |
| Instance ID + Preview/Sandbox domain | `integrator-6647233.oktapreview.com` |
| Instance ID + Gov domain | `integrator-6647233.okta-gov.com` |

---

## 1.150

### Release updates - August 2026

#### Resolved issue

- Fixed an issue where duplicate process name validation failed to detect a name with trailing whitespace (PRIV-243293).

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
