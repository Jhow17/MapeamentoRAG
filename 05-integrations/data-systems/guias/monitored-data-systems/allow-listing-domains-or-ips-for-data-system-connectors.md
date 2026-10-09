---
title: "Allow-listing domains or IPs for data system connectors"
slug: "allow-listing-domains-or-ips-for-data-system-connectors"
updated: 2025-10-30T18:58:44Z
published: 2025-11-03T06:13:35Z
canonical: "helpcenter.securiti.ai/allow-listing-domains-or-ips-for-data-system-connectors"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Allow-listing domains or IPs for data system connectors

To ensure secure communication between Securiti and data systems, you must allowlist specific IP addresses in your firewall or security settings. This requirement varies depending on the deployment type (PCS, SaaS-hosted, or self-hosted) and involves two types of IP addresses:

> [!NOTE]
> **Note**
> 
> IP addresses must be allowlisted for both self-hosted and Securiti cloud connectors, for a secure connection.

- Fixed/static IPs
- NAT IPs

### Allowlisting NAT IP addresses

In the Security Group of your SaaS data systems or private cloud storage in AWS, GCP, or Azure, add the following IP addresses to the allow list depending on the production endpoint you are using.

- The public IP addresses of any Securiti pods running in your environment.
- The appropriate Securiti Network Address Translation (NAT) IP addresses from the table below to permit the Securiti cloud to access your data system hosted on private cloud storage, SaaS, or self-hosted.

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

### Allowlisting Fixed or static IP addresses

For private cloud storage or self-hosted data system connectors, if you have deployed Securiti pods or elastic pods in your environment, add the following in the allow list of your network firewall, proxy, or WAF:

- The IP addresses or a globally resolvable name of the object storage service (S3 bucket, etc) for your private cloud storage.
- The URL or (preferably) the IP addresses for the appropriate Securiti Load Balancer from the table below:

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
