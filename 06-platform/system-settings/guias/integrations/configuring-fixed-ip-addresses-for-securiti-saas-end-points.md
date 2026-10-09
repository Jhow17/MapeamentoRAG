---
title: "Configuring fixed IP addresses for Securiti SaaS end points"
slug: "configuring-fixed-ip-addresses-for-securiti-saas-end-points"
updated: 2025-10-31T13:39:02Z
published: 2025-11-03T06:11:41Z
canonical: "helpcenter.securiti.ai/configuring-fixed-ip-addresses-for-securiti-saas-end-points"
area: platform
modulo: system-settings
tipo: guia
data_captura: 2026-10-08
---

# Configuring fixed IP addresses for Securiti SaaS end points

You can restrict traffic leaving your network boundary and entering Securiti’s SaaS instances (for example from pods and elastic pods or REST/GraphQL API integrations) by using fixed IP addresses instead of allow-listing by URL.

Use the addresses in the table below in your proxies and firewalls. See [Pod Prerequisites](/v1/docs/securiti-pods-and-elastic-pods) for a complete list of URLs that a pod or elastic pod must be able to access for correct operation.

> [!NOTE]
> **Note**
> 
> Configuring these fixed IP addresses only controls access to the Securiti UI, and doesn't apply to other hosts that our pods access, such as packages.securiti.ai and the various .amazonaws.com hosts.

| Production instance | Endpoint | IP address |
| --- | --- | --- |
| U.S. Cloud | - `app.securiti.ai` - `dbaas.securiti.ai` | - `3.33.255.181` - `15.197.226.17` |
| `edc.app.securiti.ai` | - `99.83.154.190` - `75.2.75.41` |
| `wf-mt.app.securiti.ai` | - `99.83.192.141` - `13.248.185.49` |
| EU Cloud | - `app.eu.securiti.ai` - `dbaas.eu.securiti.ai` | - `13.248.146.34` - `76.223.10.152` |
| `edc.app.eu.securiti.ai` | - `13.248.157.18` - `76.223.17.131` |
| `wf-mt.app.eu.securiti.ai` | - `3.33.157.145` - `13.248.203.29` |
| U.S. GCP Cloud | - `app1.securiti.ai` - `dbaas1.securiti.ai` | `130.211.15.136` |
| `wf-mt.app1.securiti.ai` | `34.117.180.251` |
| `edc.app1.securiti.ai` | `34.149.178.111` |
| Indonesia Cloud (Jakarta) | - `app2.securiti.ai` - `dbaas2.securiti.ai` | - `15.197.177.4` - `99.83.174.152` |
| `edc.app2.securiti.ai` | - `75.2.80.61` - `35.71.139.160` |
| `wf-mt.app2.securiti.ai` | - `75.2.24.0` - `35.71.162.135` |
| Canada Cloud (Montreal) | - `app3.securiti.ai` - `dbaas3.securiti.ai` | - `3.33.247.163` - `15.197.223.53` |
| `edc.app3.securiti.ai` | - `13.248.237.13` - `99.83.252.143` |
| `wf-mt.app3.securiti.ai` | - `75.2.30.3` - `99.83.173.145` |
| Australia Cloud (Sydney) | - `app4.securiti.ai` - `dbaas4.securiti.ai` | - `75.2.95.27` - `99.83.242.162` |
| `edc.app4.securiti.ai` | - `13.248.177.10` - `99.83.131.159` |
| `wf-mt.app4.securiti.ai` | - `52.223.22.58` - `99.83.129.186` |
| United Arab Emirates (UAE) Cloud | - `app5.securiti.ai` - `dbaas5securiti.ai` | - `75.2.112.22` - `76.223.121.184` |
| `edc.app5.securiti.ai` | - `13.248.249.42` - `76.223.78.161` |
| `wf-mt.app5.securiti.ai` | - `99.83.204.142` - `52.223.10.36` |
| India Cloud (Mumbai) | - `app6.securiti.ai` - `dbaas6.securiti.ai` | - `75.2.73.43` - `99.83.227.174` |
| `edc.app6.securiti.ai` | - `99.83.199.138` - `75.2.111.48` |
| `wf-mt.app6.securiti.ai` | - `99.83.153.136` - `15.197.164.36` |
| Kingdom of Saudi Arabia (KSA) Cloud | `app7.securiti.ai` | - `34.54.157.214` |
| State of Qatar Cloud | `app8.securiti.ai` `http://dbaas8.securiti.ai/` | - `34.54.165.185` |
| `app8.securiti.ai` | - `34.8.52.253` |

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>

## Related

- [Configuring generic SAML single sign-on](/configuring-single-sign-on-configuring-generic-saml-single-sign-on.md)
- [Configuring single sign-on](/system-settings-configuring-single-sign-on.md)
- [Configuring private cloud storage](/system-settings-configuring-private-cloud-storage.md)
