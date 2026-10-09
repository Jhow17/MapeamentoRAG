---
title: "Configuring cookie scanner allow-listing"
slug: "configuring-cookie-scanner-allow-listing"
updated: 2026-09-03T06:49:38Z
published: 2026-09-03T06:49:38Z
canonical: "helpcenter.securiti.ai/configuring-cookie-scanner-allow-listing"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Configuring cookie scanner allow-listing

You must allow-list the following IP addresses to permit scanning by the Securiti cookie scanner if:

- Your firewalls or WAFs are configured to block the entire AWS or Azure address ranges.
- Your website is configured to challenge with captchas to eliminate or suppress bot traffic.

| Production instance | Endpoint | NATIP address |
| --- | --- | --- |
| U.S. Cloud | `app.securiti.ai` | - `54.68.117.210` - `44.232.248.202` - `35.155.217.93` |
| EU Cloud | `app.eu.securiti.ai` | - `54.73.208.151` - `52.18.221.170` - `52.215.125.10` |
| U.S. GCP Cloud | `app1.securiti.ai` | - `34.105.10.226` - `34.105.44.52` |
| Indonesia Cloud (Jakarta) | `app2.securiti.ai` | - `108.136.119.196` - `108.137.87.223` - `108.136.196.30` |
| Canada Cloud (Montreal) | `app3.securiti.ai` | - `3.97.59.2` - `15.222.204.203 ` - `3.97.187.88` |
| Australia Cloud (Sydney) | `app4.securiti.ai` | - `13.239.141.172` - `3.104.48.164` - `54.252.203.75` |
| United Arab Emirates (UAE) Cloud | `app5.securiti.ai` | - `3.29.154.64` - `3.29.228.59` - `3.29.219.172` |
| India Cloud (Mumbai) | `app6.securiti.ai` | - `52.66.187.150` - `3.7.77.210` - `13.127.253.194` |
| Kingdom of Saudi Arabia (KSA) Cloud | `app7.securiti.ai` | - `34.166.62.175` - `34.166.60.3` |
| State of Qatar Cloud | `app8.securiti.ai` | - `34.18.56.161` - `34.18.83.173` |
