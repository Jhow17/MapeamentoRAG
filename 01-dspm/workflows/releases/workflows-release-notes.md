---
title: "Workflows release notes"
slug: "workflows-release-notes"
updated: 2026-09-21T21:00:02Z
published: 2026-09-21T21:00:02Z
canonical: "helpcenter.securiti.ai/workflows-release-notes"
area: dspm
modulo: workflows
tipo: release
data_captura: 2026-10-06
---

# Workflows release notes

## 1.151

### Release updates - September 2026

No updates

---

## 1.150

### Release updates - August 2026

No updates

---

## 1.149

### Release updates - August 2026

#### Improved security for Function node

Securiti has further strengthened the Function node's protection against unauthorized network access, credential misuse, code injection, and other exploit attempts originating from workflow code.

> [!CAUTION]
> Warning
> 
> This update changes behavior for existing workflows. If your workflows use `helpers.requestOAuth2()`, `helpers.updateCredentialsInDb()`, `helpers.getAndUpdateRefreshToken()`, or `helpers.getUpdatedOptionsWithToken()`, you must update them, since these functions are no longer available. If your workflows use `helpers.request()` to reach internal or private IP addresses (such as `127.x`, `10.x`, `172.16.x`, `192.168.x`, or `169.254.x` ranges), through a proxy option pointing to an internal address, or through a redirect to a private IP address, the request now returns an error instead of succeeding.

The Function node now blocks:

- Requests to internal, private, and reserved network ranges, including loopback addresses (`127.0.0.0/8`, `::1`), private IPv4 ranges (`10.0.0.0/8`, `172.16.0.0/12`, `192.168.0.0/16`), IPv6 unique local addresses (`fc00::/7`, `fd00::/8`), link-local addresses (`169.254.0.0/16`, `fe80::/10`), unspecified addresses (`0.0.0.0/8`), carrier-grade NAT (`100.64.0.0/10`), benchmarking and reserved ranges (`198.18.0.0/15`), multicast (`224.0.0.0/4`), reserved/broadcast ranges (`240.0.0.0/4`), and IPv4-mapped IPv6 addresses (`::ffff:x.x.x.x`).
- Requests to Kubernetes service discovery endpoints, whether referenced by the original hostname (`kubernetes.default.svc`), its fully qualified domain name (`kubernetes.default.svc.cluster.local`), a short hostname (`kubernetes.default`), a case-variant form (`KUBERNETES.DEFAULT.SVC`), the GCP metadata hostname (`metadata.google.internal`), or a cluster-internal IP address such as `10.100.0.1`.
- Use of privileged internal helper functions, including `helpers.requestOAuth2`, `helpers.updateCredentialsInDb`, `helpers.getAndUpdateRefreshToken`, and `helpers.getUpdatedOptionsWithToken`.
- Access to `.process` and `.constructor` on runtime objects within the Function node sandbox, preventing attempts to reach the underlying JavaScript runtime.
- Server-side request forgery (SSRF) attempts made through the `helpers.request` function, including direct requests to cloud metadata addresses, obfuscated address representations, redirects to internal destinations (including through URL-shortening services), and requests routed to internal destinations via base URL or proxy configuration options.

For more information, see [Function node documentation](/latest/docs/function-regular-node).

---

## 1.148

### Release updates - July 2026

#### Adding support for script execution in Databricks regular node

Securiti now lets you execute a SQL script in a Databricks workflow node. A script can contain multiple queries, so you can run them together within a single node instead of chaining multiple Databricks nodes together in your workflow. This gives you an additional way to structure workflows that require several queries against Databricks, alongside the existing option of connecting separate nodes.

To use this capability, set the **Operation** field in the **Parameters** tab to **Execute Script** and add your script, as shown below (FR-5571).

![Databricks interface showing options to execute SQL scripts and manage database operations.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/execute-script(1).png)

For more information, see [Databricks node documentation](https://helpcenter.securiti.ai/docs/databrick-regular-node).

---

## 1.147

### Release updates - June 2026

No updates
